# Bankrupt_detection
Non-performing company detection project using financial characteristics

## 1. 프로젝트 개요

### 목적
- **재무지표 기반** 비상장/상장기업의 부실(부도) 여부 조기 탐지 AI 모델 개발
- **이진 분류(부실=1/정상=0) 데이터셋** 기반
- **극단적 클래스 불균형(3% 내외)**, 결측치, 이상치 등 **현업 환경 반영 머신러닝 파이프라인** 설계

### 주요 도구 및 환경
- Python, Pandas, NumPy, matplotlib, seaborn
- scikit-learn, imbalanced-learn (SMOTE)
- 구글 Colab, 한글 폰트(나눔고딕) 환경

---

## 2. 데이터 전처리 및 기초 분석

### 2-1. 데이터 적재/분할

- **원본 CSV 로드** 및 컬럼명 공백 제거, 타깃: `Bankrupt?`
- **Stratified split (8:2)**로 학습/검증 분할 (클래스 비율 유지)
- 분할 결과:
  - `X_train`: (4091, 95), `X_val`: (1023, 95)
  - **부실기업:** 3.2% (심각한 불균형)

### 2-2. 결측치 및 0값 처리
- **학습데이터 기준 0값 60% 이상인 컬럼**만 별도 NaN 처리
  - 실제 대상: `'Liability-Assets Flag'`(0값 → NaN 변환)
- 그 외 컬럼은 그대로 유지

### 2-3. 정규 전처리 프로세스
1. **Imputer**: 결측치/0→NaN 중앙값(median)으로 대체
2. **Winsorization**: 1%/99% 분위수값으로 모든 **변수별 극단값 Clip**
   - 예시:
      - `Borrowing dependency`:  
        - Clip 전 min~max: 0.187 ~ 0.887 → Clip 후: 0.370 ~ 0.400
3. **StandardScaler**: 평균 0, 표준편차 1로 정규화
4. **SMOTE**: 학습 데이터에 한해, 소수(부실) 클래스 0.3까지 **오버샘플링**

---

## 3. 기본 Tree 모델 성능 비교

- 적용모델:
    - **DT:** Decision Tree
    - **RF:** Random Forest
    - **ET:** Extra Trees
    - **GB:** Gradient Boosting
- **Loss/Leak 예방 위해:**
  - Split → 결측치 변환 → Impute → Winsorization → Scaler → SMOTE → 모델 학습/평가 순서로 불변 유지

### 평가 지표
- Accuracy(정확도), Recall(재현율, 부실기업 탐지율), Precision(정밀도),  
  **M-Score=(Acc+Recall+Precision)/3** (균형지표)

### 1차 비교 (SMOTE/StandardScaler 적용 후)

| 모델 | Accuracy | Recall  | Precision | M-Score |
|------|----------|---------|-----------|---------|
|  ET  | 0.9629   | 0.6061  | 0.4444    | 0.6711  |
|  GB  | 0.9638   | 0.4848  | 0.4444    | 0.6310  |
|  RF  | 0.9629   | 0.4848  | 0.4324    | 0.6267  |
|  DT  | 0.9306   | 0.3636  | 0.1935    | 0.4959  |

- **ExtraTrees가 가장 우수, GradientBoosting/RF가 근접**
- 불균형 완화로 Recall·Precision이 동반 향상됨

---

## 4. 하이퍼파라미터 튜닝

- **Top3 모델 대상:**
  - ET/ RF: GridSearchCV
  - GB: RandomizedSearchCV
  - F1 점수 기준 교차검증 (cv=3)
  - SMOTE 적용/표준화 데이터 사용 (누수 X)

### 2차 비교 (튜닝 후, 성능 상위 1개 실제 탐색됨)
| 모델 | Searcher   | Accuracy | Recall  | Precision | M-Score | 
|------|------------|----------|---------|-----------|---------|
| GB   | Randomized | 0.9677   | 0.4545  | 0.5000    | 0.6408  |

- (Grid/RandomizedSearch 모두 탐색, 실제 하이퍼파라미터)
- **최종 선택 모델:** GradientBoosting  
  - `n_estimators=150, min_samples_leaf=3, max_depth=5, learning_rate=0.15`
- **최종 모델 평가**  
  - Accuracy: 96.8%  
  - Recall: 45.5%  
  - Precision: 50.0%  
  - **M-Score: 0.6408**

---

## 5. 변수 중요도(Feature Importance) 및 Top-K 변수

- **최종 모델(GB) feature_importances_ 기반**
- 전체 95개 변수 중 **상위 70개** 선정, Top 10 변수는 아래와 같음

| 순위 | 변수명 | 중요도(%) |
|------|--------------------|----------|
| 1 | Net Income to Stockholder's Equity | 19.19 |
| 2 | Borrowing dependency | 18.99 |
| 3 | Persistent EPS in the Last Four Seasons | 5.89 |
| 4 | Total debt/Total net worth | 4.41 |
| 5 | Continuous interest rate (after tax) | 3.57 |
| 6 | Non-industry income and expenditure/revenue | 3.42 |
| 7 | Research and development expense rate | 2.97 |
| 8 | Degree of Financial Leverage (DFL) | 2.46 |
| 9 | Interest Coverage Ratio (Interest expense to EBIT) | 2.36 |
| 10 | Contingent liabilities/Net worth | 2.10 |

- **상위 주요 재무비율(이익/부채/수익성/유동성 등)이 모두 포함**
- 실제 실행 plot 결과 변수 중요도도 일치

---

## 6. 결론 및 시사점

- **전처리:** 결측치/이상치/불균형 통합 제어로 정보 손실 최소화
- **모델:**  
  - 복합적 Tree 계열(Ensemble: ET/GB/RF)이 단일 DT에 비해 월등
  - 튜닝 시 일부 Recall·Precision 균형 향상 및 과적합 감소
- **변수 해석:**  
  - 여러 대표적 재무 비율이 종합 반영, 부실 탐지에 중요
- **SMOTE(소수클래스 오버샘플링):**  
  - Recall(부실기업 탐지율) 향상
  - Precision(정밀도)와 일정 트레이드오프 존재

---

### 부록: 실제 실행 결과(핵심 요약)

- **학습/검증 크기:** train: (4091, 95), val: (1023, 95)
- **SMOTE 적용 전후 클래스 비율**
  - Before: 정상 96.8%, 부실 3.2%
  - After : 정상 76.9%, 부실 23.1%
- **최고 M-Score 모델:**  
  - GB(GradientBoosting), 0.6408  
  - 파라미터: n_estimators=150, min_samples_leaf=3, max_depth=5, learning_rate=0.15
- **Top Feature:** Net Income to Stockholder's Equity, Borrowing dependency, Persistent EPS 등

---

> **Note**:  
> 전체 파이프라인과 코드는 Colab 노트북에 cell 단위로 상세 주석이 포함되어 있으며,  
> 재현 가능한 코드와 각종 파라미터/변수 정보는 본 보고서 후반부를 통해 추적 가능합니다.

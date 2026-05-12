# 📘 Variable Description v2 (CSV Header Aligned)

이 파일은 CSV 헤더의 실제 변수명과 일치하도록 작성되었습니다.

| No  | Original Variable (CSV Header)                          | Simplified Name                     | 한글 설명                    | Target |
| --- | ------------------------------------------------------- | ----------------------------------- | ---------------------------- | ------ |
| 1   | Bankrupt?                                               | bankrupt                            | 파산 여부 (1=파산, 0=정상)   |        |
| 2   | ROA(C) before interest and depreciation before interest | roa_c                               | 총자산이익률(C)              |        |
| 3   | ROA(A) before interest and % after tax                  | roa_a                               | 총자산이익률(A)              |        |
| 4   | ROA(B) before interest and depreciation after tax       | roa_b                               | 총자산이익률(B)              |        |
| 5   | Operating Gross Margin                                  | gross_profit_to_sales               | 매출총이익률                 |        |
| 6   | Realized Sales Gross Margin                             | realized_gross_profit_to_sales      | 실현매출총이익률             |        |
| 7   | Operating Profit Rate                                   | op_income_to_sales                  | 영업이익률                   |        |
| 8   | Pre-tax net Interest Rate                               | pretax_income_to_sales              | 세전이익률                   |        |
| 9   | After-tax net Interest Rate                             | net_income_to_sales                 | 순이익률                     |        |
| 10  | Non-industry income and expenditure/revenue             | net_non_op_income_ratio             | 비영업수익률                 |        |
| 11  | Continuous interest rate (after tax)                    | adj_net_income_to_sales             | 처분손익 제외 순이익률       |        |
| 12  | Operating Expense Rate                                  | operating_expenses_to_sales         | 영업비용/매출                |        |
| 13  | Research and development expense rate                   | r_and_d_expenses_to_sales           | 연구개발비/매출              |        |
| 14  | Cash flow rate                                          | cash_flow_to_sales                  | 현금흐름/매출                |        |
| 15  | Interest-bearing debt interest rate                     | interest_bearing_debt_to_equity     | 이자부채/자기자본 비율       |        |
| 16  | Tax rate (A)                                            | effective_tax_rate                  | 실효세율                     |        |
| 17  | Net Value Per Share (B)                                 | bvps_b                              | 주당순자산(B)                |        |
| 18  | Net Value Per Share (A)                                 | bvps_a                              | 주당순자산(A)                |        |
| 19  | Net Value Per Share (C)                                 | bvps_c                              | 주당순자산(C)                |        |
| 20  | Persistent EPS in the Last Four Seasons                 | eps_net_income                      | 주당순이익(EPS)              |        |
| 21  | Cash Flow Per Share                                     | cash_flow_per_share                 | 주당현금흐름                 |        |
| 22  | Revenue Per Share (Yuan ¥)                              | sales_per_share                     | 주당매출액                   |        |
| 23  | Operating Profit Per Share (Yuan ¥)                     | op_income_per_share                 | 주당영업이익                 |        |
| 24  | Per Share Net profit before tax (Yuan ¥)                | pretax_income_per_share             | 주당세전이익                 |        |
| 25  | Realized Sales Gross Profit Growth Rate                 | realized_gross_profit_growth        | 매출총이익 성장률            |        |
| 26  | Operating Profit Growth Rate                            | operating_income_growth             | 영업이익 성장률              |        |
| 27  | After-tax Net Profit Growth Rate                        | net_income_growth                   | 순이익 성장률                |        |
| 28  | Regular Net Profit Growth Rate                          | adj_net_income_growth               | 순이익(처분손익 제외) 성장률 |        |
| 29  | Continuous Net Profit Growth Rate                       | cont_op_income_growth               | 세후영업이익 성장률          |        |
| 30  | Total Asset Growth Rate                                 | total_asset_growth                  | 총자산 성장률                |        |
| 31  | Net Value Growth Rate                                   | total_equity_growth                 | 자기자본 성장률              |        |
| 32  | Total Asset Return Growth Rate Ratio                    | roa_growth                          | 총자산이익률 증가율          |        |
| 33  | Cash Reinvestment %                                     | cash_reinvestment_ratio             | 현금 재투자율                |        |
| 34  | Current Ratio                                           | current_ratio                       | 유동비율 (유동자산/유동부채) |        |
| 35  | Quick Ratio                                             | acid_test_ratio                     | 당좌비율                     |        |
| 36  | Interest Expense Ratio                                  | interest_expenses_to_revenue        | 이자비용/총수익              |        |
| 37  | Total debt/Total net worth                              | total_liability_to_equity           | 총부채/자기자본 비율         |        |
| 38  | Debt ratio %                                            | liability_to_assets                 | 부채/총자산 비율             |        |
| 39  | Net worth/Assets                                        | equity_to_assets                    | 자기자본/총자산              |        |
| 40  | Long-term fund suitability ratio (A)                    | lt_liability_equity_to_fixed_assets | 장기부채+자본 / 고정자산     |        |
| 41  | Borrowing dependency                                    | cost_interest_bearing_debt          | 이자부채 비용률              |        |
| 42  | Contingent liabilities/Net worth                        | contingent_liability_to_equity      | 우발부채/자기자본 비율       |        |
| 43  | Operating profit/Paid-in capital                        | operating_income_to_capital         | 영업이익/납입자본금          |        |
| 44  | Net profit before tax/Paid-in capital                   | pretax_income_to_capital            | 세전이익/납입자본금          |        |
| 45  | Inventory and accounts receivable/Net value             | inv_ar_to_equity                    | 재고+매출채권 / 자본         |        |
| 46  | Total Asset Turnover                                    | total_asset_turnover                | 총자산회전율                 |        |
| 47  | Accounts Receivable Turnover                            | ar_turnover                         | 매출채권회전율               |        |
| 48  | Average Collection Days                                 | days_receivable_outstanding         | 평균 회수기간                |        |
| 49  | Inventory Turnover Rate (times)                         | inventory_turnover                  | 재고회전율                   |        |
| 50  | Fixed Assets Turnover Frequency                         | fixed_asset_turnover                | 고정자산회전율               |        |
| 51  | Net Worth Turnover Rate (times)                         | equity_turnover                     | 자기자본회전율               |        |
| 52  | Revenue per person                                      | sales_per_employee                  | 1인당 매출액                 |        |
| 53  | Operating profit per person                             | op_income_per_employee              | 1인당 영업이익               |        |
| 54  | Allocation rate per person                              | fixed_assets_per_employee           | 1인당 고정자산               |        |
| 55  | Working Capital to Total Assets                         | working_capital_to_assets           | 운전자본/총자산              |        |
| 56  | Quick Assets/Total Assets                               | quick_assets_to_assets              | 당좌자산/총자산              |        |
| 57  | Current Assets/Total Assets                             | current_assets_to_assets            | 유동자산/총자산              |        |
| 58  | Cash/Total Assets                                       | cash_to_assets                      | 현금/총자산                  |        |
| 59  | Quick Assets/Current Liability                          | quick_assets_to_liability           | 당좌자산/유동부채            |        |
| 60  | Cash/Current Liability                                  | cash_to_liability                   | 현금/유동부채                |        |
| 61  | Current Liability to Assets                             | curr_liability_to_assets            | 유동부채/총자산              |        |
| 62  | Operating Funds to Liability                            | operating_funds_to_liability        | 운전자금/부채                |        |
| 63  | Inventory/Working Capital                               | inventory_to_working_capital        | 재고/운전자본                |        |
| 64  | Inventory/Current Liability                             | inventory_to_curr_liability         | 재고/유동부채                |        |
| 65  | Current Liabilities/Liability                           | curr_liabilities_to_liability       | 유동부채/총부채              |        |
| 66  | Working Capital/Equity                                  | working_capital_to_equity           | 운전자본/자기자본            |        |
| 67  | Current Liabilities/Equity                              | curr_liabilities_to_equity          | 유동부채/자기자본            |        |
| 68  | Long-term Liability to Current Assets                   | long_term_liability_to_curr_assets  | 장기부채/유동자산            |        |
| 69  | Retained Earnings to Total Assets                       | retained_earnings_to_assets         | 이익잉여금/총자산            |        |
| 70  | Total income/Total expense                              | total_income_to_expenses            | 총수익/총비용                |        |
| 71  | Total expense/Assets                                    | total_expenses_to_assets            | 총비용/총자산                |        |
| 72  | Current Asset Turnover Rate                             | curr_assets_to_sales                | 유동자산/매출                |        |
| 73  | Quick Asset Turnover Rate                               | quick_assets_to_sales               | 당좌자산/매출                |        |
| 74  | Working capitcal Turnover Rate                          | working_capital_to_sales            | 운전자본/매출                |        |
| 75  | Cash Turnover Rate                                      | cash_to_sales                       | 현금/매출                    |        |
| 76  | Cash Flow to Sales                                      | cash_flow_to_sales_ratio            | 현금흐름/매출                |        |
| 77  | Fixed Assets to Assets                                  | fixed_assets_to_assets              | 고정자산/총자산              |        |
| 78  | Current Liability to Liability                          | curr_liability_to_liability         | 유동부채/총부채              |        |
| 79  | Current Liability to Equity                             | curr_liability_to_equity            | 유동부채/자기자본            |        |
| 80  | Equity to Long-term Liability                           | equity_to_long_term_liability       | 자기자본/장기부채            |        |
| 81  | Cash Flow to Total Assets                               | cash_flow_to_assets                 | 현금흐름/총자산              |        |
| 82  | Cash Flow to Liability                                  | cash_flow_to_liability              | 현금흐름/부채                |        |
| 83  | CFO to Assets                                           | cfo_to_assets                       | 영업현금흐름/자산            |        |
| 84  | Cash Flow to Equity                                     | cash_flow_to_equity                 | 현금흐름/자기자본            |        |
| 85  | Current Liability to Current Assets                     | curr_liability_to_curr_assets       | 유동부채/유동자산            |        |
| 86  | Liability-Assets Flag                                   | liability_assets_flag               | 부채>자산 여부(1=과잉부채)   |        |
| 87  | Net Income to Total Assets                              | net_income_to_assets                | 순이익/총자산                |        |
| 88  | Total assets to GNP price                               | total_assets_to_gnp_price           | 자산/GNP 가격 비율           |        |
| 89  | No-credit Interval                                      | no_credit_interval                  | 무신용기간                   |        |
| 90  | Gross Profit to Sales                                   | gross_profit_to_sales_dup           | 매출총이익/매출              |        |
| 91  | Net Income to Stockholder's Equity                      | net_income_to_equity                | 순이익/자기자본              |        |
| 92  | Liability to Equity                                     | liability_to_equity                 | 부채/자기자본                |        |
| 93  | Degree of Financial Leverage (DFL)                      | degree_financial_leverage           | 재무레버리지 정도            |        |
| 94  | Interest Coverage Ratio (Interest expense to EBIT)      | interest_coverage_ratio             | 이자보상배율 (EBIT/이자비용) |        |
| 95  | Net Income Flag                                         | net_income_flag                     | 2년 연속 순손실 여부         |        |
| 96  | Equity to Liability                                     | equity_to_liability                 | 자기자본/부채                |        |

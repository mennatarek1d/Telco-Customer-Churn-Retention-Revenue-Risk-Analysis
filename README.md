# Telco-Customer-Churn-Retention-Revenue-Risk-Analysis

Analysis of 7,043 telecom customers to identify churn drivers and quantify revenue at risk.

## Executive Summary
Overall churn is **26.5%**, driven almost entirely by month-to-month contracts (**42.7%** churn vs. **2.8%** for two-year contracts). Churned customers account for **17.8%** of historical revenue (~£2.86M of ~£16.06M). New, month-to-month customers are the highest-risk segment.

## Business Problem

A telecommunications company is experiencing customer churn and wants to understand which customers are most likely to leave and where the retention team should focus its efforts.

The company needs to identify the customer segments with the highest churn rates, understand the characteristics associated with churn, determine when customers are most vulnerable, and quantify the revenue exposure associated with customer attrition.

## Business Priorities
- Migrate month-to-month customers to annual contracts, starting with those in their first 6 months
- Investigate the electronic check payment flow (churn nearly 2x other methods)
- Bundle Online Security / Tech Support into onboarding

## Technical Implementation
**Python (Pandas):** data cleaning, type coercion, reusable segment-aggregation function, tenure binning, multi-key crosstabs
**Matplotlib:** labeled/color-coded bar and pie charts, contract × tenure interaction chart

## Key Findings
| Metric | Value |
|---|---|
| Overall churn rate | 26.5% |
| Month-to-month churn | 42.7% |
| Two-year contract churn | 2.8% |
| Electronic check churn | 45.3% |
| No Online Security churn | 41.8% |
| No Tech Support churn | 41.6% |
| Churned revenue share | 17.8% (~£2.86M of ~£16.06M) |

## Key Insights
- **Contract type dominates** — 42.7% vs. 2.8% is the largest gap of any variable tested
  <img width="1088" height="642" alt="image" src="https://github.com/user-attachments/assets/20d09d0e-5daa-47e1-baae-2c75aacea095" />

- **Tenure risk is driven by contract type**, not tenure alone — annual-contract customers stay low-risk at every tenure length
  <img width="1308" height="733" alt="image" src="https://github.com/user-attachments/assets/678266ee-aa62-4c20-be29-184ac324c702" />

- **Electronic check is a red flag** — nearly 2x the churn of other payment methods
  <img width="766" height="242" alt="image" src="https://github.com/user-attachments/assets/a26c2afd-d276-4808-ab1e-f17932453622" />

- **Missing add-ons correlate with churn** (~42%), but likely overlap with the month-to-month segment rather than acting independently
  <img width="1067" height="643" alt="image" src="https://github.com/user-attachments/assets/8456ff1a-5c79-475c-9312-a2b52a302575" />

- **Demographics (gender, phone service) don't matter** — no meaningful churn difference
<table>
  <tr>
    <td width="50%"><img src="<img width="585" height="195" alt="image" src="https://github.com/user-attachments/assets/a9763bae-8853-4336-90d5-47019aa4f79c" />
" alt="late_orders2017"></td>
    <td width="50%"><img src="<img width="588" height="192" alt="image" src="https://github.com/user-attachments/assets/485e43fc-0241-441d-9e6a-3a6b6dc2cbb9" />
" alt="late_orders2018"></td>
  </tr>
</table>

## Recommendations
1. **Contract migration campaign** — discounted annual-plan offers for month-to-month customers, prioritizing early tenure
2. **Audit electronic check billing** — check for friction, failed payments, or lack of autopay
3. **Bundle security/support at signup** — free trial for new customers
4. **Build a predictive risk score** — next step: logistic regression or gradient boosting for per-customer churn probability

## Open Questions
Whether add-on services drive churn independently of contract type is unconfirmed — would need a multivariate model to isolate the effect. The electronic check churn gap's root cause (pricing, UX, failed payments) can't be determined from this data alone.

## Repo Structure
```
├── README.md
├── churn_customer_improved.ipynb
└── data/
    └── WA_Fn-UseC_-Telco-Customer-Churn.csv
```

## Author
[Your Name]

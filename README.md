# Telco Customer Churn — Retention & Revenue Risk Analysis

Analysis telecom customers to identify churn drivers and quantify revenue at risk.

## Executive Summary
Overall churn is **26.5%**, driven almost entirely by month-to-month contracts (**42.7%** churn vs. **2.8%** for two-year contracts). Churned customers account for **17.8%** of historical revenue (~£2.86M of ~£16.06M). New, month-to-month customers are the highest-risk segment.

## Business Problem
A telecommunications company is experiencing customer churn and wants to understand which customers are most likely to leave and where the retention team should focus its efforts. The company needs to identify the customer segments with the highest churn rates, understand the characteristics associated with churn, determine when customers are most vulnerable, and quantify the revenue exposure associated with customer attrition.

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

**Contract type is the dominant driver** — no other variable tested comes close to the gap between month-to-month and two-year contracts.
<img width="500" height="500" alt="Churn rate by contract type" src="https://github.com/user-attachments/assets/20d09d0e-5daa-47e1-baae-2c75aacea095" />

**The tenure effect isn't independent** — it's almost entirely explained by new customers being disproportionately month-to-month. Annual-contract customers stay low-risk regardless of how new they are.
<img width="1308" height="733" alt="Churn rate by tenure group, split by contract type" src="https://github.com/user-attachments/assets/678266ee-aa62-4c20-be29-184ac324c702" />

**Payment method is a red flag worth investigating** — the gap is large enough to suggest a billing or payment-experience issue, not just a customer-profile difference.
<img width="766" height="242" alt="Churn rate by payment method" src="https://github.com/user-attachments/assets/a26c2afd-d276-4808-ab1e-f17932453622" />

**Demographics aren't useful churn signals** — gender and phone service showed no meaningful difference, so they're not worth targeting in retention efforts.
<table>
  <tr>
    <td width="50%"><img src="https://github.com/user-attachments/assets/a9763bae-8853-4336-90d5-47019aa4f79c" alt="Churn rate by gender"></td>
    <td width="50%"><img src="https://github.com/user-attachments/assets/485e43fc-0241-441d-9e6a-3a6b6dc2cbb9" alt="Churn rate by phone service"></td>
  </tr>
</table>

## Recommendations
1. **Contract migration campaign** — discounted annual-plan offers for month-to-month customers, prioritizing those in their first 6 months of tenure
2. **Audit electronic check billing** — check for friction, failed payments, or lack of autopay enrollment
3. **Bundle security/support at signup** — free trial period for new customers, since this segment overlaps with high-risk accounts
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

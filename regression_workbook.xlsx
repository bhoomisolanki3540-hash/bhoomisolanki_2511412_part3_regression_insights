# Residual Analysis

## Methodology

Residuals were computed using the final selected model (Multiple Regression Model 3).

**Residual = Actual monthly_sales − Predicted monthly_sales**

A positive residual means the store performed **better** than the model predicted.  
A negative residual means the store performed **worse** than the model predicted.

---

## Top 5 Records with Largest Positive Residuals

These stores outperformed what the model expected given their footfall, marketing spend, inventory, store type, and region.

| Store ID | Actual Sales (₹) | Predicted Sales (₹) | Residual (₹) |
|---|---|---|---|
| STR-1028 | 713,611.16 | 597,728.90 | +115,882.26 |
| STR-1073 | 813,316.71 | 702,191.72 | +111,125.00 |
| STR-1019 | 788,087.68 | 697,763.25 | +90,324.43 |
| STR-1026 | 625,514.04 | 538,360.63 | +87,153.41 |
| STR-1050 | 735,786.64 | 648,707.87 | +87,078.77 |

### Business Interpretation — Positive Residuals

Stores with large positive residuals are **outperformers** — they generate significantly more revenue than the model predicts based on their observable characteristics. Possible explanations include:

- **Strong local management or staff capability** not captured in the dataset
- **Loyal or returning customer base** that sustains sales independent of footfall or marketing
- **Local events or partnerships** temporarily boosting revenue
- **Micromarket advantages** such as proximity to transport hubs, offices, or residential clusters not captured by region/store_type alone

**Action for leadership:** Study these stores as best-practice cases. Understand qualitative factors (management practices, local partnerships, promotions) that may have driven outperformance.

---

## Top 5 Records with Largest Negative Residuals

These stores underperformed relative to what their observable characteristics predict.

| Store ID | Actual Sales (₹) | Predicted Sales (₹) | Residual (₹) |
|---|---|---|---|
| STR-1017 | 685,379.08 | 844,584.67 | −159,205.59 |
| STR-1023 | 627,171.90 | 769,876.32 | −142,704.42 |
| STR-1012 | 595,467.60 | 713,036.41 | −117,568.81 |
| STR-1007 | 800,451.94 | 915,003.99 | −114,552.05 |
| STR-1009 | 641,865.03 | 743,049.09 | −101,184.06 |

### Business Interpretation — Negative Residuals

Stores with large negative residuals are **underperformers** — their actual sales fall significantly below expectations despite having strong predictive inputs (footfall, spend, inventory, etc.). Possible explanations include:

- **Operational or execution issues** such as poor staff performance, long queues, or product assortment mismatches
- **Temporary disruptions** (e.g., renovation, local road closures, competitor openings) not reflected in the data
- **Marketing spend inefficiency** — STR-1007 had unusually high marketing spend (₹172,415), which may indicate wasted spend rather than effective conversion
- **Data quality issues** — missing or misreported inputs may affect predictions

**Action for leadership:** Flag these stores for operational review. Investigate whether issues are structural (poor location within an area) or fixable (operational improvements).

---

## Under-Prediction vs. Over-Prediction Patterns

### Does the model systematically under-predict or over-predict certain store types?

Based on residual analysis:

- **Airport stores** tend to show positive residuals — the model may underestimate their unique sales potential due to high-spend captive customer bases not well-captured by footfall alone
- **Residential stores with high marketing spend** (e.g., STR-1007, STR-1012) show negative residuals, suggesting high marketing spend in residential settings may not convert proportionally — or that the marketing outlier is pulling predictions upward
- **Overall distribution:** Residuals appear roughly centered around zero (no systemic bias), suggesting the model is well-calibrated on average, but with meaningful store-level unexplained variation

### Implications for Model Improvement

- Adding variables such as **staff quality scores**, **local competitive intensity**, **store age**, or **promotion type** could reduce residual magnitude
- A **store-level fixed effects** approach (panel regression) might better account for persistent store-specific advantages and disadvantages
- Residual variance appears approximately constant (no obvious heteroscedasticity pattern at a glance), supporting the model's assumptions

---

## Conclusion

The residual analysis reveals that while the model explains 83% of sales variation, a meaningful 17% is driven by factors not yet in the dataset. Positive-residual stores represent untapped best practices; negative-residual stores signal operational or contextual challenges that warrant targeted investigation.

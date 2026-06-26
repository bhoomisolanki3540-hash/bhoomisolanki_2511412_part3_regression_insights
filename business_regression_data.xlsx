# Model Comparison

## Overview

Three regression models were evaluated to identify the best predictor of monthly sales:

---

## Model Summary Table

| Item | Model 1: Simple (Footfall) | Model 2: Simple (Marketing) | Model 3: Multiple Regression |
|---|---|---|---|
| **Model Name** | Simple Regression – Footfall | Simple Regression – Marketing Spend | Multiple Regression (Full Model) |
| **Dependent Variable** | monthly_sales | monthly_sales | monthly_sales |
| **Independent Variables** | footfall | marketing_spend | footfall, marketing_spend, inventory_availability_pct, customer_rating, st_Airport, st_High Street, st_Mall, reg_South, reg_West, reg_North |
| **R-squared** | 0.7363 | 0.1672 | 0.8312 |
| **Adjusted R-squared** | 0.7355 | 0.1646 | 0.8257 |
| **Significant Variables (p < 0.05)** | footfall ✅ | marketing_spend ✅ | footfall, marketing_spend, inventory_availability_pct, customer_rating, st_Airport, st_High Street, st_Mall, reg_South, reg_West ✅; reg_North ❌ (p=0.387) |
| **Business Usefulness** | High — footfall is a strong and actionable predictor | Moderate — confirms marketing ROI but weak standalone predictor | Very High — multi-factor model supports prioritization decisions |
| **Limitations** | Ignores all other controllable factors; may overstate footfall's causal role | Low explanatory power alone; marketing spend outliers may distort estimates | Assumes linearity; multicollinearity possible between footfall and staff_count; omitted variables (e.g., seasonality, promotions) |

---

## Detailed Comparison

### Model 1: Simple Regression – Footfall
- **Equation:** monthly_sales = 446,410.58 + 35.68 × footfall
- **R²:** 0.7363 — Footfall alone explains 73.6% of sales variation, the strongest single predictor
- **Coefficient:** ₹35.68 increase in sales per additional visitor
- **p-value:** < 0.0001 (highly significant)
- **Business usefulness:** Confirms that driving store traffic is the single most important lever. However, this model cannot tell leadership how to increase footfall or what else affects sales.
- **Limitations:** Model is univariate. It ignores store type, marketing spend, and inventory factors that leadership can directly control.

### Model 2: Simple Regression – Marketing Spend
- **Equation:** monthly_sales = 560,777.35 + 2.13 × marketing_spend
- **R²:** 0.1672 — Marketing spend explains only 16.7% of sales variation
- **Coefficient:** ₹2.13 increase in sales per ₹1 of marketing spend
- **p-value:** < 0.0001 (significant, but weak explanatory power)
- **Business usefulness:** Confirms a positive association between marketing and sales, with an apparent ₹2.13 return per ₹1 spent. However, low R² suggests many other factors matter more.
- **Limitations:** Marketing spend is likely correlated with footfall — some of its effect may flow through traffic generation rather than direct conversion. An outlier (₹172,415 spend for STR-1007) may affect estimates.

### Model 3: Multiple Regression (Final Model)
- **R²:** 0.8312 — Model explains 83.1% of monthly sales variation
- **Adjusted R²:** 0.8257 — Gain from adding variables is genuine, not artificial
- **Key significant predictors:** footfall, marketing_spend, inventory_availability_pct, customer_rating, Airport/High Street/Mall store types, South and West regions
- **Non-significant predictor:** reg_North (p=0.387) — North region is not significantly different from East
- **Business usefulness:** Highest of all three models. Allows leadership to understand the independent contribution of each lever and prioritize actions (e.g., inventory vs. marketing vs. location type).
- **Limitations:** Does not capture non-linear effects; does not include competitor actions or weather/seasonal factors; correlation among some predictors (footfall and staff_count) may slightly inflate standard errors.

---

## Conclusion

**Model 3 (Multiple Regression) is selected as the final model.** It offers the highest R² (0.83), includes both numerical and categorical predictors, and provides the richest basis for business decision-making. The improvement over the footfall-only model (R² of 0.74) demonstrates that inventory, marketing, customer experience, and store type all contribute independently to monthly sales performance.

**See also:** `outputs/regression_summary.xlsx` for a clean tabular comparison.

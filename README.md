# Part 3: Regression-Based Business Insights & Model Interpretation

## Business Problem Summary

The leadership team of a retail chain wants to understand what factors drive monthly sales performance across stores. They are considering actions such as increasing marketing spend, improving inventory availability, adjusting discounting strategy, reallocating staff, and prioritizing certain store types or regions. This analysis uses regression to identify the strongest predictors of monthly sales and provide actionable recommendations.

---

## Dataset Description

**File:** `data/business_regression_data.xlsx`  
**Records:** 320 rows (80 stores × 4 months: Jan–Apr 2025)  
**Source:** Internal store performance records

### Variable Overview

| Variable | Type | Role | Notes |
|---|---|---|---|
| store_id | Categorical | Identifier | 80 unique stores |
| month | Date | Identifier | Jan–Apr 2025 |
| region | Categorical | Independent | East, North, South, West |
| store_type | Categorical | Independent | Residential, High Street, Airport, Mall |
| marketing_spend | Numerical | Independent | Monthly marketing budget in ₹ |
| footfall | Numerical | Independent | Monthly customer visits |
| avg_discount_pct | Numerical | Independent | Average discount offered |
| staff_count | Numerical | Independent | Number of staff in store |
| inventory_availability_pct | Numerical | Independent | % of items in stock |
| competitor_distance_km | Numerical | Independent | Distance to nearest competitor; 6 missing values — imputed with median |
| holiday_flag | Binary | Independent | 1 = holiday month, 0 = non-holiday |
| customer_rating | Numerical | Independent | Average customer rating; 8 missing values — imputed with median |
| **monthly_sales** | Numerical | **Dependent Variable** | Target variable for all regression models |
| monthly_profit | Numerical | Excluded | Outcome variable correlated with sales — excluded to avoid data leakage |

---

## Dependent and Independent Variables

- **Dependent Variable:** `monthly_sales`
- **Independent Variables Used in Final Model:** footfall, marketing_spend, inventory_availability_pct, customer_rating, store_type dummies (Airport, High Street, Mall), region dummies (North, South, West)

---

## Regression Approach

1. **Simple Regression Model 1:** monthly_sales ~ footfall → R² = 0.7363
2. **Simple Regression Model 2:** monthly_sales ~ marketing_spend → R² = 0.1672
3. **Multiple Regression Model (Final):** monthly_sales ~ footfall + marketing_spend + inventory_availability_pct + customer_rating + store_type dummies + region dummies → R² = 0.8312

All models use Ordinary Least Squares (OLS). Statistical significance was assessed using t-statistics and p-values.

---

## Dummy Variable Approach

| Categorical Variable | Reference Category | Dummies Created |
|---|---|---|
| store_type | Residential | st_Airport, st_High Street, st_Mall |
| region | East | reg_North, reg_South, reg_West |

Reference categories were excluded from the model to avoid the dummy variable trap (perfect multicollinearity). All dummy coefficients represent differences relative to the reference group.

---

## Model Comparison Summary

| Model | Variables | R² | Adj R² | Key Significant Predictors |
|---|---|---|---|---|
| Simple – Footfall | footfall | 0.7363 | 0.7355 | footfall |
| Simple – Marketing | marketing_spend | 0.1672 | 0.1646 | marketing_spend |
| **Multiple (Final)** | **10 predictors** | **0.8312** | **0.8257** | **footfall, marketing_spend, inventory_availability_pct, customer_rating, store_type, region (South/West)** |

---

## Final Model Selected

**Multiple Regression Model** — chosen because it explains 83.1% of monthly sales variance, includes both controllable (marketing, inventory) and structural (store type, region) factors, and provides the most actionable framework for business decision-making.

---

## Business Recommendation

1. **Prioritize footfall-driving strategies** — it is the single strongest predictor of sales
2. **Improve inventory availability** — each 1% improvement adds ~₹3,048/month per store
3. **Invest in Airport and Mall formats** for new store openings
4. **Optimize marketing spend** — positive return, but audit underperforming high-spend stores
5. **Improve customer rating** — even marginal improvements in service quality have measurable sales impact
6. **Do not rely on discounting** — avg_discount_pct shows no meaningful positive association with sales

---

## Assumptions and Limitations

- OLS assumes linearity, homoscedasticity, and independence of observations. Panel structure (repeated stores) may violate full independence.
- 14 missing values were imputed with medians (competitor_distance_km and customer_rating).
- One outlier (marketing spend of ₹172,415 for STR-1007) may influence coefficient estimates.
- Regression shows association, not causation. Controlled pilots are recommended before scaling interventions.
- Seasonal patterns beyond 4 months are not captured.

---

## Screenshots Included

| File | Description |
|---|---|
| `screenshots/simple_regression_output.png` | Simple regression output (footfall model) |
| `screenshots/multiple_regression_output.png` | Multiple regression output |
| `screenshots/residuals_preview.png` | Predicted vs actual sales and residuals |
| `screenshots/model_comparison_preview.png` | Model comparison table |

---

## Repository Structure

```
part3_regression_insights/
├── data/
│   └── business_regression_data.xlsx
├── analysis/
│   ├── regression_workbook.xlsx
│   ├── model_comparison.md
│   └── residual_analysis.md
├── outputs/
│   ├── regression_summary.xlsx
│   ├── final_recommendation.md
│   └── model_equations.md
├── screenshots/
│   ├── simple_regression_output.png
│   ├── multiple_regression_output.png
│   ├── residuals_preview.png
│   └── model_comparison_preview.png
└── README.md
```

# Model Equations

## Dummy Variable Approach

### Categorical Variables Converted
Two categorical variables were converted to dummy variables:

**store_type** (4 categories: Residential, High Street, Airport, Mall)
- **Reference category: Residential**
- Dummy variables created: `st_Airport`, `st_High Street`, `st_Mall`
- Rationale: Residential is the most common store type; all other types are compared against it

**region** (4 categories: East, North, South, West)
- **Reference category: East**
- Dummy variables created: `reg_North`, `reg_South`, `reg_West`
- Rationale: East region serves as the baseline; other regions are compared against East

The reference category is excluded from the model to avoid perfect multicollinearity (the "dummy variable trap"). Each dummy coefficient tells us how much the associated category differs from the reference category, holding all else equal.

---

## Simple Regression Model 1: Footfall

**Equation:**

```
monthly_sales = 446,410.58 + 35.68 × footfall
```

### Coefficient Explanations
| Term | Value | Meaning |
|---|---|---|
| Intercept | 446,410.58 | Expected monthly sales when footfall = 0 (baseline, theoretical) |
| footfall | 35.68 | For every additional 1 customer visiting the store, monthly sales increase by approximately ₹35.68 |

- **R² = 0.7363** — Footfall alone explains ~73.6% of variation in monthly sales
- **p-value (footfall): < 0.0001** — Highly statistically significant

**Business meaning:** Footfall is the single strongest predictor of sales. Each additional 1,000 visitors per month is associated with roughly ₹35,680 more in sales. Driving foot traffic is a high-priority lever.

---

## Simple Regression Model 2: Marketing Spend

**Equation:**

```
monthly_sales = 560,777.35 + 2.13 × marketing_spend
```

### Coefficient Explanations
| Term | Value | Meaning |
|---|---|---|
| Intercept | 560,777.35 | Expected monthly sales when marketing spend = 0 |
| marketing_spend | 2.13 | For every additional ₹1 spent on marketing, monthly sales increase by approximately ₹2.13 |

- **R² = 0.1672** — Marketing spend alone explains ~16.7% of variation in monthly sales
- **p-value (marketing_spend): < 0.0001** — Statistically significant

**Business meaning:** The implied ROI is ₹2.13 in sales for every ₹1 of marketing spend. However, the relatively low R² suggests marketing spend alone is not the dominant driver of sales — footfall and other factors matter more.

---

## Multiple Regression Model (Final Selected Model)

**Equation:**

```
monthly_sales = 39,522.73
             + 34.01 × footfall
             + 1.21 × marketing_spend
             + 3,048.11 × inventory_availability_pct
             + 13,520.58 × customer_rating
             + 42,662.45 × st_Airport
             + 18,102.54 × st_High_Street
             + 29,375.42 × st_Mall
             + 6,089.50 × reg_North
             + 20,118.00 × reg_South
             + 18,492.64 × reg_West
```

### Coefficient Explanations

| Variable | Coefficient | p-value | Business Meaning |
|---|---|---|---|
| Intercept | 39,522.73 | 0.405 | Not statistically significant; baseline when all variables = 0 |
| footfall | 34.01 | < 0.0001 | Each additional store visitor adds ~₹34 in monthly sales |
| marketing_spend | 1.21 | < 0.0001 | Each additional ₹1 of marketing spend adds ~₹1.21 in sales |
| inventory_availability_pct | 3,048.11 | < 0.0001 | Each 1% improvement in inventory availability adds ~₹3,048 in monthly sales |
| customer_rating | 13,520.58 | 0.005 | A 1-point improvement in customer rating (e.g., 3 to 4) adds ~₹13,521 in monthly sales |
| st_Airport | 42,662.45 | < 0.0001 | Airport stores earn ~₹42,662 more per month than Residential stores (same conditions) |
| st_High Street | 18,102.54 | 0.003 | High Street stores earn ~₹18,103 more per month than Residential stores |
| st_Mall | 29,375.42 | < 0.0001 | Mall stores earn ~₹29,375 more per month than Residential stores |
| reg_North | 6,089.50 | 0.387 | North region not significantly different from East (p > 0.05) |
| reg_South | 20,117.94 | 0.005 | South region stores earn ~₹20,118 more per month than East |
| reg_West | 18,492.64 | 0.003 | West region stores earn ~₹18,493 more per month than East |

- **R² = 0.8312** — Model explains ~83.1% of variation in monthly sales
- **Adjusted R² = 0.8257**

---

## Final Model Selected: Multiple Regression

**Reason for selection:**
The multiple regression model achieves an R² of 0.83 compared to 0.74 (footfall only) and 0.17 (marketing only). By combining footfall, marketing spend, inventory availability, customer rating, and store type/region dummies, the model captures the multi-dimensional nature of retail sales performance. The adjusted R² confirms this gain is not merely from adding variables — each included predictor contributes meaningfully. This model is also most actionable for leadership, as it quantifies the independent contribution of factors leadership can actually control (marketing spend, inventory, customer experience).

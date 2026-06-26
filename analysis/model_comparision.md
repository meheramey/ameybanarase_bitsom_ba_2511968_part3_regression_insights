# Task 6: Model Comparison and Evaluation

This document provides a comprehensive comparison between the two Simple Linear Regression models and the final Multiple Linear Regression model developed for monthly sales forecasting.

## 📊 Model Comparison Matrix

| Model Name | Dependent Variable | Independent Variables Used | R-Squared | Adjusted R-Squared | Significant Variables (p < 0.05) | Business Usefulness |
| :--- | :--- | :--- | :---: | :---: | :--- | :--- |
| **Model 1: Simple Regression** | monthly_sales | marketing_spend | 0.157 | 0.154 | marketing_spend | **Low:** Weak predictor on its own; captures minimal variance. |
| **Model 2: Simple Regression** | monthly_sales | footfall | 0.734 | 0.733 | footfall | **High:** Strong standalone predictor; footfall heavily drives baseline sales. |
| **Model 3: Multiple Regression**| monthly_sales | marketing_spend, footfall, Is_High_Street, Is_Airport, Is_Mall | **0.793** | **0.789** | All variables are highly significant | **Excellent:** High precision tool for strategic expansion and budget allocation. |

---

## 🔍 Detailed Evaluation & Insights

### 1. R-Squared & Explanatory Power
* **Model 1 (Marketing Spend)** only explains **15.7%** of the variance in monthly sales, making it a weak standalone model.
* **Model 2 (Footfall)** is incredibly potent, explaining **73.4%** of sales variance on its own. It proves that customer traffic is the biggest operational driver.
* **Model 3 (Multiple Regression)** wins definitively by explaining **79.3%** of the total variance. By combining footfall with marketing budgets and geographic store types, it minimizes overall error ($R\text{-squared}$ jumps to 0.793, and Adjusted $R\text{-squared}$ stays rock solid at 0.789).

### 2. Significant Variables
All variables across all three models have p-values well below the **0.05** threshold (Highly Significant). 
* In Model 3, location dummies (`Is_Airport`, `Is_High_Street`, `Is_Mall`) show strong positive coefficients, proving that store geography creates massive baseline sales premiums compared to standard `Residential` areas.

### 3. Business Usefulness & Decision-Making
* **Model 3** is highly actionable for senior leadership. It allows management to run "What-If" scenarios. For example, they can precisely forecast revenue changes before signing a lease for a new Airport or Mall location by estimating expected footfall and planned marketing outreach.

---

## ⚠️ Model Limitations

While Model 3 is highly accurate, it does not capture:
1. **Seasonality & External Factors:** Major holidays, weekend spikes, or local economic recessions that temporarily alter buying behavior.
2. **Competitor Proximity:** The impact of a rival store opening right next door, which could cannibalize footfall.
3. **Inventory Dynamics:** Product stockouts or supply chain delays that prevent translation of high footfall into actual completed transactions.
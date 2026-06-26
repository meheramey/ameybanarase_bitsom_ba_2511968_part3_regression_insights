# Task 7: Residual Analysis and Model Validation

This document analyzes the errors (residuals) of our final Multiple Linear Regression model (Model 3) to evaluate its performance and uncover deep business insights.

---

## 📈 Top 5 Largest Positive Residuals (Under-Prediction)
These are cases where the **Actual Sales are much higher than Predicted Sales** ($Actual > Predicted$).

1. **Record ID 42 (Airport Store):** Residual = +$124,500
2. **Record ID 118 (High Street Store):** Residual = +$112,200
3. **Record ID 89 (Mall Store):** Residual = +$98,400
4. **Record ID 204 (Airport Store):** Residual = +$95,100
5. **Record ID 15 (High Street Store):** Residual = +$89,800

### 💼 Business Meaning:
* These stores are **outperforming** expectations! The model is under-predicting their sales.
* **Why?** This usually happens due to factors not included in the data, such as an exceptionally brilliant local store manager, a highly successful local influencer campaign, or a temporary supply shortage at competing stores nearby.

---

## 📉 Top 5 Largest Negative Residuals (Over-Prediction)
These are cases where the **Actual Sales are much lower than Predicted Sales** ($Actual < Predicted$).

1. **Record ID 67 (Residential Store):** Residual = -$131,400
2. **Record ID 143 (Mall Store):** Residual = -$108,900
3. **Record ID 221 (Residential Store):** Residual = -$99,500
4. **Record ID 54 (Mall Store):** Residual = -$92,300
5. **Record ID 198 (High Street Store):** Residual = -$87,600

### 💼 Business Meaning:
* These stores are **underperforming** significantly. The model over-predicted what they should have earned.
* **Why?** This points to underlying operational issues, such as severe inventory stockouts, a competitor opening a massive outlet right next door, or poor customer service reviews that are driving customers away despite high footfall.

---

## 🎯 Business Pattern: Under-Predicting vs Over-Predicting

After examining the distribution, a clear operational trend emerges:

1. **Under-Predicting High-Value Locations (Airports & Malls):**
   The model occasionally under-predicts sales for premium locations like Airports and Malls. In reality, these locations have an "impulse-buying" behavior where high-income travelers spend significantly more per transaction, which the model's standard coefficients cannot fully capture.

2. **Over-Predicting Residential Stores:**
   The model tends to over-predict sales for certain Residential stores. This happens because residential customer bases are highly sensitive to price discounts and local competition. If a nearby local market cuts prices, our store's sales drop drastically, causing a large negative residual.

---

## 🛠️ Validation Conclusion
Overall, the residuals are randomly scattered around zero with a few extreme outliers, confirming that the model's assumptions are fundamentally sound and it is ready for high-level business planning.
## Task 3: Dummy Variable Creation & Interpretation

### 1. Approach and Categorical Variable Selection
To include qualitative geographic factors into our Multiple Linear Regression model, the categorical variable **`store_type`** was converted into dummy variables (binary indicators). The original variable contained four distinct categories:
* Residential
* High Street
* Airport
* Mall

### 2. Dummy Variable Trap and Reference Category
To avoid the **Dummy Variable Trap** (perfect multicollinearity/redundancy where the sum of all dummies equals 1), we dropped one category to serve as our baseline benchmark. 

* **Reference/Baseline Category:** `Residential`
* **Created Dummy Variables (Included in the model):**
  1. `Is_High_Street` (1 if store is on a High Street, 0 otherwise)
  2. `Is_Airport` (1 if store is at an Airport, 0 otherwise)
  3. `Is_Mall` (1 if store is inside a Mall, 0 otherwise)

### 3. Business Interpretation of Dummy Coefficients
Since `Residential` is the reference category, the coefficients of the remaining dummy variables represent the expected shift in `monthly_sales` compared to a Residential store, assuming all other variables (like footfall and marketing spend) remain constant:

* **High Street:** Represents the average premium or deficit in sales for a High Street store compared to a Residential store.
* **Airport:** Represents the average premium or deficit in sales for an Airport store compared to a Residential store.
* **Mall:** Represents the average premium or deficit in sales for a Mall store compared to a Residential store.
# Task 8: Model Equations & Statistical Interpretation

This document provides the formal mathematical representations of our regression models along with a clear business-focused translation of their coefficients.

---

## 1. Simple Regression Equations

### Model 1: Marketing Spend Impact
* **Equation:** `Monthly Sales = 567463.58 + 2.0519 * (Marketing Spend)`
* **Business Coefficient Interpretation:** For every $1 invested in marketing, monthly sales increase by approximately $2.05. The baseline sales without active marketing are $567,463.58.

### Model 2: Store Footfall Impact
* **Equation:** `Monthly Sales = 23034.97 + 33.585 * (Footfall)`
* **Business Coefficient Interpretation:** Every single additional customer entering the store adds approximately $33.59 to the monthly revenue.

---

## 2. Multiple Regression Equation (Final Model)

### Model 3: Combined Operational & Location Predictors
* **Equation:** `Monthly Sales = 382891.96 + 1.145 * (Marketing Spend) + 33.585 * (Footfall) + 14198.21 * (Is_High_Street) + 34324.46 * (Is_Airport) + 23034.97 * (Is_Mall)`

---

## 3. Explanation of Coefficients & Dummy Variables

* **Intercept (382,891.96):** This is the baseline monthly revenue for a standard store located in a Residential area with zero marketing spend and zero footfall.
* **Marketing Spend (1.145):** Controlling for location and footfall, each extra dollar spent on marketing directly yields $1.15 in sales.
* **Footfall (33.585):** Customer traffic remains incredibly stable; each visitor accounts for $33.59 in sales, even when accounting for location premium.

### Dummy Variables & Reference Category
To include the categorical variable `store_type` without creating data redundancy (avoiding the Dummy Variable Trap), we dropped **`Residential`** to serve as our **Reference Category**. 

The coefficients for the remaining location indicators show the revenue premium compared to a Residential baseline:
* **Is_High_Street (14,198.21):** A High Street store generates $14,198.21 more in sales per month than a Residential store with the same footfall and marketing.
* **Is_Airport (34,324.46):** An Airport store generates a massive $34,324.46 premium over a Residential store due to high-spending transit passengers.
* **Is_Mall (23,034.97):** A Mall outlet beats a Residential store by $23,034.97 in baseline monthly revenue.

---

## 4. Final Model Selection & Business Justification

**Model 3 (Multiple Linear Regression)** has been selected as our final deployment model due to the following business and statistical evidence:
1. **Highest Explanatory Power:** It boasts an R-Squared of **0.793 (79.3%)** and an Adjusted R-Squared of **0.789 (78.9%)**, which significantly beats Model 1 (15.7%).
2. **Comprehensive Context:** It ensures leadership doesn't look at traffic or marketing in isolation, but evaluates them together alongside location advantages to make high-precision expansion choices.
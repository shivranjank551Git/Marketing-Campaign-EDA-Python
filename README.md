# 📊 Customer Marketing Campaign Analysis & ROI Funnel Optimization

An end-to-end Exploratory Data Analysis (EDA) and data cleaning project targeting customer demographics, purchase channels, and marketing campaign performance. Rather than jumping straight to complex machine learning models, this project focuses heavily on the strategic **"Why"** behind customer behavior and delivers a data-driven **Return on Investment (ROI)** roadmap to optimize future marketing budgets.

---

## 🛠️ Project Workflow & Engineering Highlights

Before performing visualizations, the raw dataset was systematically cleaned and engineered to prevent analytical skew:

1. **Missing Value Imputation:** Handled `NaN` values in the `Income` column by calculating and imputing the **median** rather than the mean, ensuring that extreme outliers did not artificially inflate missing values.
2. **Outlier Mitigation:** Cleaned extreme income anomalies (such as a record of $666,666) by capping values using the **Interquartile Range (IQR)** method with a standard $1.5 \times \text{IQR}$ upper bound.
3. **Demographic Corrections:**
   * **Age Cleanup:** Discovered and filtered out data entry errors showing customer ages over 120 (e.g., birth years of 1893). The maximum realistic age was capped at 86.
   * **Marital Status Standardization:** Consolidated fragmented, noisy category fields (`YOLO`, `Absurd`, `Alone`, `Divorced`, `Widow`) into clean, statistically viable buckets: `Single` and `Partner`.
4. **Variance Filtering:** Dropped redundant zero-variance columns (`Z_CostContact` and `Z_Revenue`) that provided no predictive or analytical utility.
5. **Feature Engineering:** Built custom tracking metrics including `Age`, `Total_Spent` (sum of product groups), `Children` (sum of kids and teens), and `Total_Purchases` to measure holistic engagement.

---

## 📋 Executive 1-Page Summary Report

### 🔍 1. The Core "Why" Behind Customer Behavior
Our data analysis reveals that while overall customer demographic segments behave uniformly in terms of purchasing frequency, distinct financial value patterns emerge:
* **The High-Income Multipliers:** Independent of marital configuration, top revenue margins are driven by a distinct high-income segment. Our EDA confirmed that `Income` scales heavily ($r = 0.80$) with `Total_Spent`.
* **The Single-Professional Margin:** While "Single" and "Partnered" households share near-identical transaction frequencies (~12.5 purchases), **Single customers spend roughly 4% more overall** (Avg: \$621.64 vs \$597.00).
* **The Household Friction Point:** Households with children showcase lower disposable income and act as friction zones for active marketing campaign conversions.

---

### 📊 2. Marketing Funnel & Channel ROI Performance
By mapping transaction volume against proportional revenue and applying typical infrastructure cost constraints (Server maintenance vs. Brick-and-Mortar vs. Print/Postage), our channels yielded the following ROI profiles:

| Marketing Channel | Total Volume (Units) | Est. Unit Cost | Estimated Financial ROI (%) | Strategic Efficiency (ROI Assessment) |
| :--- | :---: | :---: | :---: | :--- |
| 🌐 **Web Purchases** | ~8,000 | \$0.50 | **~9,558%** | **Maximum ROI:** Minimal marginal cost per transaction. The lack of physical overhead gives our digital store an astronomical financial yield. |
| 🏪 **Store Purchases** | ~9,000+ | \$3.00 | **~1,510%** | **High ROI:** Our foundational volume driver. Represents strong customer trust but incurs physical overhead limits. |
| ✉️ **Catalog Purchases** | ~6,000 | \$5.50 | **Deficit / Low** | **Low ROI:** Produced the lowest structural conversion relative to high layout, printing, and postal overhead. |

---

### 🚀 3. Strategic Budget Recommendations

Based on the empirical insights above, the following immediate budget reallocations are recommended to maximize portfolio efficiency:

1. **Defund Catalog Distribution by 20% and Shift Capital to Digital Web Platforms**  
   * *Action:* Pivot budget out of printing physical mailers and reinvest those funds entirely into website conversion optimization, desktop/mobile UX refinement, and web-specific promotions.
2. **Re-align Campaign Target Audience Criteria**  
   * *Action:* Restrict generic demographic marketing campaigns. Direct programmatic digital dollars explicitly towards child-free segments and single working professionals who maintain the highest disposable income trends.
3. **Deploy Omni-Channel Web-to-Store Loops**  
   * *Action:* Leverage our high-margin Web infrastructure to capture customer orders, but incentivize "Buy Online, Pick Up In-Store" (BOPIS) to pull digital shoppers into high-volume physical retail environments.

---

## 💻 Tech Stack Used
* **Language:** Python
* **Environment:** Jupyter Notebooks
* **Libraries:** `pandas`, `numpy`, `seaborn`, `matplotlib`

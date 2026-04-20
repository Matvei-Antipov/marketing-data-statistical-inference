# Comprehensive Analysis of the Customer Personality Dataset: From Normalization to Statistical Hypothesis Testing

**Author:** Matvii Antipov  
**Affiliations:** * Student, National Technical University "Kharkiv Polytechnic Institute" (NTU KhPI)
* Guest Student, Osnabrück University of Applied Sciences

## 1. Abstract
This repository contains the results of a comprehensive Exploratory Data Analysis (EDA) and statistical hypothesis testing pipeline applied to the "Customer Personality Analysis" marketing dataset. The primary objective of this study is the mathematical justification of customer retention strategies through the segmentation of the consumer base and the evaluation of their responsiveness to marketing campaigns versus organic brand loyalty.

## 2. Problem Statement and Hypotheses
The research is directed at resolving the problem of customer retention. The study rigorously tests the following statistical hypothesis:

* **Null Hypothesis ($H_0$):** There is no statistically significant difference in the proportion of discount-driven purchases between loyal customers and random/occasional buyers.
* **Alternative Hypothesis ($H_1$):** Random or occasional buyers make a statistically significantly higher proportion of their purchases due to discounts and advertising compared to loyal customers.

## 3. Research Methodology (Pipeline)
The analysis was conducted following a structured Data Science pipeline:

1. **Data Preparation and Feature Engineering:**
   * Removed missing values (`NaN`), zero-variance features (`Z_CostContact`, `Z_Revenue`), and data anomalies (e.g., Age > 100, Income > 200,000).
   * Engineered the target metric `Deal_Ratio` (the percentage of purchases made with a discount relative to total purchases).
   * Scaled numerical features utilizing `StandardScaler`.
2. **Machine Learning and Customer Segmentation:**
   * Applied the **K-Means** clustering algorithm.
   * Determined the optimal number of clusters ($k=4$) using the **Elbow Method**.
3. **Target Group Identification:**
   * Profiled and isolated the target cohorts for testing: the "Loyal Elite" (Cluster 1) and "Occasional Buyers" (Cluster 0).
4. **Distribution Analysis:**
   * Assessed the normality of the target metric's distribution using the **Shapiro-Wilk Test**.
5. **Statistical Hypothesis Testing:**
   * Executed a one-tailed, non-parametric **Mann-Whitney U Test** to mathematically evaluate the difference between the cohorts.

## 4. Analytical Results
The K-Means algorithm successfully partitioned the customer base into four distinct clusters. Profiling revealed substantial behavioral differences between the target groups:

* **Discount-Sales Ratio (Occasional Buyers):** 33.9%
* **Discount-Sales Ratio (Loyal Elite):** 7.0%

Results of the statistical inference:
* **Shapiro-Wilk p-value:** $9.94 \times 10^{-13}$ (Confirming a highly skewed, non-normal distribution, which justifies the use of a non-parametric test).
* **Mann-Whitney U Statistic:** 344444.0
* **Mann-Whitney U p-value:** $1.52 \times 10^{-165}$

## 5. Conclusions and Business Strategy
**The Null Hypothesis (H0) is firmly rejected.** The statistical analysis provides conclusive mathematical proof that occasional and low-activity buyers cannot be effectively retained by appealing to organic product quality or brand loyalty. The only statistically validated and effective strategy for retaining this specific segment relies on **targeted marketing campaigns and aggressive promotional discounts**.

Conversely, providing regular discounts to the "Loyal Elite" segment is highly inefficient. It merely erodes profit margins without yielding any significant increase in their purchasing activity.

## 6. Technology Stack
* **Python 3**
* **Pandas** (Data manipulation and cleaning)
* **Scikit-learn** (K-Means clustering, Feature scaling)
* **SciPy** (Shapiro-Wilk, Mann-Whitney U tests)
* **Matplotlib** (Elbow Method visualization)
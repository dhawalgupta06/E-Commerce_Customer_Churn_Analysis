# E-Commerce Customer Churn & Retention Analysis

## Project Overview

Customer churn is an important business problem for e-commerce companies
because losing customers can affect retention, repeat purchasing, and
long-term customer relationships.

This project analyzes an anonymized e-commerce customer dataset
containing **5,630 customers and 20 variables**. The objective is to
understand customer behavior, engagement, purchasing patterns, service
experience, and customer characteristics to identify factors
**associated with churn** and determine which customer segments should
be prioritized for retention efforts.

The project follows a complete analytical workflow using **Python,
Pandas, NumPy, and Matplotlib**, from data understanding and cleaning
through exploratory churn analysis, customer segmentation, and
business-focused visualization.

> This is a descriptive analytics project. The findings show
> associations within the available data and should not be interpreted
> as causal relationships or churn predictions.

------------------------------------------------------------------------

## Business Objective

**Analyze customer behavior, engagement, purchasing patterns, service
experience, and customer characteristics to identify key factors
associated with churn and determine which customer segments should be
prioritized for retention efforts.**

The analysis focuses on answering four business questions:

1.  What is the overall level of customer churn?
2.  Which customer characteristics and behaviors are associated with
    higher churn?
3.  Which combinations of factors identify particularly high-risk
    customer groups?
4.  Where should retention efforts be prioritized based on the observed
    patterns?

------------------------------------------------------------------------

## Dataset

The project uses the **E-Commerce Customer Churn Analysis and
Prediction** dataset published by Ankit Verma on Kaggle.

-   **Customers:** 5,630
-   **Variables:** 20
-   **Target variable:** `Churn`
-   **Churn definition:** `0 = Retained`, `1 = Churned`
-   **Overall churn rate:** 16.84%

The dataset contains customer-level information related to tenure, login
behavior, purchasing activity, preferred order category, complaints,
satisfaction, registered devices, order recency, coupons, cashback, and
other customer characteristics.

The dataset is anonymized and does not contain revenue, profit, customer
lifetime value, or individual order-value information. Therefore, this
project does **not** estimate the financial impact of churn.

------------------------------------------------------------------------

## Tools & Technologies

-   **Python**
-   **Pandas** --- data cleaning, transformation, segmentation, and
    analysis
-   **NumPy** --- numerical operations
-   **Matplotlib** --- business-focused data visualization
-   **Jupyter Notebook**
-   **Excel / OpenPyXL** --- source and cleaned dataset handling
-   **Git & GitHub** --- version control and project documentation

------------------------------------------------------------------------

## Project Workflow

### 1. Data Understanding

The raw dataset was examined to understand its structure, variables,
missing values, categorical inconsistencies, duplicates, and numerical
ranges.

Key quality observations included:

-   No duplicate customer IDs
-   No fully duplicated records
-   Missing values in seven numerical columns
-   Inconsistent labels in login device, payment mode, and preferred
    order category
-   Upper-range numerical values were inspected before deciding whether
    they required treatment

### 2. Data Cleaning

The analysis-ready dataset was prepared by:

-   Standardizing inconsistent categorical labels
-   Imputing missing numerical values using appropriate median or mean
    values
-   Revalidating missing values and duplicates
-   Exporting a cleaned dataset for subsequent analysis

### 3. Customer Churn Analysis

Customer churn was analyzed across lifecycle, engagement, purchasing
behavior, and customer-experience variables.

Rather than analyzing every available variable simply because it
existed, the project focused on factors that produced meaningful
business signals.

### 4. Customer Risk Segmentation

The strongest individual churn signals were combined to create
actionable customer segments based on:

-   **Customer tenure**
-   **Complaint history**

This allowed the analysis to move beyond individual variables and
identify customer groups with substantially different churn rates.

### 5. Visualization

The strongest findings were translated into six focused Matplotlib
visualizations:

-   Overall Customer Churn
-   Churn Rate by Tenure Group
-   Churn Rate by Complaint Status
-   Churn Rate by Preferred Order Category
-   Churn Rate by Number of Registered Devices
-   Churn Rate by Customer Risk Segment

------------------------------------------------------------------------

## Key Business Insights

### Overall Churn

Of the 5,630 customers analyzed:

-   **4,682 were retained**
-   **948 churned**
-   **Overall churn rate: 16.84%**

This provides the baseline against which individual customer groups were
compared.

### Early-Tenure Customers Show the Highest Churn

Customers with **0--3 months of tenure** had a churn rate of **41.86%**,
substantially above the overall churn rate.

The churn rate fell sharply to **7.46%** among customers with 4--6
months of tenure.

This indicates that churn is heavily concentrated in the earliest stage
of the customer lifecycle.

### Complaints Are Strongly Associated with Churn

Customers who had registered a complaint showed a **31.67% churn rate**,
compared with **10.93%** among customers without a complaint.

Complaint history therefore emerged as one of the strongest individual
churn signals in the analysis.

### Preferred Order Category Shows Meaningful Differences

Churn varied considerably across preferred product categories:

  Preferred Order Category     Churn Rate
  -------------------------- ------------
  Mobile                           27.40%
  Fashion                          15.50%
  Laptop & Accessory               10.24%
  Others                            7.58%
  Grocery                           4.88%

Customers preferring the **Mobile** category had the highest observed
churn rate.

### Registered Devices Are Associated with Higher Churn

Churn generally increased as the number of registered devices increased:

  Registered Devices     Churn Rate
  -------------------- ------------
  1                           9.36%
  2                           9.42%
  3                          14.95%
  4                          16.49%
  5                          22.47%
  6                          34.57%

The six-device group contains fewer customers than the major groups, so
its result should be interpreted cautiously. Nevertheless, the broader
pattern suggests that device registration is a useful behavioral signal
for further investigation.

------------------------------------------------------------------------

## Customer Risk Segmentation

Tenure and complaint history were combined because both were strong
churn indicators individually.

  Customer Segment                 Customers   Churned   Churn Rate
  ------------------------------ ----------- --------- ------------
  New + Complaint                        522       345   **66.09%**
  New + No Complaint                   1,038       308   **29.67%**
  Longer Tenure + Complaint            1,082       163   **15.06%**
  Longer Tenure + No Complaint         2,988       132    **4.42%**

**New customers with a complaint represent the highest-priority
retention segment**, with approximately two-thirds of customers in this
group having churned.

The segmentation also shows that tenure and complaint history become
especially informative when considered together.

------------------------------------------------------------------------

## Retention Priorities & Recommendations

Based on the observed patterns, retention efforts should primarily focus
on the early customer lifecycle and customer-service experience.

**1. Strengthen early-customer onboarding**

The very high churn rate among customers in their first three months
suggests that the early customer experience deserves particular
attention. The business should review onboarding, first-purchase
experience, communication, and early engagement processes.

**2. Prioritize complaints from new customers**

New customers who had complained recorded the highest churn rate in the
analysis at 66.09%. Complaints from early-tenure customers should
therefore receive high retention priority, with faster resolution and
appropriate follow-up.

**3. Investigate the Mobile-category customer experience**

Customers preferring the Mobile category showed substantially higher
churn than other order categories. Further analysis should investigate
whether product experience, fulfillment, support, returns, pricing, or
other category-specific factors may explain the observed difference.

**4. Monitor customers with higher device registrations**

Higher registered-device counts were associated with higher churn rates.
This pattern should be investigated further to determine whether it
reflects account behavior, login friction, customer characteristics, or
another underlying factor.

These recommendations are intended as areas for business investigation
and retention prioritization; the available observational data does not
establish that these factors cause churn.

------------------------------------------------------------------------

## Project Structure

``` text
ecommerce-customer-churn-analysis/
│
├── data/
│   ├── E Commerce Dataset.xlsx
│   └── E Commerce Dataset Cleaned.xlsx
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_customer_churn_analysis.ipynb
│   ├── 04_customer_segmentation.ipynb
│   └── 05_visualization.ipynb
│
├── outputs/
│   └── figures/
│
├── README.md
├── requirements.txt
└── .gitignore
```

------------------------------------------------------------------------

## Notebook Guide

  ------------------------------------------------------------------------
  Notebook                             Purpose
  ------------------------------------ -----------------------------------
  `01_data_understanding.ipynb`        Dataset structure, quality
                                       assessment, missing values,
                                       duplicates, categorical
                                       inconsistencies, and numerical
                                       inspection

  `02_data_cleaning.ipynb`             Categorical standardization,
                                       missing-value treatment,
                                       validation, and cleaned-data
                                       preparation

  `03_customer_churn_analysis.ipynb`   Analysis of churn across customer
                                       lifecycle, engagement, purchasing
                                       behavior, and experience

  `04_customer_segmentation.ipynb`     Tenure × complaint customer
                                       segmentation and retention-priority
                                       identification

  `05_visualization.ipynb`             Matplotlib visualization of the
                                       strongest churn findings and
                                       customer risk segments
  ------------------------------------------------------------------------

------------------------------------------------------------------------

## Limitations

The findings should be interpreted within the limitations of the
available dataset:

-   The dataset is anonymized, so findings cannot be attributed to a
    specific real-world company.
-   The analysis identifies **associations, not causal relationships**.
-   Missing numerical values required imputation during data cleaning.
-   The dataset does not contain revenue, profit, CLV, or detailed
    transaction values, so the financial impact of churn cannot be
    quantified.
-   Some relationships in the wider analysis were counterintuitive and
    would require additional business context or data to explain
    confidently.
-   This project intentionally focuses on **descriptive business
    analysis rather than machine-learning churn prediction**.

------------------------------------------------------------------------

## Conclusion

The analysis found that customer churn is not distributed evenly across
the customer base.

The strongest retention concern appears during the **early customer
lifecycle**, particularly when a new customer also has a **complaint**.
Customers with 0--3 months of tenure had a 41.86% churn rate, while the
combined **New + Complaint** segment reached 66.09%.

Preferred order category and registered-device count also showed
meaningful differences in churn behavior.

Together, these findings provide a practical basis for prioritizing
retention efforts toward the customer groups displaying the highest
observed churn risk while highlighting areas that require deeper
business investigation.

------------------------------------------------------------------------

## Author

**Dhawal Gupta**

Business, Finance & Data Analyst

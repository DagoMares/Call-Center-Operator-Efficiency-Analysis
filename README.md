# Call-Center Operator Efficiency Analysis 📞📊

**Operational efficiency analysis and identification of ineffective operators for the "CallMeMaybe" virtual telephony service.**

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-orange.svg)](https://public.tableau.com/views/inef_ops/CallMeMaybe-Ops?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 📋 Table of Contents
- [Call-Center Operator Efficiency Analysis 📞📊](#call-center-operator-efficiency-analysis-)
  - [📋 Table of Contents](#-table-of-contents)
  - [🏢 Project Context](#-project-context)
  - [❓ Problem Statement](#-problem-statement)
  - [⚙️ Methodology](#️-methodology)
  - [📉 Inefficiency Definition](#-inefficiency-definition)
  - [🧪 Hypothesis Testing Results](#-hypothesis-testing-results)
  - [🚀 Conclusions and Recommendations](#-conclusions-and-recommendations)
  - [💻 Technologies Used](#-technologies-used)
  - [📊 Visualization](#-visualization)

---

## 🏢 Project Context
"CallMeMaybe" is a virtual telephony service provider looking to optimize its human resources management. The company needs to better understand its operators' performance to improve customer service quality and operational efficiency.

The dataset contains records of calls (internal and external), duration, waiting times, and call status (missed or answered) over a specific period.

## ❓ Problem Statement
Management lacks objective, data-driven criteria to determine which operators are underperforming. The main objectives are:
1.  Define metrics that constitute an "ineffective" operator.
2.  Identify operators who meet these conditions.
3.  Propose improvement actions based on statistical testing.

## ⚙️ Methodology
The analysis was conducted following these steps:

1.  **Data Preprocessing**: Cleaning duplicates, handling null values, and converting data types (dates, booleans).
2.  **Exploratory Data Analysis (EDA)**: Studying the distribution of incoming vs. outgoing calls, waiting times, and daily volumes.
3.  **Threshold Definition (Data-Driven)**: Using percentiles (85th, 90th, 95th) to establish objective performance limits.
4.  **Hypothesis Testing**: Statistical validation of differences between groups (Levene's Test and Student's t-test).
5.  **Segmentation**: Binary classification of operators (Effective / Ineffective).

## 📉 Inefficiency Definition
Based on the data distribution analysis, the following critical KPIs were established. An operator is considered **ineffective** if they meet any of these conditions:

*   **Incoming Calls**:
    *   Missed call rate > **10%** (85th Percentile+).
    *   Average waiting time > **80 seconds** (90th Percentile+).
*   **Outgoing Calls**:
    *   Total calls made < **8** (Low productivity).

## 🧪 Hypothesis Testing Results
Statistical tests were performed with a significance level of `alpha = 0.05` to validate the findings:

| Hypothesis                                  | Statistical Test      | Result (p-value) | Conclusion                                                                                |
| :------------------------------------------ | :-------------------- | :--------------- | :---------------------------------------------------------------------------------------- |
| **1. Waiting Times:** Internal < External   | t-test (unequal var.) | `0.000`          | **H0 Rejected**. External clients wait significantly longer.                              |
| **2. Missed Rate:** Ineffective > Effective | t-test (unequal var.) | `1.82e-04`       | **H0 Rejected**. Operators marked as ineffective have statistically inferior performance. |
| **3. Missed Rate:** Internal ≠ External     | Z-test (proportions)  | `0.000`          | **H0 Rejected**. There is a significant difference in attention based on call origin.     |

## 🚀 Conclusions and Recommendations

1.  **Priority on External Calls**: Analysis showed the bottleneck lies with external calls (real clients). It is recommended to reassign internal operators to external lines during peak hours.
2.  **Targeted Intervention**: A list of ineffective operators was generated. Immediate dismissal is not recommended; instead, **specific training** on reducing waiting times is advised.
3.  **Infrastructure Review**: Outliers in waiting times suggest potential technical failures in call routing, not just human error.

## 💻 Technologies Used
*   **Python**: Primary language.
*   **Pandas & NumPy**: Data manipulation and aggregation.
*   **SciPy Stats**: Hypothesis testing (Levene, t-test, Z-test).
*   **Matplotlib & Seaborn**: Static visualization of distributions and boxplots.
*   **Tableau**: Interactive dashboard for management.

## 📊 Visualization
You can interact with the results dashboard here:
👉 **[View Dashboard on Tableau Public](https://public.tableau.com/views/inef_ops/CallMeMaybe-Ops?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---
*Author: [Dagoberto Mares](https://github.com/DagoMares)*

*Contact: [![Gmail Badge](https://img.shields.io/badge/-dagobertomares0@gmail.com-c14438?style=flat&logo=Gmail&logoColor=white&link=mailto:dagobertomares0@gmail.com)](mailto:dagobertomares0@gmail.com) -
[![Linkedin Badge](https://img.shields.io/badge/-dagobertomares-0072b1?style=flat&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/dagoberto-mares/)](https://www.linkedin.com/in/dagoberto-mares/)*

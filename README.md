# NYC Payroll EDA: Compensation, Overtime, and High-Pay Prediction

## Authors

* **Brian Lyu (Student A)**
  Responsible for:

  * Project design & research questions
  * Data cleaning & feature engineering
  * Exploratory Data Analysis (EDA)

* **Zien Zhu (Student B)**
  Responsible for:

  * Advanced analysis & interpretation
  * Machine learning modeling & evaluation

---

## Project Overview

This project conducts an exploratory data analysis (EDA) on New York City employee payroll data to understand how compensation is structured and what factors drive high earnings.

The project combines:

* **Exploratory Data Analysis (EDA)** to uncover patterns
* **Lightweight Machine Learning** to validate predictive relationships

The primary goal is to analyze how **base salary, overtime pay, and other compensation components** contribute to total income, and whether high compensation can be predicted from employee characteristics.

---

## Research Questions

This project focuses on three core questions:

1. **Compensation Structure**
   How is total compensation distributed across base salary, overtime pay, and other income sources?

2. **Group Differences**
   How do compensation patterns vary across:

   * Agencies
   * Boroughs
   * Job titles
   * Pay basis types

3. **High-Pay Prediction**
   Can features such as salary, tenure, and overtime usage predict whether an employee belongs to a high-pay group?

---

## Dataset

The dataset includes payroll records for approximately **10,000 NYC employees**, with **17 variables** covering employee attributes and compensation details.

### Key Variables

| Variable              | Description              |
| --------------------- | ------------------------ |
| fiscal_year           | Fiscal year of record    |
| agency_name           | Employer agency          |
| work_location_borough | Work location            |
| title_description     | Job title                |
| pay_basis             | Pay type (annual/hourly) |
| base_salary           | Base salary              |
| regular_hours         | Regular hours worked     |
| regular_gross_paid    | Regular pay              |
| ot_hours              | Overtime hours           |
| total_ot_paid         | Overtime compensation    |
| total_other_pay       | Other payments           |
| agency_start_date     | Start date               |

---

## Data Cleaning and Feature Engineering (Student A)

Data preprocessing steps:

* Converted string-based numeric fields into proper numeric types
* Parsed `agency_start_date` into datetime
* Handled missing values and removed invalid records
* Filtered anomalies (e.g., negative compensation or hours)

### Engineered Features

* **total_compensation**
  = regular_gross_paid + total_ot_paid + total_other_pay

* **tenure_years**
  = years since agency_start_date

* **overtime_share**
  = total_ot_paid / total_compensation

* **other_pay_share**
  = total_other_pay / total_compensation

* **high_pay (target variable)**
  = 1 if total_compensation > median, else 0

---

## Exploratory Data Analysis (Student A)

Key analyses include:

* Distribution of salary and total compensation
* Overtime usage patterns
* Compensation differences across boroughs and agencies
* Relationship between base salary and total earnings
* Compensation composition across job types

### Key EDA Insights

* Compensation is **highly right-skewed**
* Overtime significantly increases total income for certain roles
* Strong heterogeneity across agencies and job categories

---

## Advanced Analysis & Interpretation (Student B)

### Agency-Level Inequality

* Significant variation in compensation across agencies
* Indicates structural differences in:

  * Budget allocation
  * Job specialization
  * Operational demand

---

### Overtime as a Key Driver

* High-income employees:

  * Work more overtime
  * Depend more on overtime pay

* Suggests compensation is **workload-driven**, not purely salary-based

---

### Compensation Structure Differences

Employees fall into distinct groups:

* Salary-dominant income
* Overtime-heavy income
* Mixed compensation structures

---

### Correlation Analysis

* Strong: base salary ↔ total compensation
* Moderate: overtime pay ↔ total compensation
* Weak: location ↔ compensation

Conclusion:
→ Financial variables dominate
→ Demographic/location variables less important

---

## Machine Learning Analysis (Student B)

### Task

Binary classification: predict **high_pay**

---

### Models

* Logistic Regression
* Random Forest (feature importance)

---

### Evaluation Metrics

* Precision
* Recall
* F1-score

---

### Results

* Base salary = strongest predictor
* Overtime variables = highly influential
* Tenure = secondary factor

### Interpretation

Machine learning results **confirm EDA findings**:

> High compensation = Base Salary + Overtime Participation

---

## Key Insights

1. **Compensation Inequality**
   Income distribution is highly skewed

2. **Overtime Dependence**
   Overtime is a major driver of high earnings

3. **Agency & Role Effects**
   Strong structural differences exist

4. **Predictability**
   High pay can be predicted using a small set of features

---

## Implications

* **Policy**
  Heavy overtime may indicate staffing inefficiencies

* **Equity**
  Compensation differences raise fairness concerns

* **Workforce Planning**
  Need to balance workload and compensation structures

---

## Limitations

* Sample dataset (not full population)
* Data quality issues (missing/inconsistent values)
* Observational → no causal inference

---

## Conclusion

NYC employee compensation is driven by:

* Base salary (baseline)
* Overtime participation (key differentiator)
* Agency-level structure (systemic factor)

# NYC Payroll EDA: Compensation, Overtime, and High-Pay Prediction

## Project Overview

This project conducts an exploratory data analysis (EDA) of New York City employee payroll data to better understand compensation patterns across different agencies, job roles, and locations. The analysis focuses on how employee income is structured and how different factors relate to high compensation.

The project combines **exploratory data analysis (EDA)** with a **lightweight machine learning task**. EDA is used to uncover patterns and relationships within the payroll data, while a simple classification model is built to test whether employee attributes can predict membership in a high-pay group.

The goal is to better understand how base salary, overtime pay, and other compensation components contribute to overall earnings in the NYC workforce.

---

## Research Questions

This project investigates three main questions:

1. **Compensation Structure**
   How is employee compensation distributed across base salary, overtime pay, and other payments?

2. **Group Differences**
   Do compensation patterns vary across agencies, boroughs, job titles, and pay basis types?

3. **High-Pay Prediction**
   Can employee characteristics such as salary, tenure, and overtime usage help predict whether an employee belongs to a high-pay group?

---

## Dataset

The dataset contains payroll information for **10,000 NYC employees** and includes **17 original variables** covering employee information, job details, and compensation components.

Key variables include:

| Variable              | Description                        |
| --------------------- | ---------------------------------- |
| fiscal_year           | Fiscal year of payroll record      |
| agency_name           | Agency employing the worker        |
| work_location_borough | Borough where the employee works   |
| title_description     | Job title                          |
| pay_basis             | Type of pay (annual, hourly, etc.) |
| base_salary           | Base salary                        |
| regular_hours         | Total regular working hours        |
| regular_gross_paid    | Regular compensation paid          |
| ot_hours              | Overtime hours worked              |
| total_ot_paid         | Total overtime pay                 |
| total_other_pay       | Other compensation payments        |
| agency_start_date     | Start date at the agency           |

---

## Data Cleaning and Feature Engineering

Before analysis, several preprocessing steps were performed:

* Converted string fields representing numbers into numeric types
* Converted `agency_start_date` to a datetime format
* Checked and handled missing values
* Identified and filtered anomalous records (e.g., negative hours or compensation)

Several derived variables were created:

* **total_compensation**
  `regular_gross_paid + total_ot_paid + total_other_pay`

* **tenure_years**
  Employee tenure calculated from `agency_start_date`

* **overtime_share**
  Percentage of total income coming from overtime pay

* **other_pay_share**
  Percentage of income from other payments

* **high_pay (target variable)**
  Binary variable indicating whether total compensation exceeds the dataset median

---

## Exploratory Data Analysis

The EDA phase investigates patterns in employee compensation through visualizations and grouped analysis.

Key analyses include:

* Distribution of salary and total compensation
* Distribution of overtime hours and overtime pay
* Differences in compensation across boroughs and pay types
* Relationship between base salary and total earnings
* Comparison of compensation structures across agencies
* Overtime dependence across different job groups

The goal of this stage is to identify meaningful patterns and generate insights about how employee compensation is structured.

---

## Machine Learning Analysis

A simple classification task was implemented to predict whether an employee belongs to the **high-pay group**.

### Target Variable

`high_pay`

Employees with total compensation above the dataset median are labeled as **1**, and others as **0**.

### Models Used

Two models were implemented:

* **Logistic Regression**

### Evaluation Metrics

Models were evaluated using:

* Precision
* Recall
* F1-score

Random Forest was also used to examine **feature importance**, helping identify which factors most strongly influence high compensation.

---

## Key Findings

Some major observations from the analysis include:

* Employee compensation is highly right-skewed, with a small number of workers earning significantly higher total pay.
* Overtime pay contributes substantially to total earnings for some job categories.
* Compensation patterns vary significantly across agencies and job titles.
* Base salary and overtime participation appear to be strong predictors of high-pay status.


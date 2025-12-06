# 📊 **Bank Loan Analysis Dashboard**
### *Power BI | Tableau | SQL | Data Modeling | DAX*

This project provides an end-to-end analysis of a bank’s loan portfolio, evaluating loan performance, customer behavior, and key financial metrics.  
The analysis was built using **Power BI**, **Tableau**, **SQL**, and **DAX**, with complete data cleaning, modeling, and visual storytelling.

---

## 🚀 **Project Overview**

The objective of this dashboard is to help stakeholders track:

- Total loan applications  
- Funded vs. received amounts  
- Month-over-month (MoM) and month-to-date (MTD) performance  
- Distribution of **good vs. bad loans**  
- Loan performance by **state**, **purpose**, **term**, **employee length**, and **home ownership**  
- Detailed loan-level data for operational insights  

The analysis helps the bank monitor trends, identify risks, and improve loan strategies.

---

## 📦 Bank Loan Analysis
-│
-├── 📊 Power BI Dashboard (Summary, Overview, Details)
-├── 📈 Tableau Visualizations
-├── 📄 Dataset (bank_loan.csv + Date Table)
-├── 🧮 DAX Measures
-└── 🗄️ SQL Scripts (Data Cleaning & Verification)

---

## 🧹 **Data Cleaning & Verification (SQL)**

Data validation and preprocessing were performed using SQL. Key steps included:

- Handling missing and invalid values  
- Standardizing date formats  
- Creating derived fields  
- Verifying loan status metrics  
- Aggregating MTD, PMTD, and MOM values  

### Example SQL Queries Used

#### ✔ Loan Status Summary
```sql
SELECT 
    loan_status,
    COUNT(id) AS LoanCount,
    SUM(total_payment) AS Total_Amount_Received,
    SUM(loan_amount) AS Total_Funded_Amount,
    AVG(int_rate * 100) AS Interest_Rate,
    AVG(dti * 100) AS DTI
FROM bank_loan_data
GROUP BY loan_status;

---

##✔ MTD Funded & Received Amount

SELECT 
    loan_status,
    SUM(total_payment) AS MTD_Total_Amount_Received,
    SUM(loan_amount) AS MTD_Total_Funded_Amount
FROM bank_loan_data
WHERE MONTH(issue_date) = 12
GROUP BY loan_status;

---

## 📐 Data Modeling

A star-schema style model was created in Power BI:

## Tables Used

bank_loan (fact table)

Date Table (custom built)

Select Measure (disconnected table for dynamic switching)


## Relationships

Date Table [Date] → bank_loan [issue_date]

---

## | Tool         | Purpose                          |
| ------------ | -------------------------------- |
| **Power BI** | Data modeling & DAX calculations |
| **Tableau**  | Visual analytics                 |
| **SQL**      | Data cleaning and verification   |
| **Excel**    | Preprocessing & file management  |
| **DAX**      | Business logic & KPIs            |
---

All relationships set to single-direction for optimized performance

## 📁 **Project Structure**


# 🏦 Loan Portfolio & Risk Analytics Dashboard | Power BI + PostgreSQL

## 🚀 Overview

This project is an interactive **Loan Portfolio & Risk Analytics Dashboard** built using **Power BI**, **PostgreSQL**, **Power Query**, and **DAX**. It transforms raw financial loan data into actionable business insights through executive-level dashboards and KPI-driven reports.

The solution analyzes loan performance, customer demographics, credit risk, revenue, and portfolio health using SQL-based data aggregation and dynamic Power BI visualizations.

---

## 🎯 Objectives

- Analyze loan portfolio performance
- Monitor funding and repayment trends
- Evaluate customer demographics
- Identify high-risk borrowers
- Compare loan grades and purposes
- Analyze geographic loan distribution
- Build an executive-level interactive dashboard

---

## 📸 Dashboard Screenshots

### 🏠 Home Page

![Home Page](screenshots/home-page.jpeg)

### 💰 Loan Analytics

![Loan Analytics](screenshots/loan-analytics.jpeg)

### 👥 Customer Analytics

![Customer Analytics](screenshots/customer-analytics.jpeg)

### ⚠️ Risk Analytics

![Risk Analytics](screenshots/risk-analytics.jpeg)

### 📊 Portfolio Summary

![Portfolio Summary](screenshots/summary-dashboard.jpeg)

---

## 📊 Key KPIs

### 💰 Loan Analytics
- Total Portfolio Value
- Total Loan Applications
- Average Loan Amount
- Estimated Interest Revenue

### 👥 Customer Analytics
- Total Customers
- Average Annual Income
- Average DTI
- Average Installment

### ⚠️ Risk Analytics
- Charged-Off Loans
- Risk Rate
- Expected Loss
- High Risk Customers

### 📊 Portfolio Summary
- Largest Loan Issued
- Total Revenue
- Total Funded Amount
- Average Interest Rate

---

## 📈 Dashboard Features

- Executive KPI Cards
- Interactive Navigation
- Dynamic DAX Measures
- Loan Portfolio Analysis
- Customer Analytics
- Credit Risk Assessment
- Revenue Analysis
- Geographic Analysis
- Interactive Filters & Slicers
- Drill-down Reports

---

## 🧹 Data Preparation

The dataset was processed using **PostgreSQL** and **Power Query** before visualization.

### Transformations Performed

- Removed duplicate and inconsistent records
- Standardized data types
- Converted date fields
- Validated numerical columns
- Created optimized SQL Views
- Built a clean Power BI data model

---

## 🧠 SQL Views

To improve dashboard performance, multiple PostgreSQL views were created for business reporting.

### Loan Analytics
- Loan KPIs
- Monthly Loan Trend
- Loan Purpose Analysis
- Loan Status Distribution
- Grade Analysis

### Customer Analytics
- Customer KPIs
- Home Ownership Analysis
- Income Band Analysis
- Employment Length Analysis

### Risk Analytics
- Risk KPIs
- Grade-wise Risk
- Purpose-wise Risk
- Monthly Risk Trend
- Risk Summary

### Portfolio Summary
- State Summary
- Revenue by Purpose
- Portfolio Snapshot

---

## 📊 Core DAX Measures

### 🚨 High Risk Customers

Identifies borrowers with poor credit quality based on loan grade, DTI, and charged-off status.

```DAX
High Risk Customers =
CALCULATE(
    DISTINCTCOUNT('public financial_loan'[member_id]),
    'public financial_loan'[grade] IN {"E","F","G"},
    'public financial_loan'[dti] > 20,
    'public financial_loan'[loan_status] = "Charged Off"
)
```

---

### 💸 Expected Loss

Calculates the total loan amount associated with charged-off loans.

```DAX
Expected Loss =
CALCULATE(
    SUM('public financial_loan'[loan_amount]),
    'public financial_loan'[loan_status] = "Charged Off"
)
```

---

### 💰 Estimated Interest Revenue

Estimates revenue generated from issued loans.

```DAX
Estimated Interest Revenue =
SUMX(
    'public financial_loan',
    'public financial_loan'[loan_amount] *
    'public financial_loan'[int_rate] / 100
)
```

---

---

## 📊 Business Impact

This dashboard provides a comprehensive view of lending performance and portfolio health, enabling stakeholders to:

- Monitor overall loan portfolio growth
- Identify high-risk customers and loan segments
- Analyze customer demographics and borrowing behavior
- Compare loan performance across grades and purposes
- Track monthly lending trends and estimated revenue
- Support data-driven lending and risk management decisions

---

## 🛠️ Tools & Technologies

- 📊 Power BI Desktop
- 🐘 PostgreSQL
- 🧮 SQL
- 🔄 Power Query
- 📐 Data Modeling
- 📈 DAX (Data Analysis Expressions)

---

## 📂 Repository Structure

```text
loan-portfolio-risk-analytics-dashboard/
│
├── README.md
├── loan_analytics.pbix
├── Loan Portfolio Dashboard.pdf
├── financial_loan.xlsx
├── financial_loan_cleaned.csv
└── screenshots/
    ├── home-page.jpeg
    ├── loan-analytics.jpeg
    ├── customer-analytics.jpeg
    ├── risk-analytics.jpeg
    └── summary-dashboard.jpeg
```

---

## 🚀 Getting Started

1. Clone this repository.
2. Import the loan dataset into PostgreSQL.
3. Execute the SQL scripts to create the required views.
4. Open `Loan Portfolio Dashboard.pbix` in **Power BI Desktop**.
5. Refresh the data connection.
6. Explore the dashboard using the interactive slicers and filters.

---

## ⭐ Author

**Garvita Jain**

Built as a portfolio project to demonstrate practical skills in:

- Power BI
- PostgreSQL
- SQL
- DAX
- Power Query
- Data Modeling
- Business Intelligence
- Financial Analytics

---

## 📄 License

This project is shared for **educational and portfolio purposes**.

---

⭐ If you found this project useful, consider giving the repository a **Star**!

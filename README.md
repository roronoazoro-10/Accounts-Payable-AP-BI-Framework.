# 📊 Accounts Payable (AP) BI Framework

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-blue?style=for-the-badge)
![Data Modeling](https://img.shields.io/badge/Data_Modeling-Star_Schema-brightgreen?style=for-the-badge)

## 📌 Executive Summary
Managing corporate cash flow is critical to business survival. This project is an end-to-end **Accounts Payable BI Framework** designed to transition finance teams away from static Excel sheets into a dynamic, automated reporting environment. 

This dashboard provides finance executives and AP managers with immediate visibility into overall cash liabilities, department-wise debt concentrations, and critical invoice aging metrics.

---

## 🎬 Interactive Dashboard Demo
*(Recruiter Note: The animation below demonstrates the active relationship filters, cross-filtering capabilities, and multi-layered drill-downs built into the live Power BI model.)*

![Interactive Dashboard Demo](Dashboard_Demo.gif)

---

## 📈 Key Performance Indicators (KPIs)
* **Total Invoice Amount ($387K):** Total raw transaction volume processed through the system.
* **Outstanding Balance ($142K):** Total active liabilities currently owed to vendors.
* **Average DPO (25.40 Days):** Dynamic Days Payable Outstanding tracking payment efficiency against the current calendar date (`TODAY()`).

---

## 🛠️ Technical Architecture & Skills Demonstrated

### 1. Data Ingestion & ETL (Power Query)
* Connected and extracted transactional data and vendor records.
* Executed data cleaning, structural shaping, and enforced strict `Dim_` and `Fact_` naming conventions.

### 2. Relational Data Modeling (Star Schema)
* Designed a One-to-Many Star Schema connecting descriptive dimensions (`Dim_Vendors`) to the core transactional table (`Fact_Invoices`) using `VendorID`.
* Optimized the architecture for fast cross-filtering and rapid query execution.

### 3. Advanced DAX Calculations
Demonstrated ability to manipulate filter contexts and perform row-by-row time calculations:

**Context Transition (Isolating Overdue Balance):**
```dax
Overdue Balance = 
CALCULATE(
    [Total Invoice Amount],
    Fact_Invoices[Status] = "Overdue"
)

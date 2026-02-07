# Loan-Default-Credit-Risk-Analytics
**🔗 Dashboard Link :**  [Click here to view dashboard](https://app.powerbi.com/view?r=eyJrIjoiYTM2MTFiNDctOWU3Zi00NWNkLThhMzEtNmRkOWRjNjZmYTQ5IiwidCI6IjEzOGVlZmNmLTdkOTMtNGVhNS1hMTc2LTUxMjU0MDFhODVmNSJ9)
# 📌 Project Overview

This project presents an **end-to-end Credit Risk Analytics Dashboard** designed to analyze loan portfolio performance, borrower risk behavior, and default trends.

The solution transforms structured loan-level data into actionable insights that simulate real-world banking and fintech risk monitoring systems.

## 🎯 Dashboard Provides a 360° Analytical View Of:

- 📉 **Default Rate Analysis**
- 💰 **Loan Exposure Monitoring**
- 👤 **Borrower Demographic Segmentation**
- 🏦 **Credit Score Risk Categorization**
- 📊 **Year-over-Year Portfolio Performance**
- 📈 **Financial Stability Indicators**
  - Income Analysis  
  - Debt-to-Income (DTI) Monitoring  
  - Co-signer Impact  
  - Mortgage Evaluation  



## 🛠️ Key Highlights

This project demonstrates practical implementation of:

- Financial Analytics  
- Risk Segmentation  
- Portfolio Performance Monitoring  
- Business Intelligence Reporting using **Power BI**

> 🚀 Built to simulate real-world banking and fintech credit risk monitoring systems.

## 🏗️ Analytical Architecture

The dashboard follows a structured BI development approach:

- 📂 Raw structured loan dataset  
- 🧹 Data cleaning & transformation using Power Query  
- 📐 Feature engineering using DAX  
- ⭐ Star-schema inspired data modeling  
- 📊 Advanced DAX measures for KPIs & time intelligence  
- 📈 Interactive visual storytelling in Power BI  

---

## 🔄 Analytical Flow

Loan Dataset → Data Transformation → Data Modeling → DAX Metrics → Risk Insights
## 📂 Dataset Description

The dataset contains borrower-level loan records with the following attributes:

---

### 🔹 Borrower Information

- Age  
- Age Groups *(Derived)*  
- Education  
- Employment Type  
- Marital Status  
- Income  
- Income Bracket *(Derived)*  
- Has Co-signer *(Binary)*  
- Has Dependents *(Binary)*  
- Has Mortgage *(Binary)*  

---

### 🔹 Credit Risk Indicators

- Credit Score  
- Credit Score Category *(Derived)*  
- DTI Ratio  
- Default *(Binary)*  

---

### 🔹 Loan Details

- Loan ID  
- Loan Amount  
- Interest Rate  
- Loan Term  
- Loan Purpose  
- Loan Date  
- Year *(Derived for Time Intelligence)*
## 📐 Data Modeling

The model is designed using a structured BI approach:

---

### 🔹 Fact Table

**Loan_Default**

Contains:

- LoanAmount  
- Default  
- InterestRate  
- DTI Ratio  
- LoanTerm  
- Income  

---

### 🔹 Derived Columns (Feature Engineering)

- Credit Score Category  
- Income Bracket  
- Age Groups  
- Year  

These engineered features improve segmentation and risk profiling.

## 📊 Key Performance Indicators (KPIs)

---

### 💰 Portfolio Exposure

- Total Loan Amount  
- Number of Loans  
- Median Loan Amount  

---

### 📉 Risk Metrics

- Total Defaults  
- Default Rate (%)  
- Default Rate by Employment Type  
- Default Rate by Year  

---

### 📈 Time Intelligence

- Loan Amount Year-to-Date (YTD)  
- Year-over-Year Loan Amount Change  
- Year-over-Year Default Change
## 🧮 DAX Measures Implemented



### 🔹 Core Measures

```DAX
Total Loan Amount = 
SUM(Loan_default[LoanAmount])

No. of Loan = 
DISTINCTCOUNT(Loan_default[LoanID])

Total Defaults =
CALCULATE(
    COUNTROWS(Loan_default),
    Loan_default[Default] = TRUE()
)

Default Rate =
DIVIDE([Total Defaults], [No. of Loan])
```
### 🔹 Time Intelligence

```DAX
Loan Amount YTD =
TOTALYTD(
    [Total Loan Amount],
    'Date'[Date]
)

YOY Loan Amount Change =
VAR PrevYear =
    CALCULATE(
        [Total Loan Amount],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
RETURN
DIVIDE([Total Loan Amount] - PrevYear, PrevYear)
```
This demonstrates use of:

- CALCULATE  
- Context transition  
- Filter propagation  
- Time intelligence functions  
- Iterator optimization  
## 📈 Dashboard Analysis & Insights


### 1️⃣ Loan Portfolio Overview

- Identified employment categories with higher default concentration  
- Detected income-level influence on loan size  
- Analyzed exposure distribution by loan purpose  

📌 **Insight:** Certain employment types show higher default probability, indicating risk-adjusted lending opportunities.

---

### 2️⃣ Demographic Risk Segmentation

- Middle-age adults show higher total loan exposure  
- Low credit score category strongly correlates with increased default risk  
- Presence of co-signer reduces default likelihood  

📌 **Insight:** Credit score segmentation plays a critical role in portfolio risk management.

---

### 3️⃣ Financial Risk Trends

- Year-over-Year loan growth monitored  
- YoY default movement analyzed  
- Exposure shifts across marital status and credit categories  

📌 **Insight:** Portfolio growth must be monitored alongside default trends to prevent risk accumulation.
## 🧠 Skills Demonstrated



### 📊 Business Intelligence

- KPI development  
- Executive dashboard design  
- Risk analytics visualization  
- Financial storytelling  

---

### 📐 Data Modeling

- Star schema implementation  
- Feature engineering using DAX  
- Context-aware measure design  

---

### 🧮 DAX & Advanced Analytics

- CALCULATE & FILTER context control  
- Time intelligence functions  
- Segmentation-based calculations  
- Median & iterator functions  

## 💼 Business Value Delivered

This dashboard enables financial decision-makers to:

- 📉 Monitor default risk in real time  
- 💰 Track loan portfolio exposure  
- 👤 Identify high-risk borrower segments  
- 📊 Analyze credit score impact on defaults  
- 📈 Monitor YoY growth vs risk movement  

The solution supports data-driven credit policy optimization and proactive risk management.

---

## 🚀 Future Improvements

- Integration with SQL or cloud data warehouse  
- Predictive default modeling using Machine Learning  
- Risk scoring automation  
- Role-Level Security (RLS) implementation  
- Real-time refresh integration  

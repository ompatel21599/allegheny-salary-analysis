## 📌 Project Overview

This project performs a comprehensive **Business Intelligence & Machine Learning analysis** on the **Allegheny County Employee Salaries dataset (December 2019)** sourced from the US Government Open Data portal. The goal is to uncover salary trends, gender pay gaps, departmental pay distribution, and build predictive models for annual salary estimation.

> 📍 *Academic Project — Business Intelligence & Machine Learning*
> 👤 *Om BharatKumar Patel*
> 📂 *Data Source: [data.gov — Allegheny County Employee Salaries](https://catalog.data.gov/dataset/allegheny-county-employee-salaries)*

---

## 🎯 Key Questions Answered

- Which job titles have the highest gross pay? *(Top 10)*
- Does ethnicity have a direct correlation to overtime pay?
- Is there a gender pay gap in annual salary and overtime?
- Which departments pay employees the most and least? *(Top 3)*
- What is the ratio of Active vs Terminated employees by department?
- Can we predict an employee's salary based on experience, department, and gender?

---

## 🗂️ Repository Structure

```
📦 allegheny-salary-analysis/
├── 📓 B1G6.ipynb          # Python ML analysis (Linear, Multi-Linear, Random Forest, Logistic Regression)
├── 📊 B1G6.pbix           # Power BI Dashboard
├── 📑 B1G6.pptx           # Final Presentation (14 slides)
├── 📋 B1G6.xlsx           # Cleaned dataset (Excel)
└── 📄 README.md
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python (Jupyter Notebook)** | Data cleaning, EDA, ML models |
| **Power BI** | Interactive dashboards & KPIs |
| **Excel** | Cleaned dataset storage & exploration |
| **Pandas / NumPy** | Data manipulation & feature engineering |
| **Scikit-learn** | Machine Learning models |
| **Matplotlib / Seaborn** | Data visualization |
| **Statsmodels** | OLS Regression summary & statistics |

---

## ⚙️ Data Processing & Feature Engineering

Raw data was cleaned and transformed using **Pandas**:

- Handled null values — replaced blanks with `NaN`, removed columns with >20% missing values
- Converted `DATE_STARTED`, `ORIG_START`, `DATE_TERM` to datetime format
- **Engineered new features:**
  - `YEAR_EXPERIENCE` — calculated from `ORIG_START` to `DATE_TERM`
  - `Department_Code` — label encoded from department names
  - `SEX_Code` — encoded (Female = 0, Male = 1)
- Applied **High Correlation Filter** — dropped features with correlation > 0.9 to reduce multicollinearity

---

## 🤖 Machine Learning Models

### 1️⃣ Simple Linear Regression
- **Features:** Years of Experience
- **Target:** Annual Salary
- **Goal:** Understand how experience alone predicts salary

### 2️⃣ Multiple Linear Regression
- **Features:** Years of Experience, Department Code, Sex Code
- **Target:** Annual Salary
- Used both **Scikit-learn** and **Statsmodels OLS** for detailed statistical summary

### 3️⃣ Random Forest Regression ⭐ *(Best Model)*
- **Features:** Years of Experience, Department Code, Sex Code
- **Target:** Annual Salary
- Lowest RMSE among all regression models
- **Conclusion:** Random Forest outperformed Linear Regression with higher accuracy

### 4️⃣ Logistic Regression
- **Features:** Department Code, Years of Experience, Annual Salary
- **Target:** Sex Code (Gender classification)
- Evaluated using **Confusion Matrix**, **Classification Report**, and **ROC Curve**

---

## 📊 Key Findings & Insights

### 💰 Salary & Pay
- **Male employees earn more** than female employees in both annual salary and overtime pay
- The majority of departments reflect **male-dominated average experience and pay**
- **Top-paying job titles** are concentrated in law enforcement and healthcare roles

### 🏛️ Department Analysis
- **Top 3 highest-paying departments** identified via Power BI dashboard
- Some departments have significantly higher **overtime pay** linked to specific ethnic groups

### 👥 Gender Insights
- Gender roles are evident in department distribution
- Logistic regression confirmed that **department and experience are predictors of gender role assignments** in certain job categories

### 📋 Employment Status
- Dataset includes both **Active and Terminated** employees
- Pay status ratio analyzed across departments

---

## 📈 Power BI Dashboard Highlights

- Top 10 job titles by Gross Pay
- Gender pay comparison (Annual Salary & Overtime)
- Department-wise pay distribution (Top & Bottom 3)
- Ethnicity vs Overtime correlation
- Average experience by gender per department
- Active vs Terminated employee ratio

---

## 🚀 How to Run the Python Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/allegheny-salary-analysis.git
   ```

2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels openpyxl
   ```

3. Open the notebook:
   ```bash
   jupyter notebook B1G6.ipynb
   ```

4. Place `datasetz.csv` (raw dataset) and `B1G6.xlsx` (cleaned dataset) in the same folder and run all cells.

> 📊 Open `B1G6.pbix` in **Microsoft Power BI Desktop** to explore the interactive dashboard.

---

## 📋 Project Workflow

`Data Collection` → `Data Cleaning` → `Feature Engineering` → `Dimension Reduction` → `ML Modeling` → `Visualization` → `Dashboard`

<img width="1302" height="732" alt="Dashboard" src="https://github.com/user-attachments/assets/9197ee55-68c8-467a-9507-1c9e2fd3f2a9" />

---

## 📬 Contact

**Om BharatKumar Patel**

> ⭐ *If you found this project helpful, consider giving it a star!*

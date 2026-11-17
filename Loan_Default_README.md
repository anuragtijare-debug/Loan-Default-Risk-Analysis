# Loan Default Risk Analysis

![Power BI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811) ![DAX](https://img.shields.io/badge/DAX-Measures-blue) ![SQL](https://img.shields.io/badge/SQL-Analysis-lightgrey) ![Python](https://img.shields.io/badge/Python-Analysis-yellow) ![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A Power BI portfolio project analyzing loan default risk, borrower profiles, credit behavior, financial performance, and portfolio health.

The project uses borrower-level and loan-level data to identify which borrower segments carry the highest default risk and to turn those patterns into practical lending recommendations. <ADD: number of loan records and the period the data covers>

> Replace every `<ADD: ...>` placeholder in this file with your own value before uploading. They mark numbers and file names that were not in the original README.

## 📑 Table of Contents

- [About This Project](#about-this-project)
- [Problem Statement](#problem-statement)
- [Business Questions](#business-questions)
- [Dataset Overview](#dataset-overview)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
  - [1. Data Preparation](#1-data-preparation)
  - [2. Risk Segmentation](#2-risk-segmentation)
  - [3. KPI Calculation](#3-kpi-calculation)
  - [4. Power BI Dashboard](#4-power-bi-dashboard)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Technical Specifications](#technical-specifications)
- [How to Review the Project](#how-to-review-the-project)
- [Limitations](#limitations)
- [Author](#author)

## About This Project

This project analyzes loan default behavior using data preparation in Power Query and SQL/Python, and Power BI for interactive visualization.

The analysis focuses on default rates across employment type, loan purpose, age group, income group, DTI ratio and credit score, and on the overall health of the loan portfolio.

The project demonstrates:

- **Data preparation:** Reviewing the dataset, checking data types and cleaning it with Power Query.
- **Segmentation:** Building age, income, DTI and credit score groups and four risk categories.
- **KPI calculation:** Measuring default rate, loan amount, interest rate, credit score and a portfolio health score with DAX.
- **Power BI reporting:** Presenting risk, customer and financial views through a five-page dashboard.
- **Business interpretation:** Translating observed default patterns into lending recommendations while acknowledging data limitations.

## Problem Statement

Loan default is one of the most important challenges for banks, NBFCs and lending companies. A high default rate affects profitability, risk exposure and portfolio quality, and looking at the overall default rate alone does not show which borrowers drive it.

This project uses loan-level data to evaluate default patterns across borrower characteristics and to identify the segments where lending decisions can be improved.

The analysis is designed to answer the following business questions.

## Business Questions

1. **Overall Default Rate:** What is the overall default rate of the portfolio?
2. **Risky Segments:** Which borrower segments are the most risky?
3. **Income:** How does income affect default probability?
4. **Employment:** Which employment type has the highest default risk?
5. **DTI Ratio:** How does the debt-to-income ratio affect repayment behavior?
6. **Credit Score:** Which credit score groups contribute most to portfolio risk?
7. **Actions:** What actions can reduce future loan defaults?

## Dataset Overview

The project uses a borrower-level loan dataset. <ADD: source of the dataset and file name, for example `loan_default.csv`>

| Column | Description |
|---|---|
| Loan ID | Unique identifier for each loan |
| Age | Age of the borrower |
| Income | Annual income of the borrower |
| Loan Amount | Loan amount sanctioned to the borrower |
| Credit Score | Borrower credit score |
| Months Employed | Employment duration in months |
| Number of Credit Lines | Number of existing credit lines |
| Interest Rate | Interest rate charged on the loan |
| Loan Term | Loan repayment duration |
| DTI Ratio | Debt-to-income ratio |
| Education | Education level of the borrower |
| Employment Type | Borrower employment status |
| Marital Status | Marital status of the borrower |
| Has Mortgage | Mortgage status of the borrower |
| Has Dependents | Whether the borrower has dependents |
| Loan Purpose | Purpose of the loan |
| Has Co-Signer | Co-signer availability |
| Default | Target variable indicating loan default |

### Dataset Summary

| Attribute | Details |
|---|---|
| Loan records | <ADD: number of rows> |
| Columns | 18 |
| Analysis period | <ADD: from year – to year> |
| Source format | <ADD: CSV / Excel> |
| Target variable | `Default` |

## Project Structure

Adjust this tree to match the files in your repository.

```
Loan-Default-Risk-Analysis/
│
├── Dataset/
│   └── <ADD: loan_default.csv>
│
├── SQL/                              # remove if you have no SQL scripts
│   └── <ADD: sql_file_name.sql>
│
├── Python/                           # remove if you have no notebook
│   └── <ADD: analysis_notebook.ipynb>
│
├── Power BI/
│   ├── <ADD: Loan_Default_Dashboard.pbix>
│   └── <ADD: Loan_Default_Dashboard.pdf>
│
├── Screenshots/
│   ├── 01_Overview.png
│   ├── 02_Risk_Analysis.png
│   ├── 03_Customer_Analysis.png
│   ├── 04_Financial_Analysis.png
│   └── 05_Default_Prediction.png
│
└── README.md
```

## Methodology

### 1. Data Preparation

The data preparation process:

- Imported and reviewed the loan default dataset.
- Checked column names, data types and field meanings.
- Identified numerical and categorical variables.
- Cleaned and transformed the data using Power Query.
- Created calculated columns for segmentation (age group, income group, DTI group, interest rate group and credit score band).

### 2. Risk Segmentation

Borrowers were segmented into risk categories based on credit score and default behavior.

| Risk Category | Criteria |
|---|---|
| Low Risk | Credit score 700 and above |
| Medium Risk | Credit score 600–699 |
| High Risk | Credit score 500–599 |
| Critical Risk | Credit score below 500 |

Additional risk factors considered: low income, high DTI ratio, unemployment, no co-signer, young borrower age group and business loan purpose.

### 3. KPI Calculation

The project uses the following key performance indicators, built as DAX measures.

| KPI | Description |
|---|---|
| Total Loans | Total number of loans in the portfolio |
| Total Loan Amount | Total value of issued loans |
| Average Loan Amount | Average sanctioned loan amount |
| Default Rate | Percentage of loans that defaulted |
| Non-Default Rate | Percentage of performing loans |
| Average Interest Rate | Average interest rate across loans |
| Average Credit Score | Average borrower credit score |
| Average DTI Ratio | Average debt-to-income ratio |
| High-Risk Borrowers | Borrowers in the high-risk credit score range |
| Critical-Risk Borrowers | Borrowers with a very low credit score |
| Portfolio Health Score | Composite view of portfolio quality: <ADD: the formula or components you used> |

**Default Rate formula:** <ADD: your DAX measure, for example `DIVIDE(COUNTROWS(FILTER(Loans, Loans[Default] = 1)), COUNTROWS(Loans))`>

> **Important:** Default probability in this project means the observed default rate of a segment. It is not the output of a predictive model.

### 4. Power BI Dashboard

The dashboard contains five pages designed for different analytical perspectives.

**Page 1: Executive Overview**
A high-level summary of the loan portfolio through KPI cards for total loans, total loan amount, average loan amount, default rate, non-default rate, average interest rate, average credit score and portfolio health score.

**Page 2: Risk Analysis**
Analyzes default risk across borrower and loan characteristics: default rate by employment type, loan purpose, age group and DTI group, plus the high-risk and critical-risk borrower segments.

**Page 3: Customer Analysis**
Focuses on borrower profile and behavior: borrower count by age group, default rate by income group, distribution by education, and mortgage status, marital status, co-signer and dependents analysis.

**Page 4: Financial Analysis**
Analyzes loan amount, interest rate and portfolio value: average loan amount by education, total loan amount over years, total loans by interest rate group, default rate by income group, and the minimum and maximum loan amount and interest rate.

**Page 5: Default Probability**
Highlights the overall default probability, young and senior borrower risk, default rate by age, income and DTI group, and segment-wise risk analysis.

### Dashboard Screenshots

#### Executive Overview
![Executive Overview](Screenshots/01_Overview.png)

#### Risk Analysis
![Risk Analysis](Screenshots/02_Risk_Analysis.png)

#### Customer Analysis
![Customer Analysis](Screenshots/03_Customer_Analysis.png)

#### Financial Analysis
![Financial Analysis](Screenshots/04_Financial_Analysis.png)

#### Default Probability
![Default Probability](Screenshots/05_Default_Prediction.png)

## Key Findings

### 1. Age
- Borrowers aged 18–25 show the highest default risk (<ADD: default rate %>).
- Borrowers aged 56–69 show the lowest default risk (<ADD: default rate %>).
- **Interpretation:** Default risk falls as borrower age rises, so younger applicants need closer underwriting.

### 2. Income
- Borrowers with income below $30K have the highest default probability (<ADD: default rate %>).
- **Interpretation:** Low income is one of the strongest signals of default risk in this dataset.

### 3. Employment and DTI
- Unemployed borrowers show higher default risk than full-time borrowers.
- A higher DTI ratio increases default probability.
- **Interpretation:** Repayment capacity, shown by employment status and existing debt load, affects default behavior.

### 4. Co-Signer and Loan Purpose
- Borrowers without a co-signer show higher risk exposure.
- Home loans show comparatively lower default risk.
- **Interpretation:** Loans with shared responsibility or a secured purpose perform better.

### 5. Credit Score
- Borrowers with low credit scores represent the most critical risk segment (<ADD: number of critical-risk borrowers and their default rate>).
- **Interpretation:** Credit score is the clearest way to separate low-risk from high-risk borrowers.

### Overall KPI Summary

| Metric | Result |
|---|---|
| Total Loans | <ADD> |
| Total Loan Amount | <ADD> |
| Average Loan Amount | <ADD> |
| Default Rate | <ADD> |
| Average Interest Rate | <ADD> |
| Average Credit Score | <ADD> |
| Portfolio Health Score | <ADD> |
| Analysis Period | <ADD> |

## Business Recommendations

1. **Strengthen underwriting for young borrowers:** Borrowers aged 18–25 show high default probability. Apply additional income and employment verification.
2. **Monitor low-income borrowers:** Borrowers earning below $30K have the highest default risk. Review loan limits and approval thresholds for this group.
3. **Encourage co-signers for high-risk profiles:** Borrowers without co-signers show higher risk exposure, and a co-signer can reduce repayment risk.
4. **Control high DTI exposure:** Monitor borrowers with high debt-to-income ratios closely and use DTI-based approval rules to improve portfolio quality.
5. **Reduce exposure to critical-risk borrowers:** Borrowers with credit scores below 500 need stricter risk checks and early-warning indicators.
6. **Expand low-risk segments:** Senior borrowers and borrowers with high credit scores show better repayment behavior and can be targeted for safer portfolio growth.

These recommendations reflect patterns observed in the available dataset and are not a substitute for a full credit risk model.

## Technical Specifications

| Component | Technology / Approach |
|---|---|
| Data input | <ADD: CSV / Excel> |
| Data preparation | Power Query, <ADD: SQL / Python if used> |
| Segmentation | Calculated columns |
| Dashboard | Microsoft Power BI |
| Measures | DAX |
| Output formats | PBIX, PDF, PNG, Markdown |
| Analysis type | Descriptive and exploratory risk analysis |

## How to Review the Project

### 1. Review the Source Data
Open the file in `Dataset/` to inspect the borrower and loan fields.

### 2. Review the Preparation Steps
<ADD: if you have SQL or Python files, name them here and say what each one does>

### 3. Open the Power BI Dashboard
Open the `.pbix` file in `Power BI/` with Microsoft Power BI Desktop. If required, update the data source path to your local copy of the dataset, then refresh the data.

### 4. Review the Screenshots
The `Screenshots/` folder has an image of each of the five dashboard pages.

## Limitations

- **Observed rates, not predictions:** The "Default Probability" page shows observed default rates by segment. No predictive model was built.
- **Correlation, not causation:** Patterns such as higher default among young or low-income borrowers describe the dataset and do not prove cause.
- **Defined segmentation:** The credit score bands, and the portfolio health score, are project-defined and are not regulatory standards.
- **Limited loan information:** Collateral, repayment history, loan stage and economic conditions are not in the dataset.
- **Interpretation:** Findings describe patterns in the supplied dataset and should not be generalized to all lenders.
- **Data provenance:** <ADD: where the data came from and whether it is real or synthetic>

## Author

**Anurag Tijare**

Data Analyst / BI Developer

GitHub: [@your-username](https://github.com/your-username)
LinkedIn: [in/your-profile](https://www.linkedin.com/in/your-profile)

**Loan Default Risk Analysis**
Power BI • DAX • SQL • Python • Credit Risk Analytics

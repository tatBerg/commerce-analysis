# E-commerce Sales & Customer Analytics

End-to-end analysis of transactional e-commerce data: from raw-data validation and cleaning to SQL analysis, customer segmentation, business insights, and an executive dashboard.

## Project Objective

The purpose of this project is to simulate a real-world analytics engagement with an e-commerce business.

The dataset is treated as a raw client data export rather than a prepared educational dataset.

The project follows the complete analytical workflow:

**Raw Data → Data Audit → Data Cleaning → Data Modeling → SQL Analysis → EDA → Customer & Product Analytics → Visualization → Business Insights → Recommendations**

The main objective is not only to calculate metrics, but to determine:

- what is happening in the business;
- how reliable the available data is;
- what drives revenue;
- how sales change over time;
- which products contribute most to business performance;
- how customer behavior differs;
- how concentrated revenue is across customers and products;
- how returns affect business performance;
- which patterns require further investigation;
- which business questions cannot be answered with the available data.

---

## Business Context

An e-commerce company has accumulated transactional sales data but does not have a structured analytics system.

Management wants to understand overall business performance and identify patterns in sales, customers, products, geography, and returns.

The initial business request is intentionally broad:

> Analyze the available transaction data and determine what management should know about the current state of the business.

Part of the analyst's responsibility is therefore to translate a broad business request into measurable analytical questions and clearly state the limitations of the available data.

---

## Dataset

Source: **[E-Commerce Data on Kaggle](https://www.kaggle.com/datasets/carrie1/ecommerce-data)** (`carrie1/ecommerce-data`).

Download the dataset from the source above and place `data.csv` in `data/raw/data.csv`.
The raw CSV is excluded from Git and must be downloaded separately after cloning the repository.

The dataset contains transactional records from an online retail business.

Raw data is stored separately and must remain unchanged throughout the project.

Expected source fields include:

- `InvoiceNo`
- `StockCode`
- `Description`
- `Quantity`
- `InvoiceDate`
- `UnitPrice`
- `CustomerID`
- `Country`

Field definitions, table grain, data types, quality issues, and analytical limitations will be established during the Data Audit stage rather than assumed in advance.

---

## Core Business Questions

The analysis is designed to investigate several areas of the business.

### Business Performance

- What is the overall scale of the business?
- How should revenue and completed sales be defined?
- How many orders, customers, and product units are represented?
- What is the typical order value?
- How does business performance change over time?
- Are observed changes driven by order volume, order value, or both?

### Sales Dynamics

- How does revenue change by month, week, day, and other relevant periods?
- Are there signs of seasonality?
- Are there unusual sales spikes or declines?
- Are all periods in the dataset directly comparable?
- What explains unusually strong or weak periods?

### Product Performance

- Which products contribute most to revenue?
- Which products sell most frequently?
- Which products generate high unit volume but relatively low revenue?
- Which products generate high revenue despite lower sales frequency?
- How concentrated is revenue across the assortment?
- Is there evidence of a long-tail product structure?
- Which products are associated with unusual return behavior?

### Customer Analytics

- How many identifiable customers are present?
- How much revenue does a typical customer generate?
- How frequently do customers purchase?
- How concentrated is revenue among customers?
- How do new and returning customers differ?
- Can meaningful customer segments be created?
- What limitations affect customer-level analysis?

### Geographic Performance

- Which markets generate the largest sales volume?
- How do countries differ in order volume, customer count, and order value?
- Is the business heavily dependent on one geographic market?
- How do secondary markets compare when the dominant market is excluded?

### Returns

- How significant are returns or cancellations?
- How do they change over time?
- Which products and customers are associated with them?
- Can returned transactions reliably be linked to original purchases?
- How should returns affect revenue and customer metrics?

### Business Concentration

- How concentrated is revenue across customers?
- How concentrated is revenue across products?
- Does the actual distribution resemble a Pareto-type structure?
- How exposed is the business to a relatively small number of customers or products?

---

## Data Quality Questions

Before business analysis begins, the dataset will be audited for:

- missing values;
- duplicated records;
- incorrect data types;
- invalid dates;
- zero values;
- negative values;
- suspicious transaction identifiers;
- unusual quantities;
- unusual prices;
- extreme orders;
- inconsistent product information;
- incomplete reporting periods;
- potential cancellation or return records.

No record will be removed solely because it appears unusual.

Every cleaning decision must be documented and justified.

---

## Analytical Scope

The project contains the following analytical components:

1. Data understanding
2. Data quality audit
3. Data cleaning
4. Feature engineering
5. KPI definition
6. Revenue analysis
7. Order analysis
8. Product analysis
9. ABC analysis
10. Geographic analysis
11. Customer analysis
12. New vs. returning customer analysis
13. RFM segmentation
14. Returns analysis
15. Anomaly investigation
16. Pareto analysis
17. Relationship analysis
18. Cohort analysis where supported by the data
19. SQL business analysis
20. Dashboard development
21. Executive summary
22. Business recommendations
23. Analysis limitations
24. Additional data requirements

---

## Technology Stack

### Python

Used for:

- data inspection;
- data-quality analysis;
- cleaning;
- feature engineering;
- exploratory analysis;
- validation;
- advanced customer analysis.

Primary libraries:

- `pandas`
- `numpy`
- `matplotlib`

Additional libraries will only be added where analytically justified.

### SQL

Used to reproduce and solve business questions using relational analytical logic.

Planned concepts include:

- filtering;
- aggregation;
- grouping;
- conditional logic;
- date operations;
- CTEs;
- subqueries;
- window functions;
- ranking;
- period-over-period calculations.

### Jupyter Notebook

Used for interactive investigation and documented analytical reasoning.

### Visualization / BI

Used to transform analytical results into a management-facing dashboard.

The dashboard should prioritize decision-relevant information rather than displaying every calculated metric.

### Git / GitHub

Used for project version control and portfolio presentation.

---

## Project Structure

```text
ecommerce-analysis/
│
├── data/
│   ├── raw/
│   │   └── data.csv
│   │
│   └── processed/
│
├── notebooks/
│   ├── 01_data_audit.ipynb
│   ├── 02_data_cleaning.ipynb
│   └── 03_eda.ipynb
│
├── sql/
│   └── analysis.sql
│
├── dashboard/
│
├── reports/
│
├── README.md
├── TECHNICAL_PLAN.md
└── requirements.txt
```

---

## Data Management Rules

### Raw Data

Files inside `data/raw/` are treated as immutable source data.

They must never be manually edited or overwritten.

### Processed Data

Cleaned or transformed datasets are stored separately in:

`data/processed/`

Every transformation from raw to processed data must be reproducible through code.

### Reproducibility

The final project should be reproducible from the original source data without manually editing spreadsheet cells.

---

## Analytical Principles

### Do not clean before understanding

Potentially problematic observations must first be investigated.

### Do not confuse unusual with incorrect

Outliers can represent:

- genuine large orders;
- wholesale customers;
- returns;
- operational events;
- data-entry errors.

The reason must be investigated before exclusion.

### Separate facts from hypotheses

An observed relationship does not automatically establish causality.

Findings should distinguish between:

- observed evidence;
- interpretation;
- hypothesis;
- recommendation.

### Define metrics explicitly

Metrics such as:

- revenue;
- order;
- customer;
- return;
- average order value;
- repeat customer;

must have documented definitions before being used.

### State limitations

If the available data cannot answer a business question reliably, this must be stated rather than replaced with an unsupported assumption.

---

## Expected Deliverables

The completed project should contain:

- reproducible raw-to-clean data pipeline;
- documented data-quality audit;
- cleaning policy;
- cleaned analytical dataset;
- SQL analysis;
- KPI framework;
- exploratory analysis;
- customer analysis;
- product analysis;
- geographic analysis;
- returns analysis;
- RFM segmentation;
- Pareto analysis;
- cohort analysis if methodologically valid;
- management dashboard;
- executive summary;
- business recommendations;
- data limitations;
- list of additional data required for deeper analysis.

---

## Final Reporting Framework

Major findings should follow the structure:

**Evidence → Insight → Business Implication → Recommendation**

Recommendations must be traceable to analytical evidence.

The final report should also distinguish between:

**Known → Likely → Unknown → Additional data required**

---

## Project Status

**Current stage:** Data Understanding & Data Quality Audit

No cleaning or business conclusions should be performed until the initial audit is complete.

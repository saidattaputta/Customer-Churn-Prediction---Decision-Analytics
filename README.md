# Customer Churn Prediction — Business & Statistical Analysis

A notebook-led customer churn case study using the IBM Telco Customer Churn dataset. This repository focuses on understanding the business decision behind churn, examining the dataset, exploring churn patterns, and applying statistical hypothesis testing.

> This is a separate project from [Customer-Churn-Prediction-Retention-Analytics](https://github.com/saidattaputta/Customer-Churn-Prediction-Retention-Analytics), which contains a deployed machine-learning application and API. This repository is the earlier business-analysis and statistics workstream.

## Business Objective

Help a customer-retention team understand which customer groups show higher churn and what evidence can inform prioritization of retention outreach.

The intended decision is to identify which existing customers or segments should be investigated first, rather than distributing retention resources uniformly.

## Project Workflow

| Notebook | Focus |
|---|---|
| `01_business_problem.ipynb` | Define customer churn, business impact, decision owner, and the cost of missed churn |
| `02_data_understanding.ipynb` | Load the Telco dataset, inspect records and feature types, and document data-quality observations |
| `03_deep_eda.ipynb` | Explore churn patterns across tenure, contract type, charges, and service attributes |
| `04_applied_statistics.ipynb` | Formulate and test a hypothesis comparing monthly charges for churned and retained customers |

## Dataset

The repository includes the IBM Telco Customer Churn dataset:

- 7,043 customer records
- Binary target: `Churn` (Yes/No)
- Demographic, contract, service, tenure, and billing variables

## Results and Evidence

The following descriptive figures were calculated from the committed raw Telco CSV during this documentation review. They are not outputs of a newly executed notebook or statistical test.

### Dataset-level churn distribution

| Churn outcome | Customers | Share |
|---|---:|---:|
| No churn | 5,174 | 73.46% |
| Churn | 1,869 | 26.54% |
| **Total** | **7,043** | **100.00%** |

### Monthly charges by churn outcome

The raw dataset contains the following descriptive MonthlyCharges statistics:

| Group | Customers | Mean monthly charges | Median monthly charges | Minimum | Maximum |
|---|---:|---:|---:|---:|---:|
| Churn = Yes | 1,869 | 74.44 | 79.65 | 18.85 | 118.35 |
| Churn = No | 5,174 | 61.27 | 64.43 | 18.25 | 118.75 |

The churned group has a higher mean monthly charge by **13.17** in the raw dataset. This is a descriptive difference only; it does not establish statistical significance or causation.

### Statistical testing status

The saved 04_applied_statistics.ipynb notebook loads the cleaned dataset, selects MonthlyCharges and Churn, and separates monthly charges into churned and non-churned groups. The committed notebook outputs show the data split and sample rows, but do not contain a saved t-test statistic, p-value, confidence interval, or effect size. Therefore this README does not claim a completed significant hypothesis-test result.

The notebook's stated comparison can be completed by reporting the test statistic, p-value, confidence interval, effect size, and the assumptions used.

## Tools

- Python
- pandas and NumPy
- Matplotlib and Seaborn
- SciPy / statistical testing concepts
- Jupyter Notebook

## Repository Contents

```text
.
├── 01_business_problem.ipynb
├── 02_data_understanding.ipynb
├── 03_deep_eda.ipynb
├── 04_applied_statistics.ipynb
└── data/
    ├── clean_data.csv
    └── raw/
        └── WA_Fn-UseC_-Telco-Customer-Churn.csv
```

## Run Locally

```bash
git clone https://github.com/saidattaputta/Customer-Churn-Prediction---Decision-Analytics.git
cd Customer-Churn-Prediction---Decision-Analytics
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
pip install pandas numpy matplotlib seaborn scipy jupyter
jupyter notebook
```

Open and run the notebooks in numeric order. Some notebook cells use paths relative to the repository root; run Jupyter from that directory.

## Scope and Limitations

- This repository documents exploratory and statistical analysis; it is not the deployed prediction service.
- Statistical association does not imply causation.
- The notebook workflow should be rerun from the first notebook to regenerate derived data consistently.
- Review the statistical test assumptions and report the test statistic, p-value, confidence interval, and effect size when presenting conclusions.


---

**Sai Datta Putta**

[LinkedIn](https://www.linkedin.com/in/sai-datta-putta/)

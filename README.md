# UK Mortgage Risk Research

An empirical analysis of UK mortgage arrears and possession activity using official quarterly data from **2011 Q1 to 2024 Q4**.

## Project overview

This project examines mortgage stress as a staged process:

> **Mortgage-market conditions → serious arrears → possession activity**

The final analytical dataset contains **56 quarterly observations and 23 variables**. The analysis is conducted in Python and combines descriptive statistics, correlation analysis, visualisation, and lagged regression models with Newey–West heteroskedasticity and autocorrelation consistent standard errors.

The findings are interpreted as **associations rather than causal effects**.

## Research questions

1. How did UK mortgage arrears and possession activity change between 2011 and 2024?
2. Which mortgage-market conditions are associated with later serious arrears?
3. Are serious arrears associated with subsequent possession activity?

## Data sources

The repository uses official data from:

- Bank of England Mortgage Lenders and Administrators Statistics
- Financial Conduct Authority mortgage product sales data
- Office for National Statistics UK House Price Index

Original source files and the source manifest are stored in:

```text
data_raw/official_sources/
```

## Main variables

The analysis includes:

- serious arrears rate
- total arrears rate
- new possessions
- stock of possessions
- average mortgage interest rate
- fixed-rate mortgage share
- high loan-to-value lending
- impaired credit-history lending
- gross mortgage advances
- new mortgage commitments
- UK house-price growth

## Methods

The analytical workflow includes:

- data cleaning and quarterly alignment
- descriptive statistics
- Pearson correlation analysis
- trend visualisation
- one-quarter-lagged explanatory variables
- ordinary least squares regression
- Newey–West HAC standard errors
- log transformation of new possessions in the second model

### Model 1

The first model examines associations between lagged mortgage-market conditions and the serious arrears rate.

### Model 2

The second model examines whether lagged serious arrears and other market indicators are associated with later new possessions.

## Headline findings

Across the 2011 Q1–2024 Q4 sample:

- serious arrears averaged approximately **1.03%**
- total arrears averaged approximately **1.43%**
- new possessions averaged approximately **3,452 per quarter**
- higher lagged mortgage interest rates were positively associated with serious arrears
- a higher fixed-rate share and stronger gross lending activity were negatively associated with serious arrears
- lagged serious arrears were strongly positively associated with later possessions
- high loan-to-value lending was positively associated with possessions in the second model

These results should be interpreted cautiously because the dataset is an aggregate time series and several variables share long-run trends.

## Repository structure

```text
UK-mortgage-risk-research/
├── data_raw/
│   └── official_sources/
├── data_clean/
├── outputs/
│   ├── figures/
│   └── tables/
├── paper/
├── python/
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## Main files

- `data_clean/uk_mortgage_risk_final_research_dataset.csv` — final analysis dataset
- `python/UK_mortgage.ipynb` — Python data preparation and statistical analysis
- `outputs/figures/` — exported visualisations
- `outputs/tables/` — descriptive, correlation, and regression outputs
- `paper/UK_Mortgage_Risk_Research_Paper.docx` — research paper

## Running the analysis

Clone the repository:

```bash
git clone https://github.com/Linpaws7/UK-mortgage-risk-research.git
cd UK-mortgage-risk-research
```

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook python/UK_mortgage.ipynb
```

## Reproducibility note

The analysis is based on the files included in this repository. The notebook should be run from the repository root.

Before using the project on another computer, confirm that the notebook uses repository-relative paths rather than machine-specific local paths.

## Limitations

- The dataset contains only 56 quarterly observations.
- The analysis uses aggregate UK-level data rather than household-level or lender-level records.
- The regressions are associational and do not establish causality.
- Common long-run trends may influence some estimated relationships.
- Mortgage possessions were affected by lender forbearance, court disruption, and policy intervention during the COVID-19 period.
- The results should therefore be treated as exploratory evidence.

## Paper

The paper presents the full research design, results, interpretation, and limitations:

Read the research paper - paper/UK_Mortgage_Risk_Research_Paper.docx

## Licence

The repository code is released under the MIT Licence.

The original datasets remain subject to the terms and licences of the Bank of England, Financial Conduct Authority, and Office for National Statistics.

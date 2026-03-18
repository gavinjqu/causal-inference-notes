# Causal Inference Methods in Economics

**Author**: Gavin Qu

Applied causal inference techniques from an Economics Masters course (EC963), implemented in Python. Each notebook replicates a classic empirical study using modern econometric methods.

## Notebooks

| Notebook | Paper | Methods |
|----------|-------|---------|
| [Lab 1: Randomized Experiments](notebooks/lab1_randomized_experiments.ipynb) | Chattopadhyay & Duflo (2004); Gerber, Green & Larimer (2008) | Difference in means, t-tests, OLS, balance checks, subgroup analysis |
| [Lab 2: Matching](notebooks/lab2_matching.ipynb) | Eggers & Hainmueller (2009); Dehejia & Wahba (1999) | Exact matching, nearest-neighbor matching, Mahalanobis distance, ATT estimation |
| [Lab 3: Difference-in-Differences](notebooks/lab3_difference_in_differences.ipynb) | Dinas et al. (2019); Card & Krueger (1994) | Manual DiD, interaction regression, parallel trends, two-way fixed effects |
| [Lab 4: Instrumental Variables](notebooks/lab4_instrumental_variables.ipynb) | Sesame Street experiment; Acemoglu, Johnson & Robinson (2001) | ITT, LATE, Wald estimator, first-stage F-test, 2SLS |
| [Lab 5: Regression Discontinuity](notebooks/lab5_regression_discontinuity.ipynb) | Meyersson (2014) | Sharp RDD, bandwidth selection, local linear regression, LOESS |
| [Midterm: COVID-19 Curfew Evaluation](notebooks/midterm_covid_curfew_evaluation.ipynb) | France's 2021 reinforced curfew policy | DiD, cross-sectional comparison, before-after analysis, RDD discussion |

## Methods Overview

- **Randomized Experiments**: The gold standard for causal inference. Random assignment ensures treatment and control groups are comparable in expectation.
- **Matching**: Constructs a comparison group by pairing treated units with similar untreated units based on observed covariates, under the Conditional Independence Assumption.
- **Difference-in-Differences**: Compares changes over time between treated and control groups, identifying causal effects under the parallel trends assumption.
- **Instrumental Variables**: Addresses endogeneity by using an exogenous source of variation (instrument) that affects the outcome only through the treatment.
- **Regression Discontinuity**: Exploits a known threshold in a continuous assignment variable, comparing units just above and below the cutoff.

## Setup

This project uses [uv](https://docs.astral.sh/uv/) for dependency management.

```bash
# Install dependencies and create virtual environment
uv sync

# Run Jupyter notebooks
uv run jupyter notebook

# Render Quarto documents
cd quarto && quarto render
```

## License

MIT

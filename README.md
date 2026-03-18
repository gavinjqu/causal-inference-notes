# Causal Inference Methods in Economics

**Author**: Gavin Qu

Applied causal inference techniques from an Economics Masters course (EC963), implemented in Python. Each lab replicates a classic empirical study using modern econometric methods.

## Labs

| Lab | Paper | Methods |
|-----|-------|---------|
| Lab 1: Randomized Experiments | Chattopadhyay & Duflo (2004); Gerber, Green & Larimer (2008) | Difference in means, t-tests, OLS, balance checks, subgroup analysis |
| Lab 2: Matching | Eggers & Hainmueller (2009); Dehejia & Wahba (1999) | Exact matching, nearest-neighbor matching, Mahalanobis distance, ATT estimation |
| Lab 3: Difference-in-Differences | Dinas et al. (2019); Card & Krueger (1994) | Manual DiD, interaction regression, parallel trends, two-way fixed effects |
| Lab 4: Instrumental Variables | Sesame Street experiment; Acemoglu, Johnson & Robinson (2001) | ITT, LATE, Wald estimator, first-stage F-test, 2SLS |
| Lab 5: Regression Discontinuity | Meyersson (2014) | Sharp RDD, bandwidth selection, local linear regression, LOESS |
| Midterm: COVID-19 Curfew Evaluation | France's 2021 reinforced curfew policy | DiD, cross-sectional comparison, before-after analysis, RDD discussion |

Each lab is available in two formats:

- **Jupyter notebooks** in [`notebooks/`](notebooks/) — interactive `.ipynb` files, good for step-by-step exploration
- **Quarto documents** in [`quarto/`](quarto/) — plain-text `.qmd` files that render to a navigable HTML website with table of contents, cross-references, and cleaner diffs in version control

## Getting Started

### Prerequisites

- **Python 3.11+**
- [**uv**](https://docs.astral.sh/uv/) — fast Python package manager (replaces pip/venv)
- [**Quarto**](https://quarto.org/docs/get-started/) — only needed if you want to render the `.qmd` files

### Install dependencies

```bash
uv sync
```

This creates a `.venv/` virtual environment and installs all required packages (numpy, pandas, statsmodels, linearmodels, etc.). No need to manually create a venv or run `pip install`.

### Run the Jupyter notebooks

```bash
uv run jupyter notebook
```

Then open any notebook in `notebooks/` from the browser.

### Render the Quarto site

```bash
cd quarto
uv run quarto preview   # live preview with hot-reload
uv run quarto render     # build static HTML to quarto/_output/
```

The rendered site includes a navbar, table of contents, and all code output and figures.

## Project Structure

```
├── pyproject.toml       # Python dependencies (managed by uv)
├── data/                # Datasets (.csv, .dta) organized by lab
├── notebooks/           # Jupyter notebooks (.ipynb)
└── quarto/              # Quarto documents (.qmd)
    ├── _quarto.yml      # Site configuration (theme, navigation)
    ├── index.qmd        # Landing page
    └── *.qmd            # One file per lab
```

## Methods Overview

- **Randomized Experiments**: The gold standard for causal inference. Random assignment ensures treatment and control groups are comparable in expectation.
- **Matching**: Constructs a comparison group by pairing treated units with similar untreated units based on observed covariates, under the Conditional Independence Assumption.
- **Difference-in-Differences**: Compares changes over time between treated and control groups, identifying causal effects under the parallel trends assumption.
- **Instrumental Variables**: Addresses endogeneity by using an exogenous source of variation (instrument) that affects the outcome only through the treatment.
- **Regression Discontinuity**: Exploits a known threshold in a continuous assignment variable, comparing units just above and below the cutoff.

## License

MIT

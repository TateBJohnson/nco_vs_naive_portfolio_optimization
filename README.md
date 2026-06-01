# NCO vs. Naive Portfolio Optimization Under Realistic Constraints

Implements a constrained copula-based portfolio optimization framework comparing Nested
Clustered Optimization (NCO) against naive equal-weighting across 19 risky assets.
Fits Student-t marginals and a Gaussian copula on a 2000-day training window, then
evaluates three competing portfolios on a 500-day held-out test set under long-only,
no-borrowing constraints and two CRRA utility regimes.

## Structure

```
nco_vs_naive_portfolio_optimization/
├── nco_portfolio_analysis.ipynb   # main analysis notebook
├── data/
│   ├── vmls_portfolio_returns.csv # daily returns, 19 risky assets + risk-free
│   └── copula_model.pkl           # pre-fitted Student-t marginals and Gaussian copula
└── .gitignore
```

## What the Notebook Covers

- **Part (a)** - Constrained CRRA optimizer, copula simulation helpers, and portfolio
  construction for NCO, all-at-once, and 1/N under gamma = 1 and gamma = 3
- **Part (b)** - Out-of-sample horse race: wealth paths, log-growth distributions,
  and summary statistics across all three portfolios and both utility regimes
- **Part (c)** - Why correlation distance D_ij = sqrt(0.5 * (1 - rho_ij))
  is used instead of raw correlations for clustering
- **Part (d)** - Synthesis: NCO vs all-at-once under constraints, risk-free cash
  shares across regimes, and naive equal-weighting as a benchmark

## Dependencies

```
numpy, pandas, scipy, matplotlib, seaborn
```

## Running

Open `nco_portfolio_analysis.ipynb` and run all cells top to bottom.
Both data files must be present in `data/`.

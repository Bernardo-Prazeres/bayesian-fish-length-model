# Bayesian Modelling of Fish Length

Academic assignment for Bayesian Methods, NOVA FCT, 2025-2026.

## Objective

Model the length (*Y*) of a fish species using biological and environmental covariates — age, gender, and percentage of rocky terrain in the habitat (relief) — under the Bayesian paradigm, with MCMC fitting (JAGS/R2jags).

Sample: *n* = 45 fish.

## Models compared

| Model | Description | DIC |
|---|---|---|
| **Model 1** | Simple Normal, no covariates (global μ and τ only) | 5.42 |
| **Model 2** | Multiple linear regression (age + gender + relief) | **-1.71** ✅ |
| **Model 3** | Individual random effect per fish | 10.49 |

## Main result

**Model 2 (multiple linear regression)** was selected as the best model, combining:
- Lowest DIC (best fit/complexity trade-off)
- Best predictive performance (MAE = 0.096, scaled MAE = 0.327)
- Direct biological interpretability: **age** has a significant positive effect on length; **gender** shows that males tend to be shorter than females (sexual dimorphism); **relief** is not relevant
- Lower overfitting risk than Model 3 (which estimates 45 extra parameters for 45 observations)

All models converged adequately (R̂ ≤ 1.0015 across all parameters, high effective sample sizes).

## Structure of the work

1. Exploratory data analysis (distributions, correlations, relationships by gender)
2. Specification and fitting of each model (BUGS/JAGS)
3. Convergence diagnostics (trace plots, autocorrelation, R̂)
4. Posterior predictive checks
5. Final comparison and model selection

## Authors

Bernardo Prazeres, María Teresa Viciosa, Miguel Pimentel — NOVA FCT, supervised by Prof. Isabel Natário

## Files

- `Enunciado5.Rmd` — R Markdown source code (full analysis, JAGS models, plots)
- `Enunciado5.pdf` — final report generated from the Rmd

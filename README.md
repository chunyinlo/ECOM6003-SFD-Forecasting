# ECOM6003 Project 2 – Univariate SFD Forecasting

This repository contains the univariate forecasting work for ECOM6003 Project 2: Forecasting State Final Demand (SFD).

## Contents

- `ECOM6003 Chun Yin LoUnivariate Forecasting GitHub.ipynb` – main analysis notebook
- `SFD_clean.xlsx` – quarterly SFD data for NSW, VIC, QLD, SA, WA and TAS
- `outputs` – selected model results, forecast accuracy tables and figures

## Method

Two univariate forecasting approaches are compared for each state:

1. Random Walk with Drift
2. ARIMA

The data are split into:

- Training sample: 1985 Q3 to 2025 Q2
- Test sample: 2025 Q3 to 2026 Q2
- Full sample: 1985 Q3 to 2026 Q2
- Operational forecast horizon: 2026 Q3 to 2027 Q2

ARIMA models are estimated using first differencing (`d = 1`). Candidate specifications are compared using AIC and BIC, with Ljung–Box residual diagnostics used as an additional model check.

Forecast performance is evaluated using RMSE and MAE over the four-quarter holdout period.

## Main univariate results

The Random Walk with Drift performs better for NSW, VIC and SA. For QLD, the Random Walk with Drift and ARIMA(0,1,0) with drift produce almost identical results.

ARIMA performs better for WA and TAS:

- WA: ARIMA(3,1,0) with drift
- TAS: ARIMA(0,1,1) with drift

The univariate results are later compared with the multivariate VAR/VECM results before the final forecasting model is selected for each state.

## Notes

The forecasts shown here are based on the univariate models only. The final forecasts will be selected after comparing these results with the VAR/VECM models.

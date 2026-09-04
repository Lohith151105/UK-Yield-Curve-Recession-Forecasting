# Can the UK Yield Curve Predict Recessions?

> **Project status:** Work in progress

## Overview

This project investigates whether the slope of the UK government yield curve can forecast UK recessions. It combines UK government-bond yield data with quarterly real GDP data and estimates recession probabilities at different forecast horizons.

The project is designed as a forecasting exercise rather than a causal analysis. It asks whether the yield curve contains useful advance information about recessions, not whether yield-curve inversions cause recessions.

## Research question

**How accurately does the slope of the UK government yield curve forecast whether the UK economy will be in a technical recession 1, 2, 4 and 6 quarters ahead?**

## Economic intuition

The yield spread measures the difference between longer-term and shorter-term government-bond yields:

The yield spread is calculated as:

> **Yield spread = 10-year gilt yield − 2-year gilt yield**

A negative spread represents an inverted yield curve. Inversions may reflect restrictive monetary conditions, expectations of weaker economic growth and expectations of future interest-rate cuts.

The main hypothesis is therefore that a lower yield spread will be associated with a higher probability of a future recession.

## Planned methodology

1. Collect UK government yield-curve data from the Bank of England.
2. Collect seasonally adjusted real GDP data from the Office for National Statistics.
3. Convert daily gilt yields into quarterly averages.
4. Construct the yield spread and a technical-recession indicator.
5. Estimate separate logit models for recessions 1, 2, 4 and 6 quarters ahead.
6. Estimate probit models as a robustness exercise.
7. Conduct expanding-window pseudo-out-of-sample forecasts.
8. Compare forecasting performance with a historical-frequency benchmark.
9. Evaluate forecasts using ROC-AUC, Brier scores and classification measures.
10. Examine sensitivity to alternative yield spreads and the COVID-19 recession.

## Provisional data sources

- [Bank of England yield curves](https://www.bankofengland.co.uk/statistics/yield-curves)
- [ONS real GDP series (ABMI)](https://www.ons.gov.uk/economy/grossdomesticproductgdp/timeseries/abmi/pn2)

The precise yield spread and sample period remain provisional until the historical coverage of the raw yield data has been inspected.

## Repository structure

```text
.
├── data/
│   ├── raw/              # Original source files
│   └── processed/        # Cleaned and merged datasets
├── notebooks/            # Data preparation and analysis notebooks
├── outputs/
│   ├── figures/          # Final visualisations
│   └── tables/           # Model and evaluation results
├── report/               # Final written report
├── src/                  # Reusable Python code
├── requirements.txt      # Python dependencies
└── README.md
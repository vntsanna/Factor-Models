# Factor Models 

This notebook replicates the FRED-MD pipeline to extract common factors from a large panel of US macroeconomic series and to forecast **Industrial Production (INDPRO)** and **inflation (CPI)** with both **rolling one-step-ahead** and **six-month-ahead** horizons.

## Overview
- McCracken–Ng transformations, outlier handling, standardisation
- Factor extraction via **PCA** (Stock & Watson normalisation)
- Number of factors via **Bai & Ng (PC_p2)**
- **EM algorithm** to handle missing data
- Factor relevance via **marginal R²** and ranking of top series
- **Forecasting**:
  - **Rolling one-step-ahead** (real-time style): re-estimate factors each period and predict \(t+1\)
  - **Six-month-ahead iterative**: feed forecasts forward to reach \(t+6\)
- Evaluation with standard error metrics and plots

## Results
- **Selected factors:** 7  
  → explaining **47.36%** of total variance (sample up to 03/2025)  
- **Rolling one-step-ahead forecast (ΔCPI):**
  - MSE = **0.360**
  - RMSE = **0.600**

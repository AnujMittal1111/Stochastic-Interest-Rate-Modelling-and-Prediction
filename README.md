# Stochastic Interest Rate Modelling and Prediction

## Project Overview

This project presents a complete implementation of the Cox–Ingersoll–Ross (CIR) stochastic interest rate model for modelling and predicting the term structure of interest rates. The workflow covers data preprocessing, model calibration, yield curve reconstruction, performance evaluation, and model enhancement through a Jump-Diffusion extension.

The objective is to reconstruct the yield curve using the short-term interest rate and evaluate the predictive capability of the CIR framework on unseen market data.

---

## Project Structure

```
Stochastic-Interest-Rate-Modelling-and-Prediction/
│
├── Datasets/
│   ├── train_data.csv
│   ├── test_data.csv
│   └── test_data_3M.csv
│
├── CIR_Model.ipynb
│
└── README.md
```

---

## Methodology

### Section A: Data Preparation and Preprocessing

- Data quality assessment
- Missing value treatment
- Outlier detection using IQR
- Yield curve cleaning pipeline
- Mathematical viability checks for CIR calibration

### Section B: CIR Model Development and Calibration

- CIR stochastic differential equation implementation
- Maximum Likelihood Estimation (MLE) calibration
- Ordinary Least Squares (OLS) calibration
- Feller condition verification
- Parameter estimation and validation

### Section C: Yield Curve Reconstruction

- Yield curve generation using calibrated CIR parameters
- Risk-neutral cross-sectional calibration
- Prediction of multiple maturities from the 3-month rate
- Performance evaluation using:
  - R² Score
  - RMSE
  - MAE
  - Residual Analysis

### Section D: Jump-Diffusion Extension

- Incorporation of Poisson jump processes
- Jump intensity estimation
- Jump volatility estimation
- Comparison between standard CIR and Jump-Diffusion CIR

### Section E: Critical Analysis

- Theoretical limitations of CIR models
- Practical challenges in calibration
- Risk management implications
- Model comparison and interpretation

---

## CIR Model

The CIR short-rate process is defined as:

\[
dr_t = \kappa(\theta-r_t)dt + \sigma\sqrt{r_t}dW_t
\]

where:

- κ = Mean reversion speed
- θ = Long-run mean level
- σ = Volatility parameter
- \(W_t\) = Standard Brownian Motion

The model guarantees non-negative interest rates when the Feller condition holds:

\[
2\kappa\theta \geq \sigma^2
\]

---

## Jump-Diffusion Extension

To better capture sudden market shocks, the CIR framework is extended with a jump component:

\[
dr_t = \kappa(\theta-r_t)dt + \sigma\sqrt{r_t}dW_t + J_t dN_t
\]

where:

- \(N_t\) represents a Poisson jump process
- \(J_t\) denotes jump magnitude

This extension improves the model's ability to represent extreme market events and heavy-tailed behaviour.

---

## Technologies Used

- Python
- NumPy
- Pandas
- SciPy
- Matplotlib
- Google Colab

---

## Evaluation Metrics

Model performance is assessed using:

- Coefficient of Determination (R²)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Residual Distribution Analysis

---

## Author

Anuj Mittal

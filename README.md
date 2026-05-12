# 📈 Factor-Exposure Analyzer (Fama-French 3-Factor Model)

![Factor Exposure Analysis Results](results.png)

This project provides a robust quantitative pipeline to analyze the sensitivity of specific stock returns (focusing on AI and Semiconductor sectors) to fundamental market factors. Utilizing the **Fama-French 3-Factor Model**, it decomposes asset returns into Market Risk, Size (SMB), and Value (HML) exposures through Ordinary Least Squares (OLS) regression.

## 📖 Overview

In quantitative finance, understanding a portfolio's or stock's "factor tilt" is essential for risk decomposition and alpha generation. This tool addresses the need for a transparent, step-by-step implementation of factor analysis, moving from raw return simulation to visual risk reporting.

The workflow implements:
1.  **Synthetic Data Generation:** Simulates realistic log-returns for stocks like NVDA, ASML, AMD, and TSM alongside Fama-French benchmarks.
2.  **Excess Return Processing:** Prepares data for regression by adjusting for the Risk-Free Rate.
3.  **OLS Regression Engine:** Computes Alpha (idiosyncratic return), Betas (factor sensitivities), and statistical significance (p-values, R-squared).
4.  **Visual Risk Mapping:** Generates comparative reports to visualize "Growth" vs "Value" and "Market" tilts.

## 🛠️ Key Features

-   **Realistic Simulation:** Accounts for sectoral dynamics (e.g., tech stocks' high beta and negative HML tilt).
-   **Automated Regression Pipeline:** Iterates through multiple assets to produce a consolidated factor exposure table.
-   **Statistical Metrics:** Provides R-squared for model fit and p-values for factor significance.
-   **Seaborn Visualization:** High-quality bar charts for intuitive factor exposure comparison.

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Libraries: `pandas`, `numpy`, `statsmodels`, `matplotlib`, `seaborn`

### Installation
```bash
git clone https://github.com/ArifKemal/factor_analysis.git
cd factor_analysis
pip install -r requirements.txt
```

### Usage
Open the main analysis notebook to explore the full lifecycle:
1.  Launch `Factor_Exposure_Analyzer.ipynb`.
2.  Execute cells to generate the `factor_exposure_data.csv` and visualize the results.

## 📊 Methodology Detail

### Fama-French 3-Factor Model
The model explains stock returns using three variables:
- **Market (Mkt-RF):** Performance of the overall market over the risk-free rate.
- **Size (SMB):** "Small Minus Big" performance (Small-cap vs Large-cap).
- **Value (HML):** "High Minus Low" performance (Value vs Growth).

### Expected Results for Tech
Typically, high-growth semiconductor stocks exhibit:
- **High Market Beta (>1.2):** High sensitivity to market movements.
- **Positive SMB:** Small-cap characteristics or aggressive growth behavior.
- **Negative HML:** A strong "Growth" tilt as opposed to "Value".

---
*Disclaimer: This project is for educational purposes. Simulated data does not reflect real-time market conditions.*

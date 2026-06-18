# Portfolio Stress Testing Engine

## Executive Summary & Architectural Overview

### System Architecture
The **Portfolio Stress Testing Engine** is built on a scalable, modular architecture designed for institutional-grade risk analysis:
- **Data Ingestion Pipeline**: Integrates the `yfinance` API to aggregate high-fidelity historical price data across a diversified, multi-asset portfolio.
- **Quantitative Analytics Core**: Employs custom statistical models to compute tail-risk metrics—including 95% **Value at Risk (VaR)** and **Expected Shortfall (ES)**—while tracking risk-adjusted performance via annualized **Sharpe** and **Sortino** ratios.
- **Scenario Simulation Framework**: Features a robust 'What-If' engine to model hypothetical market shocks (e.g., sector-specific drawdowns, interest rate spikes), enabling proactive hedging strategies.
- **Interactive Visualization Layer**: Leverages `Plotly` to deliver dynamic risk dashboards, rendering historical drawdowns, return distributions, and granular waterfall contribution charts.

### Stress Testing Analysis & Findings
The engine successfully quantified portfolio resilience across varying market regimes:
- **Historical Tail Risk**: The **2020 COVID-19 Crash** generated the sharpest acute tail risk, realizing an Expected Shortfall (ES) of **-5.67%**, eclipsing the **-3.55%** ES of the **2008 Financial Crisis**. Despite deeper immediate losses in 2020, the portfolio's risk-adjusted recovery was superior (Sortino: 0.09) compared to the prolonged drawdown of 2008 (Sortino: -1.11).
- **Hypothetical 'Tech Crash'**: Simulating a severe technology sector shock projected a **3.00%** aggregate portfolio contraction. Crucially, waterfall attribution revealed that "flight-to-quality" assets (BND and GLD) provided a **1.00% absolute hedge**, effectively blunting the **4.00% drawdown** originating from equity exposures (QQQ, SPY, VTI).

### Strategic Insights & Future Roadmap
- **Portfolio Resilience**: Equal-weighted allocations into non-correlated assets (Gold and Bonds) proved to be essential shock absorbers during periods of severe equity distress.
- **Future Enhancements**: Next-generation iterations of this engine will integrate **Monte Carlo Simulations** for stochastic path generation and **Macroeconomic Factor Models** to correlate portfolio volatility directly with leading indicators like inflation and GDP growth.

## Project Structure
```text
portfolio-stress-testing-engine/
│
├── notebook/
│   └── Portfolio_Stress_Testing.ipynb
│
├── images/
│   ├── max_drawdown.png
│   ├── PORTFOLIO__RETURN.png
│   ├── risk metrics.png
│   └── waterfallgraph.png
│
├── README.md
│
├── requirements.txt
│
└── LICENSE
```

## Setup Instructions
1. Clone this repository.
2. Install the requirements: `pip install -r requirements.txt`
3. Open `notebook/Portfolio_Stress_Testing.ipynb` in Jupyter or VS Code.

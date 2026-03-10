# Quantitative Equity Analysis & Market Regime Dashboard

A **Python-based quantitative research toolkit** designed to analyze the statistical behavior of individual equities using historical market data from **Yahoo Finance**.

The framework allows users to **select any stock ticker** and run a full analysis pipeline including **breakout statistics, bear market regime detection, and seasonal performance patterns**.

This project focuses on identifying **statistical edges in equity time series** through the analysis of:

- price action dynamics
- historical drawdowns
- recovery structures
- seasonal return patterns

The ticker symbol can be easily modified to perform the same analysis on **any publicly traded stock available on Yahoo Finance**.

---

# Core Features

## 1. Highs & Forward Returns Analysis

This module identifies **52-week highs (252 trading days)** and performs a statistical analysis on subsequent price behavior.

The goal is to measure whether **new highs tend to lead to continuation or mean reversion**.

Forward returns are computed across multiple horizons:

- **20 trading days**
- **60 trading days**
- **120 trading days**

### Key Metric

**Breakout vs Fakeout Frequency**

The model evaluates how often new highs lead to **continued upward momentum versus short-term reversals**.

### Visual Insight

The chart illustrates the historical relationship between **new yearly highs** and the **expected magnitude of future returns**.

![Highs & Forward Returns](highs&forward_returns.png)

---

## 2. Bear Market & Recovery Profiling

This module detects **Bear Market regimes**, defined as **peak-to-trough declines of at least 20%**.

Beyond simple detection, the algorithm profiles the full **drawdown and recovery structure**.

### Key Metrics

- **Time to Bottom**  
  Measures the duration of the crash phase.

- **Recovery Velocity**  
  Time required to recover to the **previous all-time high (ATH)**.

- **Secondary Drawdowns**  
  Volatility clusters occurring during the recovery phase.

This analysis helps quantify how **different stocks behave during major stress events**.

![Bear Market Profiling](bear_market.png)

---

## 3. Seasonality & Percentile Confidence Bands

This module provides a **normalized view of annual performance patterns**.

Each historical year is aligned to a common starting point (**Base = 0**), allowing the model to estimate the **typical yearly trajectory**.

The framework computes:

- **Median yearly path**
- **10th percentile band**
- **25th percentile band**
- **75th percentile band**
- **90th percentile band**

### Applications

**Alpha Generation**

Identify months where the stock **consistently outperforms or underperforms** its historical median.

**Risk Management**

Highlight periods where price action **moves outside the 90th percentile**, signaling potential **mean reversion or extreme momentum**.

![Seasonality Percentile Bands](seasonality_percentile_bands.png)

---

# Flexible Ticker Selection

The analysis pipeline is **ticker-agnostic**.

Users can simply modify the ticker variable to run the full research workflow on any equity.

Example:

```python
ticker = "AAPL"

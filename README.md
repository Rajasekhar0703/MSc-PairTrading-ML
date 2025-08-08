# MSc-PairTrading-ML
Master’s project in Data Science: Development of a predictive pair trading strategy combining cointegration analysis with XGBoost, Random Forest, and LSTM models.
# A Machine Learning Approach for Predictive Pair Trading  
**Combining Cointegration with Random Forest, XGBoost, and LSTM**

## 📌 Abstract
This project develops a **hybrid machine learning–based pair trading strategy** that integrates advanced predictive models — Random Forest, XGBoost, and Long Short-Term Memory (LSTM) — with conventional statistical techniques.  

The goal is **intraday trading** by exploiting mean-reverting behavior in **cointegrated stock pairs** from the **S&P 500** and **Dow Jones** indices. Data is sourced from **Alpha Vantage** and **Yahoo Finance**, with cointegration detected via **Engle–Granger** and **Johansen** tests.

Key highlights:
- **Technical indicators** (Bollinger Bands, RSI, MACD) extracted for supervised models.
- LSTM for sequential pattern recognition.
- Random Forest & XGBoost for high-precision classification of spread movement.
- Backtested using a rule-based approach.

**Results:**
- **XGBoost**: Best performance — avg. profit **$2.12/trade**, Sharpe ratio **0.461**, cumulative return **4.57%**.
- **LSTM**: Strong temporal learning but slightly lower returns (**3.38%**).
- All models outperformed baseline strategies in returns and risk-adjusted metrics.

---

## 📂 Table of Contents
- [Introduction](#-introduction)
- [Objectives](#-objectives)
- [Methodology](#-methodology)
- [Legal, Social, and Ethical Considerations](#-legal-social-and-ethical-considerations)
- [Background](#-background)
- [Literature & Technology Review](#-literature--technology-review)
- [Implementation](#-implementation)
- [Evaluation & Results](#-evaluation--results)
- [Conclusion](#-conclusion)
- [Future Work](#-future-work)
- [Reflection](#-reflection)

---

## 📖 Introduction
The project applies **machine learning** to a **market-neutral pairs trading strategy** that captures short-term mispricing between **statistically related stocks**.

Approach:
- Combine **RNN-based methods** (LSTM) with **econometric analysis** (correlation, cointegration).
- Source **real-time and historical market data** via Alpha Vantage API.
- Generate **long/short trading signals** from predicted spread movements.

Motivation:
- Aligns with the trend toward **data-driven, risk-adjusted investing** in volatile, regulated markets.
- Supports development of **adaptive, automated trading systems**.

---

## 🎯 Objectives
- **Develop & evaluate** a machine learning–driven pair trading system.
- Predict **mean-reversion opportunities** in cointegrated pairs from S&P 500 and Dow Jones.
- Compare **LSTM** against **Random Forest** and **XGBoost** for signal generation.
- Optimize **profitability** while managing **risk**.

---

## 🛠 Methodology
1. **Data Collection & Preprocessing**  
   - Historical intraday/daily data from Alpha Vantage API & Yahoo Finance.
   - Data cleaning, alignment, normalization.

2. **Pair Selection**  
   - Pearson correlation filtering.
   - Engle–Granger & Johansen cointegration tests.

3. **Spread Construction & Feature Engineering**  
   - OLS hedge ratio calculation.
   - Z-score, volatility, technical indicators (RSI, MACD, Bollinger Bands).

4. **Model Development**  
   - LSTM (time-series prediction).
   - Random Forest & XGBoost (classification of spread direction).

5. **Backtesting & Evaluation**  
   - Rule-based & ML-based signal integration.
   - Metrics: Sharpe ratio, max drawdown, total profit, win rate.

---

## ⚖ Legal, Social, and Ethical Considerations
- **Data Licensing** — Compliance with Alpha Vantage & Yahoo Finance terms.
- **Regulatory Compliance** — Adherence to SEC/MiFID II guidelines.
- **AI Responsibility** — Avoid bias, ensure explainability & fairness.
- **Societal Impact** — Narrowing gap between institutional & retail traders.

---

## 📚 Background
- **Pairs Trading**: Popular market-neutral strategy exploiting mean-reversion.
- **Challenge**: Traditional methods lose effectiveness in dynamic, nonlinear markets.
- **Opportunity**: LSTM and ensemble methods can adapt to **high-frequency volatility**.

---

## 📖 Literature & Technology Review
- LSTM-based forecasting improves **intraday trade accuracy** (Flori & Regoli, 2021).
- Random Forest & Gradient Boosting effective for **nonlinear financial patterns**.
- Framework: **Python**, `statsmodels`, `scikit-learn`, `TensorFlow/Keras`, `xgboost`.

---

## ⚙ Implementation
System architecture:
- **Data Layer** — Fetches historical prices.
- **Preprocessing Module** — Cleans/aligns datasets.
- **Statistical Tests** — Engle–Granger, Johansen.
- **Feature Engineering** — Technical indicators, z-scores.
- **ML Models** — LSTM, Random Forest, XGBoost.
- **Backtesting Engine** — Trade simulation with performance metrics.

---

## 📊 Evaluation & Results
| Metric               | XGBoost | Random Forest | LSTM  | Best Model |
|----------------------|---------|--------------|-------|------------|
| Total Profit ($)     | 457.00  | 456.94       | 338.26| XGBoost    |
| Cumulative Return (%)| 4.57    | 4.57         | 3.38  | XGBoost/RF |
| Sharpe Ratio         | 0.461   | 0.461        | 0.334 | XGBoost/RF |
| Max Drawdown (%)     | -0.67   | -0.67        | -1.68 | XGBoost/RF |
| Trades               | 215     | 215          | 242   | LSTM       |
| Win Rate (%)         | 41.40   | 42.33        | 41.74 | RF         |
| Avg. P&L ($/trade)   | 2.1220  | 2.1218       | 1.3948| XGBoost    |

**Insights:**
- XGBoost = best risk-return profile.
- Random Forest = slightly higher win rate.
- LSTM = more trades, higher sensitivity to patterns but lower returns.

---

## 🏁 Conclusion
- **XGBoost** recommended for its balance of profitability, risk control, and interpretability.
- Statistical foundation (cointegration, z-score) + ML enhances robustness.
- LSTM promising but requires further optimization.

---

## 🔮 Future Work
- Live deployment with brokerage APIs.
- Walk-forward optimization for varying market regimes.
- Ensemble stacking of LSTM + tree-based models.
- Incorporating **sentiment analysis** (FinBERT, news feeds).
- Reinforcement learning for adaptive trade sizing.

---

## 💭 Reflection
This project was both **technically challenging** and **insightful**:
- Strengthened expertise in **quantitative finance**, **machine learning**, and **backtesting**.
- Learned the importance of **strong statistical foundations** before ML modeling.
- Time constraints limited real-time deployment and GUI creation.
- Future iterations would focus on **version control**, **early expert feedback**, and **buffer time for debugging**.

---

## 📜 License
This project is released under the MIT License — see `LICENSE` for details.

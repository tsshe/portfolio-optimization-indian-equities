# Diversified Portfolio Optimization for Indian Equities
### Using Sharpe Ratio Maximization | NMIMS BSc Applied Mathematical Computing, 2025

**Authors:** Juhi Kariya · Diyanshi Shah · Tanushri Shetty  
**Supervisor:** Dr. Debasmita Mukherjee, NSOMASA, NMIMS Mumbai

---

## Objective
Build a sector-diversified portfolio of Indian equities that **maximizes the Sharpe Ratio** 
while respecting a user-defined risk tolerance — providing a practical, data-driven 
investment tool for retail investors.

---

## Repository Structure
1. RD_FINAL.ipynb          #Main notebook (data, optimization, results, UI)
2. Dissertation_Report.pdf #Full project report
3. README.md

---

## Methodology at a Glance

| Step | What Happens |
|------|-------------|
| **Stock Universe** | 25 NSE stocks across 5 sectors (Tech/IT, Banking & Finance, Consumer, Healthcare, Infrastructure) |
| **Combinations** | All 5⁵ = 3,125 five-stock portfolios (one per sector) generated |
| **Filtering** | Equal-weight risk computed; portfolios exceeding user's risk threshold + 5% are removed |
| **Optimization** | SLSQP maximizes Sharpe Ratio with budget + no-short-selling constraints |
| **Validation** | Trained on 2020–2023 data; evaluated out-of-sample on 2023–2025 |

---

## Key Results

| Metric | Training (3Y) | Evaluation (2Y) | Equal-Weight Baseline |
|--------|-------------|----------------|----------------------|
| Expected Return | 35.43% | 36.63% | 25.12% |
| Volatility | 13.99% | 20.15% | 14.24% |
| Sharpe Ratio | 2.05 | 1.49 | 1.29 |
| Sortino Ratio | 3.90 | 2.53 | 2.05 |
| Max Drawdown | -14.51% | -58.55% | -46.68% |

**Optimal Portfolio:** Zydus Lifesciences (36.4%) · Cholamandalam Finance (26.6%) · 
Hindustan Aeronautics (18.3%) · Oracle Financial Services (10.2%) · Mold-Tek Packaging (8.4%)

---

## Tech Stack
- **Python** — pandas, numpy, scipy, yfinance, matplotlib, seaborn
- **Optimization** — `scipy.optimize.minimize` with `method='SLSQP'`
- **UI** — Flask (Google Colab)

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/portfolio-optimization-indian-equities.git

# 2. Install dependencies
pip install pandas numpy scipy yfinance matplotlib seaborn flask

# 3. Open the notebook
jupyter notebook RD_FINAL.ipynb
```

---

## Core Formula

**Sharpe Ratio:**

$$S = \frac{R_p - R_f}{\sigma_p}$$

where $R_p$ = portfolio return, $R_f$ = 6.7\% (Indian government bond rate), $\sigma_p$ = portfolio volatility

---

## References
1. Sharpe, W.F. (1967) — *A Linear Programming Algorithm for Mutual Fund Portfolio Selection*
2. Lee & Lerro (1973) — *Optimizing the Portfolio Selection for Mutual Funds*
3. Abdi et al. (2024) — *Prospective Portfolio Optimization with LSTM and Sharpe Ratio Maximization*
4. Hilpisch, Y. (2018) — *Python for Finance*, O'Reilly, Chapter 13

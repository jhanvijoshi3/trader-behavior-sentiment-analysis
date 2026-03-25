# Trader Performance vs Market Sentiment
**Primetrade.ai — Data Science Intern Assignment**

## Executive Summary
This analysis examines how market sentiment (Fear vs Greed) influences trader performance and behavior. Results show that profitability and win rates improve in Greed regimes, while Fear periods lead to lower performance and inefficient trading behavior. Based on these findings, sentiment-aware risk management strategies are proposed.

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook trader_sentiment_analysis.ipynb
```

Place both CSV files (`fear_greed_index.csv`, `historical_data.csv`) in the same folder. Run all cells top-to-bottom.

---

## What's inside

| Section | Content |
|---------|---------|
| 1–2 | Data loading, cleaning, merge, feature engineering |
| 3 | Key metrics table by sentiment regime |
| 4 | 3 charts: performance, behaviour, segmentation + insights |
| 5 | Two actionable strategy rules |
| 6 | Bonus: logistic regression predicting next-day profitability |

---
## Methodology
- Cleaned and aligned sentiment and trading datasets at daily level
- Engineered key metrics: PnL, win rate, trade size, trade frequency
- Compared performance across sentiment regimes
- Segmented traders (frequent vs infrequent, winners vs losers)
- Derived insights using statistical summaries and visualizations

---

## Key Findings

**Insight 1 — Performance follows sentiment.**
Win rate and mean net PnL rise monotonically from Extreme Fear to Extreme Greed. The gap is ~9 percentage points in win rate across 200,000+ trades.

**Insight 2 — Traders go longer and bigger in Greed.**
Long ratio rises from ~0.48 (Extreme Fear) to ~0.65 (Extreme Greed). Shorting into Fear does not help — win rates are still lowest then.

**Insight 3 — Net Winners are consistent; Net Losers are sentiment-driven.**
Net Winners hold above 50% win rate across all regimes. Frequent traders lose their edge on Fear days but keep the same activity level — that is the leak.

---

## Strategy Recommendations

**Strategy 1 — Size down in Fear**
When FG Index < 40: reduce position sizes by 30%+, avoid new Long entries.
When FG Index > 60: normal or slightly larger sizes; Long bias is supported.

**Strategy 2 — Frequent traders throttle on Fear days**
Cut trade count ~50% on Extreme Fear days. Infrequent traders are largely unaffected — their selectivity already acts as a filter.

---
## Conclusion
Market sentiment acts as a measurable signal influencing both trader behavior and performance. Incorporating sentiment into trading decisions can significantly improve risk-adjusted outcomes.

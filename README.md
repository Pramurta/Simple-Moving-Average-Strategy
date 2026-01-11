# Simple Moving Average (SMA) Strategy — 1-Day Hold (10/50)

This repository contains a Jupyter Notebook implementing a simple moving-average based trading strategy using **10-day** and **50-day** SMAs.

Notebook: `Simple_Moving_Average_Trading_Strategy.ipynb`

> ⚠️ Educational project only — not financial advice.

---

## Strategy Logic

This strategy uses a trend condition to decide whether to take a **one-day long trade**:

### Rule
- **Buy (enter long):** when `SMA(10) > SMA(50)` (signal generated on day *t*)
- **Sell (exit):** **the next trading day** (*t+1*)

In other words, the strategy profits (or loses) from the **next-day return** on days where the 10-day SMA is above the 50-day SMA.

### Intuition
When the short-term average is above the long-term average, it suggests positive momentum / an uptrend. The strategy then attempts to capture a small, short-horizon move by holding only for one day.

---

## What the Notebook Does

Typical flow:
1. Load historical price data
2. Compute `SMA10` and `SMA50`
3. Generate a boolean signal: `SMA10 > SMA50`
4. Convert the signal into **next-day trade returns**
5. Compare strategy performance vs buy-and-hold
6. Plot price + SMAs and performance (if included)

---

## Setup

### Clone
```bash
git clone https://github.com/Pramurta/Simple-Moving-Average-Strategy.git
cd Simple-Moving-Average-Strategy

# AlgonikHQ Research Log

Testing trading ideas properly — and publishing what fails, not just what works.

**Status (1 Nov 2026):** demo only. No strategy tested so far has passed its own pass criteria after real costs.
Not financial advice.

---

## Why this exists

Most trading accounts only show the wins. This log shows the whole process: every idea, how it was tested,
and why most of them didn't survive. The goal is a system good enough for a prop-firm challenge — and the
honesty to say when one isn't there yet.

## How every idea is tested

1. **Rules first.** Entry, exit and pass/fail criteria are written down *before* any results are seen. No changing them afterwards.
2. **Real costs.** Every trade pays the bid/ask spread, overnight financing at current broker rates, and a slippage buffer.
3. **The flip test.** Every signal is also traded backwards. A real edge must clearly beat its own reverse — otherwise the direction is luck.
4. **The random test.** Same stops, same exits, random entry times. A real signal must beat at least 90% of random runs.
5. **Unseen data.** Ideas are designed on one period, checked on another, and only the survivors get one final run on data held back.
6. **Measured in R.** Results are in multiples of the amount risked per trade, so every market compares fairly.

## Results so far

About 55 variants and tens of thousands of simulated trades, across FX, stock indices, metals, energy,
grains and bonds, from 15-minute to weekly charts, 2005–2026.

| Idea family | Markets | Avg per trade after costs | Real direction edge? | Verdict |
|---|---|---|---|---|
| Intraday fair-value-gap entries | FX majors | −0.10R to −0.19R | No — same result traded backwards | Ruled out |
| London session breakout | FX majors | −0.02R to −0.10R | Tiny, not significant | Ruled out — spread is ~2× the edge |
| Daily breakout / trend following | FX majors | −0.07R to −0.54R | No | Ruled out |
| Multi-week trend following | 24 indices & commodities | about +0.02R | Longs only | Rising markets, not timing |
| Long-only trend, indices & gold | 13 markets, 2005–2026 | −0.06R to −0.16R after financing | Beats random 83–87% | Financing eats it |
| Short-hold dip-buying | 24 markets | −0.03R to −0.06R | No | Ruled out |
| Daily mean reversion (3 versions) | FX majors, 2005–2026 | −0.05R to −0.10R | No | Ruled out |
| Turn-of-month | 11 stock indices | about −0.02R | Small, inconsistent | Financing eats it |
| Momentum-leader breakouts, short holds | Low-cost indices & commodities | about +0.02R | **Yes** — survives flip and random tests on unseen data | Real but too small — tracked live |

## What we learned

1. **The cost squeeze.** Intraday trades pay more in spread than their edge is worth. Multi-week trades pay more in
   overnight financing than they earn. Holds of one to five days, closed before the weekend, are the cheapest zone.
2. **Rising markets fool backtests.** Long-only systems on stock indices looked good — until random long entries
   made money too. The "edge" was the market going up, not the signal.
3. **The flip test catches illusions.** The bot's original entry made the same result traded backwards. It was picking
   direction at random.
4. **One real signal.** Strong markets breaking out in the direction of their trend tend to keep going for a few days.
   It is statistically real — but small, and costs take most of it.
5. **Process beats patterns.** After dozens of variants, more tweaking mostly raises the chance of finding something
   that only looks good by luck. Knowing when to stop is part of the method.

## Live now (demo account)

- A demo trading bot with hardened risk controls, automatic failure alerts, and a weekly edge report measured in R.
- A forward "shadow" of the momentum-leader signal: it logs every signal and its outcome, places no orders, and
  tests the idea on data nobody has seen yet.

## Go-live gates (set in advance)

Nothing trades real money until it shows, on unseen and live data:
- average result of at least **+0.10R** per trade after all costs
- profit factor of at least **1.2**
- **50+** trades
- drawdown comfortably inside prop-firm limits (5% daily, 10% total)

## Not published here

Exact rules, settings, instrument lists, code, live signals and account details stay private.

## Updates

Monthly: live demo results in R, good or bad.

---

*Demo results only. Past or simulated performance is not a guide to future results. Not financial advice.*
*© AlgonikHQ*

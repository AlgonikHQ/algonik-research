# Forward tests, weeks 2-3 (to 20 Nov 2026)

Paper tests on frozen rules. No money traded. 1R = the risk on one trade.

## Week 14-20 Nov

| Test | This week | Total | Closed |
|---|---|---|---|
| Trend following (T11) | -12.45R | -29.58R | 29 (13 open) |
| Pre-Fed drift (F1) | - | - | 0 |
| Wide-gap carry (F2) | - | -1.01R | 1 (2 open) |
| Positioning fade (COT) | - | -1.08R | 1 (3 open) |
| Intraday momentum (IM) | -2.28R | -4.93R | 48 |
| Opening-range breakout (ORB) | +34.55R | +39.15R | 80 |

Combined this week: +19.82R over 58 trades. Without the best day: +12.93R.

## What happened

US indices sold off hard this week. The breakout test made almost all of its gain from shorts on one-way days. The trend test lost on the same move as its long index and silver positions were stopped out. Its 29 closed trades are all stops because the winners are still open.

The breakout's validation backtest was flat, and its 80 forward trades come from about 14 trading days. This is one regime, not evidence of an edge. Its review stays at the pre-set trade count.

## Setup check

A separate executor places the two intraday strategies as demo orders. Over two weeks it matched the paper decisions 80 out of 80 on market and direction. Next: live demo orders and a fill-by-fill comparison.

## Corrections

- The weekly report showed a pass for "average at least 2 standard errors above zero", but only checked the average. Fixed. The live demo is at +0.29R +/- 0.48 (2 SE) over 49 trades: positive, not yet significant.
- One positioning-fade trade (closed 13 Nov, -1.08R) is in the total but was missed from both weekly breakdowns. Totals were always correct.
- The broker's practice server went into maintenance and the bot restarted in a loop. It now waits at startup instead.

## Changes from community feedback

For new tests only (running tests keep their rules):
- Review intraday tests on daily R totals, since same-day trades move together.
- Size reviews for about 80% power, not 50%.
- Leave out one week at a time per test, and tally which market regimes the sample covered.
- Show open trend positions at current value next to closed trades.

Ideas tested: 70. Passed: 0.

Demo research only. Not financial advice.

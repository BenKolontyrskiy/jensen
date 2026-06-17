End-of-day review and close. Run this at or after 3:30 PM ET on trading days. This is the EOD agent.

## Steps

1. **Run /portfolio** — get current state, execute any Section 9/10 required actions first.

2. **Thursday / Friday close rule** — hard check:
   - If today is Thursday: EXIT all leveraged ETF positions at market close. No exceptions. Log each exit.
   - If today is Friday and any leveraged ETF is still open: EXIT immediately at current price. Log as weekend-rule forced exit.

3. **Stale position audit** — for each open position:
   - How many trading days has it been held?
   - Is the original catalyst still active, or has it resolved / gone stale?
   - If held > 2–3 days with no new catalyst: flag for exit (per Section 5 position management rules)
   - If exiting: generate the trade log entry (exit reason: "stale — no new catalyst")

4. **Execute flagged exits** — for any position flagged in steps 1–3, execute the sell via Robinhood MCP. Log each trade immediately.

5. **Generate cycle summary** — append to trade_log.md:

```
## [TIMESTAMP UTC] CYCLE SUMMARY — [DATE]

### Positions closed today
[Ticker | Entry $X → Exit $X | P&L % | Reason]

### Open positions at close
[Ticker | Shares | Entry $X | Current $X | Unrealized P&L | Catalyst status | Days held]

### Cash & buying power
Cash: $[X] | Buying power: $[X] | Total: $[X]

### Circuit breaker status
[INACTIVE / WARNING / TRIGGERED] — [X]% from peak of $[X]

### Watchlist for next session
[Ticker | Catalyst | Conviction | Trigger condition]

### Thesis notes
[Any observation about what worked / didn't today. 2–3 sentences max.]
```

6. **Pre-market plan** — based on current watchlist and any news that may have broken near close, draft the next session's plan:
   - Which positions carry over (and why)?
   - Which catalysts are expected in pre-market or at open tomorrow?
   - What's the priority order for deploying remaining cash?

Log the pre-market plan as a WATCHLIST entry in trade_log.md.

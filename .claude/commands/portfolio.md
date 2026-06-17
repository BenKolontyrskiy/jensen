Pull a full portfolio snapshot from Robinhood and run all active position checks. This is the portfolio-state agent.

## Steps

1. **Fetch from Robinhood MCP**:
   - All equity positions (ticker, shares, avg cost, current price, unrealized P&L %)
   - Cash balance and buying power
   - Open orders (pending fills)
   - Account total value

2. **Circuit breaker check** (Section 6):
   - Compute current portfolio peak from trade_log.md (highest total value logged)
   - Calculate drawdown: (peak − current) / peak × 100
   - If drawdown ≥ 10%: FLAG as CIRCUIT BREAKER TRIGGERED — halt new entries, list positions for review
   - If drawdown 7–9.9%: FLAG as WARNING — approaching circuit breaker

3. **Section 9 profit-taking check** — run on every position with unrealized gain:

   For each position, determine:
   - Gain % (unrealized)
   - Momentum state (use price action from quote data: compare current vs. entry day high, volume)
   - Catalyst state (read original trade_log.md entry: is the catalyst still live, partially resolved, or fully resolved?)
   - Position size as % of total portfolio

   Apply the Section 9 trigger matrix. Flag any position that requires action:
   - EXIT immediately (momentum reversing, gain > +25%)
   - TAKE PARTIAL (specified % off)
   - HOLD (no action needed)

4. **Section 10 leveraged ETF hold check** — run on every leveraged ETF position:
   - What day is it? If Thursday close or Friday: EXIT — weekend rule, no exceptions
   - Has hold time limit been reached? (from the original log entry's "Maximum hold date")
   - Is current VIX above 25? → EXIT 3x immediately, assess 2x
   - Loss > −10% from entry? → EXIT immediately
   - Gain > +30%? → EXIT full position

5. **Output a structured report**:

```
PORTFOLIO STATE — [TIMESTAMP]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Cash:           $[X]
Equity value:   $[X]
Total value:    $[X]
Portfolio peak: $[X]
Drawdown:       [X]% [SAFE / WARNING / CIRCUIT BREAKER]

POSITIONS
[Ticker] | [Shares] | Entry $[X] → Now $[X] | [+/-X%] | [ACTION NEEDED / HOLD]

OPEN ORDERS
[Any pending orders]

ACTIONS REQUIRED
[List any positions flagged by S9/S10 checks with specific action]
```

6. **Log to trade_log.md** — append a PORTFOLIO-SNAPSHOT entry with the full state. If any position requires action, flag it clearly so the main agent loop can act on it.

Post-trade review for a closed position. This is the recursive learning agent — it reads closed trades and produces lessons that feed back into investment_thesis.md.

Usage: /post-trade [TICKER] — or run without a ticker to review all positions closed since the last post-trade review.

## Steps

1. **Find the trade entries** — read trade_log.md and locate:
   - The original BUY entry for [TICKER] (or all recently closed positions if no ticker given)
   - The EXIT entry
   - Any WATCHLIST or NO-ACTION entries for the same ticker in between

2. **Reconstruct the trade timeline**:
   - Entry: date, price, catalyst cited, conviction level, gates that passed, exit condition set
   - Hold period: what happened during the hold? (search for any log entries or news mentioning the ticker)
   - Exit: date, price, exit reason (catalyst priced / thesis broke / stale / stop hit / profit-taking rule)
   - Outcome: P&L %, holding days, vs. expected holding period

3. **Evaluate each filter gate** — for the original entry, assess in hindsight:
   - Gate 1 (real bottleneck): Was it? Did the bottleneck thesis hold up?
   - Gate 2 (not yet priced): Was entry before or after the main repricing?
   - Gate 3 (specific catalyst): Did the named catalyst actually drive price action?
   - Gate 4 (catalyst clarity): Was the direct connection accurate?
   - Gate 5 (liquidity): Were exits clean?
   - Gate 6 (bear case): Did the named bear case materialize, or was the actual risk different?

4. **Evaluate sizing and timing**:
   - Was conviction level (Very High / High / Medium / Low) appropriate in hindsight?
   - Was entry timing early (before repricing), on-time, or late (after most of the move)?
   - Was exit on-time (catalyst priced), early (left gains), or late (gave back gains)?
   - If a leveraged ETF was used: did VIX/trend conditions at entry predict outcome well?

5. **Identify patterns** — compare this trade against the learnings/ directory. Look for recurring themes:
   - Same catalyst type appearing again? Did it behave the same way?
   - Same pillar? Same entry timing dynamic?
   - Same exit failure mode (overstaying, exiting too early)?

6. **Write a learnings file** — save to `learnings/[TICKER]-[DATE].md`:

```markdown
# Post-Trade Review: [TICKER] — [ENTRY DATE] to [EXIT DATE]

## Outcome
P&L: [+/-X%] | Hold: [N days] | Entry $[X] → Exit $[X]

## What went right
[Specific observations about what the thesis got correct]

## What went wrong or could be sharper
[Specific observations — be precise: "Gate 2 was marginal because the headline ran 4 hours before entry"]

## Gate accuracy (1 = accurate in hindsight, 0 = inaccurate)
- Gate 1 (real bottleneck): [1/0] — [1 line why]
- Gate 2 (not yet priced): [1/0] — [1 line why]
- Gate 3 (specific catalyst): [1/0] — [1 line why]

## Proposed thesis updates
[Specific, line-level changes to investment_thesis.md — or "none" if thesis held up well]
Example: "Section 3 Pillar 1 — add catalyst type: 'Utility rate case delay (negative catalyst for VST/CEG — exit signal)'"
Example: "Section 4 Gate 2 — add note: 'If stock already ran >5% pre-market on the catalyst, Gate 2 fails — skip'"

## Pattern flags
[Any pattern this trade confirms or breaks from prior learnings]
```

7. **Surface proposed thesis updates** — after writing the learnings file, if there are any proposed changes to investment_thesis.md, present them as a clear diff for review:

```
PROPOSED THESIS UPDATE
Section: [X]
Current text: "[exact current text]"
Proposed: "[new text]"
Reason: [1 sentence from the post-trade analysis]
```

Do NOT auto-apply changes to investment_thesis.md. Present them for human review. The human approves, then you write the change.

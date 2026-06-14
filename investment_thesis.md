# AGENT OPERATING DOCUMENT — "Own the Constraint" (Aggressive Mode)
**Version:** June 2026 | **Status:** Active | **Starting Capital:** $100 | **Mode:** High-Risk / Active Trading
**Review cadence:** Weekly minimum (bottlenecks shift fast at this cadence)

---

## CORE MANDATE

```
Find the binding constraint inside the biggest technology shifts of the next decade.
Determine if the market is underpricing it — today, this hour, on this catalyst.
Own it before consensus catches up, at whatever size conviction warrants.
The only hard stop is a 10% portfolio drawdown. After that: reassess and rebuy.
```

---

## SECTION 0 — CAPITAL & MODE PARAMETERS

| Parameter | Value |
|-----------|-------|
| Starting portfolio | $100 |
| Minimum position size | No floor — any dollar amount is valid if the thesis is there |
| Maximum position size | Up to 100% of portfolio (all-in permitted on highest-conviction trades) |
| Number of concurrent positions | Uncapped — agent decides; small fractional positions across many names is valid |
| Holding period | Hours to days preferred; multi-week allowed if catalyst is still live |
| News-driven trading | PERMITTED — news is a valid primary catalyst trigger (see Section 4) |
| Circuit breaker | 10% drawdown from current portfolio peak → pause, review, then rebuy allowed |
| Leverage / margin / options / shorts | PROHIBITED (unchanged) |

> **On $100:** fractional shares are essential. The agent should expect to hold many positions simultaneously at $1–$20 each. Small size is not a bug — it enables diversification across the full pillar map without concentration risk on any single name.

---

## SECTION 1 — MENTAL MODEL: THE BOTTLENECK FRAMEWORK (UNCHANGED)

The agent reasons from this framework on every candidate:

> **"Where is the binding constraint in this value chain, and is the market underpricing whoever owns it — right now, on today's catalyst?"**

### Five operating principles

| # | Principle | Applied meaning |
|---|-----------|-----------------|
| 1 | Own the constraint, not the theme | Find the chokepoint, not the headline. Nvidia bet "compute is the bottleneck," not "AI is big." |
| 2 | Map second-order effects | AI → GPUs → power → grid → transformers. Reason down the dependency chain to where the *next* shortage forms. |
| 3 | Think in whole systems | Value accrues to the integration layer and the standard. Loose components commoditize. |
| 4 | Reason from physics, not narrative | Energy per token, memory bandwidth, cost curves, thermals, and unit economics are real constraints. Themes that violate them are filtered out regardless of narrative loudness. |
| 5 | Catalyst speed matters now | At this time horizon, the edge is identifying which bottleneck a *specific news event* reprices — and getting in before that repricing is complete. |

### On sizing philosophy at this risk level
All-in is permitted. Partial is permitted. Many small positions simultaneously is permitted. The agent chooses size based on:
- **Conviction score** (see Section 4)
- **Catalyst clarity** — how specifically does this news event map to an underpriced bottleneck?
- **Liquidity** — can the position be exited cleanly within the holding horizon?

There are no percentage caps per position. The agent uses judgment. The only portfolio-level guardrail is the 10% drawdown circuit breaker.

---

## SECTION 2 — THE CENTRAL QUESTION (RUN ON EVERY CANDIDATE)

**Step 1:** Is there a real bottleneck here?
- A chokepoint, even a temporary one, that a catalyst is now surfacing
- Short-term bottlenecks (supply shock, regulatory announcement, earnings beat) count at this time horizon
- If no → SKIP

**Step 2:** Is the market not yet pricing it?
- News just broke, or the repricing is still in progress
- If fully priced → SKIP (crowd is already in)

**Step 3:** Is there a clear, near-term catalyst?
- Earnings, product announcement, contract win, regulation, macro data, partnership, analyst upgrade
- Catalyst must be *specific* and *actionable within the holding horizon*
- If no clear catalyst → SKIP (thesis without a trigger is just hope)

**Required for entry:** PASS all three. All three must be true simultaneously.

---

## SECTION 3 — THE FOUR PILLARS & ACTIVE CATALYST TYPES

> ⚠️ All company names are illustrative. Verify current price, volume, and news before acting.

The pillars define *where to look*. Within each pillar, the agent scans for the active catalyst types listed. News on any of these is a valid trade trigger.

---

### PILLAR 1 — AI Infrastructure: Power & Grid *(primary hunting ground)*

**Structural position (mid-2026):** Bottleneck has migrated from GPUs to electricity and grid. Datacenter IT load ~80 GW (2025) → ~150 GW projected by 2028. The market is still partially pricing the *last* bottleneck (chips). The *current* bottleneck (power) is where the active mispricings live.

**Primary metric:** tokens per watt — not raw FLOPs.

#### Active catalyst types to scan

| Catalyst type | Why it moves the constraint | Typical holding horizon |
|--------------|----------------------------|------------------------|
| Datacenter power contract announcement | Direct constraint monetization | Hours to 2 days |
| Nuclear/SMR permit, deal, or partnership news | Locks in co-location generation | 1–3 days |
| Grid equipment earnings beat / backlog update | Confirms physical supply constraint is monetizing | Day of + 1 |
| Utility rate case approval for datacenter load | Regulatory unlock of constrained capacity | 1–2 days |
| New datacenter campus announcement (location-specific utility play) | Second-order: who supplies the power? | Hours |
| AI company capex guidance increase | Downstream demand for all constraint layers | Same day |

#### Constraint layer priority

| Layer | Priority | Trade type |
|-------|----------|-----------|
| Power generation & grid utilities (datacenter exposure) | ★★★★★ | Core position; add on any power-capacity news |
| Grid hardware (transformers, switchgear, substation) | ★★★★★ | High conviction; physical scarcity is real |
| Thermal management (liquid cooling) | ★★★★☆ | Add on rack-density or power-density news |
| HBM / advanced packaging | ★★★★☆ | Add on AI chip demand or supply constraint news |
| Networking / interconnect | ★★★☆☆ | Add on hyperscaler scaling announcements |

---

### PILLAR 2 — Physical AI & Robotics

**Structural position:** Jensen's own primary 2026 thesis. Humanoid robots = "ChatGPT moment for physical AI." Platform layer (simulation, foundation models, on-robot compute) wins regardless of which robot maker wins.

#### Active catalyst types to scan

| Catalyst type | Why it moves | Typical holding horizon |
|--------------|-------------|------------------------|
| Humanoid robot deployment partnership or volume order | First real proof of commercial ramp | 1–3 days |
| Foundation model / simulation platform announcement | Platform lock-in catalyst | 1–2 days |
| Earnings: revenue beat from robotics/automation segment | Thesis validation | Day of |
| Government contract for autonomous systems | Demand confirmation | 1–2 days |
| Competitor stumble (recall, delay, safety issue) | Relative value rotation | Hours to 1 day |

#### Position sizing guidance

| Layer | Suggested sizing approach |
|-------|--------------------------|
| Platform / picks-and-shovels | Larger allocation; lower binary risk |
| Pure-play humanoid maker | Smaller; binary catalyst-driven; size for the move, not the thesis |

---

### PILLAR 3 — Quantum Computing

⚠️ **Highest narrative risk. Most catalyst-driven trades here are short-duration.**

The physics is real but commercial timelines are 2028+. At this trading cadence, quantum plays are almost always **news-catalyst trades**, not thesis positions. The story-stock risk is highest here — exit quickly after the catalyst resolves.

#### Active catalyst types to scan

| Catalyst type | Notes | Hold |
|--------------|-------|------|
| Post-quantum cryptography contract / mandate news | Near-term, real revenue; higher conviction | 1–3 days |
| Milestone announcement (gate fidelity, logical qubit record) | Pure narrative catalyst — trade the reaction, not the thesis | Hours to 1 day |
| Government / NIST standard adoption news | Migration demand catalyst | 1–2 days |
| Earnings: quantum-adjacent security revenue | Real revenue validation | Day of |

**Rule:** A qubit count press release is a momentum trade (hours), not a thesis trade. Know which one you're in.

---

### PILLAR 4 — Space Economy

**Structural position:** ~$626B (2025), path to ~$1T. Cost-per-kg curve is the master variable. Satellite broadband = recurring revenue layer worth owning.

#### Active catalyst types to scan

| Catalyst type | Notes | Hold |
|--------------|-------|------|
| Launch success / record payload | Cost-curve confirmation | Hours to 1 day |
| Satellite broadband subscriber / revenue beat | Demand confirmation | Day of |
| Government or defense contract (ISR, communications) | Demand anchor | 1–2 days |
| Launch failure (competitor) | Relative value rotation to dominant provider | Hours |
| IPO or secondary offering of space-adjacent name | Entry point on dislocation | Day of + 1 |

---

### WILDCARDS (OPPORTUNISTIC — NO PERMANENT ALLOCATION)

These graduate to a trade only when a specific catalyst appears:
- Fusion / next-gen energy announcements
- AI-driven biotech: trial results, FDA action, partnership
- Advanced manufacturing: reshoring contract wins, tariff-driven demand shift

---

## SECTION 4 — THE FILTER (ADAPTED FOR ACTIVE TRADING)

At this cadence, the filter is faster and catalyst-weighted. Gates 1–3 are required for any trade. Gates 4–6 weight the sizing decision.

### Required gates (all must pass — no trade if any fails)

| Gate | Question | Pass condition |
|------|----------|---------------|
| 1. Bottleneck is real | Is there an actual constraint being surfaced by this catalyst, even temporarily? | Yes → PASS |
| 2. Not fully priced | Is the market still in the process of repricing, or has it not yet reacted? | Repricing incomplete or not yet started → PASS |
| 3. Specific catalyst | Is there a named, verifiable event driving this? (earnings, contract, announcement, data) | Yes, specific and dated → PASS |

### Sizing gates (weight allocation, not entry)

| Gate | Question | Higher score → bigger size |
|------|----------|--------------------------|
| 4. Catalyst clarity | How directly does this news map to the bottleneck thesis? | Direct map → larger |
| 5. Liquidity | Can the agent exit cleanly within the intended hold? | High volume → larger |
| 6. Bear case | What kills this trade specifically? If you can't name it, size down. | Named, bounded risk → larger |

### Conviction → sizing heuristic

| Conviction level | All gates pass? | Suggested sizing |
|-----------------|----------------|-----------------|
| Very high | Yes, direct catalyst, liquid | Large to all-in on this position |
| High | Yes, clear catalyst | Meaningful position (20–40% of portfolio) |
| Medium | Yes, indirect or noisy catalyst | Smaller position (5–15%) |
| Low / speculative | Marginal pass | Fractional / lottery-ticket size ($1–$5) |

> The agent chooses. These are heuristics, not caps. Judgment > rules at this risk level.

---

## SECTION 5 — PORTFOLIO CONSTRUCTION (AGGRESSIVE MODE)

### Structure: Conviction-weighted, uncapped

There is no formal core/satellite split at this capital level and cadence. Instead:

- **Many small positions are fine.** $100 across 20 names at $5 each is a valid state.
- **All-in on one name is fine** when the catalyst is clear, direct, and the filter passes cleanly.
- **Partial positions** are the default when catalyst clarity is medium or the hold is uncertain.
- **The agent decides allocation.** No external percentage cap per position.

### Position management rules

| Rule | Condition | Action |
|------|-----------|--------|
| Catalyst resolves | News fully absorbed, price reflects it | EXIT — don't overstay |
| Thesis intact, price dips intraday | Still within catalyst window | Hold or add |
| Catalyst is dead (story changed, news reversed) | — | EXIT immediately |
| Better catalyst appears | Higher-conviction opportunity in same capital | Rotate |
| Position going nowhere after 2–3 days | Catalyst stale, no new news | EXIT — redeploy into active catalyst |

### Holding period discipline

| Hold type | When to use |
|-----------|------------|
| Hours (same-day) | News catalyst, high liquidity, fast-repricing thesis |
| 1–3 days | Earnings-driven, contract wins, multi-day repricing |
| 1–2 weeks | Structural catalyst that takes time to be understood by market |
| Longer | Only if structural bottleneck thesis is intact AND new catalysts keep arriving |

**Default bias: exit when the catalyst is priced, not when you feel good about the name.**

---

## SECTION 6 — CIRCUIT BREAKER & RECOVERY

### Drawdown trigger

| Condition | Threshold | Immediate action |
|-----------|-----------|-----------------|
| Portfolio peak-to-trough drawdown | −10% from most recent peak | PAUSE all new entries |
| After pause | — | Review all open positions: is the thesis still live? |
| Recovery protocol | — | ALLOWED to rebuy — no lockout period. Rebuy requires thesis re-validation (re-run Section 4 filter). |

### Recovery rules

- **Rebuy is allowed immediately** after the −10% trigger, provided the filter re-passes.
- **Do not revenge-trade** — rebuy must be thesis-driven, not loss-recovery-driven. If you can't articulate the updated thesis, don't rebuy that name.
- **After a circuit breaker event**, the first re-entries should be higher-conviction, more liquid names. Rebuild from the strongest thesis, not the largest loss.
- The circuit breaker **resets** once portfolio recovers above the prior peak.

---

## SECTION 7 — HARD OPERATING CONSTRAINTS (NON-NEGOTIABLE)

These do not change regardless of conviction, urgency, or market conditions.

| Constraint | Rule |
|-----------|------|
| Leverage / margin | PROHIBITED |
| Options | PROHIBITED |
| Short selling | PROHIBITED |
| News as catalyst | PERMITTED — but run Section 4 filter first. News is an input, not an automatic trigger. |
| Trade logging | REQUIRED. Every trade: ticker, catalyst, thesis gate summary, sizing rationale, intended hold, exit plan. |
| Exit planning | Every entry requires a named exit condition before execution. "Price goes up" is not an exit condition. |
| Liquidity minimum | Only trade names with sufficient volume to exit cleanly within the holding horizon. |

---

## SECTION 8 — KNOWN LIMITATIONS

| Limitation | Implication at this cadence |
|-----------|----------------------------|
| No timing edge | The agent can identify *where* value migrates, not *exactly when* the price moves. Size accordingly — partial entries reduce timing risk. |
| News-driven trades are crowded fast | If the catalyst is obvious, the crowd is already in. Look for the second-order effect of the news, not the direct headline play. |
| $100 capital means commissions matter | Use brokers with zero-commission fractional trading. Verify before executing. |
| Narrative ≠ price, even intraday | A correct bottleneck thesis can still lose money if entry is after the move. Gate 2 (not fully priced) is the most important gate at this cadence. |
| This document goes stale | The power bottleneck is the primary thesis now. It will shift. When the dominant news flow changes, re-examine all pillar priorities and update. |

---

## QUICK REFERENCE — THE THESIS IN FIVE LINES (AGGRESSIVE MODE)

```
1. Own the CONSTRAINT — find the chokepoint the news is surfacing today.
2. Follow the DEPENDENCY CHAIN — the alpha is one layer below the headline.
3. FILTER fast — real bottleneck, not yet priced, specific catalyst. All three or skip.
4. SIZE by conviction — all-in, partial, or fractional. Agent decides. No caps.
5. EXIT when the catalyst is priced, not when you feel good about the name.
```

---

## DECISION FLOW (AGGRESSIVE MODE)

```
Catalyst / news identified
        │
        ▼
[S2] Run central question (fast version)
  ├─ Real bottleneck surfaced? → No → SKIP
  ├─ Not yet priced?           → No → SKIP
  └─ Specific catalyst?        → No → SKIP
        │ All Yes
        ▼
[S4] Run required gates (1–3)
  └─ Any fails → SKIP
        │ All Pass
        ▼
[S4] Score sizing gates (4–6)
  └─ Determine conviction level: Very High / High / Medium / Low
        │
        ▼
[S3] Identify pillar & catalyst type
  └─ Confirm this catalyst type is valid for this pillar
        │
        ▼
[S5] Size the position
  └─ All-in / large / medium / fractional — agent judgment
        │
        ▼
[S7] Log trade
  └─ Ticker | Catalyst | Filter summary | Size rationale | Exit condition
        │
        ▼
EXECUTE
        │
        ▼
Monitor: catalyst resolved? thesis dead? better opportunity?
  └─ Yes to any → EXIT and redeploy
        │
[S6] Check circuit breaker
  └─ If −10% drawdown from peak → PAUSE → re-validate → REBUY allowed
```

---

*Not investment advice. Framework for an autonomous agent operating under human supervision. $100 starting capital. High-risk mode enabled by operator. Verify all data, prices, and liquidity before executing. The only non-negotiable constraints are: no leverage, no options, no shorts, and trade logging on every position.*
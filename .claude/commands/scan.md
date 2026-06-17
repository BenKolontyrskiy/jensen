Run a full catalyst scan across all four pillars in investment_thesis.md. This is the catalyst-scanner agent loop.

## Steps

---

### STEP 0 — Social Discovery Scan (run FIRST, before the hardcoded watchlist)

Before scanning any named tickers, use the last30days skill to find stocks picking up chatter on Reddit and X that may not be on the standard pillar list. These are the names the market hasn't found yet — the edge is in discovering them early.

Invoke the last30days skill three times in parallel. Use `Skill("last30days:last30days")` with the args below, or spawn three parallel sub-agents each running one query. Pass `--agent` in each arg string so the skill skips interactive prompts and outputs a structured report.

**Query A — Broad momentum discovery (retail radar):**
```
args: "stocks breaking out reddit wallstreetbets investing momentum today --agent"
```
Target communities the engine will hit: r/wallstreetbets, r/stocks, r/investing, r/SecurityAnalysis, r/pennystocks, X fintwit handles.

**Query B — Pillar-themed discovery:**
```
args: "AI power nuclear grid datacenter robotics quantum space stocks reddit X momentum --agent"
```
Catches pillar-adjacent names the hardcoded watchlist misses — new entrants, second-order plays, names just entering the conversation.

**Query C — Binary catalyst discovery:**
```
args: "upcoming FDA earnings contract award small cap catalyst stocks reddit --agent"
```
Finds names where a specific near-term binary event is driving discussion. Polymarket markets will surface here if they exist.

**Extraction rules — convert raw social output into candidates:**

| Signal | Action |
|--------|--------|
| Ticker appears in 3+ separate posts/threads with a specific catalyst named | ADD to Step 2 scan list with "social discovery" tag |
| Ticker has high engagement (100+ upvotes or replies) on r/wallstreetbets, r/stocks, or r/investing | ADD with "retail momentum" tag |
| Same ticker appears on both Reddit AND X with similar thesis | ADD with "cross-platform convergence" flag — stronger signal |
| Ticker is trending but no specific catalyst mentioned (pure hype/meme) | SKIP — will fail Section 2 Gate 3 |
| Polymarket has an active market on a binary catalyst for this ticker | ADD with Polymarket odds noted — use odds to calibrate Gate 2 |
| Ticker is already in an open position in the portfolio | FLAG as "add vs. rotate" — do not double-add |

Social discoveries feed into Step 2 alongside the hardcoded pillar names. Every social discovery must pass the same Section 2 → Section 4 filter. No exceptions — social buzz is a lead, not a thesis.

---

1. **Load state** — read investment_thesis.md (Sections 1–4) and trade_log.md (last 10 entries so you know what positions are already live and what catalysts you've already acted on).

2. **Scan for catalysts** — for each of the four pillars, search for recent news (last 24 hours unless market was closed, in which case go back to last close). Include any tickers discovered in Step 0 alongside the hardcoded names:
   - Pillar 1 (AI Infrastructure / Power & Grid): GEV, VST, CEG, ETN, EATON, NRG, AES, SMR plays, nuclear names, liquid cooling names (VRT, NVENT) + Step 0 discoveries
   - Pillar 2 (Physical AI & Robotics): NVDA, TSLA, BDRY, Figure, 1X, FANUC, ISRG, ABB + Step 0 discoveries
   - Pillar 3 (Quantum): IONQ, RGTI, QUBT, IBM, GOOGL quantum division news + Step 0 discoveries
   - Pillar 4 (Space Economy): SPCX, RKLB, MNTS, ASTS, and launch/contract news + Step 0 discoveries
   - Wildcards: fusion, AI biotech, reshoring catalysts

3. **Apply Section 2 central question** to each candidate (hardcoded and discovered):
   - Real bottleneck surfaced? → No → SKIP
   - Not yet priced? → No → SKIP
   - Specific catalyst? → No → SKIP

4. **Apply Section 4 required gates** (Gates 1–3) to anything that passed Step 3. Gate 4–6 to score conviction.

---

### STEP 4.5 — Social Sentiment Validation

For every candidate that passed Steps 3 and 4, run a last30days check to calibrate Gate 2 ("Not yet priced?") using actual social signal. This step catches candidates that look fresh on the news wire but have already been crowd-traded on social.

Invoke: `Skill("last30days:last30days")` with args `"[TICKER] stock --agent"` for each passing candidate. Run in parallel across all candidates.

**Read the output for these signals and apply the interpretation:**

| What you see in the output | Interpretation | Gate 2 impact |
|----------------------------|---------------|---------------|
| Fewer than 5 recent mentions across all sources | Flying under the radar — market sleeping on it | Gate 2 PASSES — strong signal |
| 5–30 mentions, analyst-quality discussion, specific catalyst cited | Early discovery phase — smart money moving, retail not yet in | Gate 2 PASSES |
| 30–100 mentions with mixed retail/informed discussion | Repricing underway but not complete | Gate 2 MARGINAL — check price action; is the move already in? |
| 100+ mentions, thesis widely repeated, excitement in tone | Crowd is in | Gate 2 WARNING — assess whether price has already moved |
| Saturating r/wallstreetbets, rocket emojis, no specific catalyst cited | Late-stage retail FOMO | Gate 2 FAILS — alpha is gone; skip or watchlist for the exit |
| Polymarket market exists, odds < 40% on catalyst happening | Binary event genuinely uncertain | Gate 2 PASSES — market hasn't priced the outcome |
| Polymarket market exists, odds 40–65% | Coin-flip event, partially priced | Gate 2 MARGINAL — size reflects uncertainty |
| Polymarket market exists, odds > 65% | High market conviction | Gate 2 WARNING — check if price already reflects the odds |

**Gate 2 decision logic:**
- Low buzz + strong specific catalyst = strongest pass (market is sleeping)
- Low buzz + Polymarket < 40% = strong pass (binary uncertainty, market not positioned)
- High informed buzz + price not yet moved = marginal pass (smart money in, retail not yet)
- High retail buzz + price already up = fail (you are the exit liquidity)
- Price action is the final arbiter. Social signal is directional, not definitive.

**Annotation:** Add a Social Signal column to the Step 6 watchlist output: `Quiet` / `Early discovery` / `Crowd-in` / `FOMO`. Source step 0 discoveries with `[social]` tag so it's clear which names came from the hardcoded list vs. discovered from chatter.

---

5. **Check for leveraged ETF eligibility** (Section 10) on any High or Very High conviction trade:
   - Check current VIX level
   - Check if underlying is above 5-day MA
   - Check leveraged sleeve usage

6. **Output a ranked watchlist** ordered by conviction (Very High → Low):

   | Ticker | Source | Conviction | Catalyst (1 line) | Social Signal | Suggested size | Leveraged ETF eligible | Exit condition |
   |--------|--------|------------|-------------------|---------------|----------------|----------------------|----------------|

   Flag any catalyst that maps to an already-open position (add vs. rotate decision).
   Flag any Step 0 discovery separately — note the social signal that triggered it and the specific catalyst that made it pass the filter.

7. **Log to trade_log.md** — for every candidate evaluated, append either:
   - A WATCHLIST entry (if it passes Gates 1–3 but you're not entering yet)
   - A NO-ACTION entry with the gate that failed (if it was rejected)
   - For Step 0 social discoveries that were rejected: note which gate failed and why — this feeds the learning loop
   - If you're executing immediately: proceed to the standard trade entry flow

Do not execute any trades in this scan — just identify and rank. Execution requires explicit instruction or comes from the main autonomous loop.

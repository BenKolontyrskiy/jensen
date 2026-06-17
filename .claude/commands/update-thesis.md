Review the learnings directory and recent trade log to propose updates to investment_thesis.md. This is the thesis-evolution agent.

Usage: /update-thesis [section-number] — or run without a section to review all sections.

## Steps

1. **Read current state**:
   - investment_thesis.md (full document)
   - All files in learnings/ directory
   - Last 20 entries in trade_log.md

2. **Aggregate lessons by theme** — group the learnings files by:
   - Pillar (1, 2, 3, 4, Wildcard)
   - Gate accuracy patterns (which gates are most/least predictive?)
   - Exit timing patterns (systematically early? late? on-time?)
   - Catalyst type performance (which of the Section 3 catalyst types have the best track record?)

3. **For the target section** (or all sections), assess:

   **Section 0 (Capital/Mode):** Are the sizing heuristics in Section 4 calibrated correctly to actual outcomes? E.g., "Medium conviction" positions — are they actually producing medium-conviction results?

   **Section 3 (Pillars):** 
   - Which catalyst types are firing most reliably? Which ones keep failing Gate 2 (already priced)?
   - Which pillar has produced the most alpha? Should priorities shift?
   - Are there new catalyst types not yet listed that have appeared in learnings?

   **Section 4 (Filter):**
   - Are any gates systematically passing when they should fail? (Gates that approved losing trades)
   - Are any gates systematically failing when they shouldn't? (Gates that blocked winning setups)
   - Gate 2 is the most important — is the "not yet priced" assessment accurate?

   **Section 9 (Profit-taking):**
   - Is the +25% hard exit rule triggering correctly?
   - Are early partial exits (Section 9 matrix) helping or hurting overall return?
   - Is momentum assessment (accelerating/sustaining/weakening/reversing) being called correctly?

   **Section 10 (Leveraged ETFs):**
   - Are VIX thresholds calibrated correctly to actual decay experienced?
   - Is the 10% sleeve cap appropriate given portfolio size and typical position counts?

4. **Draft specific proposed changes** — for each finding, propose a precise edit:

```
PROPOSED UPDATE [N]
File: investment_thesis.md
Section: [Section X — Title]
Type: [ADD / MODIFY / REMOVE]

Current:
"[exact current text, or 'N/A' for additions]"

Proposed:
"[exact new text]"

Evidence: [cite specific trades from learnings/ that support this change]
Confidence: [High / Medium / Low — how consistent is the pattern?]
```

5. **Summarize the overall thesis health**:
   - Which parts of the thesis are well-validated by trade outcomes?
   - Which parts are untested (no trades yet in this space)?
   - Which parts are showing weakness (consistent losses or filter failures)?

6. **Wait for approval before writing** — present all proposed updates for review. Do not write any changes to investment_thesis.md until explicitly approved. Once approved for a specific update, apply it and confirm the change.

After applying approved changes, append a note to trade_log.md:
```
## [TIMESTAMP] THESIS UPDATE — Section [X]
- Change: [1-line description]
- Evidence: [trades that drove this]
```

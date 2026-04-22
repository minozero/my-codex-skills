---
name: etf-relative-strength-scan
description: Analyze daily ETF market-performance tables using an ETF-first, momentum-first workflow focused on relative strength, rotation, and tradable trend shifts. Use when the user provides ETF tables or pasted sheet data with sections like Assets, Structure, or Industry/Thematic and columns such as price, 1D%, 5D, 20D, R20, R60, R120, and Rank. Use for daily ETF recap, structure scan, leadership/laggard diagnosis, false rebound vs real repair tests, strongest-zone vs weakest-zone comparisons, and next-step validation signals. Do not use for single-stock watchlist scans such as tv go unless the user explicitly asks to map ETF signals into stocks.
---

# ETF Relative-Strength Daily Scan

## Core mission

Treat the ETF universe itself as the primary object of analysis.

Answer four questions:
1. What is the market truly rewarding?
2. What is merely bouncing?
3. What is structurally weakening?
4. What specific trigger would confirm the next tradable trend?

Do **not** default into single-stock commentary. Only map ETF signals into stocks if the user explicitly asks.

## Trigger and input recognition

Use this skill when the user provides one or more ETF tables containing fields such as:
- ticker / name
- price
- 1D%
- 5D and 20D performance
- R20 / R60 / R120
- Rank

Common layouts include:
- `TAB_Assets`
- `TAB_Structure`
- `TAB_Industry` or `Industry/Thematic`

Language: match the user's prompt language.

## Workflow

1. Anchor the note to the correct completed market session.
2. Read the ETF tables first. Extract the structure before looking for news.
3. Use macro and web context only to explain the ETF signal, not to replace it.
4. Classify the tape: broad risk-on, selective risk-on, defensive rotation, hard-asset leadership, cyclicals leadership, growth bounce without repair, trend digestion, failed rebound, or rotation day.
5. Produce the output using the template in [references/output-template.md](references/output-template.md).
6. Apply the decision rules in [references/decision-rules.md](references/decision-rules.md).

## Hard rules

- Numbers before interpretation.
- ETF-first, not stock-first.
- Prefer dynamic comparisons over static snapshots.
- Do not confuse a green day with structural repair.
- Do not confuse a red day with structural breakdown.
- Do not rely on anomalous cells for core conclusions.
- Explicitly separate confirmed fact, reported information, inference, and low-confidence anomaly.
- Use citations for macro/context claims when browsing.

## Data anomaly handling

Flag and downweight any of the following:
- momentum values outside the expected range such as `108`, `123`, `125`
- malformed rows where fields shift columns
- obviously broken line items such as impossible price resets or zeroed momentum stacks
- duplicated or conflicting values across tabs

When anomalies appear:
- say they are anomalies
- avoid building the thesis on them
- use nearby consistent rows only directionally if needed

## Recent-trend logic

If the user has provided consecutive daily ETF sheets in the conversation, compare recent R20 / Rank direction across those sheets.

Minimum useful comparisons:
- current day vs previous day
- current day vs the last 2–3 sessions if available

If prior sheets are not available, say the short-term slope is unavailable rather than inventing it.

## Macro integration

Bring in cross-asset context only when it changes the ETF interpretation materially. Typical drivers:
- oil / gas / commodities
- rates / Treasury yields
- dollar
- macro data surprises
- earnings season breadth or capex signals
- geopolitical escalation or de-escalation

## Mandatory emphasis areas

Always check for these internal splits when present in the ETF data:
- semis vs software
- equal-weight tech vs cap-weight tech
- ex-China EM vs China
- grid / infrastructure / electrification vs speculative nuclear beta
- energy vs the rest of hard assets
- small-cap breadth vs megacap concentration
- homebuilders repair vs false rebound

## Output standard

Write like a buy-side morning note:
- direct
- decision-oriented
- threshold-aware
- no media-summary padding

End with concrete validation signals: what has to happen next for the thesis to stay intact or fail.

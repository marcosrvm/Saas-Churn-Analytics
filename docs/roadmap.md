# Roadmap

## Phase 1 — Business Framing (closed)

Defined the business questions the analysis needs to answer before touching any data. Reasoning: without a clear set of questions, it's easy to produce charts and metrics that are technically correct but don't say anything useful to a business.

Output: a locked three-pillar framework, chosen because it maps onto the customer lifecycle (arrive → generate revenue → leave) — rejected alternatives were a 5-silo structure (mirrors the raw tables instead of the business story) and a 2-pillar structure (too coarse to separate "how revenue grows" from "why customers leave").

- **Pillar 1 — Acquisition & Conversion**: Are we bringing in the right customers, and do they convert to paying accounts?
- **Pillar 2 — Monetization & Growth**: Once customers are in, how does their revenue evolve over time?
- **Pillar 3 — Churn & Its Drivers**: Why do customers leave, and what early signals show up beforehand?

Full detail: `docs/phase1_business_framing.md`.

## Phase 2 — Structural Data Exploration (next)

SQL (PostgreSQL) and Python checks on the five source tables, row counts, duplicates, join integrity, date ranges, nulls, distributions, type issues.

Goal: confirm what the data actually supports, and refine the Phase 1 sub-threads into concrete, measurable questions. The Phase 1 sub-threads were deliberately left broad for exactly this reason, final questions can't be set until the data's real structure is known.

Not started yet, technical environment (GitHub repo, VS Code, pgAdmin4/PostgreSQL) is being set up first.

## Phase 3 — Metric Building (tentative)

Once Phase 2 confirms the data supports it, build the actual metrics as SQL views/queries per pillar: conversion rates, MRR trends, churn rates.

SQL is the source of truth for metrics, not Python, this way the same views can feed both Phase 4's analysis and Phase 5's dashboard without duplicating logic in multiple places.

Scope to be confirmed once Phase 2 closes.

## Phase 4 — Deeper Analysis (tentative)

Python EDA reading from the Phase 3 SQL views (not the raw CSVs) — segments, correlations, and patterns per pillar.

Scope to be confirmed once Phase 3 closes.

## Phase 5 — Dashboard (tentative)

Power BI dashboard connecting to the same Phase 3 SQL views, presenting the findings from Phases 3–4.

Scope to be confirmed once Phase 4 closes.

---

**Note:** only Phase 1 is closed and Phase 2 is confirmed as next. Phases 3–5 are a reasonable current guess at shape, not a locked plan — they may change once earlier phases surface what the data actually supports.
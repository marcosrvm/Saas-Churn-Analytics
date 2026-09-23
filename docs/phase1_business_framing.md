# Phase 1 — Business Framing

## Purpose

Before touching any data, Phase 1 defined the business questions the analysis needs to answer. Reasoning without a clear set of questions, it's easy to produce charts and metrics that are technically correct but don't say anything useful to a business. Framing comes first, data exploration refines it later, it doesn't replace it.

## Process

Started with 10 candidate questions spread across 5 separate areas (Acquisition, Monetization, Retention, Engagement, Support — 2 questions each). This was rejected as too siloed, it organizes the analysis around what data happens to exist, rather than around the business story that data is meant to explain.

Considered a 2-pillar alternative (Grow revenue / Protect revenue), but rejected it as too coarse to separate "how revenue grows" from "why customers leave," which need different evidence.

## Locked output — the three-pillar framework

Chosen because it maps directly onto the customer lifecycle: a customer arrives, generates revenue while they stay, and eventually some leave.

### Pillar 1 — Acquisition & Conversion
Are we bringing in the right customers, and do they convert to paying accounts?

- Sub-thread: trial-to-paid conversion rate, and how it varies by referral source / industry
- Sub-thread: whether certain acquisition channels bring in higher-value or lower-churn-risk accounts

### Pillar 2 — Monetization & Growth
Once customers are in, how does their revenue evolve over time?

- Sub-thread: MRR trend and composition by plan tier
- Sub-thread: expansion (upgrades) vs. contraction (downgrades)

### Pillar 3 — Churn & Its Drivers
Why do customers leave, and what early signals show up beforehand?

- Sub-thread: churn rate and timing patterns
- Sub-thread: which account characteristics, usage drops, or support friction precede churn

## Why the sub-threads are left open

Each sub-thread above is deliberately broad, not a finalized, measurable question. Final questions can't be set until the actual structure of the data has been checked, grain, nulls, cardinality, date ranges. That check belongs to Phase 2.

## Dataset

Synthetic data simulating a B2B SaaS company, across five tables:

- accounts: account info, industry, country, signup date, referral source, plan tier, seats
- subscriptions: plan tier, MRR/ARR, upgrades, downgrades, churn, billing frequency
- feature_usage: product usage events per subscription, usage count/duration, errors
- support_tickets: response/resolution time, priority, satisfaction, escalation
- churn_events: churn date, reason code, refund, preceding upgrade/downgrade, reactivation

## What "churn" means in this dataset

Churn is defined as the event where an account ends its relationship with RavenStack, recorded in the churn_events table. The accounts table also includes a churn_flag field, but churn_events is treated as the official source of truth for whether and when a churn event occurred.

## Status

Phase 1 is closed. Its output, the three pillar framework above, is locked and carries forward into Phase 2 (structural data exploration), where the sub-threads will be refined into concrete, measurable questions based on what the data actually supports.
# RavenStack — SaaS Subscription & Churn Analytics

End-to-end SQL + Python project analyzing subscription growth, upgrades/downgrades, feature adoption, support patterns, and churn for RavenStack, a fictional AI-powered collaboration platform.

### Overview
This project simulates the analytical workflow of a Data Analyst working in a SaaS environment, using a structured, phase-based approach: business framing first, then data exploration.

- SQL for feature engineering and metric generation
- Python for data validation and EDA
- Business interpretation to identify insights that support decision-making

### Project Phases

**Phase 1 — Business framing (closed).** Defined the business questions through a three-pillar framework that maps to the customer lifecycle:
- Pillar 1 — Acquisition & Conversion: are we bringing in the right customers, and do they convert?
- Pillar 2 — Monetization & Growth: how does revenue evolve once customers are in?
- Pillar 3 — Churn & Its Drivers: why do customers leave, and what signals precede it?

**Phase 2 — Structural data exploration (current).** SQL and Python exploration of the five source tables to validate the data and refine the open sub-questions from Phase 1.

## Dataset & Sources
Synthetic SaaS data designed to replicate a real B2B subscription business. Main tables:

- accounts: customer account info, industry, country, signup date, plan tier
- subscriptions: plan tier, MRR/ARR, upgrades, downgrades, billing frequency
- feature_usage: product usage events, usage count/duration
- support_tickets: response/resolution time, priority, satisfaction
- churn_events: churn date, reason code, refund, reactivation

## Project Structure

project/
├── data/
│   └── raw/
├── docs/
├── sql/
├── notebooks/
├── src/
├── README.md
└── requirements.txt

## Languages & tools
- Python (Pandas, NumPy)
- SQL (PostgreSQL)
- Power BI (dashboard coming soon)
- Git & GitHub

## Status
Phase 1 complete. Phase 2 (data exploration) in progress.
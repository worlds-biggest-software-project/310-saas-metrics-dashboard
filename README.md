# SaaS Metrics Dashboard

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source unified view of MRR, churn, LTV, CAC, NPS, and forecasting for subscription businesses.

SaaS Metrics Dashboard is a candidate project to build a subscription analytics platform that consolidates the financial, retention, and customer-health metrics SaaS founders track today across separate tools. It is aimed at SaaS founders, CFOs, RevOps teams, and investors who need board-ready reporting and operational insight without paying enterprise pricing or stitching together ChartMogul, Baremetrics, Amplitude, and Visible.

---

## Why SaaS Metrics Dashboard?

- ChartMogul has no native forecasting and only AND-based filter logic; users must calculate projections manually.
- Baremetrics offers no customer merge/deduplication, no multi-entity or multi-currency consolidation, and pricing becomes prohibitive at higher MRR.
- ProfitWell's analytics tier is free but shallow, non-customisable, and increasingly tied to the Paddle ecosystem after acquisition.
- Mosaic and Maxio deliver CFO-grade depth but are custom-priced in the tens of thousands annually and require finance-team sophistication.
- No open-source equivalent exists for financial SaaS metrics (MRR / ARR / churn). PostHog covers product analytics under MIT, but the financial-metrics category has no self-hostable, data-sovereign option.
- Cross-source metric reconciliation, peer benchmarking outside Paddle's free tier, and AI-driven scenario modelling for non-finance teams are recurring gaps across all incumbents.

---

## Key Features

### Core Subscription Metrics

- MRR, ARR, ARPA, NRR, GRR, churn (gross and net), LTV, and CAC calculation from billing data
- MRR movement breakdown: new, expansion, contraction, churn, and reactivation
- Historical trend charts with configurable date ranges
- Cohort analysis: customer and revenue retention by signup month
- Documented metric formulas displayed alongside charts to ensure investor comparability

### Billing & Data Integration

- Native Stripe ingestion as the minimum viable billing connector
- Optional Paddle, Chargebee, Recurly, and Braintree connectors
- REST API for importing data from non-standard or custom billing systems
- Subscription lifecycle event ingestion (new, expansion, contraction, churn, reactivation)
- Multi-source aggregation across billing processors

### Segmentation, Forecasting & Reporting

- Customer segmentation by plan, geography, payment processor, and custom attributes
- 12-month MRR forecasting using cohort buildup or driver-based models
- Role-based views for founder, team, investor, and read-only access
- CSV / Excel export and embeddable investor-update charts
- Cancellation Insights: embedded exit survey feeding churn-reason analysis

### AI-Augmented Analysis

- Natural-language metric querying ("what is driving churn this quarter?") with data-backed narrative answers
- Automated anomaly detection with Slack / email alerts when metrics deviate from trend
- Churn prediction using leading indicators from product usage, billing, and support data simultaneously
- Scenario modelling for pricing changes, expansion motions, and churn-reduction initiatives
- AI-generated board-deck narratives from metric movements

### Benchmarking & Transparency

- Anonymised peer benchmarking against companies at the same ARR band and growth stage
- Public metrics pages for open-startup-style transparency
- Optional self-hosted deployment for data-sovereign customers

---

## AI-Native Advantage

Incumbents added AI churn scoring (ChartMogul) and predictive segmentation (Amplitude) in 2025–2026, but these capabilities remain locked behind paid tiers and single data domains. An AI-native build can correlate product usage, billing events, and support signals together to flag at-risk accounts earlier, expose natural-language explanations of metric movements without SQL, run scenario forecasts on live data, and auto-draft investor-ready commentary — collapsing the days CFOs currently spend preparing board decks into minutes.

---

## Tech Stack & Deployment

The reference design targets a Stripe-first ingestion path with REST APIs for additional processors and custom billing systems. Intended deployment modes are managed cloud and self-hosted (mirroring PostHog's MIT-licensed model in the adjacent product-analytics category). Relevant standards include GAAP SaaS metric definitions, ASC 606 / IFRS 15 for revenue recognition, the AARRR (Pirate Metrics) framework for PLG measurement, and OpenTelemetry / Segment-compatible event schemas for connecting product usage to financial metrics.

---

## Market Context

The broader BI and analytics market exceeds $35 billion globally; the SaaS subscription-analytics sub-segment is smaller but fast-growing, with ChartMogul reporting data from 2,500+ SaaS businesses. Incumbent pricing spans free (ProfitWell, ChartMogul free tier) through $129/month (Baremetrics) and $995/month (Amplitude), with Mosaic and Maxio custom-priced in the tens of thousands annually. Primary buyers are SaaS founders and CEOs tracking weekly growth health, CFOs and finance teams preparing board reporting, RevOps teams measuring CAC payback, and investors benchmarking portfolio company performance.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.

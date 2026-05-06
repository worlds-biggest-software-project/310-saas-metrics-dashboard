# SaaS Metrics Dashboard — Feature & Functionality Survey

> Candidate #310 · Researched: 2026-05-03

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| ChartMogul | Subscription analytics SaaS | Commercial; free to $10K MRR, paid from $149/month | https://chartmogul.com |
| Baremetrics | Subscription analytics SaaS | Commercial; from $129/month | https://baremetrics.com |
| ProfitWell (Paddle) | Revenue analytics SaaS | Commercial; analytics free, automation paid | https://paddle.com/profitwell-metrics |
| Mosaic (HiBob) | Strategic finance platform | Commercial; custom enterprise pricing | https://mosaic.tech |
| Maxio (SaaSOptics) | Revenue operations platform | Commercial; custom pricing | https://maxio.com |
| Stripe Sigma | SQL analytics on billing data | Commercial; add-on to Stripe (~$0.02/1K rows) | https://stripe.com/sigma |
| Amplitude | Product analytics SaaS | Commercial; free plan, paid from $995/month | https://amplitude.com |
| Mixpanel | Event-based product analytics | Commercial; free plan, paid from $20/month | https://mixpanel.com |
| PostHog | All-in-one product analytics | Open source (MIT); cloud or self-hosted | https://posthog.com |
| Visible.vc | Investor reporting & KPI platform | Commercial; from $79/month | https://visible.vc |

---

## Feature Analysis by Solution

### ChartMogul

**Core features**
- MRR, ARR, ARPA, and ASP tracking with historical trends
- Gross and net MRR churn rate calculation and charting
- Cohort analysis: customer churn and net MRR retention by signup cohort
- Customer lifetime value (CLV/LTV) segmentation
- MRR movement breakdown: new, expansion, contraction, churn, reactivation
- Customer growth tracking with plan and segment filtering
- CRM activity import (opportunities, tasks, call notes)
- 1-click integrations with Stripe, Braintree, Chargify, Recurly, and PayPal
- AI churn prediction and expansion opportunity scoring
- Custom attributes on customer records for segmentation

**Differentiating features**
- Purpose-built subscription data model with explicit MRR movement taxonomy
- Multi-source aggregation: combines data from multiple billing processors
- AI-native churn and expansion scoring (announced 2025–2026)
- API-first design enabling custom data import for non-standard billing systems

**UX patterns**
- Pre-built chart library requiring minimal configuration after data connection
- Metric definitions displayed alongside charts to reduce misinterpretation
- Segment-based filtering applied globally across all dashboards

**Integration points**
- REST API for data import (customers, subscriptions, charges, plans)
- Native 1-click connections to major billing processors
- Webhooks for subscription lifecycle events
- SDKs available for Go, Python, Ruby, PHP, JavaScript, Java, .NET

**Known gaps**
- Data discrepancies reported between ChartMogul and Stripe totals
- No OR-based filter logic (only AND parameters supported)
- Limited Zapier/Databox integrations for downstream workflows
- No native forecasting: users must calculate averages manually
- No mobile app reporting depth comparable to web dashboard
- No ability to correct faulty historical metric entries after the fact

**Licence / IP notes**
- Proprietary SaaS; no open-source components in the analytics engine. API client libraries are MIT-licensed on GitHub.

---

### Baremetrics

**Core features**
- Real-time MRR, ARR, LTV, ARPA, and churn tracking
- Cancellation Insights: exit survey for churned customers with trend analysis
- Recover: automated dunning with smart payment retry and targeted escalation
- Cohort, buildup, and driver-based MRR forecasting
- Customisable dashboards with role-based views and saved filter sets
- Customer segmentation by location, payment processor, and custom attributes
- Trial conversion and upgrade funnel tracking
- Public metrics pages for transparent "open startup" reporting

**Differentiating features**
- Built-in dunning (payment recovery) combined with the analytics layer — no separate tool needed
- Cancellation Insights collects qualitative churn reasons alongside quantitative metrics
- "Open Startup" public dashboards: Baremetrics pioneered real-time public metric sharing

**UX patterns**
- Dashboard-first approach: key metrics visible immediately after billing connector setup
- Smart Dashboards with pre-configured recommended metric groups
- Onboarding wizard connects Stripe or Paddle in under 5 minutes

**Integration points**
- REST API for customers, subscriptions, plans, and charges (supports non-standard billing)
- Stripe, Paddle, Braintree, Chargebee, App Store, Google Play native integrations
- Webhooks for subscription change events
- Community SDK in Ruby; unofficial PHP and JavaScript SDKs on GitHub

**Known gaps**
- No customer merge/deduplication functionality
- Data can diverge from Stripe when Stripe settings are non-standard
- Limited customisation of reports beyond the pre-built templates
- No multi-entity or multi-currency consolidation for complex businesses
- Pricing can be prohibitive for small teams with high MRR

**Licence / IP notes**
- Proprietary SaaS; no open-source edition. Community API wrapper libraries are MIT-licensed.

---

### ProfitWell (Paddle)

**Core features**
- Free MRR, LTV, CAC, churn, and cohort analytics from billing data
- Benchmarking against 34,000+ subscription companies in the ProfitWell network
- Revenue recognition reporting aligned to subscription periods
- Metrics updated every 3–6 hours (near real-time)
- Cohort reports for revenue retention and expansion analysis
- Retain: automated churn prevention and payment recovery (paid add-on)
- Metrics API for programmatic access to subscription data

**Differentiating features**
- Completely free analytics tier with no data volume caps
- Anonymous peer benchmarking against a large network of subscription companies
- Deep integration with Paddle's billing infrastructure for Paddle-native companies

**UX patterns**
- Zero-friction onboarding: 5-minute setup via billing connector
- Dashboard is read-oriented and non-configurable; simplicity over flexibility

**Integration points**
- Metrics API (REST) for retrieving timeseries subscription data
- Native connection to Stripe, Recurly, Braintree, Chargebee, Zuora, and Paddle Billing
- Paddle Developer portal documents seven new /metrics endpoints added in 2026

**Known gaps**
- Analytics depth is shallower than ChartMogul; fewer segmentation options
- Product heavily oriented toward the Paddle ecosystem after the acquisition
- Dashboard is not customisable — users cannot build custom views
- No built-in forecasting beyond basic trend lines

**Licence / IP notes**
- Proprietary SaaS; analytics tier is free but Retain/Engage are paid. No open-source edition.

---

### Mosaic (now part of HiBob)

**Core features**
- 150+ pre-built SaaS metrics including ARR, MRR, NRR, CAC, LTV, and cohort retention
- Real-time financial planning (FP&A) with scenario modelling
- Automated board report generation (board packages reduced from 2 days to 2 hours)
- Cash-flow forecasting and burn rate analysis
- Multi-entity consolidation for companies with complex legal structures
- 30+ native integrations with ERP, CRM, HRIS, and billing systems
- Custom formula builder for bespoke metric definitions

**Differentiating features**
- Bridges the gap between SaaS operational metrics and GAAP financial statements
- CFO-level strategic finance layer: OKR alignment, headcount planning, and M&A modelling
- Automated board deck narrative generation with supporting charts

**UX patterns**
- Finance-team-first UX: spreadsheet-familiar interface with formula editing
- Role-based access control separating board, executive, and analyst views
- Presentation-mode for board and investor reporting

**Integration points**
- NetSuite, Salesforce, Snowflake, BambooHR, Gusto, Stripe native integrations
- Real-time data sync across all connected sources
- API access for custom data pipelines (documentation on mosaic.tech developer portal)

**Known gaps**
- Enterprise pricing puts it out of reach for early-stage companies
- Requires finance team sophistication to configure and interpret outputs
- Acquired by HiBob (an HR platform) in February 2025 — product roadmap uncertainty
- Less useful for product-led or B2C SaaS companies with simpler billing structures

**Licence / IP notes**
- Proprietary SaaS; no open-source edition. Acquired by HiBob for $35M in February 2025.

---

### Maxio (SaaSOptics)

**Core features**
- GAAP/IFRS-compliant revenue recognition automation (ASC 606 / IFRS 15)
- Subscription lifecycle management: billing, invoicing, and ARR tracking
- Custom dashboards with drill-down reporting and 30+ one-click report templates
- ARR summary, DSO, and cohort retention reports
- Dunning and payment retry automation
- Salesforce AppExchange integration for quote-to-cash workflows
- Supports complex B2B contract structures (usage-based, milestone billing, multi-element)

**Differentiating features**
- Purpose-built for complex B2B subscription billing — handles variable consideration, contract modifications, and multi-element arrangements that simpler tools cannot
- Only platform in this set with full revenue recognition compliance built in
- Manages $10 billion in revenue across 2,300+ customers

**UX patterns**
- Finance and accounting-oriented UX; not self-serve for non-finance users
- Workflow-driven interface guiding users through subscription and billing lifecycle stages

**Integration points**
- Salesforce CRM native integration
- NetSuite ERP integration
- REST API for subscription management and reporting data export
- Stripe payment processing connector

**Known gaps**
- Less developer-friendly than ChartMogul or Baremetrics for custom integrations
- Not suited for B2C or PLG companies with high-volume, low-value subscriptions
- Product analytics (activation, feature usage) not available — finance metrics only
- Pricing not published; enterprise sales process required

**Licence / IP notes**
- Proprietary SaaS; formed from the merger of SaaSOptics and Chargify under the Maxio brand. No open-source components.

---

### Stripe Sigma

**Core features**
- SQL and AI-powered analytics layer on top of live Stripe billing data
- Pre-built query templates for MRR trends, churn, subscription growth, and failed payments
- AI assistant (Sigma Assistant) converts plain-English questions into SQL queries
- Data Pipeline integration: export Stripe data to Snowflake, Redshift, Databricks, BigQuery, S3, GCS, or Azure Blob
- No data syncing delay — operates directly on live Stripe transaction data
- Read-only SQL access for accounting reconciliation and custom metric tracking

**Differentiating features**
- Data is sourced from Stripe itself — the authoritative billing system of record with zero lag
- AI query assistant lowers the SQL barrier for non-technical founders
- Direct warehouse export enables custom analytics stacks and data mesh architectures

**UX patterns**
- Developer-first: SQL query editor inside the Stripe Dashboard
- No pre-built SaaS KPI dashboard UI; users must write or adapt queries
- Suitable for teams with analytics engineering capability

**Integration points**
- Native to Stripe Dashboard; no separate login or tool required
- Data Pipeline exports to all major cloud warehouses and object stores
- Stripe API provides full subscription, invoice, customer, and meter data via REST

**Known gaps**
- Stripe-only: no cross-processor aggregation (unlike ChartMogul)
- Requires SQL proficiency; not self-serve for non-technical founders
- No built-in dashboard or visualisation layer — raw query output only
- Priced per query row processed ($0.02/1K rows), which can escalate for large datasets

**Licence / IP notes**
- Proprietary Stripe add-on. No open-source edition. Data Pipeline usage is a separate Stripe product with its own pricing.

---

### Amplitude

**Core features**
- Event-based product analytics with trend graphs, funnels, retention, and flows
- Behavioral cohort analysis and audience segmentation
- AI Predictions: segment users by likelihood to perform a future action
- Natural-language query interface ("Ask Amplitude" / Global Agent)
- Session Replay Agent with AI-powered summary and Magic Playlists
- Dashboard Monitoring Agent: detects metric changes and notifies via Slack/email
- A/B testing and feature flag management (Amplitude Experiment)
- Account-level analytics for B2B SaaS (company-level cohorts)

**Differentiating features**
- Most mature agentic AI layer in 2026: four specialised agents covering monitoring, session review, experimentation, and feedback analysis
- Predictive segmentation available for communication frequency, dynamic pricing, and content personalisation
- Combines product analytics with experimentation in a single platform

**UX patterns**
- Chart builder with drag-and-drop event selection; no SQL required for standard queries
- Dashboard library with role-specific recommended views (growth, retention, monetisation)
- Notebook format for analysis workflows combining charts, text, and data

**Integration points**
- SDKs for JavaScript, iOS, Android, React Native, Python, Java, Go, .NET, Ruby, PHP
- Webhooks for custom monitor alerts
- Cohort Webhooks for syncing audience segments to downstream tools
- 200+ data destination and source connectors in the Amplitude Data catalog
- REST API with Postman collection in the Amplitude Developers Postman profile

**Known gaps**
- Financial SaaS metrics (MRR, ARR, CAC payback) are not first-class; product analytics is the primary focus
- Paid plan pricing starts at $995/month — cost-prohibitive for early-stage companies
- Data warehouse connector (Amplitude Data) is a separate paid module
- Steep learning curve for non-analytics teams; complex query model

**Licence / IP notes**
- Proprietary SaaS; Amplitude is publicly traded (AMPL). No open-source analytics engine.

---

### Mixpanel

**Core features**
- Event-based analytics with Insights, Funnels, Retention, Flows, and Paths reports
- Behavioral cohorts integrated with every report type
- Session Replay with AI-powered summaries, React Native support, and Magic Playlists
- Warehouse Connectors to Snowflake, BigQuery, Databricks, and Redshift
- Metric Trees for hierarchical KPI decomposition
- Spark AI query builder (natural language to analytics query)
- Feature flags and integrated experiments

**Differentiating features**
- Best-in-class funnel and retention analytics with drag-and-drop configuration
- Session Replay natively embedded in the product analytics flow (same tool, same user)
- Warehouse-native mode: query data where it lives without replication

**UX patterns**
- Self-serve, non-SQL analytics for business users; SQL layer available for power users
- Query results annotated with cohort context for cross-report consistency
- Progressive disclosure: simple views by default with drilldown available

**Integration points**
- SDKs for JavaScript, iOS, Android, Python, Ruby, Java, Go, PHP
- Ingestion API (REST) for server-side event tracking
- Data Pipelines for exporting to cloud warehouses
- Cohort sync webhook spec for partner integrations
- Zapier and Segment native integrations

**Known gaps**
- Not purpose-built for financial SaaS metrics (MRR, CAC, LTV); revenue metrics require custom event design
- Account-level analytics for B2B SaaS is less mature than Amplitude
- Warehouse Connectors require technical setup not accessible to non-engineers
- Enterprise pricing for advanced features

**Licence / IP notes**
- Proprietary SaaS; no open-source edition. SDKs are MIT-licensed on GitHub.

---

### PostHog

**Core features**
- Product analytics: trends, funnels, retention, paths, and stickiness
- Web analytics with page view and session tracking
- Session Replay and Heatmaps
- Feature flags and A/B experimentation
- Error tracking
- Customer surveys
- Data warehouse (built-in, powered by ClickHouse)
- Customer Data Platform (CDP)
- AI product assistant for debugging and feature development
- LLM analytics for AI-native products (token usage, model latency, conversation quality)

**Differentiating features**
- Only tool in this set available as open source (MIT) with full self-hosting support
- All-in-one developer platform: replaces Amplitude + LaunchDarkly + Hotjar + Segment in a single product
- LLM observability is a unique native capability for teams building AI products
- SOC 2, GDPR-ready, and HIPAA-compliant on cloud; self-hosted deployments enable full data sovereignty

**UX patterns**
- Developer-first onboarding: snippet or SDK; no sales process required
- Free tier with generous limits (1M events, 5K recordings, 1M flag requests per month)
- Unified interface across all product tools — no context switching between analytics and flags

**Integration points**
- SDKs for JavaScript, Python, iOS, Android, React Native, Ruby, Go, PHP, Java, .NET, and more
- REST API with rate limits (240/min, 1200/hour) for analytics and metadata endpoints
- Warehouse Connector for Snowflake and BigQuery
- Segment and Rudderstack source compatibility (drop-in replacement)
- Open-source self-hosted deployment via Docker/Kubernetes

**Known gaps**
- Self-hosted edition scales to ~100K events/month before migration to cloud is recommended
- No native financial SaaS metrics (MRR, ARR, churn) — requires custom event design
- Less mature AI prediction/scoring features compared to Amplitude
- Community support for self-hosted; SLA-backed support requires cloud plan

**Licence / IP notes**
- Core platform: MIT licence on GitHub. Enterprise add-ons (SSO, advanced permissions, HIPAA BAA) are proprietary.

---

### Visible.vc

**Core features**
- Investor update builder with rich-text editor and embedded KPI charts
- Pre-built update templates (standard, Y Combinator, Techstars minimum viable update)
- Fundraising CRM with pipeline management and investor contact tracking
- Secure data room with per-slide deck analytics
- Portfolio KPI tracking for VC funds (540+ funds on platform)
- Automated LP reporting and tear sheet generation
- KPI metric tracking with historical trend charts
- Slack, Stripe, Salesforce, HubSpot, Mixpanel, Google Analytics, QuickBooks, Xero, and Zapier integrations

**Differentiating features**
- Purpose-built for investor relationship management alongside metric reporting — unique category positioning
- Portfolio monitoring mode for VC fund investors tracking multiple companies simultaneously
- Per-slide deck analytics: investors see which slides received attention

**UX patterns**
- Founder-first UX designed for monthly or quarterly reporting cadence
- Template-driven workflow: select template, populate metrics, distribute
- Dual interface: founder dashboard and investor portfolio monitoring view

**Integration points**
- Native connections to Stripe, QuickBooks Online, Xero, Salesforce, HubSpot, Mixpanel, Google Analytics, and Slack
- Zapier connector for custom automation
- REST API for programmatic metric submission (enterprise tier)

**Known gaps**
- Primarily a reporting and communication tool; lacks deep operational analytics
- Metric calculation logic is not disclosed or customisable
- No dunning, forecasting, or product analytics capabilities
- VC fund monitoring tier has separate pricing from founder tier

**Licence / IP notes**
- Proprietary SaaS; no open-source edition. Chicago-based, founded 2014.

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- MRR, ARR, churn rate, LTV, CAC, ARPA, and NRR calculation from billing data
- Stripe integration as minimum viable billing connector
- Cohort analysis: customer and revenue retention by signup period
- Historical trend charts for all core metrics
- Subscription lifecycle event tracking (new, expansion, contraction, churn, reactivation)
- Role-based access control for team and investor views
- CSV/Excel data export

### Differentiating Features
- Multi-source billing aggregation across processors (ChartMogul strength)
- Built-in dunning and payment recovery (Baremetrics Recover; ProfitWell Retain)
- GAAP/IFRS-compliant revenue recognition (Maxio only in this set)
- Agentic AI: natural-language querying, monitoring agents, and predictive scoring (Amplitude leading)
- Investor reporting and fundraising CRM (Visible unique category)
- Self-hosting and data sovereignty (PostHog only)
- Anonymous peer benchmarking against large subscription company network (ProfitWell)

### Underserved Areas / Opportunities
- Cross-source metric consistency: discrepancies between platform and billing processor numbers are a recurring complaint with no automated reconciliation available
- Qualitative + quantitative churn analysis in a single workflow: most tools separate exit surveys from metric dashboards
- PLG / product-led growth metrics: activation rates, feature adoption, and time-to-value are not natively tracked in financial-metric tools (ChartMogul, Baremetrics, Maxio)
- Multi-currency and multi-entity consolidation for globally distributed SaaS companies below enterprise pricing tiers
- Open-source financial SaaS metrics: PostHog covers product analytics open source, but no equivalent exists for MRR/ARR/churn dashboards
- AI-driven scenario modelling accessible to non-finance teams (Mosaic covers this for enterprise but no affordable equivalent exists)
- Automatic peer benchmarking with stage-appropriate comparisons (ProfitWell has this but only for Paddle/free-tier users)

### AI-Augmentation Candidates
- Churn prediction using leading indicators from product usage, billing, and support data simultaneously (beyond single-source signals)
- Natural-language metric explanation: "What is driving the NRR decline this quarter?" with AI-synthesised narrative
- Automated anomaly detection on metric timeseries with root-cause hypothesis generation
- AI-generated board pack narratives from metric movements without manual CFO writing
- Intelligent dunning: personalised payment recovery messaging optimised per customer segment
- Cohort benchmarking: AI matching of a company to peer cohort and automated gap commentary

---

## Legal & IP Summary

No patent-protected features were identified across the solutions surveyed. All SaaS metric calculation methodologies (MRR, ARR, churn, LTV, CAC) are industry-standard formulas documented in public literature and not proprietary. API client libraries for ChartMogul, Baremetrics, Amplitude, Mixpanel, and PostHog are MIT-licensed on GitHub and freely reusable. PostHog's core product is MIT-licensed and can be forked and extended. Stripe Sigma is a proprietary Stripe product and its query engine cannot be reproduced, but the underlying billing data schema and metric definitions are publicly documented in Stripe's developer docs. No copyright or licensing concerns were identified that would affect building an AI-native open-source alternative in this category.

---

## Recommended Feature Scope

**Must-have (MVP)**
- Connect to Stripe (and optionally Paddle, Chargebee, or via API for custom billing) to ingest subscription data
- Calculate and display MRR, ARR, churn rate (gross and net), NRR, LTV, CAC, ARPA, and MRR movement breakdown
- Cohort analysis: customer and revenue retention by signup month
- Historical trend charts for all metrics with configurable date ranges
- Basic customer segmentation (by plan, geography, or custom attribute)
- Role-based access: founder, team, investor, and read-only views

**Should-have (v1.1)**
- AI natural-language query: ask "what is driving churn?" and receive a data-backed explanation
- Automated anomaly detection with Slack/email alerts when metrics deviate from trend
- Peer benchmarking: compare metrics against anonymised companies at the same ARR band
- Dunning integration: connect to Stripe's retry logic and surface recovery metrics
- Cancellation Insights: embedded exit survey feeding churn reason analysis
- Forecasting: 12-month MRR projection using cohort-based buildup or driver-based model

**Nice-to-have (backlog)**
- Multi-source billing aggregation (Stripe + Paddle + Recurly in a single dashboard)
- GAAP/IFRS revenue recognition alignment notes alongside operational MRR/ARR
- Investor reporting module with embeddable charts and update email templates
- PLG bridge: connect product usage events (PostHog or Mixpanel) to financial metrics for activation-to-revenue correlation
- Public metrics page for open-startup transparency
- Self-hosted deployment option for data-sovereign customers

# Standards & API Reference

> Project: SaaS Metrics Dashboard · Generated: 2026-05-03

## Industry Standards & Specifications

### Accounting & Revenue Standards

**ASC 606 — Revenue from Contracts with Customers (FASB)**
- URL: https://www.fasb.org/Page/ShowPdf?path=ASU+2014-09.pdf
- The US GAAP standard governing revenue recognition. Relevant because MRR and ARR are operating metrics, not recognised revenue; dashboards should clarify which formula is used and how it relates to ASC 606 recognised revenue for investor comparability.

**IFRS 15 — Revenue from Contracts with Customers (IASB)**
- URL: https://www.ifrs.org/issued-standards/list-of-standards/ifrs-15-revenue-from-contracts-with-customers/
- The international counterpart to ASC 606 using the same five-step recognition model. The key difference is the collectibility threshold (50% under IFRS 15 versus 75–80% under ASC 606). Multi-currency SaaS dashboards serving international companies must account for both standards.

**GAAP SaaS Metric Definitions (industry de-facto)**
- URL: https://a16z.com/16-metrics/ (Andreessen Horowitz canonical SaaS metrics reference)
- There is no single ISO standard for MRR, ARR, NRR, GRR, CAC, LTV, or churn calculation. Dashboards must document their formula choices explicitly. The a16z 16 Metrics and ChartMogul SaaS Metrics Library are the most widely cited definitional references used in practice.

---

### ISO Standards

**ISO/IEC 27001:2022 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- Defines requirements for establishing, implementing, maintaining, and continually improving an information security management system. Relevant to any SaaS analytics dashboard storing sensitive billing and revenue data. SOC 2 Type II certification maps closely to ISO 27001 controls.

**ISO/IEC 27701:2019 — Privacy Information Management**
- URL: https://www.iso.org/standard/71670.html
- Extension to ISO 27001 and ISO 27002 for privacy information management, acting as a framework for PII controllers and processors. Relevant because analytics dashboards aggregate customer subscription data that qualifies as personal data under GDPR.

**ISO 19731:2017 — Digital Analytics and Web Analyses**
- URL: https://www.iso.org/standard/66187.html
- Covers vocabulary and service requirements for digital analytics and web analyses for market, opinion, and social research. The closest ISO standard to the analytics domain; relevant as a definitional baseline for analytics terminology.

**ISO/IEC 24668:2022 — Process Management Framework for Big Data Analytics**
- URL: https://www.iso.org/standard/78368.html
- Framework for AI and big data analytics process management. Relevant if the dashboard incorporates AI-driven churn prediction or anomaly detection at scale.

---

### W3C & IETF Standards

**RFC 6749 — The OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- Core OAuth 2.0 specification defining the authorization framework for third-party access to protected resources. Required for any dashboard that authenticates users against identity providers or accesses billing APIs on behalf of users.

**RFC 7636 — Proof Key for Code Exchange (PKCE)**
- URL: https://datatracker.ietf.org/doc/html/rfc7636
- Extension to the OAuth 2.0 Authorization Code flow that prevents authorization code interception attacks. Required for all browser-based and native clients per OAuth 2.1 best practices; should be implemented by default in any SaaS dashboard.

**RFC 9700 — Best Current Practice for OAuth 2.0 Security**
- URL: https://datatracker.ietf.org/doc/rfc9700/
- The current OAuth 2.0 security best practice document. Mandates PKCE for all clients, deprecates the implicit flow, and recommends binding refresh tokens to client instances.

**OpenID Connect Core 1.0**
- URL: https://openid.net/specs/openid-connect-core-1_0.html
- Identity layer built on top of OAuth 2.0. The standard for implementing SSO in SaaS dashboards, enabling "sign in with Google / GitHub / Okta" and carrying user identity claims.

**RFC 7807 — Problem Details for HTTP APIs**
- URL: https://datatracker.ietf.org/doc/html/rfc7807
- Standard format for conveying machine-readable error details in HTTP API responses. Relevant to implementing consistent, parseable error responses in the dashboard's own REST API.

**RFC 8288 — Web Linking**
- URL: https://datatracker.ietf.org/doc/html/rfc8288
- Defines the Link header field for hypermedia linking in HTTP APIs, underpinning pagination patterns in REST API responses — directly relevant to the dashboard's API design for paginated metric timeseries results.

**W3C WCAG 2.2 (ISO/IEC 40500:2025)**
- URL: https://www.w3.org/TR/WCAG22/
- Web Content Accessibility Guidelines, formalised as an ISO standard in October 2025. Relevant for any customer-facing dashboard UI to meet accessibility requirements for enterprise procurement.

---

### Data Model & API Specifications

**OpenAPI Specification 3.1 (OAS 3.1)**
- URL: https://spec.openapis.org/oas/v3.1.0
- The de-facto standard for documenting REST APIs. Any dashboard exposing a public or partner API should publish an OAS 3.1 document. Enables SDK generation, Postman collection export, and automated API testing.

**JSON Schema (Draft 2020-12)**
- URL: https://json-schema.org/specification
- Standard for describing and validating JSON data structures. Used by OpenAPI 3.1 for request/response schema definitions, and by Segment Protocols for validating analytics event payloads.

**Segment Spec (Twilio Segment)**
- URL: https://segment.com/docs/connections/spec/
- De-facto industry standard for product analytics event schemas. Defines the Track, Identify, Page, Group, and Alias call types along with common fields (anonymousId, userId, timestamp, context). A SaaS metrics dashboard ingesting product usage data should align to the Segment Spec for interoperability with the broad ecosystem of CDP and analytics tools.

**Segment B2B SaaS Spec**
- URL: https://segment.com/docs/connections/spec/b2b-saas/
- Extension of the Segment Spec covering B2B SaaS-specific events (Signed Up, Trial Started, Trial Converted, Account Created, Account Deleted). Provides standardised event naming conventions for the exact use case of a SaaS metrics dashboard's data ingestion layer.

**OpenTelemetry Metrics Data Model**
- URL: https://opentelemetry.io/docs/specs/otel/metrics/data-model/
- CNCF standard for representing and exporting metrics, logs, and traces. Relevant if the dashboard exposes its own metrics for observability, or if it ingests infrastructure and API usage metrics alongside subscription data.

---

### Security & Privacy Standards

**GDPR — General Data Protection Regulation (EU) 2016/679**
- URL: https://gdpr.eu/
- Applies to any analytics dashboard processing personal data of EU residents. Requires lawful basis for processing, data subject rights (access, erasure, portability), and Data Processing Agreements (DPAs) under Article 28. In 2026, fines reached €20M or 4% of global annual turnover for serious violations.

**SOC 2 Type II (AICPA Trust Services Criteria)**
- URL: https://www.aicpa.org/resources/landing/system-and-organization-controls-soc-suite-of-services
- The de-facto SaaS security certification in North America. Covers Security (mandatory), Availability, Confidentiality, Processing Integrity, and Privacy criteria. Enterprise buyers expect SOC 2 Type II for dashboards that handle billing and revenue data.

**OWASP Top 10 (2021)**
- URL: https://owasp.org/www-project-top-ten/
- The standard awareness document for web application security risks. Directly relevant to securing a SaaS dashboard's API, authentication flows, and data access controls. Injection, Broken Access Control, and Security Misconfiguration are the highest-priority risks for a multi-tenant analytics application.

**NIST Cybersecurity Framework (CSF) 2.0**
- URL: https://www.nist.gov/cyberframework
- US framework for improving critical infrastructure cybersecurity. Increasingly referenced in enterprise procurement questionnaires alongside SOC 2 and ISO 27001.

---

### MCP Server Specifications

**Model Context Protocol (Anthropic)**
- URL: https://modelcontextprotocol.io/
- Open protocol for connecting AI models to external data sources and tools. An AI-native SaaS metrics dashboard could expose an MCP server, allowing AI assistants (Claude, Cursor, etc.) to query live metric data, run cohort analysis, or generate board narratives via tool calls without custom integration work.

---

## Similar Products — Developer Documentation & APIs

### ChartMogul
- **Description:** Purpose-built subscription analytics platform with REST API for importing billing data and retrieving calculated SaaS metrics.
- **API Documentation:** https://dev.chartmogul.com/docs/introduction/
- **API Reference:** https://dev.chartmogul.com/reference
- **SDKs/Libraries:** Go (https://github.com/chartmogul/chartmogul-go), Python, Ruby, PHP, JavaScript, Java, .NET — all MIT-licensed on GitHub under the `chartmogul` org.
- **Authentication:** HTTP Basic Authentication over HTTPS; API key required.
- **Standards:** REST/JSON; no published OpenAPI spec.
- **Key Capabilities via API:** Import customers, plans, subscriptions, and charges; retrieve calculated metrics (MRR, churn, LTV, cohort reports) as timeseries data; add custom attributes to customer records.

### Baremetrics
- **Description:** Subscription analytics SaaS with metrics, dunning, and cancellation insights. API enables custom billing source ingestion.
- **API Documentation:** https://developers.baremetrics.com/reference/introduction
- **Quick Start:** https://developers.baremetrics.com/reference/quick-start
- **SDKs/Libraries:** Ruby gem (https://github.com/rewindio/baremetrics_api); unofficial PHP and JavaScript clients on GitHub.
- **Authentication:** API key (passed as Authorization Bearer token); keys managed in Settings.
- **Standards:** REST/JSON.
- **Key Capabilities via API:** Create and manage customers, subscriptions, plans, and charges; retrieve metric timeseries data; requires Source ID for provider.

### Paddle (ProfitWell Metrics)
- **Description:** Subscription analytics embedded in the Paddle billing platform; free metrics API for subscription companies.
- **API Documentation:** https://developer.paddle.com/concepts/profitwell-metrics
- **Metrics API (2026):** https://developer.paddle.com/changelog/2026/metrics-api
- **Customers API:** https://www.paddle.com/help/profitwell-metrics/export-data/customers-api/customers-api
- **SDKs/Libraries:** Paddle official SDKs on https://github.com/paddlehq (JavaScript, Python, PHP, Ruby, Go).
- **Authentication:** API key for ProfitWell Metrics; OAuth 2.0 for Paddle Billing API.
- **Standards:** REST/JSON; OpenAPI spec published for Paddle Billing API.
- **Key Capabilities via API:** Seven new /metrics endpoints (2026) returning timeseries data; Customers API for exporting subscriber data; full Paddle Billing REST API for subscription management.

### Stripe (Billing API + Sigma)
- **Description:** Payment and billing infrastructure with a comprehensive REST API, SQL analytics layer (Sigma), and data warehouse export (Data Pipeline).
- **API Documentation:** https://docs.stripe.com/api
- **Billing Docs:** https://docs.stripe.com/billing
- **Subscriptions API Reference:** https://docs.stripe.com/api/subscriptions
- **Sigma (SQL Analytics):** https://stripe.com/sigma and https://docs.stripe.com/stripe-data
- **Data Pipeline (Warehouse Export):** https://docs.stripe.com/stripe-data/available-data
- **SDKs/Libraries:** Official libraries for Node.js, Python, Ruby, PHP, Java, Go, .NET, and more — all on https://github.com/stripe.
- **Authentication:** API key (secret key for server-side, publishable key for client-side).
- **Standards:** REST/JSON; OpenAPI specification published at https://raw.githubusercontent.com/stripe/openapi/master/openapi/spec3.json.
- **Key Capabilities via API:** Full subscription lifecycle management; invoice and payment data; usage-based billing meters; Sigma SQL for custom metric queries; Data Pipeline exports to Snowflake, Redshift, Databricks, BigQuery, S3, GCS, and Azure Blob.

### Amplitude
- **Description:** Product analytics platform with REST APIs for event ingestion, cohort management, and data export; multiple webhook types.
- **API Documentation:** https://amplitude.com/docs/apis
- **Developer Hub:** https://amplitude.com/docs/developers
- **SDK Documentation:** https://amplitude.com/docs/sdks
- **Postman Collection:** https://www.postman.com/amplitude-dev-docs/amplitude-developers/documentation/2hjpzte/amplitude-analytics-apis
- **SDKs/Libraries:** JavaScript, iOS, Android, React Native, Python, Java, Go, .NET, Ruby, PHP — https://github.com/amplitude.
- **Authentication:** API key for event ingestion; Secret Key for management APIs.
- **Standards:** REST/JSON; no published OpenAPI spec, but Postman collection available.
- **Webhooks:** Monitor alerts via webhook; Event/User streaming webhooks; Cohort webhooks with add/remove batches. Retry logic: 9 attempts over 4 hours on failure.

### Mixpanel
- **Description:** Event-based product analytics platform with ingestion API, query API, cohort sync, and warehouse connectors.
- **API Documentation:** https://developer.mixpanel.com/reference/overview
- **Ingestion API:** https://developer.mixpanel.com/reference/ingestion-api
- **SDK Documentation:** https://docs.mixpanel.com/docs/tracking-methods/sdks
- **Cohort Sync Spec:** https://docs.mixpanel.com/docs/cohort-sync/build-an-integration
- **SDKs/Libraries:** JavaScript (https://docs.mixpanel.com/docs/tracking-methods/sdks/javascript), iOS, Android, Python, Ruby, Java, Go, PHP — all MIT-licensed on GitHub.
- **Authentication:** Project token for event ingestion; Service Account credentials for Query API.
- **Standards:** REST/JSON; Ingestion API uses URL-encoded or JSON payloads.
- **Webhooks:** Cohort sync webhooks (paid plans); webhook spec published for partner integrations.

### PostHog
- **Description:** Open-source all-in-one analytics platform with REST API, SDKs in every major language, and self-hosted deployment option.
- **API Documentation:** https://posthog.com/docs/api
- **SDK Documentation:** https://posthog.com/docs/libraries
- **GitHub (open source):** https://github.com/PostHog/posthog
- **SDKs/Libraries:** JavaScript, Python, iOS (Swift), Android, React Native, Ruby, Go, PHP, Java, .NET, Elixir, Rust — MIT-licensed.
- **Authentication:** Personal API key for management APIs; Project API key for event ingestion.
- **Standards:** REST/JSON; rate limits: 240 requests/minute, 1200 requests/hour for analytics endpoints.
- **Standards Compliance:** SOC 2 (cloud), GDPR-ready, HIPAA-compliant (cloud with BAA); MIT open-source core.
- **Key Capabilities via API:** Event ingestion, funnel/retention/trend queries, cohort management, feature flag evaluation, session replay data access, and data warehouse export to Snowflake and BigQuery.

### Segment (Twilio)
- **Description:** Customer Data Platform with standardised event spec, source SDKs, and 450+ destination integrations. Acts as the data collection and routing layer feeding analytics dashboards.
- **Spec Documentation:** https://segment.com/docs/connections/spec/
- **Protocols (Tracking Plan):** https://segment.com/docs/protocols/
- **B2B SaaS Spec:** https://segment.com/docs/connections/spec/b2b-saas/
- **SDKs/Libraries:** JavaScript, iOS, Android, Python, Ruby, Java, Go, PHP, .NET — all open-source on https://github.com/segmentio.
- **Authentication:** Write Key per source; OAuth 2.0 for Public API.
- **Standards:** REST/JSON; JSON Schema used for Tracking Plan validation; OpenAPI spec available for Public API.
- **Key Capabilities:** Event spec enforcement via Protocols; 450+ destination connectors; Reverse ETL for syncing warehouse data back to tools; real-time event streaming via Kinesis or Pub/Sub.

---

## Notes

**Metric definition fragmentation:** No single ISO or IETF standard governs SaaS metric calculations. MRR, ARR, NRR, GRR, LTV, and CAC formulas vary across vendors (e.g., whether contracted not-yet-active ARR is included, whether reactivations offset churn). An AI-native dashboard should document its formula choices explicitly and ideally provide formula-level transparency to users.

**OpenAPI coverage gap:** Of the major SaaS analytics platforms surveyed, only Stripe publishes a comprehensive OpenAPI specification. ChartMogul, Baremetrics, and Amplitude rely on documentation-only API references without machine-readable specs. This represents a tooling gap where an AI-native platform could differentiate by shipping a complete OAS 3.1 spec from day one.

**MCP opportunity:** No existing SaaS metrics platform currently publishes an MCP server. Building an MCP server alongside the dashboard API would allow AI coding assistants and agents to query live MRR, churn, and cohort data directly, enabling a new category of conversational analytics workflows without custom integration.

**GDPR and data residency:** In 2026, regulators increasingly use automated scanning to verify backend behaviour against stated privacy policies. Dashboards storing EU subscriber billing data must implement GDPR controls at the data model level (pseudonymisation, deletion propagation, access logs), not just at the policy level.

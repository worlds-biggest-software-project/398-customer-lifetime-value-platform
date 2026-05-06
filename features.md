# Customer Lifetime Value Platform — Feature & Functionality Survey

> Candidate #398 · Researched: 2026-05-06

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Lifetimely (by AMP) | SaaS — Shopify-native | Commercial; from $29/month | https://useamp.com/products/analytics/lifetime-value |
| Klaviyo | SaaS — e-commerce CDP/ESP | Commercial; from $45/month | https://www.klaviyo.com |
| Omniconvert Reveal | SaaS — e-commerce analytics | Commercial; free trial available | https://www.omniconvert.com/reveal/ |
| Retina AI | SaaS — enterprise predictive CLV | Commercial; custom pricing | https://retina.ai |
| Braze | SaaS — enterprise CEP | Commercial; $50,000+/year | https://www.braze.com |
| Adobe Experience Platform (AEP) | SaaS — enterprise CDP | Commercial; enterprise pricing | https://experienceleague.adobe.com/en/docs/experience-platform |
| Salesforce Einstein / Data Cloud | SaaS — enterprise CRM/AI | Commercial; enterprise pricing | https://www.salesforce.com |
| PyMC-Marketing | Open-source Python library | Apache 2.0 | https://github.com/pymc-labs/pymc-marketing |
| BTYD (Buy Till You Die) | Open-source Python library | MIT | https://github.com/ColtAllen/btyd |
| Lifetimes (Python) | Open-source Python library (maintenance mode) | MIT | https://github.com/CamDavidsonPilon/lifetimes |

---

## Feature Analysis by Solution

### Lifetimely (by AMP)

**Core features**
- Real-time profit and loss dashboard with COGS integration
- LTV cohort analysis segmented by acquisition channel, first product purchased, geography, and cohort date
- CAC payback period calculation by channel and cohort
- Predictive LTV modelling to forecast future customer value
- Multi-touch attribution across Google, Meta, TikTok, and email
- Integrations with Klaviyo, QuickBooks, Amazon, and major shipping apps

**Differentiating features**
- Best-in-class Shopify cohort reporting with cumulative revenue and repeat purchase rate per cohort
- Unified P&L that blends marketing spend with order revenue in a single view
- Reports a median 12% LTV uplift for merchants using the tool

**UX patterns**
- Shopify App Store installation; zero-configuration data ingestion from Shopify Orders API
- Dashboard-first with progressive drill-down into cohort detail
- Designed for non-technical DTC founders and growth marketers

**Integration points**
- Shopify and Amazon native connectors
- Ad platform connectors: Google Ads, Meta, TikTok
- Email/retention: Klaviyo integration
- Accounting: QuickBooks

**Known gaps**
- Shopify-only; no connector for WooCommerce, Magento, or custom commerce stacks
- No individual-level predictive scoring; cohort-level only
- No API for exporting LTV scores to external systems or ad platforms directly
- Limited subscription/SaaS business model support

**Licence / IP notes**
- Proprietary SaaS; no open-source components exposed

---

### Klaviyo

**Core features**
- Predictive CLV scoring per customer profile (total CLV, predicted CLV, churn risk)
- Expected Date of Next Order (EDNO) prediction
- Average Time Between Orders metric
- CLV-based audience segmentation for campaign targeting
- CLV dashboard with cohort breakdown
- Automated flows triggered by churn risk and CLV tier

**Differentiating features**
- CLV predictions accessible via REST API (Profiles endpoint with `?additional-fields[profile]=predictive_analytics`)
- Deep native integration with Shopify, WooCommerce, Magento, and BigCommerce
- Unlocks predictions once baseline is met: 500+ customers, 180 days of history, 3+ orders per customer

**UX patterns**
- ESP-first interface; CLV is surfaced within the segment builder and campaign flow editor
- CLV segments can be used to trigger retention automations without leaving Klaviyo
- Progressive disclosure: basic CLV visible in dashboard, full API access for technical users

**Integration points**
- Native e-commerce platform integrations (Shopify, WooCommerce, Magento, BigCommerce)
- REST API at developers.klaviyo.com; OpenAPI spec available
- Google Ads and Meta custom audience sync for CLV-based suppression and lookalike seeding

**Known gaps**
- CLV model is a black box; no insight into model weights or feature importance
- Requires Klaviyo as the email/SMS platform; not usable as a standalone CLV engine
- Minimum data requirements exclude early-stage brands
- No support for non-contractual B2B or subscription businesses

**Licence / IP notes**
- Proprietary SaaS; CLV model is a closed black-box system
- API access governed by Klaviyo Developer Terms

---

### Omniconvert Reveal

**Core features**
- Automated RFM (Recency, Frequency, Monetary) segmentation producing 11 standard customer groups
- LTV per RFM segment reporting
- CAC tracking and CAC-to-LTV ratio by segment
- Ideal Customer Profile (ICP) identification based on RFM and LTV signals
- NPS survey integration linked to customer segments
- Retention and churn monitoring

**Differentiating features**
- RFM segmentation auto-calibrates to each store's actual purchase patterns rather than fixed thresholds
- NPS measurement linked directly to customer value tiers — a rare combination
- Customer Value Optimization (CVO) methodology baked into product workflow

**UX patterns**
- Shopify App Store installation with 30-day free trial
- Guided onboarding around ICP definition and RFM segment interpretation
- Segment-centric dashboard rather than individual customer view

**Integration points**
- Shopify native
- Email platform integrations for segment-based campaign triggers
- NPS collection tooling built in

**Known gaps**
- Shopify-only
- RFM is a historical, rule-based model; no probabilistic or ML-based predictive LTV
- No ad platform integration for CLV-based bidding
- No API for exporting scores or segment memberships

**Licence / IP notes**
- Proprietary SaaS

---

### Retina AI

**Core features**
- Individual-level early CLV prediction (claimed 90%+ accuracy)
- CLV scores available within hours of data ingestion
- Segment-level CLV analytics and attribute decomposition
- Backtest mode to validate model accuracy against historical data
- Lookalike audience seeding on Facebook/Meta using CLV-ranked customer lists
- Two-way Snowflake data pipeline integration

**Differentiating features**
- Specialises in early CLV prediction — scoring customers within their first 1–14 days
- CLV scores delivered via data warehouse (Snowflake) as primary delivery mechanism, not just a dashboard
- Direct Facebook campaign optimisation using CLV tiers for suppression and value-based bidding

**UX patterns**
- Enterprise sales-led onboarding; not self-service
- Dashboard for CLV analytics; primary consumption of scores is via warehouse or ad platform
- Data exploration UI for attribute-level CLV decomposition

**Integration points**
- Snowflake reverse ETL for CLV score delivery
- Facebook/Meta Custom Audiences API integration
- mParticle partnership for real-time event-level CLV updates
- REST API for real-time CLV access in web/mobile app contexts

**Known gaps**
- Closed model; no explainability or feature importance exposed to end users
- Enterprise pricing puts it out of reach for mid-market brands
- Limited support for non-e-commerce business models (subscription SaaS)
- No self-service tier

**Licence / IP notes**
- Proprietary SaaS; enterprise contracts

---

### Braze

**Core features**
- Cross-channel customer engagement orchestration (email, push, in-app, SMS, WhatsApp)
- AI-powered audience segmentation with CLV-adjacent signals (churn propensity, conversion likelihood)
- Real-time behavioural triggers and journey orchestration
- A/B and multivariate testing across touchpoints
- CLV metric tracking at segment and individual level
- Advanced analytics with custom SQL query support

**Differentiating features**
- API-first architecture supporting custom CLV integrations via webhook and REST endpoints
- Real-time event streaming from e-commerce, product, and marketing systems for continuous CLV recalculation
- Enterprise scale: designed for millions of users with sub-second latency
- Segment CDPs and mParticle natively supported as data sources

**UX patterns**
- Enterprise technical implementation required; not a self-service product
- Canvas visual journey builder for lifecycle campaign design
- CLV surfaced as a metric within analytics rather than as a primary feature

**Integration points**
- REST API documented at braze.com/docs/api
- Segment, mParticle, Amplitude as CDP connectors
- Snowflake Data Share for warehouse-native analytics
- Google Ads and Meta Custom Audiences for audience activation

**Known gaps**
- CLV is computed externally and ingested; Braze does not natively model LTV
- High cost of entry ($50k+/year) excludes SMB and mid-market
- Implementation requires dedicated engineering resources
- No built-in probabilistic LTV model; depends on upstream data pipeline

**Licence / IP notes**
- Proprietary SaaS; custom enterprise licensing

---

### Adobe Experience Platform (AEP / Real-Time CDP)

**Core features**
- Real-Time Customer Profile with computed attributes (lifetime purchase value, time between purchases)
- Query Service (SQL interface) for CLV metric construction from raw event data
- Data Distiller for custom CLV model output and BI dashboard integration
- Audience builder for CLV-tier segmentation
- Real-time streaming ingestion for continuous profile updates

**Differentiating features**
- Computed attributes on customer profiles allow CLV to be queried without custom SQL each time
- Integrates with Adobe Analytics, Adobe Target, and Adobe Campaign for full activation
- Data model built on XDM (Experience Data Model), an open standard for customer event schemas

**UX patterns**
- Enterprise implementation by Adobe partners; significant configuration overhead
- SQL-first workflow for CLV metric creation; non-technical users dependent on pre-built dashboards
- Designed for organisations with dedicated data engineering and MarTech teams

**Integration points**
- REST APIs and batch/streaming ingestion APIs (documented on Experience League)
- Adobe ecosystem: Analytics, Target, Campaign, Journey Optimizer
- Snowflake, Databricks, and Google BigQuery integrations
- Google Ads and Meta activation via Audience Destinations

**Known gaps**
- Very high implementation complexity and cost
- CLV is a derived metric that requires significant data engineering to implement correctly
- No pre-built LTV model; SQL queries must be custom-authored
- Vendor lock-in risk with proprietary XDM schema layer

**Licence / IP notes**
- Proprietary SaaS; enterprise licensing
- XDM (Experience Data Model) is open-source and published on GitHub

---

### Salesforce Einstein / Data Cloud

**Core features**
- Predictive CLV scoring via Einstein AI using purchase history and behavioural signals
- CLV-based audience segmentation in Marketing Cloud
- Real-time CLV recalculation using Data Cloud event streaming
- Cross-sell and upsell propensity scoring alongside CLV
- Churn risk scoring integrated with CLV projection

**Differentiating features**
- Unified CRM-to-CLV pipeline: Salesforce CRM data feeds directly into Einstein predictions
- Calculated Insights feature for custom CLV metric definitions in Data Cloud
- Predictions accessible within CRM records for sales team use cases (not just marketing)

**UX patterns**
- Enterprise configuration; requires Salesforce admin and implementation partner
- CLV visible on individual contact/account records in CRM UI
- Minimum data requirement: 400+ examples per outcome; 6–12 months history recommended

**Integration points**
- Salesforce CRM (native)
- Marketing Cloud for campaign activation
- Data Cloud REST APIs for external data ingestion
- Google Ads and Meta Audiences via Marketing Cloud connectors

**Known gaps**
- Tightly coupled to Salesforce ecosystem; difficult to use CLV scores outside Salesforce
- Requires significant historical data volume before predictions activate
- Black-box model; no explainability layer for predictions
- Full implementation typically takes 3–4 months; ROI typically realised at 12–18 months

**Licence / IP notes**
- Proprietary SaaS; enterprise licensing

---

### PyMC-Marketing (open source)

**Core features**
- BG/NBD model for non-contractual customer transaction modelling
- Pareto/NBD model support
- Gamma-Gamma model for expected transaction value
- Contractual CLV models (survival analysis for subscription businesses)
- Bayesian inference enabling CLV modelling with as little as a few months of data
- Media Mix Modelling (MMM) in the same library

**Differentiating features**
- Full posterior distribution outputs — uncertainty quantification on every CLV prediction
- Bayesian approach requires less historical data than frequentist methods
- Unified library for CLV and attribution (MMM), enabling joint optimisation
- Open-source with Apache 2.0 licence; fully auditable and extensible

**UX patterns**
- Python library consumed via Jupyter notebooks and data science pipelines
- No UI; outputs are Python objects, DataFrames, and plots
- Documentation on pymc-marketing.io with quickstart notebooks

**Integration points**
- Standard Python ecosystem (pandas, numpy, scikit-learn, arviz)
- Outputs to any data warehouse via Python connectors
- Can be wrapped in FastAPI or similar for API serving

**Known gaps**
- No UI or dashboard layer; requires engineering to operationalise
- No built-in ad platform connectors
- Model training and scoring requires data science expertise
- Production deployment and scheduling must be built separately

**Licence / IP notes**
- Apache 2.0 — permissive; safe for commercial use and embedding

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Historical LTV calculation by customer cohort (acquisition date, channel, geography)
- Repeat purchase rate and average order value per cohort
- CAC-to-LTV ratio by acquisition channel
- Customer churn / lapse detection
- Segment-level dashboards filterable by cohort, channel, product, and geography
- Integration with at least one major e-commerce platform (Shopify, BigCommerce, WooCommerce)

### Differentiating Features
- Individual-level predictive LTV scoring with confidence intervals
- Early CLV prediction within 1–14 days of first purchase
- LTV score delivery via data warehouse (Snowflake, BigQuery) for downstream activation
- Ad platform integration for value-based bidding (Google Ads Customer Match, Meta Custom Audiences)
- Probabilistic model outputs with uncertainty quantification (Bayesian approaches)
- Cross-business-model support: both contractual (subscription) and non-contractual (transactional) customers

### Underserved Areas / Opportunities
- Open-source, self-hostable CLV platform with no vendor lock-in
- Cross-business-model support in a single tool (subscription + transactional simultaneously)
- Explainable LTV predictions with feature importance and what-if simulation
- Privacy-preserving LTV modelling compatible with GDPR and CCPA constraints (differential privacy, on-premise deployment)
- Real-time LTV scoring at point of acquisition for immediate channel optimisation
- Native MCP (Model Context Protocol) server for LLM-driven CLV querying and interpretation
- LTV-to-CAC optimisation recommendations as a first-class feature, not just a metric

### AI-Augmentation Candidates
- Automatic model selection based on business model type (contractual vs. non-contractual, high- vs. low-frequency)
- LLM-assisted interpretation of cohort anomalies and actionable retention recommendations
- AI-driven cold-start LTV estimation from first-session behavioural signals
- Automated hyperparameter tuning and model retraining scheduling
- Natural-language querying of LTV dashboards ("Which channel has the best 12-month LTV?")

---

## Legal & IP Summary

No patents were identified on the core statistical models (BG/NBD, Pareto/NBD, Gamma-Gamma, or survival analysis approaches) — these are published academic models from peer-reviewed literature (Fader, Hardie & Lee, 2005; Schmittlein, Morrison & Colombo, 1987) and are freely implementable. The primary open-source libraries (PyMC-Marketing under Apache 2.0, BTYD under MIT, lifetimes under MIT) are permissively licensed and safe to use as a foundation. Proprietary CLV platforms protect their implementations through trade secrets and SaaS subscription terms rather than patents. The XDM (Experience Data Model) schema published by Adobe is open-source. No copyright or licensing concerns were identified that would impede building an open-source CLV platform based on standard statistical models.

---

## Recommended Feature Scope

**Must-have (MVP)**
- Cohort-level historical LTV analysis: revenue, repeat purchase rate, CAC payback period by channel, geography, and product
- BG/NBD and Gamma-Gamma predictive LTV model for non-contractual customers
- Survival analysis model for contractual/subscription customers
- LTV dashboard with cohort filtering and drill-down
- Acquisition channel ROI report (CAC vs. cohort LTV curves)
- REST API for LTV score ingestion into downstream systems

**Should-have (v1.1)**
- Individual-level early CLV scoring (within first 14 days of acquisition)
- Google Ads Customer Match and Meta Custom Audiences integration for value-based bidding
- Automated churn-risk alerting for high-value customers showing early lapse signals
- Snowflake and BigQuery connectors for score delivery
- Model explainability: feature importance and what-if simulation per customer segment

**Nice-to-have (backlog)**
- Natural-language LTV querying via LLM interface (MCP server)
- Differential-privacy mode for privacy-preserving scoring
- Automated model selection by business model type
- Multi-touch attribution integrated with LTV curves
- Self-service onboarding for non-technical users with guided ICP identification

# Customer Lifetime Value Platform

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An open-source, cross-business-model platform for historical and predictive customer lifetime value modelling, acquisition ROI analysis, and segment-level LTV tracking.

The Customer Lifetime Value Platform ingests transaction, subscription, and engagement data to compute both historical and predictive LTV at the individual customer and segment level. It is built for growth, marketing, and finance teams who need to allocate acquisition spend and retention investment based on durable customer value rather than aggregate averages, and to feed LTV signals back into ad platforms for value-based bidding.

---

## Why Customer Lifetime Value Platform?

- Customer acquisition costs have increased by more than 220% over the past eight years, yet most teams still manage spend against aggregate averages rather than segment- or individual-level LTV.
- Incumbents like Lifetimely and Omniconvert Reveal are Shopify-only and offer no connectors for WooCommerce, Magento, or custom commerce stacks.
- Klaviyo's predictive CLV is a black-box model that requires Klaviyo as the email/SMS platform and excludes early-stage brands through minimum data requirements (500+ customers, 180 days, 3+ orders per customer).
- Enterprise tools such as Retina AI, Braze ($50,000+/year), Adobe Experience Platform, and Salesforce Einstein price out mid-market organisations and lock customers into proprietary ecosystems.
- No widely adopted tool supports both contractual (subscription) and non-contractual (transactional) customers in a single platform, forcing organisations with mixed revenue models to stitch together multiple systems.

---

## Key Features

### Historical LTV & Cohort Analysis

- Cohort-level LTV by acquisition date, channel, geography, and product line
- Repeat purchase rate and average order value per cohort
- CAC payback period calculation by channel and cohort
- CAC-to-LTV ratio reporting across acquisition sources
- Segment-level dashboards filterable by cohort, channel, product, and geography

### Predictive LTV Modelling

- BG/NBD and Pareto/NBD models for non-contractual customer bases
- Gamma-Gamma model for expected transaction value
- Survival analysis for contractual and subscription customers
- Bayesian inference with full posterior distributions and uncertainty quantification
- Individual-level early CLV scoring within the first 1–14 days of acquisition

### Acquisition ROI & Activation

- Acquisition channel ROI report comparing CAC against cohort LTV curves
- Google Ads Customer Match and Meta Custom Audiences integration for value-based bidding and lookalike seeding
- Snowflake and BigQuery connectors for LTV score delivery via reverse ETL
- REST API for ingestion of LTV scores into downstream systems

### Retention & Alerting

- Automated churn-risk alerting for high-value customers showing early lapse signals
- Expected Date of Next Order and Average Time Between Orders signals
- Segment-based triggers for retention automations

### Explainability & Operationalisation

- Feature importance and what-if simulation per customer segment
- Backtest mode to validate model accuracy against historical data
- Automated model selection based on contractual vs. non-contractual business model
- Natural-language LTV querying via an LLM interface (MCP server)

---

## AI-Native Advantage

AI capabilities address gaps that incumbents leave open: automatic model selection between contractual and non-contractual frameworks based on business-model signals, AI-driven cold-start LTV estimation from first-session behavioural signals (research shows predictive CLV models outperform historical calculations by 25–40%, with AI-driven implementations identifying high-value users within 7–14 days), LLM-assisted interpretation of cohort anomalies with actionable retention recommendations, and natural-language querying of LTV dashboards. Unlike the black-box models offered by Klaviyo, Retina AI, and Salesforce Einstein, predictions are paired with feature importance and uncertainty quantification.

---

## Tech Stack & Deployment

The platform is designed around the standard Python data-science stack: the `lifetimes` library, PyMC-Marketing (Apache 2.0), and BTYD (MIT) for probabilistic modelling, with `scikit-survival` for subscription churn projection. dbt handles cohort construction and CAC-to-LTV join logic; Snowflake and BigQuery serve as the analytical warehouse and primary score-delivery channel. Identity resolution is handled via Segment or Rudderstack. Activation flows through Google Ads Customer Match and Meta Custom Audiences APIs. Apache Airflow orchestrates retraining and scoring jobs, and MLflow tracks experiments and model versions. Self-hostable deployment is a primary goal, with no vendor lock-in.

---

## Market Context

LTV platforms sit at the intersection of analytics, CRM, and marketing technology. Incumbent pricing ranges from $29/month for Shopify-native tools like Lifetimely up to $50,000+/year for enterprise platforms such as Braze, with Adobe Experience Platform, Salesforce Einstein, and Retina AI sold under custom enterprise contracts. Primary buyers are growth and marketing leaders at direct-to-consumer e-commerce brands, subscription businesses, and mid-market organisations that operate across both transactional and subscription revenue streams.

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

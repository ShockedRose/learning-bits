# PostHog learning path

Suggested order for becoming useful with PostHog on real products. Adjust depth based on whether you need analytics only, feature flags/experiments, or the full stack (replay, surveys, pipelines).

## 0. Prerequisites

- Comfortable with web/app basics (pages, users, events)
- For instrumentation: JavaScript/TypeScript (or your app’s language)
- Helpful: SQL basics (PostHog HogQL / insights often benefit from it)
- Helpful: product sense (what to measure vs vanity metrics)

## 1. Platform fundamentals

Understand what PostHog is and how a project is structured before wiring SDKs.

**Learn**

- PostHog Cloud vs self-hosted (when each makes sense)
- Projects, organizations, and environments
- Persons, distinct IDs, anonymous → identified user merge
- Events vs properties; autocapture vs custom events
- Privacy, consent, and what not to send (PII, secrets)

**Resources**

- [PostHog docs home](https://posthog.com/docs)
- [What is PostHog?](https://posthog.com/docs/product-os)
- [PostHog Cloud vs self-host](https://posthog.com/docs/self-host)
- [Privacy and compliance overview](https://posthog.com/docs/privacy)

**Practice**

- Create a free PostHog Cloud account and a project
- Explore the demo/sample data (or install the toolbar on a sandbox site)
- Sketch an event taxonomy for a simple app (signup, activate, pay)

## 2. Instrumentation (SDKs and event capture)

You cannot analyze what you do not capture cleanly.

**Learn**

- Web JS SDK: init, `capture`, `identify`, `group`, `register` / super properties
- Autocapture: strengths, noise, and when to prefer custom events
- Server-side capture (Node, Python, etc.) for reliable backend events
- Naming conventions (`object_action` or `category:action`) and property schemas
- Source maps / error tracking basics if you use PostHog for exceptions

**Resources**

- [JavaScript web SDK](https://posthog.com/docs/libraries/js)
- [Identify users](https://posthog.com/docs/product-analytics/identify)
- [Capturing events](https://posthog.com/docs/product-analytics/capture-events)
- [Autocapture](https://posthog.com/docs/product-analytics/autocapture)
- [Server libraries](https://posthog.com/docs/libraries) (pick your stack)

**Practice**

- Install the JS SDK on a local or staging app
- Capture 3–5 custom events with consistent properties
- Identify a user after login and verify person merge in PostHog
- Add one backend event (e.g. `payment_succeeded`) via a server library

## 3. Product analytics

Turn events into answers product and growth teams care about.

**Learn**

- Insights: trends, funnels, retention, paths, stickiness, lifecycle
- Filters, breakdowns, cohorts, and formulas
- HogQL for custom queries when UI insights are not enough
- Dashboards and sharing with stakeholders
- Actions (reusable event definitions) and annotations

**Resources**

- [Product analytics](https://posthog.com/docs/product-analytics)
- [Funnels](https://posthog.com/docs/product-analytics/funnels)
- [Retention](https://posthog.com/docs/product-analytics/retention)
- [HogQL](https://posthog.com/docs/hogql)
- [Actions](https://posthog.com/docs/data/actions)

**Practice**

- Build a signup → activation funnel and find the biggest drop-off
- Create a weekly retention chart for a key action
- Save a dashboard with 4–6 insights for one product surface
- Write one HogQL query that the UI could not express cleanly

## 4. Feature flags and experiments

Ship safely and measure impact.

**Learn**

- Boolean, multivariate, and remote-config flags
- Targeting: cohorts, person properties, percentage rollouts
- Local evaluation vs remote evaluation (latency / reliability tradeoffs)
- Experiments (A/B tests): hypothesis, metrics, statistical significance
- Feature flag best practices (cleanup, defaults, kill switches)

**Resources**

- [Feature flags](https://posthog.com/docs/feature-flags)
- [Creating feature flags](https://posthog.com/docs/feature-flags/creating-feature-flags)
- [Experiments](https://posthog.com/docs/experiments)
- [Experiment insights / stats](https://posthog.com/docs/experiments/statistics)

**Practice**

- Gate a UI change behind a flag and roll out to 10% → 50% → 100%
- Target a flag by email domain or a custom person property
- Run a simple A/B experiment with a primary conversion metric

## 5. Session replay, surveys, and qualitative tools

Combine quantitative analytics with qualitative signal.

**Learn**

- Session replay: privacy masks, network capture, when to sample
- Linking replays to funnels and frustration signals
- Surveys: NPS, product-market fit, in-app prompts
- Heatmaps / toolbar (if relevant to your web product)

**Resources**

- [Session replay](https://posthog.com/docs/session-replay)
- [Privacy controls for replay](https://posthog.com/docs/session-replay/privacy)
- [Surveys](https://posthog.com/docs/surveys)
- [Toolbar](https://posthog.com/docs/toolbar)

**Practice**

- Enable replay with input masking on a staging site
- Watch 5 sessions that abandoned a funnel step
- Launch one short in-app survey tied to a cohort (e.g. power users)

## 6. Data pipelines, warehouse, and advanced topics (optional)

Useful once capture and core analytics are solid.

**Learn**

- Batch exports / data warehouse sync (BigQuery, S3, Snowflake, etc.)
- Destinations and CDP-style flows
- Group analytics (B2B accounts/companies)
- SQL insights and notebooks for deeper analysis
- Self-hosting considerations (ops cost, upgrades, clickhouse)

**Resources**

- [Data pipeline / CDP](https://posthog.com/docs/cdp)
- [Batch exports](https://posthog.com/docs/cdp/batch-exports)
- [Data warehouse](https://posthog.com/docs/data-warehouse)
- [Group analytics](https://posthog.com/docs/product-analytics/group-analytics)
- [Self-host deploy overview](https://posthog.com/docs/self-host)

**Practice**

- (If B2B) model companies as groups and chart usage by account
- Export a small dataset to a warehouse or CSV and join with another source
- Skim self-host docs only if Cloud is not an option for your constraints

## Suggested sequence (compact)

1. Cloud project + event taxonomy sketch  
2. JS SDK + identify + a few custom events  
3. Funnel + retention + one shared dashboard  
4. Feature flag rollout on a real UI change  
5. Session replay on funnel drop-offs  
6. (Optional) Experiment, surveys, warehouse export  

## Skills checklist

Copy into [follow-ups.md](./follow-ups.md) and mark as you go.

- [ ] PostHog Cloud project created
- [ ] Event naming convention documented
- [ ] JS (or other) SDK installed and capturing events
- [ ] `identify` used correctly after auth
- [ ] Funnel insight built and interpreted
- [ ] Retention or paths insight built
- [ ] Dashboard shared with a stakeholder (or teammate)
- [ ] Feature flag created and consumed in code
- [ ] Percentage or property-based targeting used
- [ ] Session replay enabled with privacy masking
- [ ] (Optional) Experiment completed end-to-end
- [ ] (Optional) Survey or HogQL query shipped
- [ ] (Optional) Warehouse / batch export configured

## Extra learning resources

- [PostHog tutorials](https://posthog.com/tutorials) — task-oriented walkthroughs by stack and use case  
- [PostHog blog](https://posthog.com/blog) — product updates and how-to deep dives  
- [PostHog YouTube](https://www.youtube.com/@PostHog) — demos and explainers  
- [PostHog GitHub](https://github.com/PostHog/posthog) — source, issues, and changelog context  
- [PostHog community / Slack](https://posthog.com/questions) — ask questions and search prior answers  

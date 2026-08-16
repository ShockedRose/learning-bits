# Shopify learning path (developer)

Suggested order for becoming useful on real Shopify projects. Adjust depth based on whether you aim at themes, apps, or headless.

## 0. Prerequisites

- HTML, CSS, JavaScript (ES modules, async/await)
- Git and basic CLI comfort
- For apps / Hydrogen: React and TypeScript
- Helpful: GraphQL basics (queries, mutations, variables)

## 1. Platform fundamentals

Understand how a Shopify store is put together before writing code.

**Learn**

- Admin, Online Store, products/variants/collections, checkout, apps vs themes
- Plans (Basic → Plus) and what Plus unlocks for merchants
- Shopify Partner account and development stores
- Shopify CLI for themes and apps

**Resources**

- [Shopify.dev docs](https://shopify.dev/docs)
- [Partner Dashboard](https://partners.shopify.com/)
- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli)

**Practice**

- Create a Partner account and a development store
- Add sample products, a collection, and a basic checkout test order

## 2. Theme development (Liquid / Online Store 2.0)

Still the highest-volume work for SMB clients.

**Learn**

- Liquid syntax: objects, tags, filters
- JSON templates, sections, blocks, and section groups
- Theme settings (`settings_schema.json`, `config/settings_data.json`)
- Snippets vs sections; metafields and metaobjects
- Theme app extensions (app blocks in themes)
- Performance and accessibility basics for storefronts

**Resources**

- [Liquid reference](https://shopify.dev/docs/api/liquid)
- [Themes documentation](https://shopify.dev/docs/storefronts/themes)
- [Dawn theme](https://github.com/Shopify/dawn) (official reference theme)
- [Online Store 2.0](https://shopify.dev/docs/storefronts/themes/architecture)

**Practice**

- Duplicate Dawn, customize a section and a product template
- Add a merchant-editable block (e.g. trust badges or FAQ)
- Use metafields to drive product page content without hardcoding

## 3. APIs and integrations

Needed for custom workflows, ERPs, CRM sync, and most apps.

**Learn**

- GraphQL Admin API (preferred over REST for new work)
- Storefront API (for custom/headless frontends)
- Webhooks and idempotent handlers
- Authentication: OAuth for public apps, access tokens for custom apps
- Rate limits and cost-based GraphQL throttling
- Shopify Functions (discounts, payment/shipping customization) at a high level

**Resources**

- [Admin API](https://shopify.dev/docs/api/admin-graphql)
- [Storefront API](https://shopify.dev/docs/api/storefront)
- [Webhooks](https://shopify.dev/docs/apps/build/webhooks)
- [Shopify Functions](https://shopify.dev/docs/api/functions)

**Practice**

- Query products/orders with GraphiQL in a dev store
- Write a small script or app that listens to `orders/create`
- Build a custom app that reads inventory and writes a metafield

## 4. App development

**Learn**

- App types: custom vs public (Partner app store)
- Shopify app templates (React Router–based)
- Polaris UI components
- App Bridge for embedding in Admin
- Billing API (for public apps)
- App extensions: admin blocks, theme app extensions, checkout UI extensions (Plus / eligible plans)

**Resources**

- [Build apps](https://shopify.dev/docs/apps/build)
- [Polaris](https://polaris.shopify.com/)
- [App Bridge](https://shopify.dev/docs/api/app-bridge)

**Practice**

- Scaffold an app with Shopify CLI
- Add one Admin page that lists products and updates a metafield
- Ship a theme app extension that merchants can drag into the theme editor

## 5. Headless with Hydrogen (optional / advanced)

Choose this after themes + APIs are solid. More relevant for complex UX, multi-brand, or performance-heavy builds than for typical SMB launches.

**Learn**

- Hydrogen (React Router–based Shopify storefront toolkit)
- Oxygen hosting and preview deployments
- Cart, checkout handoff, Customer Account API
- When Liquid is enough vs when headless is justified

**Resources**

- [Hydrogen getting started](https://shopify.dev/docs/storefronts/headless/hydrogen/getting-started)
- [Hydrogen fundamentals](https://shopify.dev/docs/storefronts/headless/hydrogen/fundamentals)
- [Mock.shop](https://mock.shop) for local Storefront API practice

**Practice**

- `npx shopify hydrogen init` (quickstart), link a store, deploy a preview to Oxygen

## 6. Commerce and merchant fluency

Technical skill alone is not enough for client work.

**Learn**

- Checkout conversion basics (trust, shipping, payments, mobile)
- Local payment expectations (cards, installments, Pix, OXXO, PSE, etc.)
- Shipping / tax / multi-currency at a high level
- App ecosystem tradeoffs (apps vs custom code)
- Shopify Payments vs third-party gateways and extra transaction fees

**Resources**

- [Shopify Payments countries](https://help.shopify.com/en/manual/payments/shopify-payments/getting-set-up) (check official list; it changes)
- [Payment gateway list](https://www.shopify.com/payment-gateways)
- See also [americas-smb-opportunity.md](./americas-smb-opportunity.md)

## Suggested sequence (compact)

1. Dev store + Partner account  
2. Liquid / Dawn customization project  
3. GraphQL Admin + one webhook  
4. One custom app with Polaris  
5. (Optional) Hydrogen quickstart  
6. Package 2–3 SMB-ready offers (theme polish, migration, custom integration)

## Skills checklist

Copy into [follow-ups.md](./follow-ups.md) and mark as you go.

- [ ] Partner account + development store
- [ ] Shopify CLI installed and used for a theme
- [ ] Liquid section/block customization on Dawn
- [ ] Metafields / metaobjects used in a template
- [ ] GraphQL Admin queries and mutations
- [ ] Webhook handler for at least one topic
- [ ] Custom app scaffolded with CLI
- [ ] Polaris + App Bridge basic Admin UI
- [ ] Theme app extension installed on a theme
- [ ] Understand Payments vs third-party fees by country
- [ ] (Optional) Hydrogen storefront deployed to Oxygen

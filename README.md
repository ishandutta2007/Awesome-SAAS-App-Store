# Awesome-SAAS-App-Store

## Top SaaS App Store Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Marketplace Infrastructure, Plugin Registries & Self-Hosted App Directories*  

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **SaaS App Stores**. These platforms enable users to discover, install, and manage applications and integrations within a host SaaS ecosystem—turning a product into a platform with an extensible marketplace.



**Examples** include Atlassian Marketplace, Salesforce AppExchange (now AgentExchange), HubSpot App Marketplace, Google Workspace Marketplace, Zendesk Apps, ServiceNow Store, Shopify App Store, Slack App Directory, Microsoft AppSource, and AWS Marketplace (the category leaders).



**Open-source emphasis**: SaaS App Store is a domain where open-source tooling is **fragmented and largely immature for the core marketplace experience**. The strongest active projects are **Tabularium** (a self-hosted plugin registry with OAuth submission, signed releases, and OpenAPI) and **Open VSX** (the vendor-neutral, open-source alternative to the Visual Studio Marketplace). For building a marketplace *from* open-source commerce engines, **Mercur** provides multi-vendor primitives on Medusa, but it is a commerce marketplace, not a SaaS app directory. The critical caveat: **no open-source project replicates the enterprise procurement, billing, and runtime coupling** of the major platform app stores—those are business-model integrations that software alone cannot provide.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-products)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Atlassian Marketplace](https://marketplace.atlassian.com/)**  

  App marketplace for Jira, Confluence, and Bitbucket; **7,210 active listings** with **1,985 partners** as of 2026 . Freemium cost model with medium approval difficulty; high traffic for team tools . Deep integration with Atlassian's Data Center and Cloud ecosystems.



- **[Salesforce AppExchange (AgentExchange)](https://appexchange.salesforce.com/)**  

  The oldest and most consolidated cloud marketplace (20+ years); **6,709 listings** with **3,229 partners** . Renamed and unified into **AgentExchange** in 2026, combining AppExchange, AgentExchange, and Slack Marketplace into a single destination for agents, apps, and experts . Features semantic search, LLM-assisted listing authoring, MCP server publishing, and mandatory security reviews for private listings . Revenue share 15% (ISVforce) or 25% (OEM).



- **[HubSpot App Marketplace](https://www.hubspot.com/apps)**  

  Integration marketplace for HubSpot CRM; apps are listed without requiring transactable status, though legal and security reviews are required before listing goes live.



- **[Google Workspace Marketplace](https://workspace.google.com/marketplace)**  

  App marketplace for Google Workspace; integrates with Gmail, Drive, Calendar, and Docs; requires Google's OAuth verification and security review.



- **[Zendesk Apps](https://www.zendesk.com/apps/)**  

  App directory for Zendesk support platform; apps extend ticketing, chat, and help center functionality.



- **[ServiceNow Store](https://store.servicenow.com/)**  

  App marketplace for the Now Platform; certified apps and integrations for ITSM, HR, and security workflows.



- **[Shopify App Store](https://apps.shopify.com/)**  

  The **largest app marketplace by listings** with **13,151 active listings** and **5,502 partners** . **Fastest growing** (+613 listings, +4.66% in 30 days) . Hard approval process with revenue share; very high traffic for ecommerce apps .



- **[Slack App Directory](https://slack.com/apps)**  

  App directory for Slack; now unified into Salesforce's AgentExchange alongside AppExchange . Apps extend messaging, workflow automation, and third-party integrations.



- **[Microsoft AppSource](https://appsource.microsoft.com/)**  

  Microsoft's marketplace for business apps, add-ins, and agents across Microsoft 365, Dynamics 365, and Power Platform.



- **[AWS Marketplace](https://aws.amazon.com/marketplace)**  

  The largest enterprise data and software marketplace with **3,500+ paid commercial listings** and **48.45% market share** in data marketplace category. Purchases run through AWS billing against committed cloud spend.



## Open-Source GitHub Projects



### Plugin Registries & App Directories



- **[Tabularium](https://codeberg.org/Tabularium/Tabularium)**  

  The most complete open-source **self-hosted plugin registry** for distributing versioned artifacts (plugins, themes, snippets, SQL templates) . Features: **multi-provider submission** (GitHub, GitLab, Gitea, Forgejo—any self-hosted instance) with manifest preview on repo selection; **signed releases** (SHA-256 hash + Ed25519 signature, JWKS at `/.well-known/registry-key.json`, forwards GitHub build-provenance attestations) ; **plugin requests** with voting and claiming; **plugin ownership transfer**; **multi-language READMEs** via manifest `readmes:` field; **desktop app URL scheme** registration; **plugin type taxonomy** (Themes, Snippets, SQL templates) with separate public catalogs per type; **built-in CMS** with widget-enabled Markdown pages and per-language translation; **branding customization** (name, colors, logo, favicon, analytics, indexing policy) ; **6 languages**; **SQLite/Postgres/MySQL** auto-detected from `DATABASE_URL`; **feature flags** to disable submissions or requests without redeployment; **audit logs** for every admin action . Stack: Bun, Elysia, SvelteKit, Drizzle ORM, Dragonfly/Redis optional. **Best for teams wanting a self-hosted plugin registry** with signed releases and multi-provider Git integration—but it is a registry, not a commerce-enabled app store with billing.



- **[Open VSX](https://github.com/eclipse/openvsx)**  

  The **vendor-neutral, open-source alternative to the Visual Studio Marketplace** (Eclipse Foundation) . Full-stack solution: **Spring Boot backend** (PostgreSQL, Elasticsearch optional for search), **React web UI** (searchable gallery, user profiles, admin dashboard), and **Node.js CLI** (`ovsx`) for packaging and publishing from terminal/CI . Features: **VS Code protocol compatibility** (drop-in replacement for VS Code and VSCodium via `VSCodeAPI` adapter) ; **multi-backend storage** (Local Filesystem, AWS S3, Google Cloud Storage, Azure Blob Storage) ; **hybrid persistence** (JPA/Hibernate for CRUD, jOOQ for complex queries) . **The most mature open-source app store platform available**—but it is **VS Code extension-specific**, not a general-purpose SaaS app marketplace.



### Commerce Marketplace Engines (Build Your Own)



- **[Mercur](https://github.com/mercurjs/mercur)**  

  Open-source **multi-vendor marketplace engine** built on Medusa (MIT, ~1.6k GitHub stars) . Provides the marketplace primitives: seller onboarding, multi-vendor catalogs, per-seller commissions, admin panel, separate seller portal, and automated payouts (via Stripe Connect) . **Headless architecture**—you build your own storefront. **Best for teams wanting to build a commerce marketplace** (digital goods, services, or physical products) with vendor management—but it is **not a SaaS app store** with plugin installation, versioning, or runtime integration .



- **[Medusa](https://github.com/medusajs/medusa)**  

  Open-source headless commerce platform (MIT, ~30k GitHub stars) . Multi-vendor support via **community plugins** (e.g., `medusa-marketplace-plugin`) that add vendor stores, entity separation, and super admin impersonation . **Best for teams already on Medusa** wanting to add marketplace functionality—but it requires custom development and is not a turnkey app store .



### Additional Strong Open-Source Options



- **Saleor Apps** — Saleor's app ecosystem is open-source (BSD-3) and apps can be self-hosted, but **Saleor App Store itself is a Saleor Cloud feature** exclusive to cloud users . Self-hosted Saleor requires manual app installation .

- **Einstore** — Enterprise app store for internal app deployment, completely open source . **Niche**—for distributing internal enterprise apps rather than public SaaS marketplace listings.

- **zapstore** — Permissionless app store powered by your social network (Android) . **Consumer-focused**—for Android app distribution outside Google Play, not SaaS integrations.

- **AltStore PAL** — Open-source alternative app marketplace for iOS in the EU (enabled by the Digital Markets Act); apps are self-hosted by developers, users add sources manually . **EU-specific and iOS-only**—not relevant for SaaS app stores.



**Frameworks for building custom systems**: For a **self-hosted plugin registry with signed releases**, Tabularium provides the most complete open-source option . For a **VS Code-compatible extension marketplace**, Open VSX is the only mature choice . For a **commerce marketplace with vendors and payouts**, Mercur provides the primitives (accepting that it is not a SaaS app store) . **No open-source project replicates the enterprise procurement, billing, and runtime coupling** of Atlassian Marketplace, Salesforce AgentExchange, or Shopify App Store—those are platform-specific business integrations.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- SaaS app stores handling third-party applications and user data must comply with platform security review requirements, privacy regulations (GDPR, CCPA), and revenue-sharing agreements; **listing an app on a major marketplace often requires security certifications, code reviews, and compliance attestations**.

- **Open-source SaaS app store infrastructure is severely limited**—Tabularium provides a self-hosted plugin registry , and Open VSX provides a VS Code extension marketplace . However, **no open-source project replicates the enterprise procurement, billing, and runtime coupling** of Atlassian Marketplace, Salesforce AgentExchange, or Shopify App Store. These platforms derive their value from distribution to existing user bases and integrated billing—advantages that open-source software cannot provide.

- Verify license terms for commercial use; Tabularium is open-source (Codeberg) , Open VSX is hosted by the Eclipse Foundation (check repository license), and Mercur uses MIT .



---



**Made for platform engineers, developer relations teams, and organizations building or evaluating marketplace infrastructure.**  

Let's make SaaS app stores more open at the registry layer, but with clear eyes about the distribution and billing moats that commercial platforms still hold.

# Mealie

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Mealie is an open-source (AGPL-3.0), self-hosted recipe manager, meal planner and shopping-list application built on a FastAPI REST backend and a Vue frontend. Every feature in the UI is driven by the same public REST API: recipe CRUD and import-by-URL scraping, AI-assisted recipe creation, cookbooks, meal plans and mealplan rules, shopping lists and list items with cross-application "extras" key/value pairs, households and groups with multi-purpose labels, food/unit/tool organizers, a public "Explore" surface for unauthenticated browsing of shared content, scheduled webhooks, Apprise-backed event notifications, and admin backup/maintenance operations. The instance publishes its own OpenAPI 3.1 document and interactive Swagger UI at /openapi.json and /docs, authenticates with long-lived bearer API tokens (plus OIDC and LDAP for user login), and shares a uniform pagination, filtering and ordering grammar across nearly every collection endpoint.

**Areas:** Company · Recipes · Food · Meal Planning · Shopping Lists · Self-Hosted · Open Source · Household · Nutrition · Home Automation

## Mealie on APIs.io

Everything profiled for Mealie is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/mealie/](https://apis.io/providers/mealie/)** — or go straight to one of the APIs or properties below.

### APIs (57)

- [Mealie Admin: About API](https://apis.io/apis/mealie/mealie-admin-about-api/) — The Admin: About API from Mealie — 3 operation(s) for admin: about.
- [Mealie Admin: AI Providers API](https://apis.io/apis/mealie/mealie-admin-ai-providers-api/) — The Admin: AI Providers API from Mealie — 2 operation(s) for admin: ai providers.
- [Mealie Admin: Backups API](https://apis.io/apis/mealie/mealie-admin-backups-api/) — The Admin: Backups API from Mealie — 4 operation(s) for admin: backups.
- [Mealie Admin: Debug API](https://apis.io/apis/mealie/mealie-admin-debug-api/) — The Admin: Debug API from Mealie — 1 operation(s) for admin: debug.
- [Mealie Admin: Email API](https://apis.io/apis/mealie/mealie-admin-email-api/) — The Admin: Email API from Mealie — 1 operation(s) for admin: email.
- [Mealie Admin: Maintenance API](https://apis.io/apis/mealie/mealie-admin-maintenance-api/) — The Admin: Maintenance API from Mealie — 5 operation(s) for admin: maintenance.
- [Mealie Admin: Manage Groups API](https://apis.io/apis/mealie/mealie-admin-manage-groups-api/) — The Admin: Manage Groups API from Mealie — 2 operation(s) for admin: manage groups.
- [Mealie Admin: Manage Households API](https://apis.io/apis/mealie/mealie-admin-manage-households-api/) — The Admin: Manage Households API from Mealie — 2 operation(s) for admin: manage households.
- [Mealie Admin: Manage Users API](https://apis.io/apis/mealie/mealie-admin-manage-users-api/) — The Admin: Manage Users API from Mealie — 4 operation(s) for admin: manage users.
- [Mealie App: About API](https://apis.io/apis/mealie/mealie-app-about-api/) — The App: About API from Mealie — 3 operation(s) for app: about.
- [Mealie Explore: Categories API](https://apis.io/apis/mealie/mealie-explore-categories-api/) — The Explore: Categories API from Mealie — 2 operation(s) for explore: categories.
- [Mealie Explore: Cookbooks API](https://apis.io/apis/mealie/mealie-explore-cookbooks-api/) — The Explore: Cookbooks API from Mealie — 2 operation(s) for explore: cookbooks.
- [Mealie Explore: Foods API](https://apis.io/apis/mealie/mealie-explore-foods-api/) — The Explore: Foods API from Mealie — 2 operation(s) for explore: foods.
- [Mealie Explore: Households API](https://apis.io/apis/mealie/mealie-explore-households-api/) — The Explore: Households API from Mealie — 2 operation(s) for explore: households.
- [Mealie Explore: Recipes API](https://apis.io/apis/mealie/mealie-explore-recipes-api/) — The Explore: Recipes API from Mealie — 3 operation(s) for explore: recipes.
- [Mealie Explore: Tags API](https://apis.io/apis/mealie/mealie-explore-tags-api/) — The Explore: Tags API from Mealie — 2 operation(s) for explore: tags.
- [Mealie Explore: Tools API](https://apis.io/apis/mealie/mealie-explore-tools-api/) — The Explore: Tools API from Mealie — 2 operation(s) for explore: tools.
- [Mealie Groups: AI Provider Settings API](https://apis.io/apis/mealie/mealie-groups-ai-provider-settings-api/) — The Groups: AI Provider Settings API from Mealie — 1 operation(s) for groups: ai provider settings.
- [Mealie Groups: AI Providers API](https://apis.io/apis/mealie/mealie-groups-ai-providers-api/) — The Groups: AI Providers API from Mealie — 2 operation(s) for groups: ai providers.
- [Mealie Groups: Households API](https://apis.io/apis/mealie/mealie-groups-households-api/) — The Groups: Households API from Mealie — 2 operation(s) for groups: households.
- [Mealie Groups: Migrations API](https://apis.io/apis/mealie/mealie-groups-migrations-api/) — The Groups: Migrations API from Mealie — 1 operation(s) for groups: migrations.
- [Mealie Groups: Multi Purpose Labels API](https://apis.io/apis/mealie/mealie-groups-multi-purpose-labels-api/) — The Groups: Multi Purpose Labels API from Mealie — 2 operation(s) for groups: multi purpose labels.
- [Mealie Groups: Reports API](https://apis.io/apis/mealie/mealie-groups-reports-api/) — The Groups: Reports API from Mealie — 2 operation(s) for groups: reports.
- [Mealie Groups: Seeders API](https://apis.io/apis/mealie/mealie-groups-seeders-api/) — The Groups: Seeders API from Mealie — 3 operation(s) for groups: seeders.
- [Mealie Groups: Self Service API](https://apis.io/apis/mealie/mealie-groups-self-service-api/) — The Groups: Self Service API from Mealie — 5 operation(s) for groups: self service.
- [Mealie Households: Cookbooks API](https://apis.io/apis/mealie/mealie-households-cookbooks-api/) — The Households: Cookbooks API from Mealie — 2 operation(s) for households: cookbooks.
- [Mealie Households: Event Notifications API](https://apis.io/apis/mealie/mealie-households-event-notifications-api/) — The Households: Event Notifications API from Mealie — 3 operation(s) for households: event notifications.
- [Mealie Households: Invitations API](https://apis.io/apis/mealie/mealie-households-invitations-api/) — The Households: Invitations API from Mealie — 2 operation(s) for households: invitations.
- [Mealie Households: Mealplan Rules API](https://apis.io/apis/mealie/mealie-households-mealplan-rules-api/) — The Households: Mealplan Rules API from Mealie — 2 operation(s) for households: mealplan rules.
- [Mealie Households: Mealplans API](https://apis.io/apis/mealie/mealie-households-mealplans-api/) — The Households: Mealplans API from Mealie — 4 operation(s) for households: mealplans.
- [Mealie Households: Recipe Actions API](https://apis.io/apis/mealie/mealie-households-recipe-actions-api/) — The Households: Recipe Actions API from Mealie — 3 operation(s) for households: recipe actions.
- [Mealie Households: Self Service API](https://apis.io/apis/mealie/mealie-households-self-service-api/) — The Households: Self Service API from Mealie — 6 operation(s) for households: self service.
- [Mealie Households: Shopping List Items API](https://apis.io/apis/mealie/mealie-households-shopping-list-items-api/) — The Households: Shopping List Items API from Mealie — 3 operation(s) for households: shopping list items.
- [Mealie Households: Shopping Lists API](https://apis.io/apis/mealie/mealie-households-shopping-lists-api/) — The Households: Shopping Lists API from Mealie — 6 operation(s) for households: shopping lists.
- [Mealie Households: Webhooks API](https://apis.io/apis/mealie/mealie-households-webhooks-api/) — The Households: Webhooks API from Mealie — 4 operation(s) for households: webhooks.
- [Mealie Organizer: Categories API](https://apis.io/apis/mealie/mealie-organizer-categories-api/) — The Organizer: Categories API from Mealie — 5 operation(s) for organizer: categories.
- [Mealie Organizer: Tags API](https://apis.io/apis/mealie/mealie-organizer-tags-api/) — The Organizer: Tags API from Mealie — 5 operation(s) for organizer: tags.
- [Mealie Organizer: Tools API](https://apis.io/apis/mealie/mealie-organizer-tools-api/) — The Organizer: Tools API from Mealie — 3 operation(s) for organizer: tools.
- [Mealie Recipe: Bulk Actions API](https://apis.io/apis/mealie/mealie-recipe-bulk-actions-api/) — The Recipe: Bulk Actions API from Mealie — 7 operation(s) for recipe: bulk actions.
- [Mealie Recipe: Comments API](https://apis.io/apis/mealie/mealie-recipe-comments-api/) — The Recipe: Comments API from Mealie — 3 operation(s) for recipe: comments.
- [Mealie Recipe: CRUD API](https://apis.io/apis/mealie/mealie-recipe-crud-api/) — The Recipe: CRUD API from Mealie — 16 operation(s) for recipe: crud.
- [Mealie Recipe: Exports API](https://apis.io/apis/mealie/mealie-recipe-exports-api/) — The Recipe: Exports API from Mealie — 2 operation(s) for recipe: exports.
- [Mealie Recipe: Images and Assets API](https://apis.io/apis/mealie/mealie-recipe-images-and-assets-api/) — The Recipe: Images and Assets API from Mealie — 5 operation(s) for recipe: images and assets.
- [Mealie Recipe: Ingredient Parser API](https://apis.io/apis/mealie/mealie-recipe-ingredient-parser-api/) — The Recipe: Ingredient Parser API from Mealie — 2 operation(s) for recipe: ingredient parser.
- [Mealie Recipe: Shared API](https://apis.io/apis/mealie/mealie-recipe-shared-api/) — The Recipe: Shared API from Mealie — 2 operation(s) for recipe: shared.
- [Mealie Recipe: Timeline API](https://apis.io/apis/mealie/mealie-recipe-timeline-api/) — The Recipe: Timeline API from Mealie — 3 operation(s) for recipe: timeline.
- [Mealie Recipes: Foods API](https://apis.io/apis/mealie/mealie-recipes-foods-api/) — The Recipes: Foods API from Mealie — 3 operation(s) for recipes: foods.
- [Mealie Recipes: Units API](https://apis.io/apis/mealie/mealie-recipes-units-api/) — The Recipes: Units API from Mealie — 3 operation(s) for recipes: units.
- [Mealie Shared: Recipes API](https://apis.io/apis/mealie/mealie-shared-recipes-api/) — The Shared: Recipes API from Mealie — 2 operation(s) for shared: recipes.
- [Mealie Users: Authentication API](https://apis.io/apis/mealie/mealie-users-authentication-api/) — The Users: Authentication API from Mealie — 7 operation(s) for users: authentication.
- [Mealie Users: CRUD API](https://apis.io/apis/mealie/mealie-users-crud-api/) — The Users: CRUD API from Mealie — 6 operation(s) for users: crud.
- [Mealie Users: Images API](https://apis.io/apis/mealie/mealie-users-images-api/) — The Users: Images API from Mealie — 1 operation(s) for users: images.
- [Mealie Users: Passwords API](https://apis.io/apis/mealie/mealie-users-passwords-api/) — The Users: Passwords API from Mealie — 2 operation(s) for users: passwords.
- [Mealie Users: Ratings API](https://apis.io/apis/mealie/mealie-users-ratings-api/) — The Users: Ratings API from Mealie — 4 operation(s) for users: ratings.
- [Mealie Users: Registration API](https://apis.io/apis/mealie/mealie-users-registration-api/) — The Users: Registration API from Mealie — 1 operation(s) for users: registration.
- [Mealie Users: Tokens API](https://apis.io/apis/mealie/mealie-users-tokens-api/) — The Users: Tokens API from Mealie — 2 operation(s) for users: tokens.
- [Mealie Utils API](https://apis.io/apis/mealie/mealie-utils-api/) — The Utils API from Mealie — 1 operation(s) for utils.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Mealie Events](https://apis.io/asyncapis/mealie/mealie-events/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [mealie-mcp.yml](https://apis.io/servers/mealie/mealie-mcp-yml/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Mealie Openapi Overlay](https://apis.io/overlays/mealie/mealie-openapi-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Mealie Authentication](https://apis.io/security/mealie/mealie-authentication/)
- [Mealie Domain Security](https://apis.io/security/mealie/mealie-domain-security/)
- [Mealie Vulnerability Disclosure](https://apis.io/security/mealie/mealie-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Mealie Scopes](https://apis.io/scopes/mealie/mealie-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Mealie Plans Pricing](https://apis.io/plans/mealie/mealie-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Mealie Rate Limits](https://apis.io/rate-limits/mealie/mealie-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://mealie.io)
- [Documentation](https://docs.mealie.io)
- [Getting started](https://docs.mealie.io/documentation/getting-started/introduction/)
- [API reference](https://demo.mealie.io/docs)
- [Support](https://github.com/mealie-recipes/mealie/discussions)
- [GitHub](https://github.com/mealie-recipes)

## API Evangelist rating

**Kin Score 38.8** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 49.2 |
| Contract governance | 4.5 |
| Operational transparency | 42.1 |
| Developer ergonomics | 56.5 |
| Access clarity | 0.0 |

**Agent readiness 27.4** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 32.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/mealie/](https://apis.io/providers/mealie/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Mealie: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/mealie/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).

# HoneyBook (honeybook)

HoneyBook is an all-in-one clientflow management platform for independent, service-based businesses - photographers, event planners, designers, consultants, coaches, and similar creative entrepreneurs. It combines CRM/lead capture, proposals, contracts and e-signature, invoicing and payments, scheduling, automations, and client communication in one product. HoneyBook does not publish a self-serve public developer API or a developer portal; third-party connectivity is offered through a limited set of native integrations (QuickBooks Online, Zoom, Calendly, Flodesk, Canva, Meta Leads, Slack, Asana, monday.com) and, most broadly, through Zapier. An internal API host (api.honeybook.com) is live and clearly powers the Zapier integration and native connectors, but HoneyBook has never published a self-serve technical reference, OAuth client registration flow, or endpoint documentation for outside developers, and community requests for direct API access date back to at least January 2024 with no roadmap commitment as of this review.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/honeybook/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/honeybook/refs/heads/main/apis.yml)

## No Public Developer API

This is important context for everything below: **HoneyBook has no documented public API.** There is no `developers.honeybook.com` (the domain does not resolve), no self-serve reference, and no published OAuth client registration flow. The logical APIs listed below are an honest, clearly-labeled *model* of HoneyBook's resource surface - built from its product feature set and the five event names exposed through its Zapier integration (New Client, New Inquiry, Project Booked, Payment Received, Project Stage Changed) - not a confirmed reference. See [review.yml](review.yml) for full sourcing and verification notes.

## Tags

- CRM
- Clientflow
- Proposals
- Contracts
- Invoicing
- Payments
- Scheduling
- Creative Entrepreneurs
- Small Business

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

### HoneyBook Clients & Contacts API

Not a documented public API. Modeled from HoneyBook's Zapier triggers ("New Client," "New Inquiry") and product feature set - create, list, and retrieve clients and inquiries/leads captured through lead forms.

- **Human URL:** [https://help.honeybook.com/en/collections/68941-integrations-and-partnerships](https://help.honeybook.com/en/collections/68941-integrations-and-partnerships)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeybook.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeybook.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### HoneyBook Projects API

Not a documented public API. Modeled from HoneyBook's visual project pipeline and its Zapier triggers ("Project Booked," "Project Stage Changed") - create and list projects, and read/react to pipeline stage transitions.

- **Human URL:** [https://help.honeybook.com/en/collections/68941-integrations-and-partnerships](https://help.honeybook.com/en/collections/68941-integrations-and-partnerships)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeybook.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### HoneyBook Contracts API

Not a documented public API. Modeled as list/create/retrieve operations scoped to a project, mirroring how contracts are exposed in the product UI.

- **Human URL:** [https://www.honeybook.com/online-contracts](https://www.honeybook.com/online-contracts)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://www.honeybook.com/online-contracts)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### HoneyBook Proposals API

Not a documented public API. HoneyBook proposals combine a quote, contract, and invoice into one client-facing document, tracked as part of the "Project Booked" milestone in Zapier.

- **Human URL:** [https://www.honeybook.com/online-proposals](https://www.honeybook.com/online-proposals)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://www.honeybook.com/online-proposals)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### HoneyBook Invoices & Payments API

Not a documented public API. Modeled from HoneyBook's invoicing/payments feature and its "Payment Received" Zapier trigger. Card payments are processed starting at 2.7% + 10 cents and ACH transfers at 1.5% per HoneyBook's published pricing page.

- **Human URL:** [https://www.honeybook.com/pricing](https://www.honeybook.com/pricing)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://www.honeybook.com/pricing)
- [Documentation](https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### HoneyBook Scheduler API

Not a documented public API. HoneyBook Scheduler lets clients self-book session types against a provider's availability, gated to the Essentials and Premium plans (Starter is capped at one live session type).

- **Human URL:** [https://www.honeybook.com/features/scheduling](https://www.honeybook.com/features/scheduling)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://www.honeybook.com/features/scheduling)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### HoneyBook Webhooks / Automation Events

Not a documented public webhook API. HoneyBook's event surface is only exposed indirectly, as polling-based triggers inside its Zapier integration (New Client, New Inquiry, Project Booked, Payment Received, Project Stage Changed). Modeled here as a generic subscribe/list/delete webhook surface for completeness only.

- **Human URL:** [https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier](https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier)
- **Base URL:** `https://api.honeybook.com/v1` (modeled, unverified)

#### Properties

- [Documentation](https://help.honeybook.com/en/articles/2209205-automate-tasks-with-zapier)
- [OpenAPI](openapi/honeybook-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [GitHub Organization](https://github.com/honeybook)
- [LinkedIn](https://www.linkedin.com/company/honeybook)
- [Website](https://www.honeybook.com)
- [Documentation](https://help.honeybook.com/en/collections/68941-integrations-and-partnerships)
- [Plans](plans/honeybook-plans-pricing.yml)
- [Rate Limits](rate-limits/honeybook-rate-limits.yml)
- [Fin Ops](finops/honeybook-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

# Scalable Press (scalablepress)

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

Scalable Press is a technology-driven print-on-demand and fulfillment platform for custom apparel, accessories, and promotional products. It offers DTG (direct-to-garment) and screen printing, embroidery, laser engraving, posters, and phone cases, and ships worldwide. Its public REST API lets developers browse a wholesale blank-and-printed product catalog, generate price quotes (product, printing, and shipping costs), place and manage print-and-ship orders, track fulfillment through order events, create designs and product mockups, and retrieve billing invoices.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/scalablepress/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/scalablepress/refs/heads/main/apis.yml)

## Access Model

- **Public REST API** served from `https://api.scalablepress.com`, spanning a **v2** surface (Product, Quote, Order, Design, Customization, Billing) and a **v3** surface (Event, Mockup).
- **Authentication is HTTP Basic auth.** Your private API key is supplied as the **password**; the username is left blank. Keys are issued from your Scalable Press account.
- **Pay-per-order pricing.** There is no monthly subscription fee — you pay the product (blank) cost plus printing plus shipping per order. Orders can be placed on account credit and are held when credit is insufficient. High-volume/wholesale rates are arranged directly with Scalable Press.
- **No public WebSocket API.** Order and item status is exposed through the pull-based v3 Event API (polled over HTTP), not a server-push transport. See `review.yml`.
- Scalable Press is a commercial, closed-source SaaS platform (not self-hostable).

## Tags

- Print on Demand
- Fulfillment
- Apparel
- Custom Printing
- E-Commerce
- Wholesale

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Scalable Press Product API

Browse the wholesale blank-and-printed product catalog — list categories, list the products in a category, and retrieve product information, per-variant availability, and item-level details (colors, sizes, SKUs, pricing).

- **Base URL:** `https://api.scalablepress.com/v2`

### Scalable Press Quote API

Generate standard or bulk price quotes before ordering, itemizing product, printing, and shipping costs. Select custom shipping methods per item using carrier service codes (USPS, UPS, FedEx, DHL), and retrieve a saved quote by order token.

- **Base URL:** `https://api.scalablepress.com/v2`

### Scalable Press Order API

Place and manage print-and-ship orders — submit an order from a quote token, reprint, list orders, retrieve a single order, change the shipping address, and cancel an order.

- **Base URL:** `https://api.scalablepress.com/v2`

### Scalable Press Event API

Track order and item lifecycle through events (order, validated, paid, unpaid, printing, shipped, cancelled, address-changed, expired, hold) — query events and retrieve a single event by ID.

- **Base URL:** `https://api.scalablepress.com/v3`

### Scalable Press Design API

Create and manage reusable design objects describing artwork and its placement on a product; reference them from quotes and orders.

- **Base URL:** `https://api.scalablepress.com/v2`

### Scalable Press Mockup API

Render product mockups that preview a design applied to a product.

- **Base URL:** `https://api.scalablepress.com/v3`

### Scalable Press Billing API

Retrieve account billing — list invoices, retrieve a single invoice, and pay an invoice via PayPal.

- **Base URL:** `https://api.scalablepress.com/v2`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/scalablepress)
- [Website](https://scalablepress.com)
- [Documentation](https://scalablepress.com/docs/)
- [Sign Up / Developer API](https://scalablepress.com/api)
- [Plans](plans/scalablepress-plans-pricing.yml)
- [Rate Limits](rate-limits/scalablepress-rate-limits.yml)
- [Fin Ops](finops/scalablepress-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

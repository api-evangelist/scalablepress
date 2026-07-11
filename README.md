# Scalable Press (scalablepress)

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

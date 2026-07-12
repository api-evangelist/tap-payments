# Tap Payments (tap-payments)

Tap Payments is a payment gateway and financial infrastructure provider for the Middle East and North Africa (MENA). Its REST API lets merchants accept online payments across the GCC and Egypt - cards (Visa, Mastercard, Amex), local schemes (mada in Saudi Arabia, KNET in Kuwait, Benefit in Bahrain), and wallets (Apple Pay, Google Pay) - through Charges and Authorize/Capture flows, with Tokens for saved cards, plus Customers, Cards, Refunds, Invoices, Payouts, and merchant onboarding via the Business API.

## Access Model (read this first)

- **Self-serve, key-based.** Sign up on the [Tap dashboard](https://www.tap.company), get API keys, and start integrating. No formal API application/partner gate is required to reach the developer docs or test mode.
- **Test and live keys are separate.** Each mode has its own secret key generated in the dashboard. Test keys are prefixed `sk_test_`; live keys are prefixed `sk_live_`. There are also publishable keys (`pk_test_` / `pk_live_`) for client-side tokenization.
- **Authentication is a secret API key sent as a Bearer token:** `Authorization: Bearer sk_test_XXXXXXXX`. The secret key must stay server-side.
- **Live processing requires an approved, KYC'd merchant account** in a supported market. You can build and test fully in test mode before that approval; going live and receiving payouts requires business verification.
- **Regional footprint:** GCC (Kuwait, Saudi Arabia, UAE, Bahrain, Qatar, Oman) plus Egypt, with a single integration across markets.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tap-payments/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tap-payments/refs/heads/main/apis.yml)

**Base URL:** `https://api.tap.company/v2`

## Tags

- Payments
- Fintech
- Payment Gateway
- MENA
- Middle East
- Online Payments
- Charges
- Cards
- KNET
- mada
- Financial Infrastructure

## Timestamps

- **Created:** 2026-07-12
- **Modified:** 2026-07-12

## APIs

### Tap Payments Charges API

Create, retrieve, update, and list charges to charge a card or other payment source. Supports 3D Secure redirect flows, saved-card tokens, local schemes (mada, KNET, Benefit), and wallets. A charge references a source (token or authorize id) and a customer.

- **Human URL:** [https://developers.tap.company/reference/create-a-charge](https://developers.tap.company/reference/create-a-charge)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Charges
- Payments
- Cards

#### Properties

- [Documentation](https://developers.tap.company/docs/get-started)
- [API Reference](https://developers.tap.company/reference/create-a-charge)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Authorize API

Authorize (hold) funds on a card without capturing, then capture later by creating a charge that references the authorize id. Supports void and auto-capture windows for two-step card payments.

- **Human URL:** [https://developers.tap.company/reference/authorize](https://developers.tap.company/reference/authorize)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Authorize
- Capture
- Payments

#### Properties

- [API Reference](https://developers.tap.company/reference/authorize)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Refunds API

Issue full or partial refunds against a captured charge, then retrieve and list refunds. Refunds reference the original charge id and settle back to the original payment method.

- **Human URL:** [https://developers.tap.company/reference/create-a-refund](https://developers.tap.company/reference/create-a-refund)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Refunds
- Payments

#### Properties

- [API Reference](https://developers.tap.company/reference/create-a-refund)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Customers API

Create, retrieve, update, delete, and list customers. Tap issues a unique customer id (returned from Charges/Authorize) that you reuse to save cards, run recurring payments, and reconcile transactions.

- **Human URL:** [https://developers.tap.company/reference/create-a-customer](https://developers.tap.company/reference/create-a-customer)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Customers
- Vaulting

#### Properties

- [API Reference](https://developers.tap.company/reference/create-a-customer)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Tokens API

Tokenize a raw card, an encrypted card, a saved card, or a wallet (Apple Pay, Samsung Pay, network token) into a single-use token id consumed by the Charges or Authorize APIs. Tokens cannot be stored or reused.

- **Human URL:** [https://developers.tap.company/reference/tokens](https://developers.tap.company/reference/tokens)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Tokens
- Cards
- PCI

#### Properties

- [API Reference](https://developers.tap.company/reference/tokens)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Cards API

Manage saved cards (card-on-file) attached to a customer - retrieve, verify, list, and delete stored cards for recurring and one-click checkout.

- **Human URL:** [https://developers.tap.company/reference/retrieve-a-card](https://developers.tap.company/reference/retrieve-a-card)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Cards
- Card on File

#### Properties

- [API Reference](https://developers.tap.company/reference/retrieve-a-card)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Invoices API

Create, retrieve, update, and list hosted invoices that generate a payable link delivered by email or SMS. Invoices carry line items, currency, due dates, and customer details, and produce a charge when paid.

- **Human URL:** [https://developers.tap.company/reference/create-an-invoice](https://developers.tap.company/reference/create-an-invoice)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Invoices
- Billing

#### Properties

- [API Reference](https://developers.tap.company/reference/create-an-invoice)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Payouts API

Retrieve and list payouts (settlements) that Tap deposits to your business bank account, with a download endpoint for reconciliation exports.

- **Human URL:** [https://developers.tap.company/reference/retrieve-a-payout](https://developers.tap.company/reference/retrieve-a-payout)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Payouts
- Settlement

#### Properties

- [API Reference](https://developers.tap.company/reference/retrieve-a-payout)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Business API

Onboard and manage businesses, merchants, and their destinations for marketplace and platform use cases - create a business, list merchants, and look up destinations that funds settle to.

- **Human URL:** [https://developers.tap.company/reference/create-a-business](https://developers.tap.company/reference/create-a-business)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Onboarding
- Merchants
- Marketplace

#### Properties

- [API Reference](https://developers.tap.company/reference/create-a-business)
- [OpenAPI](openapi/tap-payments-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/tap-payments.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/tap-payments.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Tap Payments Webhooks

Server-to-server HTTP POST callbacks (Instant Payment Notification) that Tap sends to your configured endpoint when a charge, authorize, invoice, or recurring payment changes state. Payloads are signed with an HMAC-SHA256 `hashstring` header for verification. This is HTTP push, not a WebSocket.

- **Human URL:** [https://developers.tap.company/docs/webhook](https://developers.tap.company/docs/webhook)
- **Base URL:** `https://api.tap.company/v2`

#### Tags

- Webhooks
- Events
- Notifications

#### Properties

- [Documentation](https://developers.tap.company/docs/webhook)

## Common Properties

- [Domain Security](security/tap-payments-domain-security.yml)
- [Authentication](authentication/tap-payments-authentication.yml)
- [GitHub Organization](https://github.com/Tap-Payments)
- [LinkedIn](https://www.linkedin.com/company/tap-payments)
- [Website](https://www.tap.company)
- [Documentation](https://developers.tap.company/docs/get-started)
- [Plans](plans/tap-payments-plans-pricing.yml)
- [Rate Limits](rate-limits/tap-payments-rate-limits.yml)
- [Fin Ops](finops/tap-payments-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

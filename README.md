# Till Payments (till-payments)

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

Till Payments is a Sydney, Australia founded merchant acquirer and integrated-payments technology company (established 2012), focused on payments for independent software vendors, platforms, and omnichannel merchants across online, in-person, and unattended channels. Till was acquired by Nuvei in 2024 and operates as part of Nuvei's global platform while retaining its Australian home market and developer surface.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/till-payments/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/till-payments/refs/heads/main/apis.yml)

## Tags

- Payments
- Australia
- Payment Gateway
- Payment Processing
- Acquiring
- Merchant Services
- Card Payments
- In-Person Payments

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Till Payments Gateway API

The Gateway V3 API for card-present and card-not-present transactions — debit, preauthorize, capture, void, refund, payout, registration/tokenization, recurring schedules, transaction status, 3-D Secure/DCC, and dispute handling — with asynchronous callbacks via a merchant-supplied `callbackUrl`.

- **Human URL:** [https://gateway.tillpayments.com/documentation/apiv3](https://gateway.tillpayments.com/documentation/apiv3)
- **Base URL:** `https://gateway.tillpayments.com/api/v3`
- [OpenAPI](openapi/till-payments-gateway.yml)
- [Documentation](https://gateway.tillpayments.com/documentation/gateway)
- [API Reference](https://gateway.tillpayments.com/documentation/apiv3)

### Till Payments Direct PCI-enabled API

The Direct PCI-enabled Payment Platform V3 API for merchants that are PCI DSS certified to collect and transmit raw cardholder data, over HTTPS (TLS 1.2+) with JSON bodies.

- **Human URL:** [https://gateway.tillpayments.com/documentation/json-direct-pci-enabled-api](https://gateway.tillpayments.com/documentation/json-direct-pci-enabled-api)
- **Base URL:** `https://secure.tillpayments.com/api/v3`
- [OpenAPI](openapi/till-payments-direct-pci.yml)
- [API Reference](https://gateway.tillpayments.com/documentation/json-direct-pci-enabled-api)

### Till Payments Pay By Link API

Generate shareable hosted payment links. Documented on the Till developer documentation site; no downloadable OpenAPI spec was published at review time.

- **Human URL:** [https://docs.tillpayments.com/openapi/pay-by-link/paybylink/overview/](https://docs.tillpayments.com/openapi/pay-by-link/paybylink/overview/)

### Till Payments Terminal Connect API

In-person integration surface for connecting point-of-sale software to Till payment terminals. Documented via getting-started and integration guides; no downloadable OpenAPI spec was published at review time.

- **Human URL:** [https://docs.tillpayments.com/guides/terminal-connect/getting-started/](https://docs.tillpayments.com/guides/terminal-connect/getting-started/)

## Links

- **Website:** [https://tillpayments.com/](https://tillpayments.com/)
- **Developer Hub:** [https://tillpayments.com/developer-hub](https://tillpayments.com/developer-hub)
- **Documentation:** [https://docs.tillpayments.com/guides](https://docs.tillpayments.com/guides)
- **Status:** [https://status.tillpayments.com/](https://status.tillpayments.com/)
- **GitHub:** [https://github.com/tillpayments](https://github.com/tillpayments)
- **Pricing:** [https://tillpayments.com/pricing](https://tillpayments.com/pricing)
- **Blog:** [https://tillpayments.com/blog](https://tillpayments.com/blog)

## Authentication

HTTP Basic authentication over TLS 1.2+. Both harvested OpenAPI specs declare a single `basicAuth` security scheme.

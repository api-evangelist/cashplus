# Cashplus Bank (cashplus)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Cashplus Bank (legal entity Advanced Payment Solutions Limited, rebranded to **Zempler Bank** in July 2024) is a UK challenger bank founded in 2005 that grew from a prepaid-card issuer into a fully licensed bank, receiving its UK banking licence in 2021 and regulated by the Financial Conduct Authority (FCA) and the Prudential Regulation Authority (PRA). It focuses on business current accounts, personal current accounts, credit cards, and payments for micro-enterprises, sole traders, and small-to-medium businesses. Following a 2026 acquisition it operates as a subsidiary of The Access Bank UK (part of Nigeria's Access Bank plc). As an FCA-authorised ASPSP it participates in UK Open Banking under PSD2 — publishing Read/Write APIs conformant to the Open Banking Implementation Entity (OBIE) standard for Account Information (AIS), Payment Initiation (PIS), and Confirmation of Funds (CBPII), secured with FAPI-grade OAuth2/OIDC, mutual-TLS, PSD2 strong customer authentication, and OBIE/eIDAS certificates. Cashplus is **not** one of the CMA9 mandated banks. Alongside the regulated Open Banking surface it runs a first-party partner/developer platform documenting proprietary Identity, Accounts, Applications, Eligibility, Payments, Products, and Transactions APIs for embedded and commercial integrations.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cashplus/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cashplus/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- FAPI
- United Kingdom
- Payments
- Account Information
- Challenger Bank
- Business Banking
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Open Banking (OBIE Read/Write)

- **Cashplus Account Information API** — AISP API conformant to the OBIE Read/Write Standard (accounts, balances, transactions, standing orders, direct debits, beneficiaries, statements). [Docs](https://developer.zemplerbank.com/developer-guides/open-banking/identity) · [OpenAPI](openapi/cashplus-account-information-openapi.yml)
- **Cashplus Payment Initiation API** — PISP API conformant to the OBIE Read/Write Standard (domestic payments, scheduled payments, standing orders). [Docs](https://developer.zemplerbank.com/developer-guides/open-banking/identity) · [OpenAPI](openapi/cashplus-payment-initiation-openapi.yml)
- **Cashplus Confirmation of Funds API** — CBPII funds-confirmation API conformant to the OBIE Read/Write Standard. [Docs](https://developer.zemplerbank.com/developer-guides/open-banking/identity) · [OpenAPI](openapi/cashplus-confirmation-of-funds-openapi.yml)

The three OpenAPI documents in `openapi/` are the **shared OBIE UK Open Banking Read/Write v3.1.11** specifications that Cashplus/Zempler conforms to, harvested verbatim from the official OpenBankingUK repository — they are the standard, not a bank-proprietary contract.

### First-party partner APIs (developer.zemplerbank.com)

Documented for partners with a direct commercial relationship; require developer-portal onboarding.

- **Cashplus Identity API** — authentication and registration. [Docs](https://developer.zemplerbank.com/developer-guides/api/identity)
- **Cashplus Accounts API** — real-time account details and balance. [Docs](https://developer.zemplerbank.com/developer-guides/api/accounts)
- **Cashplus Applications API** — open new current accounts programmatically. [Docs](https://developer.zemplerbank.com/developer-guides/api/applications)
- **Cashplus Eligibility API** — credit card eligibility checks. [Docs](https://developer.zemplerbank.com/developer-guides/api/eligibility)
- **Cashplus Payments API** — single and batch domestic GBP payments. [Docs](https://developer.zemplerbank.com/developer-guides/api/payments)
- **Cashplus Products API** — product catalogue queries. [Docs](https://developer.zemplerbank.com/developer-guides/api/products)
- **Cashplus Transactions API** — search and filter transactions. [Docs](https://developer.zemplerbank.com/developer-guides/api/transactions)

## Common Properties

- [Website](https://www.zemplerbank.com/)
- [Developer Portal](https://developer.zemplerbank.com/)
- [API / Developer Overview](https://www.zemplerbank.com/api-developer/)
- [Open Banking](https://www.zemplerbank.com/api/)
- [Open Banking Directory](https://www.openbanking.org.uk/customers/regulated-providers/)
- [LinkedIn](https://www.linkedin.com/company/zemplerbank)
- [Blog / News](https://www.zemplerbank.com/about/news/)
- [Terms and Conditions](https://www.zemplerbank.com/terms-and-conditions/)
- [Legal](https://www.zemplerbank.com/legal/)
- [Privacy Policy](https://www.zemplerbank.com/policies/privacy-policy/)
- [Help / Support](https://www.zemplerbank.com/help/)
- [Contact](https://www.zemplerbank.com/contact/)
- [Status Page](https://status.zemplerbank.com/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

# Cashplus Bank (cashplus)

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

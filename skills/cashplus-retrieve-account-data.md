---
name: Retrieve account information (AIS)
description: Establish an account-access consent and read a customer's Cashplus/Zempler account details, balances and transactions over the OBIE Account Information API.
api: openapi/cashplus-account-information-openapi.yml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountId, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Retrieve account information (AIS)

Read-only access to a PSU's Cashplus/Zempler (Zempler Bank) accounts under the UK Open Banking OBIE Read/Write standard. Requires TPP onboarding via the Open Banking Directory, FAPI OAuth2/OIDC, and mutual-TLS.

## Preconditions
- Registered TPP with an eIDAS/OBIE transport + signing certificate.
- `clientCredentials` token (scope `accounts`) for TPP-only calls; PSU `authorizationCode` token after SCA for resource access.
- Send FAPI headers on every call: `x-fapi-interaction-id`, `x-fapi-auth-date`, `x-fapi-customer-ip-address`, `x-customer-user-agent`.

## Steps
1. **Create the consent** — `CreateAccountAccessConsents` with the requested `Permissions` (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`). Returns a `ConsentId` in `AwaitingAuthorisation`.
2. **Have the PSU authorise** — redirect the PSU through the bank's SCA/OIDC flow; exchange the code for a PSU access token.
3. **Confirm consent status** — `GetAccountAccessConsentsConsentId` should now report `Authorised`.
4. **List accounts** — `GetAccounts` returns the accounts covered by the consent.
5. **Read detail** — `GetAccountsAccountId`, `GetAccountsAccountIdBalances`, `GetAccountsAccountIdTransactions` for each `AccountId`. Page forward via `Links.Next`; total pages in `Meta.TotalPages`.

## Rules
- Only request permissions you need; the consent gates every downstream read.
- Errors return the `OBErrorResponse1` envelope with `UK.OBIE.*` detail codes (see errors/cashplus-problem-types.yml).
- Respect `429` throttling on transaction polling.

---
name: Confirm funds availability (CBPII)
description: Establish a funds-confirmation consent and check whether sufficient funds are available on a Cashplus/Zempler account over the OBIE Confirmation of Funds API.
api: openapi/cashplus-confirmation-of-funds-openapi.yml
operations: [CreateFundsConfirmationConsents, GetFundsConfirmationConsentsConsentId, CreateFundsConfirmations, DeleteFundsConfirmationConsentsConsentId]
---

# Confirm funds availability (CBPII)

Card-Based Payment Instrument Issuer (CBPII) funds check under the OBIE Read/Write Confirmation of Funds standard. Requires TPP onboarding, FAPI OAuth2/OIDC, and mutual-TLS.

## Preconditions
- Registered CBPII with OBIE/eIDAS certificates; `fundsconfirmations` scope.
- FAPI headers on every call; PSU authorisation of the funds-confirmation consent via SCA/OIDC.

## Steps
1. **Create the consent** — `CreateFundsConfirmationConsents` with the `DebtorAccount` and consent `ExpirationDateTime`. Returns a `ConsentId` in `AwaitingAuthorisation`.
2. **PSU authorises** — the PSU consents via SCA; the consent becomes `Authorised`.
3. **Confirm status** — `GetFundsConfirmationConsentsConsentId` returns the consent status.
4. **Check funds** — `CreateFundsConfirmations` with the authorised `ConsentId` and an `InstructedAmount`; the response `FundsAvailable` boolean indicates availability. This never reveals the balance.
5. **Revoke when done** — `DeleteFundsConfirmationConsentsConsentId` to end the consent.

## Rules
- The funds check returns only a yes/no `FundsAvailable`, never the account balance.
- Errors use the `OBErrorResponse1` envelope with `UK.OBIE.*` codes (see errors/cashplus-problem-types.yml).

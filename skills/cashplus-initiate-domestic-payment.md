---
name: Initiate a domestic payment (PIS)
description: Create a domestic payment consent, confirm funds, and initiate a single domestic GBP payment from a Cashplus/Zempler account over the OBIE Payment Initiation API with idempotent replay.
api: openapi/cashplus-payment-initiation-openapi.yml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a domestic payment (PIS)

Initiate a single domestic GBP payment from a PSU's Cashplus/Zempler account under the OBIE Read/Write Payment Initiation standard. Requires TPP onboarding, FAPI OAuth2/OIDC, mutual-TLS, and a detached JWS signature.

## Preconditions
- TPP with eIDAS/OBIE certificates; `payments` scope.
- FAPI headers on every call; `x-jws-signature` (detached JWS over the body) on payment operations.
- `x-idempotency-key` (max 40 chars) on every create call — a replay with the same key returns the original resource instead of duplicating the payment.

## Steps
1. **Create the payment consent** — `CreateDomesticPaymentConsents` with the `Initiation` block (creditor account, `InstructedAmount`, reference). Returns a `ConsentId`.
2. **PSU authorises** — send the PSU through SCA/OIDC; obtain the PSU access token.
3. **Confirm consent + funds** — `GetDomesticPaymentConsentsConsentId` should be `Authorised`; optionally `GetDomesticPaymentConsentsConsentIdFundsConfirmation` to check funds availability.
4. **Initiate the payment** — `CreateDomesticPayments` referencing the authorised `ConsentId`, with a fresh `x-idempotency-key` and matching `Initiation` block. Returns a `DomesticPaymentId`.
5. **Track status** — poll `GetDomesticPaymentsDomesticPaymentId` for `AcceptedSettlementCompleted` / `Rejected`.

## Rules
- The `Initiation` block on the payment MUST match the consent exactly or you get `UK.OBIE.Resource.ConsentMismatch`.
- Late submissions return `UK.OBIE.Rules.AfterCutOffDateTime`; duplicate references return `UK.OBIE.Rules.DuplicateReference`.
- Always send `x-idempotency-key` to make retries safe (see conventions/cashplus-conventions.yml).

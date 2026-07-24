---
name: Authorize and capture a card payment
description: Reserve funds on a card with a preauthorization, then capture some or all of the amount, using the Till Payments Gateway V3 API.
api: openapi/till-payments-gateway.yml
operations: [processPreauthorize, processCapture, processVoid, transactionStatusByUuid]
---

# Authorize and capture a card payment (Till Payments Gateway V3)

Use this two-step "auth then capture" flow when you need to reserve funds now and settle later (e.g. order placed, fulfilled on ship).

## Auth
- HTTP Basic: `Authorization: Basic base64(username:password)` over TLS 1.2+.
- The per-connector `apiKey` is a **path** segment: `/api/v3/transaction/{apiKey}/preauthorize`.
- Optional but recommended: HMAC-SHA512 request signing (enable "API: Enable Request Signing" on the connector).

## Steps
1. **Preauthorize** — call `processPreauthorize` with a unique `merchantTransactionId`, `amount`, `currency`, and either card data / `transactionToken` / a hosted redirect. Reads back a `uuid` and a `returnType`.
2. **Handle the returnType** — `FINISHED` = authorized; `REDIRECT`/`PENDING` = wait for the asynchronous callback to `callbackUrl` before treating it as authorized (trust the callback, not the browser redirect); `ERROR` = inspect `errors[].errorCode`.
3. **Capture** — call `processCapture` referencing the authorization's `uuid` (via `referenceUuid`) with the amount to settle (full or partial).
4. **Cancel instead?** — call `processVoid` against the authorization `uuid` to release the hold.
5. **Verify** — call `transactionStatusByUuid` to confirm the final state.

## Rules
- `merchantTransactionId` MUST be unique per transaction — reusing one returns `errorCode 3004` ("transaction ID already exists"). This is the idempotency guard; generate a fresh id per attempt and look up prior results with `transactionStatusByMerchantTransactionId`.
- Branch on the numeric `errorCode`, never the human `errorMessage`.
- See `conventions/till-payments-conventions.yml` and `errors/till-payments-problem-types.yml`.

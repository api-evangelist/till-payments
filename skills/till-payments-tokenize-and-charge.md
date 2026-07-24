---
name: Tokenize a card and charge it
description: Register (tokenize) a payment instrument once, then charge it with a debit using the stored transactionToken, on the Till Payments Gateway V3 API.
api: openapi/till-payments-gateway.yml
operations: [processRegister, processPrepareRegister, processDebit, processDeregister]
---

# Tokenize a card and charge it (Till Payments Gateway V3)

Use this flow to store a customer's payment instrument for repeat or card-on-file charges without re-collecting card data.

## Auth
HTTP Basic over TLS 1.2+; `apiKey` in the path (`/api/v3/transaction/{apiKey}/register`). Optional HMAC-SHA512 signing.

## Steps
1. **Register** — call `processRegister` (or `processPrepareRegister` for the hosted/redirect variant) with a unique `merchantTransactionId` and the card / instrument. On success the response carries a `transactionToken` (prefixed `ix::`).
2. **Charge** — call `processDebit` supplying that `transactionToken` (plus a new unique `merchantTransactionId`, `amount`, `currency`). No raw card data is needed.
3. **Repeat** — reuse the same `transactionToken` for later card-on-file debits.
4. **Remove** — call `processDeregister` to delete the stored token when the customer no longer consents.

## Rules
- Each charge needs its own unique `merchantTransactionId` (duplicate = `errorCode 3004`).
- Waiting on `REDIRECT`/`PENDING`? The definitive result arrives at your `callbackUrl` — trust the callback.
- The PCI-scoped variant of these operations lives on the Direct API (`openapi/till-payments-direct-pci.yml`, host `secure.tillpayments.com`) for merchants transmitting raw card data.

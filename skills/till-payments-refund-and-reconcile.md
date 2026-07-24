---
name: Refund a transaction and reconcile status
description: Refund a settled Till Payments transaction and confirm the outcome via status lookup and the asynchronous callback.
api: openapi/till-payments-gateway.yml
operations: [processRefund, transactionStatusByUuid, transactionStatusByMerchantTransactionId]
---

# Refund a transaction and reconcile (Till Payments Gateway V3)

## Auth
HTTP Basic over TLS 1.2+; `apiKey` in path. Optional HMAC-SHA512 signing.

## Steps
1. **Refund** — call `processRefund` with a new unique `merchantTransactionId` and a `referenceUuid` pointing at the original transaction's `uuid`. Supply the `amount` to refund (full or partial).
2. **Interpret** — `FINISHED` = refunded; `PENDING` = a callback will confirm the final state at your `callbackUrl`; `ERROR` = inspect `errors[].errorCode`.
3. **Reconcile** — call `transactionStatusByUuid` (or `transactionStatusByMerchantTransactionId`) to confirm the definitive final state before marking the order refunded in your system.

## Rules
- Trust the asynchronous callback / status lookup, not a synchronous optimistic result.
- Numeric `errorCode` drives logic (1002 validation, 1003 adapter/transaction error, 3004 duplicate id, 1004 bad signature). See `errors/till-payments-problem-types.yml`.

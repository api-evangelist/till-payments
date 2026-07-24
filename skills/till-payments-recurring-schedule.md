---
name: Run a recurring payment schedule
description: Create and manage a recurring transaction schedule (start, pause, continue, cancel) on the Till Payments Gateway V3 API.
api: openapi/till-payments-gateway.yml
operations: [startSchedule, getSchedule, pauseSchedule, continueSchedule, cancelSchedule, updateSchedule]
---

# Run a recurring payment schedule (Till Payments Gateway V3)

## Auth
HTTP Basic over TLS 1.2+; `apiKey` in path. Optional HMAC-SHA512 signing.

## Prerequisite
A stored `transactionToken` (see the tokenize-and-charge skill) to bill against.

## Steps
1. **Start** — call `startSchedule` with the `transactionToken`, amount/currency, and the recurrence definition. Returns a `scheduleId`.
2. **Inspect** — call `getSchedule` with the `scheduleId` to read current state.
3. **Amend** — call `updateSchedule` to change amount or timing.
4. **Pause / resume** — call `pauseSchedule` then `continueSchedule` on the `scheduleId`.
5. **Cancel** — call `cancelSchedule` to stop the schedule permanently.

## Rules
- Each generated charge follows the same async model — final results land on your `callbackUrl`.
- Keep `merchantTransactionId`s unique across manual and scheduled charges.
- See `conventions/till-payments-conventions.yml`.

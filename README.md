# Webhook contract change checklist

A short, practical resource for API integration teams reviewing a webhook payload change before it reaches a downstream consumer.

## A change that looks harmless

```json
// known-good
{"event":{"id":1,"total":10}}

// current
{"event":{"id":"1"}}
```

A field can still be present while changing type, nesting, or nullability. That is enough to break a consumer that was written against the earlier contract.

## Preflight

1. Compare the known-good and current payloads.
2. Identify removed fields and type changes.
3. Share an exception record with the consuming team before release.

## Free browser-local check

Run the free [Webhook Contract Checker](https://webhook-contract-checker.optomatic.app/?src=github-webhook-contract-checker). It compares pasted JSON in your browser; Optomatic does not receive or retain the payload.

## Optional paid record — €9 once

If you need a timestamped downloadable contract-change record for the exact comparison, the product offers it after a one-time Stripe Checkout payment. No subscription and no account.

This is a narrow engineering review aid, not a compatibility guarantee or professional advice.

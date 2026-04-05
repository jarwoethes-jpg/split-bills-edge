---
name: split-bills
description: Split a bill equally among people with tax and tip.
---

# Split Bills

To use this skill, call `run_js` with `scripts/index.html` and the following data schema:

```json
{
  "amount": number,
  "people": number,
  "taxPercent": number (optional),
  "taxAmount": number (optional),
  "tipPercent": number (optional),
  "tipAmount": number (optional),
  "tipBase": "subtotal" | "total" (optional, default subtotal),
  "currency": string (optional, default "$")
}
```

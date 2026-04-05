---
name: split-bills
description: Calculate equal bill splits with optional tax, tip, and per-person rounding helpers. Use when someone wants a clean subtotal/tax/tip/total breakdown and an equal split across a group.
---

# Split Bills

## Overview

Calculate an equal bill split with the same validation and rounding semantics as the Python reference implementation.

## Workflow

1. Collect the required inputs:
   - `amount`
   - `people`
2. Collect optional inputs when provided:
   - `taxPercent`
   - `taxAmount`
   - `tipPercent`
   - `tipAmount`
   - `tipBase`
   - `roundMode`
   - `currency`
3. If a required input is missing, ask only for the missing value.
4. For deterministic calculation, call `run_js` with `scripts/index.html`.
5. Pass the input as JSON using this exact schema:

```json
{
  "amount": "number|string",
  "people": "integer",
  "taxPercent": "number|string (optional)",
  "taxAmount": "number|string (optional)",
  "tipPercent": "number|string (optional)",
  "tipAmount": "number|string (optional)",
  "tipBase": "subtotal|total (optional, default: subtotal)",
  "roundMode": "none|nearest-cent|up-cent|down-cent|up-dollar (optional, default: none)",
  "currency": "string (optional)"
}
```

6. Read the returned JSON string from `window.ai_edge_gallery_get_result(data)`.
7. On success, use the `result` string directly or lightly adapt it for the user.
8. On failure, surface the `error` message clearly.

## Defaults

- `tipBase` defaults to `subtotal`.
- `roundMode` defaults to `none`.
- Tax and tip default to zero when omitted.
- Do not invent a currency symbol when none is given.

## Output Pattern

Prefer this structure:

- `Subtotal: ...`
- `Tax: ...`
- `Tip: ...`
- `Total: ...`
- `Split N ways: ... each`

If rounding is requested, also include:

- `Rounded (mode): ... each`
- `Rounding difference vs total: ...`

## Guardrails

- Reject negative amounts.
- Reject `people <= 0`.
- Reject both percent and fixed amount for tax at the same time.
- Reject both percent and fixed amount for tip at the same time.
- Reject negative tax/tip values.
- Reject unsupported `tipBase` or `roundMode` values.
- This skill supports equal splits only.

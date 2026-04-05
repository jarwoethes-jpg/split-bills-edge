# split-bills-edge

A standalone Google AI Edge Gallery skill for splitting a bill equally with optional tax, tip, subtotal-vs-total tip basis, and rounded payment suggestions.

## Files

```text
split-bills/
├── SKILL.md
└── scripts/
    └── index.html
```

## Import into Google AI Edge Gallery

1. Open **Agent Skills** in the AI Edge Gallery app.
2. Choose **Add from URL**.
3. Paste the raw `SKILL.md` URL from this repo:
   - `https://raw.githubusercontent.com/jarwoethes-jpg/split-bills-edge/main/split-bills/SKILL.md`
4. Import the skill.

The skill will automatically use `split-bills/scripts/index.html` when the model calls `run_js`.

## Supported input JSON

```json
{
  "amount": 120,
  "people": 4,
  "taxPercent": 10,
  "tipPercent": 12,
  "tipBase": "subtotal",
  "roundMode": "up-cent",
  "currency": "$"
}
```

Use either `taxPercent` or `taxAmount`, and either `tipPercent` or `tipAmount`.

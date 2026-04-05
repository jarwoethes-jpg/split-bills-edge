---
name: split-bills
description: Calculate equal bill splits with optional tax and tip.
metadata:
  homepage: https://github.com/jarwoethes-jpg/split-bills-edge
---

# Split Bills

Calculate an equal bill split.

## Instructions

Call the `run_js` tool with `index.html` and a JSON string with these fields:
- amount: (number) total bill
- people: (number) count
- taxPercent: (number, optional)
- taxAmount: (number, optional)
- tipPercent: (number, optional)
- tipAmount: (number, optional)
- currency: (string, optional)

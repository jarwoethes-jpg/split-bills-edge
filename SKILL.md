---
name: split-bills
description: Calculate equal bill splits.
---

# Split Bills

This skill calculates an equal bill split.

## Examples

* "Split a bill of $100 among 4 people."

## Instructions

Call the `run_js` tool with the following parameters:

- script name: `index.html`
- data: A JSON string with the following fields
  - amount: the total amount
  - people: number of people

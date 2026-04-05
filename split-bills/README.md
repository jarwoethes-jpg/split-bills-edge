# split-bills

AI Edge Gallery skill for equal bill splitting with optional tax, tip, and per-person rounding helpers.

## Import

Use the raw `SKILL.md` URL in AI Edge Gallery:

```text
https://raw.githubusercontent.com/<owner>/<repo>/<branch>/split-bills/SKILL.md
```

If your repository is private or on a non-default branch, use the matching raw URL for that branch.

## Files

- `SKILL.md`
- `scripts/index.html`

`scripts/index.html` exposes `window.ai_edge_gallery_get_result(data)` and returns a JSON string with either `{"result":"..."}` or `{"error":"..."}`.

# OpenClaw PR #195087 — usage query IME Enter, real UI evidence

Screenshots captured from the Control UI built out of `ui/` with Playwright Chromium, a mocked
Gateway and trusted CDP key events: the candidate `とうきょう` is composed with
`Input.imeSetComposition`, then Enter is dispatched as a real key event.

- `proof-usage-query-ime-enter.png` — annotated sheet: `view-controls.tsx` from `main` (left) versus
  this PR (right), both after the composed Enter, plus the recorded keydowns and `sessions.usage`
  request counts.
- `panel-base.png` / `panel-head.png` — the unedited frames used in the sheet.
- `report-base.json` / `report-head.json` — the harness output behind the captions: every keydown
  with `isComposing`/`defaultPrevented`, the composition events, request counts, status-line text
  and summary-strip text at each step.
- `proof.html` — the sheet layout.

The harness that produced these files is a throwaway local e2e spec; it is not part of the PR.

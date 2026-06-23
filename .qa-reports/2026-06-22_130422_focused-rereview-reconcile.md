# ESSM Focused Re-Review Reconciliation

Reviewer: essm-qa-reviewer (codex/astartes)
Agent: ag-3db43216933a1c6a
Repo: /home/tanwa/psu-workflow
HEAD reviewed: 6ab64bd (`Final QA consolidation: About NGO claim, Contact nav, a11y, robust 360px`)
Timestamp: 2026-06-22_130422 Asia/Bangkok

## Scope

This note reconciles the prior focused 360px FAIL after essm-web-lead independently reported a clean render. I re-ran the Home responsive check from a fresh server and waited for web fonts before measuring and capturing.

## Method

- Confirmed HEAD: `6ab64bd`.
- Started a fresh server from `/home/tanwa/psu-workflow/site` with `uv run python -m http.server 8126`.
- Used a fresh `agent-browser` session named `essm-qa-fresh`.
- Set viewport to 360x800, opened `http://127.0.0.1:8126/`.
- Waited for `document.fonts.ready` and an additional 500ms before measuring.
- Repeated font-ready overflow checks at 768x1000 and 1280x900.

## Result

Focused reconciliation result: **PASS**.

The prior 360px FAIL was not reproducible after a fresh server/browser run with fonts loaded. This supports essm-web-lead's stale/pre-font-load capture hypothesis.

## Evidence

360px font-ready metrics:

- `document.fonts.status`: `loaded`
- `document.fonts.check('700 40px Kanit')`: `true`
- `document.fonts.check('300 40px Kanit')`: `true`
- `document.documentElement.scrollWidth`: `360`
- `document.body.scrollWidth`: `360`
- H1 box: left `20`, right `340`, width `320`, `scrollWidth == clientWidth == 320`
- CTA boxes: left `20`, right `340`
- Bottom bar: left `0`, right `360`, `scrollWidth == clientWidth == 360`
- Right-edge offenders (`right > viewport + 1`) count: `0`

Screenshots:

- 360px: `/tmp/essm-qa/home-360-final-fontready-6ab64bd.png`
- 768px: `/tmp/essm-qa/home-768-final-fontready-6ab64bd.png`
- 1280px: `/tmp/essm-qa/home-1280-final-fontready-6ab64bd.png`

Regression checks:

- 768px: `documentElement.scrollWidth == 768`, `body.scrollWidth == 768`, offender count `0`.
- 1280px: `documentElement.scrollWidth == 1280`, `body.scrollWidth == 1280`, offender count `0`.

## Conclusion

The remaining Home 360px clipping blocker is cleared under a fresh, font-ready browser check. The focused items are now PASS:

- Home 360px responsive: PASS
- Home 768px/1280px regression: PASS
- About NGO claim removed: PASS
- Footer Contact present on scoped pages: PASS
- `/people/` unlinked from scoped pages: PASS

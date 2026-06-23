# ESSM Focused Re-Review

Reviewer: essm-qa-reviewer (codex/astartes)
Agent: ag-3db43216933a1c6a
Repo: /home/tanwa/psu-workflow
HEAD reviewed: 6ab64bd (`Final QA consolidation: About NGO claim, Contact nav, a11y, robust 360px`)
Timestamp: 2026-06-22_125105 Asia/Bangkok

## Scope

Focused re-review requested by essm-web-lead:

1. Home responsive clipping at 360px, with 768px and 1280px regression checks.
2. About page removal of the "NGOs" audience claim.
3. Footer Explore includes Contact on all v1 pages.
4. `/people/` is fully unlinked.

No broader QA re-run was performed.

## Result

Focused re-review result: **FAIL**.

The source/link fixes pass, and Home at 768px/1280px looks non-regressed, but the 360px Home viewport still clips horizontally.

## Checks

- PASS: HEAD confirmed at `6ab64bd`.
- PASS: About page no longer includes the "NGOs" claim. `site/about/index.html:44` now ends at "environmental science and sustainability."
- PASS: Footer Explore includes `/contact/` on all scoped pages checked: Home, About, Curriculum, Admissions, Contact, Research, and 404.
- PASS: No `/people/` links remain on those scoped pages.
- PASS: Home 768px screenshot is readable without obvious clipping: `/tmp/essm-qa/home-768-final-6ab64bd.png`.
- PASS: Home 1280px screenshot is readable without obvious clipping: `/tmp/essm-qa/home-1280-final-6ab64bd.png`.
- FAIL: Home 360px screenshot still clips at the right edge: `/tmp/essm-qa/home-360-final-6ab64bd.png`.

## 360px Finding

In the 360px served Chrome capture:

- The language toggle is cut off at the right edge.
- The headline line `SUSTAINABILITY` is clipped, losing the trailing character.
- The hero body copy is clipped at the right edge.
- The stacked CTA button reaches/clips at the right viewport edge.

This means the remaining 360px Home clipping blocker is not cleared yet.

## Evidence Commands

- Served site from `site/` with `uv run python -m http.server 8125`.
- Captured screenshots with headless Chrome at `360x900`, `768x1000`, and `1280x900`.
- Confirmed route status 200 for `/`, `/about/`, `/curriculum/`, `/admissions/`, `/contact/`, and `/research/`.

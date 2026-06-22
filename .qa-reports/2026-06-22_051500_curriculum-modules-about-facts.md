# QA Report — Curriculum module descriptions, plan durations, PLO check, About facts

**Date:** 2026-06-22 · **Author:** essm-content-author · **Branch:** content/curriculum-modules-durations
**Commits:** ff54963 (curriculum), b46eec3 (about)

## Scope (essm-web-lead task-brief, 4 items)

### 1. Module descriptions — DONE
Replaced the "Full module descriptions" from-source placeholder in `site/curriculum/index.html`
with cleaned-from-TQF2 content for 979-701/702/703 and thesis (979-801/802).
- Source: `/home/tanwa/academics/aunqa/program_spec/tqf2.md` Appendix ฉ (OBE course descriptions).
- Method: Option (a) — English text **as published in the TQF2**, de-hyphenated from table-conversion
  artifacts; wording preserved. **NOT** labelled "verbatim" per psu-advisory guidance.
- Each course: description + course-level learning outcomes. 701/702/703 marked Required, non-credit;
  thesis marked credited (48 Plan 1.1 / 72 Plan 1.2). 979-801/802 share description+ELOs (noted inline).
- Also fixed outdated `<meta description>` (generic "48-credit / three years" → two-plan framing) per
  CONTENT_SOURCE rule against generic duration.

### 2. Plan durations — DONE
Added to the two Plan cards: Plan 1.1 = **three-year** study plan; Plan 1.2 = **four-year** study plan.
Source: TQF2 study-plan section (psu-advisory-verified, per CONTENT_SOURCE §"Programme duration — RESOLVED").

### 3. PLO cross-check — DONE (no edit)
Verified the 5 published PLOs vs TQF2 ~lines 599–607. All five faithful in meaning:
- PLO4 renders จิตสาธารณะ ("public-mindedness") as "social responsibility" — acceptable, meaning preserved.
- PLO2 "สิ่งแวดล้อมและการจัดการ" → "environmental management" — meaning preserved.
No wording is off enough to warrant a change; meaning unchanged. **No edit made.**

### 4. About facts — DONE (1 gated)
Cross-checked vs authoritative PSU/FTE web sources (direct fetch 403/404; confirmed via web search of
psu.ac.th / en.psu.ac.th / Wikipedia):
- **FTE established 2005** — VERIFIED (Apr 19 2005, ex-Phuket Community College). Kept.
- **PSU founded 1967** — VERIFIED (first university in southern Thailand). Kept.
- **Phuket full campus since 1993** — VERIFIED (1977 origin → full satellite campus 1993 from Phuket
  Community College). Reworded to reflect lineage.
- **Campus vision quote** "An International Education Center with Global Sustainable Development" —
  COULD NOT confirm verbatim; current public vision differs ("Green, International and Smart" / international
  education hub for sustainable development). **GATED** as `.todo-fact` pending authoritative confirmation.

## QA checks
- HTML tag balance (curriculum): section 7/7, div 65/65, ol 4/4 — OK.
- No residual "verbatim" label — OK.
- All 5 course codes present (979-701/702/703/801/802) — OK.
- About todo-facts: 2 (target-applicant profile [pre-existing] + newly-gated vision) — OK.
- People page untouched (GATED for v1) — confirmed.

## Result: PASS. Zero invented facts. Vision quote gated pending source.

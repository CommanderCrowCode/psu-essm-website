# QA Review Brief — ESSM Website v1 (pre-deploy)

For the **step-5 QA committee**, run before the Tailscale operator-preview deploy.

## D-19 reviewer-harness-diff (mandatory)

Content was authored by **claude-code** (essm-content-author/monet — curriculum, about) and
**kimi-cli** (essm-content-pop-1/2/yutu — research, contact, home, a11y, SEO). Per case-law
**D-19**, the QA reviewer MUST use a **different harness than the author** — so the formal
reviewer is **codex or kimi-cli** (NOT claude-code, and not the same yutu that authored).
essm-web-lead (claude-code) does integration/coordination checks only, not the binding review.
Request the reviewer from praetor-agent-ops when population is done.

## Scope

v1 launch set (per praetor): **Home, About, Curriculum, Admissions, Contact** (+ 404).
**/people/ is GATED** — excluded from v1 (see nav note below). /research/ is v1-optional;
review it too.

Repo: `/home/tanwa/psu-workflow`, branch `main`. Serve: `cd site && python3 -m http.server`.

## Review dimensions + checklist

### 1. Truthfulness (highest priority — this is an AUN-QA-evidence site)
- [ ] Every factual claim traces to `docs/CONTENT_SOURCE.md` (TQF2-canonical). Flag ANY claim
      that doesn't.
- [ ] No invented facts; every unknown is a visible `.todo-fact` source-gated placeholder.
- [ ] Curriculum module descriptions are NOT labeled "verbatim" (they are "as-published
      cleaned"); 979-701/702/703 = non-credit; 979-801=48cr/1.1, 979-802=72cr/1.2.
- [ ] No generic "3 years" for the whole programme; plan-specific (1.1=3yr / 1.2=4yr) only.
- [ ] No published GPA figure (TQF2 states none).
- [ ] Graduation: qualifying exam, public defense, ≥2 intl articles (or 1+innovation/patent),
      language req — matches TQF2.
- [ ] Admissions English thresholds match the 24 Aug 2022 table exactly.
- [ ] Campus-vision quote remains GATED (not asserted).

### 2. AUN-QA completeness — run `docs/AUNQA_CHECKLIST.md`
- [ ] Programme-level ELOs visible (C1); programme-spec fields present (C2); assessment +
      published-criteria framing (C4); QA/accreditation statement (C8); etc.

### 3. Design fidelity (vs the ingested design system)
- [ ] Colors/sizes only from `site.css` tokens; PSU purple primary + blue accent; no
      lime/chartreuse; no emoji; journey-route motif used sparingly.
- [ ] Type = Kanit (display) + Sarabun (body); Thai-ready.

### 4. Accessibility / integrity
- [ ] One `<h1>`/page; all `<img>` have meaningful alt; AA contrast; keyboard focus visible.
- [ ] All internal links absolute + resolve (no 404s); nav + footer consistent across pages.
- [ ] Responsive at 360 / 768 / 1280px.

## Known v1-consolidation items (lead to resolve before deploy)
- [ ] **/people/ in nav + footer** — People is gated out of v1; decide remove-from-nav vs
      keep-as-"coming-soon". Lead will make this single cross-cutting edit once, post-population.
- [ ] `noindex` for the Tailscale preview leg (per dominion-lead); remove before public Render.
- [ ] Footer address ("Kathu, Phuket 83120") — verify or soften to the verified location only.

## Deliverable
Per-dimension PASS/FAIL with specific file:line findings + severity. Truthfulness FAILs are
blocking. Save to `.qa-reports/YYYY-MM-DD_HHMMSS_qa-review.md`.

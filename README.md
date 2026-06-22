# PSU ESSM Curriculum Website

Public website for the **PhD in Environmental Science and Sustainability Management** (ESSM),
Faculty of Technology and Environment (FTE), Prince of Songkla University — Phuket Campus.

Project: `psu-workflow` · Lead: `essm-web-lead` (relay-mesh).

## What this is

A **pure static site** (hand-authored HTML/CSS, no build step) that faithfully adopts the
ESSM design system. Target deployment: **Render static blueprint** (`render.yaml`), with a
**Tailscale-accessible preview first** for operator review before public launch.

## Design system

The visual language (colors, type, spacing, the journey-route motif, hero/photo-well
treatment) is ported verbatim from the supplied **University design system** into
`site/assets/css/site.css`. The canonical tokens live at the top of that file. **Do not
invent colors or sizes — pull from the `:root` tokens.** Fonts: Kanit (display) + Sarabun
(body), both Thai-glyph-complete for the EN→TH bilingual rollout, plus Noto Sans Thai fallback.

Source design files were ingested from `University design system.zip` (tokens.css,
brand-guide.md, and `.dc.html` reference mocks). The mocks are a *visual* reference; this
site reproduces their design in plain static HTML for SEO / no-JS resilience / accessibility /
fast load / easy editing.

## Content & truthfulness rules

- **Every claim must be verifiable. No invented data, no fake faculty, no guessed figures.**
- Facts not yet confirmed are marked inline with the `.todo-fact` class (dashed underline)
  and a clear "to confirm / from the program office / from TQF2" note — never published as
  fact.
- Source of truth for curriculum / outcomes / admissions / faculty = **TQF2** + the SAR.
- Verified content (program overview, faculty/campus history, PLOs, 3-year structure,
  graduation requirements) comes from aunqa-lead's AUN-QA starter content.

## Structure

```
site/
  index.html            Home
  about/index.html      About the Program
  curriculum/index.html Curriculum (3-year journey, PLOs, graduation reqs)
  admissions/index.html Admissions
  people/index.html     People (faculty / supervisors — content-gated)
  research/index.html   Research
  contact/index.html    Contact
  404.html
  assets/css/site.css   Design-system stylesheet (token source of truth)
  assets/img/           Images (logos, photos — to be added)
render.yaml             Render static blueprint
```

## Local preview

```bash
cd site && python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Tailscale-accessible preview for operator feedback first; promote to Render
(`render.yaml`) for the durable public deploy once content is operator- and
AUN-QA-approved. Add `noindex` until the public launch is signed off.

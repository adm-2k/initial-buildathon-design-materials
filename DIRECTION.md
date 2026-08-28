# Design Direction — Initial Understanding

**Project:** DevFestDC 2026 Build-a-thon — unified visual system for a hub + five small
digital-humanities tools (ontology builders, XML tools, and adjacent instruments) on a
single deployment.

**Status:** PROPOSAL — for review and confirmation before the full specification
(`DESIGN-SPEC.md`, tokens, brand book, per-app guides) is written.

---

## 1. Reading the references

### Ref A — Investor pitch deck (Dribbble 27118341)
International Typographic Style played straight. What we take:

- **One signal color.** Warm off-white ground, near-black ink, a single vermilion.
  Color is never decoration; it is an instruction.
- **Visible structure.** Hairline rules divide the page into functional compartments.
  The grid isn't implied — it's drawn.
- **Metadata as ornament.** Tiny uppercase labels anchor every region:
  `SERIES A PITCH`, `PAGE (N°001)`, `©2026`. The page knows what it is and says so.
- **Data as the hero image.** Giant machined numerals carry the composition; the
  supporting prose is set small, like footnotes.
- **Hierarchy by size and tone,** not by weight variety. Black → warm gray → accent.
- **Miniature wayfinding systems:** index dots (●○), arrows in circles, page counters.

### Ref B — SIDE NOTE editorial platform (Dribbble 27594533)
Editorial warmth inside a cellular structure. What we take:

- **The compartment header.** Navigation as a strip of bordered cells, each one an
  inventory entry: icon + label + live count — `DESIGN (24 Stories)`. The interface
  admits what it contains.
- **Print ephemera as licensed moments.** Stamps, a ticker/marquee strip, an engraved
  illustration, a pointing hand — human warmth that never breaks the grid.
- **Voice as a design element.** `MADE FOR CURIOUS MINDS`, `SURPRISE ME` — microcopy
  with a personality, set in the system's own type.
- **Paper, not pixels.** Cream ground, flat surfaces, borders instead of shadows.

### Synthesis — *Swiss chassis, editorial soul*
For digital-humanities tooling this pairing is almost pre-destined. The entire
discipline is the act of laying rigorous structure (markup, ontologies, schemas) over
humanistic material (texts, archives, artifacts). The design system should perform the
same act visually: a strict grid and metadata apparatus — the markup — wrapped around
warm paper and generous reading typography — the manuscript. Minimalism here is not
emptiness; it is the scholarly discipline of keeping the apparatus out of the text's
way. **The content of observation takes the fore; the chrome behaves like a critical
edition's margin.**

---

## 2. The concept: *The Critical Edition*

Every screen in the suite is laid out like a page from a scholarly edition:

- **Text block** — the user's material (the ontology, the XML document, the corpus)
  sits center, set for reading, given the most generous space and the quietest frame.
- **Apparatus margin** — tool controls, annotations, validation states live in a
  marginal column, set in the mono "cataloguer" voice, small and dense.
- **Folio furniture** — every view carries a running header (tool name, `TOOL (N°03)`,
  date/state) and a footer **colophon** ("Set in X and Y. Built at DevFestDC 2026,
  Washington, D.C.").

Five apps built by different hands stay one brand because the *page architecture* is
shared, not just the palette.

---

## 3. Naming candidates

| Candidate | Source | Why it works |
|---|---|---|
| **APPARATUS** ← recommended | *apparatus criticus*, the margin machinery of a critical edition | Reads as both scholarly reference and Swiss machine-aesthetic word. The hub is the apparatus; the five tools are its **Instruments**, numbered `INSTRUMENT (N°01)`–`(N°05)`. Wordmark can be set as a self-closing XML element: `<apparatus/>`. |
| **STEMMA** | Stemmatics — the tree diagram of manuscript descent | Perfect for ontology work: the logo *is* a node-and-edge diagram. Hub = root node, apps = witnesses. Slightly narrower conceptually (tree-shaped). |
| **INCUNABULA** | "Works from the cradle" — the first printed books | Charming for a build-a-thon (everyone's first builds), apps catalogued like ISTC entries. Long word; weaker as a UI-scale mark. |

Bench: *Marginalia*, *Colophon*, *Gloss/Glossary*, *Recto/Verso*.

Suggested tagline for the recommended direction: **"Instruments for reading closely."**

---

## 4. Brand behaviors (the clever bits — to confirm)

1. **Rubrication, not "brand color."** In manuscript tradition, the *rubric* is the red
   ink reserved for headings, initials, and instructions. Our single vermilion accent
   is literally named `--rubric` and is used exactly as rubricators used it: headings'
   key words, live/active states, instructions, the current position in an index —
   never decoration. This fuses the Swiss red of Ref A with manuscript history in one
   move, and it gives builders a *rule* instead of a taste judgment.
2. **XML as identity.** The wordmark is a self-closing tag. Breadcrumbs render as an
   element path (`apparatus / ontology / class`). The favicon is the closing slash.
   Section metadata can be set like attributes: `status="draft" lang="en"`.
3. **A scholarly microcopy lexicon.** Loading: `COLLATING…` · Empty state:
   `LACUNA — nothing recorded here yet.` · 404: `FOLIO MISSING` · Saved:
   `Fixed in the record` · Search: `CONCORDANCE`. Small, cheap to implement, and it
   makes five separate apps *sound* like one author.
4. **The hub is a catalogue.** The landing page is a table of contents in compartment
   cells (Ref B's header, promoted to the whole page): each tool is an entry with its
   N°, name, one-line function, and a live count — `ONTOLOGY BUILDER (N°02) — 14
   classes defined`.
5. **The event stamp.** One circular roundel — `DEVFESTDC 2026 · WASHINGTON, D.C. ·
   BUILD-A-THON` — used sparingly (colophon, splash). The one piece of print ephemera
   we borrow from Ref B.
6. **The ticker.** A single marquee strip on the hub for build-a-thon announcements
   and latest activity across the five tools. Live, playful, cheap to build.
7. **Pigment palette for data.** UI stays paper/ink/rubric only. Where charts or graph
   visualizations need categorical color (ontology graphs will), they draw from a
   reserved set named for illuminators' pigments: *lapis*, *verdigris*, *ochre*,
   *sepia*. Data gets color; chrome never does.

---

## 5. Proposed foundations (indicative — final values in the spec)

### Color

| Token | Value | Role |
|---|---|---|
| `--paper` | `#F4F1EA` | Ground — warm off-white |
| `--paper-raised` | `#FCFBF7` | Cells, panels |
| `--ink` | `#1C1A17` | Primary text |
| `--ink-2` | `#6E685E` | Secondary text (warm gray) |
| `--hairline` | `#D8D3C8` | All rules and borders, 1px |
| `--rubric` | `#E8481C` | The one accent — see behavior 1 |
| `--lapis / --verdigris / --ochre / --sepia` | `#2B4C9B / #3E7C6B / #C99A2C / #7A4A38` | Dataviz only |

Light-first. An optional inverted "**Nocturne**" reading mode (`#141310` ground, bone
text, rubric unchanged) is proposed as a stretch goal, not a requirement.

### Type — three voices, three roles

| Voice | Face (free / Google Fonts) | Role |
|---|---|---|
| **The Architect** | Archivo (alt: Inter) | UI, headlines, structure |
| **The Cataloguer** | IBM Plex Mono | Micro-labels (uppercase, tracked), metadata, XML/code, and **display numerals at poster sizes** (tabular figures) |
| **The Manuscript** | STIX Two Text (alt: Source Serif 4) | Long-form reading, source texts — STIX gives us scholarly Unicode coverage (Greek, critical signs, diacritics) for free |

Scale principle from Ref A: **no middle sizes.** Either reading scale (12/14/16/18) or
poster scale (32/56/96/160). The awkward 24px middle ground is where Swiss pages go to
die.

### Surface & grid

- 12-column grid, 8pt spacing scale, max-width ~1440px.
- **Hairlines do the work**: 1px rules and compartments instead of cards and shadows.
  Corner radius 0 (2px max on inputs). Shadows banned except true overlays.
- Every view opens with the folio header; every page ends with the colophon.

### Motion

Mechanical and brief: 120–180ms ease-out, opacity + small translate. No springs, no
bounce. The ticker is the one continuous motion. *Motion behaves like a page turn, not
a rubber band.*

---

## 6. How five apps stay one brand

1. **Shared token package** — one `tokens.css` (and optional Tailwind preset) imported
   by every app in the monorepo; no app defines its own colors or type.
2. **Shared page architecture** — folio header, apparatus margin, colophon. Layout is
   the brand.
3. **Identity by number, not by color** — each tool gets a registry number and entry in
   the catalogue; differentiation via `N°` and function, keeping the single-rubric
   discipline. (Alternative: a muted per-app tint — see open question 2.)
4. **Shared lexicon** — the microcopy list ships in the spec as a copy-paste table.
5. **`CLAUDE.md` enforcement** — since apps will be built with Claude Code, the repo
   ships a `CLAUDE.md` that binds every session to the spec: which tokens exist, what
   is banned (shadows, radii, off-system colors), and the review checklist.

---

## 7. Planned final deliverables (after confirmation)

1. `DESIGN-SPEC.md` — master specification: philosophy, tokens, type scale, grid,
   component inventory (compartment cell, label chip, arrow-circle button, ticker,
   index dots, catalogue table, footnote bar, apparatus margin), motion, voice,
   do/don't pairs.
2. `tokens.css` + Tailwind preset — drop-in for Vercel/Next.js apps.
3. `BRAND.md` — name, story, wordmark construction, rubrication rules, the stamp,
   microcopy lexicon.
4. `CLAUDE.md` — build-time guardrails for Claude Code sessions.
5. Hub-page reference mockup (HTML) demonstrating the full system.
6. Per-app one-pagers — e.g., XML editor: tags rendered in Cataloguer mono with rubric
   for element names; Ontology builder: stemma-style graph using the pigment palette.

---

## 8. Open questions

1. **Name** — Apparatus (recommended), Stemma, Incunabula, or another direction?
2. **Accent discipline** — single rubric everywhere (recommended) vs. a muted per-app
   tint for the five tools?
3. **Fonts** — free Google Fonts stack as proposed (recommended for a build-a-thon) or
   licensed faces (Neue Haas Grotesk, etc.)?
4. **Nocturne mode** — in scope or stretch goal?
5. **The five tools** — can you confirm the actual list of apps, so the per-app
   one-pagers are concrete rather than generic?
6. **DevFestDC co-branding** — are there GDG/DevFest brand requirements to honor, or
   is the event stamp sufficient?

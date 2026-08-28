# CLAUDE.md — build-session guardrails

This repository (and any monorepo these files are copied into) is governed by a
single design system: **Apparatus**. Before writing or editing any UI code, read
`DESIGN-BRIEF.md` in full. It is the contract that makes five separately-built apps
read as one product.

## Hard rules (non-negotiable)

1. **Tokens only.** Import `tokens.css` first and take every color, font family,
   type size, radius, and duration from it. Never write a hex value, `rgb()`, font
   name, or radius directly in app styles. No black anywhere — the dark is
   `var(--ink)`.
2. **Both themes, three states.** Never restructure the theming blocks in
   `tokens.css`. Never define a color only inside a media or `[data-theme]` block.
   `body` always sets `background: var(--stock)`.
3. **Page anatomy.** Every view has a folio header and a colophon; tool views have an
   apparatus margin (DESIGN-BRIEF §5).
4. **Rubrication.** Red = instruction, emphasis, live state, or error — nothing else.
   One primary action per view. Blue = interactive only.
5. **Compartments, not cards.** 1px `var(--hairline)` rules; radius 0 (2px inputs);
   no box shadows, no gradients.
6. **Lexicon verbatim** (DESIGN-BRIEF §8): `COLLATING…`, `LACUNA`, `FOLIO MISSING`,
   `Fixed in the record`, `IN REGISTER` / `OFF REGISTER`.
7. **Charts** use `--chart-*` in fixed order, `--seq-*`, `--div-*` exactly as
   specified (DESIGN-BRIEF §9). No generated hues, no dual axes, no color-only status.
8. **Type**: Archivo / IBM Plex Mono / STIX Two Text via the Google Fonts link in
   DESIGN-BRIEF §4. No sizes between 19px and 32px.

## Before you finish any view

Run the ship checklist in DESIGN-BRIEF §12. Grep your styles for `#` — any hex
outside `tokens.css` is a defect. Verify legibility in system-light, system-dark,
forced-light, and forced-dark.

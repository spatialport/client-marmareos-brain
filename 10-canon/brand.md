---
id: marmareos-canon-brand
client_id: marmareos
record_type: knowledge
service_path: branding
status: proposed
owner: alex-bellesia
authority: alex-bellesia
ip_owner: client
access_scope: internal
sensitivity: confidential
source_ref: nxto://projects/marmareos
schema_version: 1.1.0
created_at: 2026-08-11
updated_at: 2026-08-19
---
# Brand Book

Purpose: The accepted brand truth used to brief any human or AI producing work.

## Brand truth (proposed)

- Brand essence: **"la boutique italiana delle pietre naturali"** — Marmareos, from Greek μαρμάρεος ("of marble"), Arco (TN), since 1972. Boutique curation + measurable quality, not mass distribution (BRAND-BOOK.md).
- Source of truth for style: **the live site marblesmarmareos.it** — "iper-minimalista, luminosa, colori prevalentemente chiari"; lots of whitespace, hairlines, small marks; **no gold, no dark backgrounds by default, no serif** (BRAND-GUIDE.md, dated 08/07/2026).
- History with Spatial Port: brand identity + website delivered; Monte-Carlo brand film produced (STORYBOARD-MONTECARLO.md); interactive brandbook + full growth package on the client portal.

## Naming and logo (proposed)

- Public name **Marmareos**; "Marbles Marmareos S.r.l." only legal/invoicing (BRAND-GUIDE.md).
- Two official assets: **MM monogram** (`MM.svg`, primary mark for social/avatars) and **MARMAREOS wordmark** set in the **VIOLA font with 45% letter-spacing** — always use the logo files, never retype the name; graphite `#151918` on light, ivory `#FAF6F5` on dark photos; never gold or recolored (BRAND-GUIDE.md).

## Visual tokens (proposed)

- Palette (site tokens): **Pietra Avorio `#FAF6F5`** (primary background) · **Sabbia Calda `#DDD5CA`** (secondary, hairlines) · **Grigio Venato `#929490`** (muted text) · **Grafite Scura `#151918`** (text/primary) · **Deep Graphite `#3B3B3B`** (secondary dark text) (BRAND-GUIDE.md; HSL variables in BRAND-BOOK.md §13 — minor hex variants `#FAF6F4`/`#D6CEBC`/`#101715` appear there).
- Typography: **Montserrat only** (100 Thin / 300 Light / 400 Regular; Google Fonts); titles uppercase, light weights, wide tracking 0.1–0.25em; VIOLA exclusively for the wordmark; print fallback Futura/Gill Sans (BRAND-GUIDE.md, BRAND-BOOK.md).
- Color principle: **light-first** — dark backgrounds only when the material itself is dark (Portoro, Nero Marquina, dark onyx): "è la pietra a portare il buio, non il layout" (BRAND-GUIDE.md).
- Photography: natural light, veining/texture close-ups, real-life contexts; avoid cold 3D renders as primary imagery, generic stock, heavy filters (BRAND-BOOK.md).
- Asset library in brand-assets/: site CSS, logos SVG, favicons, OG image, 5 hero webp, 52 material slab JPGs, project photos (hermitage, mareterra, montecarlo-bay, private-offices…), machinery photos (BRAND-BOOK.md §13).
- **Creative-direction conflict to resolve:** the earlier draft framed the brand as "cinematic, film-first" (Monte-Carlo film); the operative BRAND-GUIDE (site-derived, later) prescribes hyper-minimalist, bright, light-first. Treat BRAND-GUIDE.md as the operating truth for social/web; the film remains a hero asset.

## Voice (proposed)

- 4 dimensions: **Esperto & Competente · Caldo & Relazionale · Raffinato & Essenziale · Autentico & Diretto** — "l'eleganza italiana non urla, suggerisce" (BRAND-BOOK.md).
- Register: premium-sober, evidence-based, consultative; approved lexicon: materia, precisione, progetto, controllo, luce, forma, dettaglio, armonia, misura, valore, equilibrio (MASTER_PROMPT_MARMAREOS.md, STYLE-COPY-GUIDE.md).
- Hard "no"s: superlatives without proof ("leader del settore"), promo shouting, multiple emoji/exclamation marks, "Non perda l'occasione!", scarcity rhetoric, AI-sounding constructions (BRAND-BOOK.md Da dire/Da non dire, STYLE-COPY-GUIDE.md).
- Languages: EN primary on social per BRAND-GUIDE; FR on Monaco/Côte d'Azur content; strategy docs internal IT; market copy IT/EN/FR with native quality, FR priority (BRAND-GUIDE.md, MASTER_PROMPT_MARMAREOS.md).
- Never promise installation ("Marmareos non cura la posa") (BRAND-GUIDE.md).
- Tone per context table (site institutional-warm, email personal, quotes "proposta non pressione", IG evocative-visual, LinkedIn authoritative, tech sheets neutral) (BRAND-BOOK.md §06).

## Messages (proposed)

- Brand statements IT/EN/FR ("Dal 1972, selezioniamo, lavoriamo e consegniamo pietre naturali di alta gamma per progetti che non ammettono compromessi.") + 6 pillar messages M1 Heritage · M2 Materia Unica · M3 Progetto Completo · M4 Standard di Qualità ("Measurable quality standards, applied with artisan rigour") · M5 Dove la Pietra Diventa Architettura · M6 Partner Globale, each with mapped usage (BRAND-BOOK.md §07).
- Signature closing line for the SP package: *"La stessa precisione. Dalla pietra alla crescita."* (STYLE-COPY-GUIDE.md).

## Channel adaptation (proposed)

- IG feed grammar: image-led carousel covers per material category; slab-on-pedestal renders only as inner swipes; strong single posts (Monaco project editorials, macros) as visual anchors; 3-column rhythm, dark tiles as spaced punctuation (FEED-STRATEGY.md).
- Social marks: MM monogram small top mark; VIOLA wordmark as bottom signature on covers/CTAs (BRAND-GUIDE.md).
- Ads copy: ≤30-char titles, premium-sober, no urgency; e.g. FR RSA "Qualité mesurable, pas promise", "Du relevé laser à la livraison" (07b-campagna-search-fr-LIVE.md).

## Approval

Human taste remains a permanent gate for brand and design outputs (per approval register policy). Client-side approver: **Virginia Ottobre** (creative/positioning validation tasks assigned to her in TODO-VIRGINIA.md); operational asset handling by Bianca.

## Open questions

- Register the brand source files: official brandbook PDF `BRANDBOOK_MM_V3.pdf` (43 pp) lives in NXTO `projects/marmareos/_input/`; brand-assets/ folder in the workspace — add refs to `80-deliverables/deliverable-register.md`.
- Reconcile hex variants between BRAND-BOOK.md (§13 CSS) and BRAND-GUIDE.md (site tokens) — BRAND-GUIDE claims to be the source of truth; confirm.
- VIOLA font licensing for web use (flagged `[FONT — verificare licenza]` in MASTER_PROMPT_MARMAREOS.md).
- Pending visual assets: image-led covers for remaining material categories and 5 Higgsfield "material in context" interiors (blocked by Higgsfield 403 access/credits) (FEED-STRATEGY.md).

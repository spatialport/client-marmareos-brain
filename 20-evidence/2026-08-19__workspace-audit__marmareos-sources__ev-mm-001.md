---
id: ev-mm-001
client_id: marmareos
record_type: evidence
service_path: company
status: proposed
owner: alex-bellesia
authority: alex-bellesia
ip_owner: client
access_scope: internal
sensitivity: confidential
source_ref: file://Documents/Claude/Projects/MARMAREOS (1)/
schema_version: 1.1.0
created_at: 2026-08-19
updated_at: 2026-08-19
---
# Evidence — Workspace audit of Marmareos source folders (2026-08-19)

Purpose: record which local sources the 10-canon Marmareos knowledge was derived from, so every fact in the canon is traceable to a file.

## Root of the audited workspace

`/Users/alexbellesia/Documents/Claude/Projects/MARMAREOS (1)/`

## Folder map (with one-line descriptions)

| Folder / file | What it contains |
|---|---|
| `fase-2-growth-plan/` | The 12 growth work packages WP-00…WP-12 (strategy 12 months, positioning, lead gen, offer, fairs, funnel, ADV, social calendar, CRM/nurturing, PR, report templates, channel budget) + live execution docs: `07b-campagna-search-fr-LIVE.md`, `campagna-milano-search-spec.md`, `seo-audit-strategia-2026-08-15.md` |
| `fase-3-sito-tracking/` | LP-01 tracking (GTM/GA4/Consent Mode v2), LP-02 GDPR/privacy draft (+docx), LP-03 campaign landing spec |
| `tools-ai/` | `00-roadmap-strumenti-ai.md` — spec of the 3 AI sales tools (AI quoting, intelligent CRM, call transcription) |
| `brand-assets/` | `BRAND-GUIDE.md` (site-derived operating brand guide) + site CSS, logos (MM.svg, wordmark), VIOLA font, favicons, hero images, 52 material slab photos, project and machinery photos |
| `_research/` | `DOSSIER.md` (shared research source of truth: market, competitors, keywords, fairs, media, tool stack) + `competitor-carat-diffusion.md` |
| `_revisione/` | `STYLE-COPY-GUIDE.md` (binding copy/style directives approved by Alex 2026-06-10) + `REVIEW-LOG.md` (review-cycle status of all deliverables) |
| `social/` | `FEED-STRATEGY.md`, `MASTER-PROMPT-SOCIAL.md`, `PIANO-MULTIMEDIA-SETTIMANA-1.md`, cover-generation skill (`skills/marmareos-cover/`) |
| `deploy-aws/` | `DEPLOY-README.md` + gated `site/` bundle of the client portal (hub, brandbook, 14 decks, KPI dashboard, link-in-bio) deployed to marmareos.spatial-port.io |
| `guida-clienti/` | Client-facing portal guide and access-email draft (`mail-accesso-portale.md`) — portal credential referenced only as `password-manager://spatial-port/marmareos/portale-clienti` |
| `pm-todo/` | PM dashboards extracted from deliverables: `TODO-SPATIALPORT.md` (85), `TODO-VIRGINIA.md` (59), `TODO-BIANCA.md` (31) |
| Root files | `MASTER_PROMPT_MARMAREOS.md` (engagement brief: legal data, contract shape, rules), `BRAND-BOOK.md` (Brand Book & Company OS v1.0), `PROMPT-ORCHESTRATORE.md`, `PROMPT-REVISIONE-FABLE5.md`, `STORYBOARD-MONTECARLO.md` (brand film), `CHECKLIST-GO-LIVE.md`, `google-ads-mcp-setup.md` |

## Canonical-location notes

- **Canonical site repo mount:** `/Users/alexbellesia/Projects/MARMAREOS/SITO-MARMAREOS`. The nested `SITO-MARMAREOS` copy inside "MARMAREOS (1)" is a **duplicate to ignore**.
- **CAMION_MC/FOTO (~2,500 raw photos)** stays in Drive/local storage — **never committed to the repo**.
- `deploy-aws/DEPLOY-README.md` notes the original deploy script lives in NXTO (`Documents/Claude/Projects/NXTO/projects/marmareos/deploy-aws/`); the bundle in this workspace was built as a stand-in when NXTO was not mounted.
- Official brandbook PDF (`BRANDBOOK_MM_V3.pdf`, 43 pp) and the SP–Marmareos contract live in NXTO `projects/marmareos/_input/` — not in this workspace.

## Governance

- No secrets are recorded in this vault. Portal/gate credentials: `password-manager://spatial-port/marmareos/portale-clienti`.
- Facts extracted into: `10-canon/company.md`, `people.md`, `offer.md`, `icp.md`, `positioning.md`, `channels.md`, `operations.md`, `brand.md` (all `status: proposed`, awaiting Alex's review).

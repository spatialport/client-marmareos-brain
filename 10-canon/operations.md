---
id: marmareos-canon-operations
client_id: marmareos
record_type: knowledge
service_path: company
status: accepted
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
# Operations

Purpose: How the company operates day to day and how the engagement runs.

## Accepted knowledge

### The 12-month growth plan (Jul 2026 → Jun 2027)
Four phases anchored to real fair windows (00-OVERVIEW-GROWTH-PLAN.md):
1. **Fondamenta (Jul–Aug 2026)** — HubSpot live with form→CRM + lead-origin tracking; GTM/GA4/Consent Mode; sales assets; FR keyword cluster.
2. **Attivazione (Sep–Nov 2026)** — Google Search FR live within cap; first IG/LinkedIn content; targeted outreach; Marmomac + EquipHotel with tracked follow-up.
3. **Accelerazione (Dec 2026–Mar 2027)** — CRM nurturing on fair/Search leads; ADV scaling only on results; first authorized project-PR.
4. **Consolidamento (Apr–Jun 2027)** — IT/EN expansion, PR luxury, channel-mix review, year-2 plan on data.
North-star metric: **tracked contracts** (pipeline value/contract revenue), never vanity metrics (MASTER_PROMPT_MARMAREOS.md).

### Client budget envelope (client spend only — SP fees never in deliverables)
ADV ≤ €500/month hard cap (actual start: €300 FR + ~€200 Milano) · Claude AI subscription ~€200/month · Sales Navigator ~€80/month from M3 · content/misc ~€50/month · HubSpot Free/Starter at €0 to start · fairs `[su preventivo]` per event; total year plan ~€9,800 excl. events; monthly Budget/Actual/Variance XLSX review (12-budget-canali.md).

### CRM & sales process
- **HubSpot** (Free → Starter) as the commercial nervous system: 6-stage pipeline, mandatory origin field with controlled values + UTM, contact import with GDPR classification of legacy contacts, nurturing sequences on the long cycle (09-crm-nurturing-outreach.md refs, DOSSIER.md §6). Form→HubSpot flow already live and tested (`origine_lead = google_search`; two test contacts to delete listed in CHECKLIST-GO-LIVE.md).
- Client-side service SLAs baked into the process: first reply ≤4h, quote ≤48h, SQL→negotiation handoff owner to be defined (Virginia/Bianca decision) (BRAND-BOOK.md, TODO files).

### GDPR / compliance state (02-gdpr-privacy.md — draft, NOT legal advice)
- Marmareos S.r.l. = data controller; Italian/EU GDPR applies (plus D.Lgs. 196/2003 as amended); Swiss law does NOT apply; Garante is the authority. DPO likely not mandatory `[legal validation]`.
- Package drafted: privacy policy (/privacy, /confidentialite), cookie policy + consent-first banner IT/EN/FR with Consent Mode v2, processing register, DPA list (Google DPF+SCC, Meta, HubSpot, Anthropic for AI tools `[with legal reserve]`), retention proposals (24 months unconverted leads, 10 years contractual).
- **Open gaps:** full legal validation pending; privacy email/PEC/referent `[dato da cliente]`; DPAs to collect and archive; LIA for B2B outreach legitimate interest; call-recording consent for the transcription tool; possible DPIA for AI tools; internal data-subject-request procedure.

### Working method (agency side)
- Documents follow the Vitalis-derived framework: standard header, exec summary, "Prossimi passi + owner (Spatial Port / Cliente / Insieme)"; placeholders never invented (`[PLACEHOLDER]`, `[da cliente]`, `[target da validare]`) (MASTER_PROMPT_MARMAREOS.md).
- Quality-review loop with rubric and review log; all deliverables at "da-analizzare" as of the log snapshot; approved directives: single sober closing signature, no scarcity rhetoric, max 1 internal quote per deck (REVIEW-LOG.md, STYLE-COPY-GUIDE.md).
- Deliverables are shipped to the password-gated client portal **marmareos.spatial-port.io** (hub, brandbook, 14 decks, KPI dashboard, link-in-bio, pm-tasks.json); gate is client-side only — deterrent, not real security; credential at `password-manager://spatial-port/marmareos/portale-clienti` (DEPLOY-README.md).
- PM: three to-do dashboards extracted from the deliverables (Spatial Port 85 / Virginia 59 / Bianca 31 tasks, June 2026 snapshot) (pm-todo/*.md).
- AI tools engagement: spec only for now — build is a separate planned activity after client go/no-go (00-roadmap-strumenti-ai.md). Software IP: `spatial-port` per manifest (no exception signed).

## Open questions

- Client-side internal workflow for quotes today (email? spreadsheet? who receives them?) — needed for the AI quoting tool build.
- Status of the 10 immediate steps of the overview (kick-off session held? targets validated?) — the June 2026 snapshot predates the live campaigns.
- Which DPAs have actually been signed/archived by Aug 2026.
- Seasonality of quarry availability and production capacity constraints (affects lead SLAs and editorial planning).

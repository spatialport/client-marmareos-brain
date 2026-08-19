---
id: marmareos-canon-channels
client_id: marmareos
record_type: knowledge
service_path: company
status: proposed
owner: alex-bellesia
authority: alex-bellesia
ip_owner: client
access_scope: internal
sensitivity: confidential
source_ref: nxto://content/marmareos
schema_version: 1.1.0
created_at: 2026-08-11
updated_at: 2026-08-19
---
# Channels

Purpose: Where the company is present, what runs there, and what performance means per channel.

## Proposed knowledge (awaiting review by Alex)

### Paid search (the live engine)
- **Google Search FR — `MM-Search-FR-CdA-Intent`**: live plan from 30 June 2026, **€300/month cap (€9.80/day)**, Maximize Clicks with Max CPC €3.00 in ramp-up, geo Monaco + Alpes-Maritimes + Saint-Tropez ("presence" targeting), French only. 5 ad groups: AG1 marbrier-luxe, AG2 marbre-sur-mesure, AG3 fournisseur-rare, AG4 pierre-architecture, AG5 yacht (paused at start). Negative list from day 1 (pas cher, effet marbre, carrelage, emploi…). Conversion `Form contatto — Sito` (AW-18285077126) (07b-campagna-search-fr-LIVE.md).
- **Google Search IT Milano — `MM-Search-IT-Milano-Intent`**: 2nd campaign, **~€200/month (€6.50/day)**, Milan +25km, built as draft; publishing blocked on Google identity verification by Alex (campagna-milano-search-spec.md).
- **Landing pages (Lovable, live):** FR **/projet** (`marblesmarmareos.it/projet?lang=fr`, "Demande de projet" modal + catalogue download) and IT **/marmo-su-misura** (Milan). SEO audit recommends **noindex** on both (CHECKLIST-GO-LIVE.md, seo-audit-strategia-2026-08-15.md).
- **Meta (IG/FB) ads:** NOT live in launch phase — planned from ~M3 as small retargeting test (€50–120/month) that subtracts from the Search quota within the €500 cap (12-budget-canali.md). (Corrects earlier draft claiming Meta film-cut ads already running.)
- Budget governance: client ADV cap **≤ €500/month** contract-wide (12/12 months); scaling rule driven by cost-per-contract, not clicks: scale only after ≥1 tracked contract or stable-CPL SQL flow ≥2 months (12-budget-canali.md).

### Organic / SEO / GEO
- Site is a client-rendered React SPA → weak organic indexing; audit (15 Aug 2026): good foundations (robots, sitemap 13 URLs, Seo.tsx meta, Consent Mode v2) but **no prerender = priority fix**; GA4 last 7 days: 49 users, ~78% of sessions from Paid Search, organic ~4 sessions/week, AI-assistant channel = 0 (seo-audit-strategia-2026-08-15.md).
- Roadmap: prerender, structured data (Organization/LocalBusiness with Arco TN + P.IVA), material pages + city pages, guides 1-2/month, FAQ schema, llms.txt, Google Business Profile (seo-audit-strategia-2026-08-15.md).

### Social
- **Instagram (top priority):** 3-4 posts/week + daily stories; feed logic "one tile per post" — image-led category covers + strong single posts (Monaco project editorials, material macros), slabs-on-pedestal only inside carousels; ivory/graphite palette, dark tiles only when material is dark (FEED-STRATEGY.md, BRAND-BOOK.md). Bio update to FR-priority pending (TODO-BIANCA.md). Recurring formats incl. R1 "Progetto del mese" `[project authorizations pending]`.
- **LinkedIn (B2B priority):** 1-2 posts/week; projects, partnerships, thought leadership signed Virginia/Mauro (BRAND-BOOK.md, 10-pr-autorevolezza-luxury.md). Facebook secondary.
- Link-in-bio page (multilingual, on the SITO-MARMAREOS bundle) with UTM tracking, DMs routed to CRM (08-calendario-editoriale-social.md tasks).

### Outreach & prospecting
- LinkedIn Sales Navigator (from ~M3, ~€80/month) — 4 saved ICP lists; first batch ~70 quality contacts; multi-touch email+LinkedIn sequences IT/EN/FR (03-lead-generation-prospecting.md, 12-budget-canali.md).

### Fairs & events (no showroom → light formats)
- **Marmomac, Verona 22–25 Sep 2026** · **EquipHotel, Paris 2–5 Nov 2026** · **Maison & Objet, Paris ~Jan 2027** (networking) · **Milano Design Week, Apr 2027**; optional **Monaco Yacht Show 23–26 Sep 2026** for lightweight marble (DOSSIER.md §4, TODO files). Each event quoted and approved individually `[su preventivo]`.

### PR / authority
- FR-first media list: AD France, Elle Décoration, IDEAT, Marie Claire Maison; IT: AD Italia, Elle Decor, Interni, Domus, Living Corriere; platforms Archiproducts + Architonic; project-PR on symbol projects only `[with authorization]`, one outlet at a time with exclusivity (DOSSIER.md §5, 10-pr-autorevolezza-luxury.md).

### Measurement
- GTM as single container → GA4 (events `generate_lead`, `file_download`/`download_catalogo`, `cta_click`, `project_engaged`) → Google Ads conversions; consent-first with Consent Mode v2; every lead lands in **HubSpot with origine + UTM** (`origine_lead = google_search` verified in preview); UTM convention `mm_search_fr_cda_intent` / per-ad-group `utm_content` (01-integrazioni-tracking.md, 07b-campagna-search-fr-LIVE.md).
- Reporting: monthly report template (Part A) + quarterly review (Part B), KPI dashboard `kpi-dashboard.html` on the client portal; traffic-light thresholds `[targets to validate after 1-2 quarters baseline]` (11-template-report.md, 00-OVERVIEW-GROWTH-PLAN.md).

## Open questions

- All access references (Google Ads, GA4, GTM, Meta, HubSpot) — record only as `password-manager://` refs; several accounts are created but billing/identity verification steps sit with the client.
- Milano campaign: has Alex completed Google identity verification and published (paused) the campaign?
- Meta retargeting start date and creative set — decision pending on Search optimization.
- Newsletter/nurturing sequences: which are actually active in HubSpot as of Aug 2026?
- Channel-level KPI targets (CPL threshold, lead/month) — all still `[target da validare]` with real data.

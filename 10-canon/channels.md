---
id: marmareos-canon-channels-update-2026-08-27-race-condition-fix
brain_slug: marmareos
kind: canon-proposal
status: proposed
record_path: 10-canon/channels.md
created_at: 2026-08-27
updated_at: 2026-08-27
source_ref: Lovable MCP code investigation + fix, project a74e6792-69e7-4dc8-a394-d7afbc51e1ff, commit 6b7591bdaac928fdfe33412faabc6cd0df260c09
author: claude-cowork
title: Root cause fix for Ads/HubSpot conversion mismatch — HubSpot write race condition resolved
tags: [paid-search, hubspot, measurement, lovable, bugfix]
redacted: false
spec_version: 1.1.0
---

## Accepted knowledge — Paid search / measurement

### Root cause identified and fixed: HubSpot dual-write race condition

Reading the Marmareos site source (Lovable project) showed that every lead form submission fired two independent, unawaited calls that both write the same contact to HubSpot:

1. `submitToHubspot()` (`src/lib/hubspot.ts`) — client-side POST to the HubSpot Forms API, includes the `hutk` tracking cookie when present. This is the path that produces `PAID_SEARCH`-attributed contacts.
2. The `score-lead` Supabase edge function (`supabase/functions/score-lead/index.ts`) — server-side upsert directly to the HubSpot CRM API using an admin token. This path produces `OFFLINE`/`INTEGRATION`-attributed contacts.

Because both calls were fired concurrently without awaiting, whichever one reached HubSpot first permanently set the contact's `hs_analytics_source`. When `score-lead` won the race, the resulting contact lost its `PAID_SEARCH` attribution even though it originated from a paid campaign — a plausible and easily-reproducible cause of the previously reported Google Ads vs. HubSpot conversion-count mismatch (see canon note added 2026-08-27, "measurement-fixes").

**Fix shipped** (commit `6b7591bdaac928fdfe33412faabc6cd0df260c09`, verified via `get_diff`): in every lead-capture handler, the `score-lead` invoke is now chained inside `.finally()` of `submitToHubspot(...)`, forcing `submitToHubspot` (and its native `hutk`-based attribution) to complete first. Files changed:
- `src/components/CatalogDownloadSection.tsx` (`handleSubmit`)
- `src/pages/Contatti.tsx` (`handleSubmit`)
- `src/pages/MarmoSuMisura.tsx` (`handleSubmit`, `handleCatalogue`)
- `src/pages/Projet.tsx` (`handleSubmit`, `handleCatalogue`)

No UI or data-shape changes; `trackLead(...)` / `trackAdsConversion()` calls remain synchronous and fire at the same point as before.

## Open questions — update

The existing open question "disallineamento conteggi Google Ads vs. contatti HubSpot" (raised 2026-08-26) should be marked partially resolved: one concrete root cause (this race condition) has been found and fixed in production as of 2026-08-27. Continue monitoring conversion counts over the next 1-2 weeks to confirm the fix closes the gap; the third-party tag-serving issue (Cloudflare tag gateway, still open, low priority) may account for any remaining residual mismatch.
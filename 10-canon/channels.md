---
id: marmareos-canon-channels
client_id: marmareos
record_type: canon
service_path: paid-acquisition
status: proposed
owner: alex
authority: alex
ip_owner: marmareos
access_scope: client-team
sensitivity: internal
source_ref: manual-verification-google-ads-ui-2026-08-26
schema_version: 1.1.0
created_at: 2026-08-10
updated_at: 2026-08-26
---

# Channels — Marmareos

## Paid search

Two live Google Ads Search campaigns (account 653-269-0547):

- `MM-Search-FR-CdA-Intent` — targeting Monaco / Côte d'Azur, French-language ads.
- `MM-Search-IT-Milano-Intent` — targeting Milano +25km, Italian-language ads.

### Accepted knowledge

- FR budget documented: €300/month (~€9.80/day).
- IT Milano budget documented: ~€200/month (~€6.50/day).
- Contractual ADV cap: ≤€500/month total account spend.
- **VERIFIED 26 Aug 2026 (Google Ads UI, account 653-269-0547, campaign view, live screenshots, last 30 days 28/07–26/08/2026):**
  - Campaign status: both `MM-Search-FR-CdA-Intent` and `MM-Search-IT-Milano-Intent` show status "Idoneo" (eligible/serving). No identity-verification block or other disapproval was in effect on either campaign at the time of verification.
  - Real configured daily budgets: FR = €8.00/day (~€243/month); IT Milano = €12.00/day (~€365/month). Account total = €20.00/day (~€600/month) — this **exceeds** the €500/month contractual ADV cap. This is a discrepancy vs. the budget figures previously recorded above, which are stale.
  - Real 30-day spend (28/07–26/08/2026): €571.52 total — FR ≈€311.58 (6 conversions, cost/conv €51.93), IT ≈€259.92 (4 conversions, cost/conv €64.98). Actual spend also exceeds the monthly cap.
  - Per-campaign performance, last 30 days, source = Google Ads (not HubSpot proxy): FR-CdA — 6 conversions, conv. rate 5.13%, cost/conv €51.93, 1,527 impressions, 117 clicks, CTR 7.66%. IT-Milano — 4 conversions, conv. rate 1.54%, cost/conv €64.98, 4,233 impressions, 259 clicks, CTR 6.12%.
  - Note: this **reverses** the preliminary reading based on the HubSpot proxy (which appeared to favor IT). On real Ads conversion data, FR converts better and at lower cost/conversion than IT.

### Open questions

- Budget vs. contractual cap: real configured Ads budgets (€20/day, ~€600/month) and real spend (€571.52 in the last 30 days) both exceed the €500/month ADV cap. Alex to decide: lower the Ads daily budgets to fit the cap, or get the client to approve a cap increase.
- Google Ads vs. HubSpot conversion count mismatch (same period): IT — 4 conversions in Google Ads vs. 6 new HubSpot contacts attributable to the IT campaign; FR — 6 conversions in Google Ads vs. 5 new HubSpot contacts attributable to the FR campaign. To investigate: possible HubSpot sync gap, or duplicate-counting on the Ads side. Not yet resolved.

~~Milano campaign: has Alex completed Google identity verification and published (paused) the campaign?~~ **Resolved 26 Aug 2026**: not blocked. Verified live in Google Ads — status "Idoneo", serving normally, same as the FR campaign.
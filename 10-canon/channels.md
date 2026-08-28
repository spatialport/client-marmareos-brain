---
id: marmareos-canon-channels-catalog-flag-shipped
client_id: marmareos
record_type: canon
service_path: paid-acquisition
status: proposed
owner: alex
authority: alex
ip_owner: marmareos
access_scope: client-team
sensitivity: internal
source_ref: lovable-edit-2026-08-27-commit-f4d0eb15e966b75bdee3a7cb31a047fe33e5de92
schema_version: 1.1.0
created_at: 2026-08-27
updated_at: 2026-08-27
---

# Channels — Marmareos — addendum 27 Aug 2026 (chiusura gap download_catalogo)

Chiude l'open question "popolamento download_catalogo" dell'addendum precedente dello stesso giorno.

## Accepted knowledge — nuova voce

- **Collegamento automatico "download_catalogo" implementato e deployato il 27/08/2026** via editor Lovable (progetto `marmareos`, commit `f4d0eb15e966b75bdee3a7cb31a047fe33e5de92`). Modifica surgical, solo backend:
  - `supabase/functions/score-lead/index.ts`: nuovo campo `downloadCatalogo` nell'input; quando true (o quando `sourceDetail` contiene "catalog", come rete di sicurezza) imposta `download_catalogo: "true"` sul contatto HubSpot via upsert API; incluso anche nel fallback "safe" in caso di retry.
  - `src/pages/MarmoSuMisura.tsx` (form catalogo landing IT `/marmo-su-misura`), `src/pages/Projet.tsx` (form catalogo landing FR `/projet`), `src/components/CatalogDownloadSection.tsx` (componente catalogo riusato altrove nel sito): tutti e tre ora passano `downloadCatalogo: true` alla chiamata `score-lead`.
  - Type check (`tsgo`) passato; edge function `score-lead` ri-deployata su Supabase. Nessuna modifica a UI/copy/layout.
- **Nota tecnica utile per investigazioni future**: `score-lead` (upsert via API HubSpot, non tracciato) e `submitToHubspot` in `src/lib/hubspot.ts` (submit via HubSpot Forms API con eventuale `hutk`) vengono chiamati IN PARALLELO, senza attendersi a vicenda, per la stessa submission di form. Questa race condition tra i due path è la causa più probabile del mix di sorgenti HubSpot osservato sui contatti storici ("PAID_SEARCH" quando `submitToHubspot`/Forms API vince la corsa e crea il contatto per primo; "OFFLINE"/"INTEGRATION" quando `score-lead` upsert via API vince e lo crea per primo) — utile per la open question sul disallineamento conteggi Ads/HubSpot già in canon.

## Open questions — aggiornamento

- Rimossa/risolta: "popolamento download_catalogo" (collegamento automatico) — ora implementato e live.
- Resta aperta la parte storica: i contatti precedenti al 27/08/2026 non vengono retroattivamente aggiornati da questa modifica (il backfill dei 5 contatti storici confermati è già stato fatto manualmente lo stesso giorno, separatamente).
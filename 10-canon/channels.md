---
id: marmareos-canon-channels-measurement-update
client_id: marmareos
record_type: canon
service_path: paid-acquisition
status: proposed
owner: alex
authority: alex
ip_owner: marmareos
access_scope: client-team
sensitivity: internal
source_ref: manual-verification-google-ads-hubspot-ui-2026-08-27
schema_version: 1.1.0
created_at: 2026-08-27
updated_at: 2026-08-27
---

# Channels — Marmareos — addendum 27 Aug 2026 (measurement fixes)

Questo addendum si aggiunge (non sostituisce) l'aggiornamento del 26/08/2026 già in revisione. Riguarda le azioni correttive di misurazione decise dopo l'analisi del disallineamento Google Ads vs HubSpot.

## Accepted knowledge — nuove voci

- **Causa del disallineamento conversioni Ads/HubSpot (indagine 27/08/2026)**: due fenomeni distinti. Lato IT, sotto-conteggio in Ads per tag di conversione servito da dominio Google (non first-party) + almeno 2 contatti su 11 creati in HubSpot via canale "OFFLINE/INTEGRATION" (non tracciamento nativo, probabile mancato fire del pixel Ads). Lato FR, probabile sovra-conteggio Ads da doppio invio dello stesso form non deduplicato in HubSpot (non confermato, richiederebbe log GTM non disponibili).
- **Conversioni avanzate per i lead: ATTIVATE il 27/08/2026** in Google Ads (Impostazioni → Conversioni avanzate per i lead), metodo "Tag Google" (tag esistente, già rilevato come configurato per includere automaticamente i dati utente dai form — nessuna modifica al sito necessaria). Risolve parzialmente il gap di misurazione segnalato come "Urgente" nella Diagnostica conversioni.
- **Proprietà HubSpot "download_catalogo" creata il 27/08/2026** (Alex, via Impostazioni proprietà Contatti): checkbox singola, gruppo "Informazioni contatto". Ancora non popolata sui contatti esistenti né collegata a un trigger automatico (GTM/evento) — vedi open question sotto.
- **Punteggio di ottimizzazione Google Ads**: passato da 70,9% (26/08) a **92,2%** (27/08) dopo applicazione da parte di Alex dei consigli su annunci/asset e parole chiave. Non tracciato in dettaglio quali singoli consigli siano stati accettati.
- **Consiglio "gateway del tag Google" (server-side tagging via Cloudflare)**: ancora APERTO, non implementato. Il sito Marmareos è su Lovable; Lovable supporta il proxy Cloudflare solo come opzione avanzata dopo che il dominio è in stato "Live", e richiede una configurazione DNS attiva (passaggio da "DNS only" a "Proxied") più il deploy del Cloudflare Worker "Google tag gateway for advertisers". Richiede un account Cloudflare e accesso DNS del dominio — non eseguibile senza queste credenziali.
- **Supermetrics**: il cliente ha deciso di NON attivarlo (connettore a pagamento). Chiuso, nessuna azione ulteriore prevista su questo fronte.

## Open questions — aggiornamento

- **Popolamento "download_catalogo"**: la proprietà esiste ma (a) non è ancora valorizzata sui contatti storici che hanno effettivamente scaricato il catalogo, (b) non è collegata a un trigger automatico lato form/GTM per i nuovi lead. Serve decidere: backfill manuale one-off dei contatti storici (proposto, in attesa di conferma) + intervento tecnico lato sito/GTM per la scrittura automatica futura (non eseguibile da questa sessione).
- **Gateway del tag Google / Cloudflare**: da valutare se vale la pena l'investimento tecnico (serve account Cloudflare + resource DNS) dato che le Conversioni avanzate per i lead (già attivate) coprono parte del gap di misurazione senza bisogno di modifiche infrastrutturali.
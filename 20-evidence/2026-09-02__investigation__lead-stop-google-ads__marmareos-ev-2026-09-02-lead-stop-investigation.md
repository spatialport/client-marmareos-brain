---
id: marmareos-ev-2026-09-02-lead-stop-investigation
client_id: marmareos
record_type: evidence
service_path: paid-media
status: proposed
owner: alex-bellesia
authority: alex-bellesia
ip_owner: client
access_scope: internal
sensitivity: confidential
source_ref: cowork-session-2026-09-02-google-ads-hubspot-aws-lovable
schema_version: 1.1.0
created_at: 2026-09-02
updated_at: 2026-09-02
---

# Indagine: stop lead 22 agosto - 2 settembre 2026

Segnalazione di Alex il 02/09/2026: nessun lead da Google Ads dal 22 agosto.
Indagine su Google Ads, HubSpot, archivio lead AWS e codice del sito Lovable.

## Evidenza raccolta

### Il funnel tecnico funziona

- Test end-to-end eseguito il 02/09/2026 sul form FR `/projet` del sito live:
  submission andata a buon fine, contatto creato in HubSpot con lead_score 66,
  qualifica `mql`, `origine_lead: google_search`. Le edge function Supabase
  `send-lead-email` e `score-lead` rispondono entrambe correttamente.
- L'archivio lead AWS (DynamoDB `marmareos-leads`, us-west-2) ha registrato la
  submission di test.

### Le submission reali sono quasi azzerate, non interrotte

- HubSpot: ultimo contatto NUOVO creato il 22/08/2026 (paid search).
- Archivio AWS: una sola submission reale fra il 22/08 e il 02/09 — un download
  catalogo del 31/08 da parte di un contatto GIA' PRESENTE in CRM (creato il
  03/08). Essendo un upsert per email, non genera un lead nuovo e resta
  invisibile in qualsiasi vista basata su data di creazione.
- Nello stesso periodo le campagne hanno prodotto circa 150 clic.

### Cronologia modifiche Google Ads (account 653-269-0547)

Otto modifiche fra il 15/08 e il 02/09, tutte dall'utenza del cliente.

- 18/08, 12:55-12:58 — quattro riduzioni di budget, due per campagna
  (MM-Search-FR-CdA-Intent e MM-Search-IT-Milano-Intent).
- 27/08, 18:04-18:06 — batch di consigli Google applicati in blocco:
  "Massimizza le conversioni" su entrambe le campagne; "Partner di ricerca di
  Google" su entrambe; "Espansione alla Rete Display" su entrambe (non
  annullabile dalla cronologia); "Parola chiave ridondante" con rimozione di 2
  keyword a corrispondenza esatta, 1 a frase e 1 generica dalla campagna FR.
  Corrisponde al salto del punteggio di ottimizzazione 70,9% -> 92,2% del 27/08.

Effetto misurato: IT-Milano passa da 1.500 impressioni e CTR 6,47% (settimana
del 17/08) a 3.016 impressioni e CTR 2,79% (settimana del 24/08) — piu' volume,
qualita' molto peggiore. FR-CdA scende da circa 257 a 81 impressioni
settimanali dopo la rimozione delle keyword.

### Misurazione delle conversioni

- Diagnostica Google Ads, stato Urgente: "Le conversioni avanzate non hanno
  registrato dati negli ultimi 7 giorni" sull'azione del tag del sito.
- L'account ha quattro azioni di conversione sovrapposte; quella con origine
  "Sito web" (ID 7666716440, creata il 30/06/2026) risultava in stato
  "Configurazione errata" con la nota "Conversion has never received data", ed
  era impostata come azione secondaria e fuori dagli obiettivi di account.
- Nessun problema a livello di account: fatturazione e norme regolari.

### Difetti di implementazione trovati nel codice del sito (Lovable)

- In tutti gli handler dei form la chiamata a `send-lead-email` e' attesa e in
  caso di errore interrompe il flusso: HubSpot, lead scoring e conversione Ads
  non vengono mai eseguiti. Single point of failure, oggi non attivo ma reale.
- `forwardToAws` gira dentro la edge function, dove UTM e gclid non esistono
  come campi: in archivio arrivano sempre nulli anche quando il gclid e'
  presente nella URL di atterraggio.
- `GOOGLE_ADS_ID` in `src/lib/gtag.ts` e' rimasto al segnaposto
  `AW-XXXXXXXXXX`, quindi il config del tag Ads non viene mai eseguito dal
  codice mentre `trackAdsConversion()` invia comunque il `send_to` verso
  AW-18285077126.
- Gli snapshot statici prerenderizzati il 15/08 (`/contatti`, `/chi-siamo`,
  `/materiali`, `/lavorazioni`, `/progetti/*`, `/privacy-policy`) referenziano
  un bundle precedente all'attuale: su quelle route gira la build del 15 agosto.
- Tre contatti HubSpot di agosto non hanno corrispettivo nell'archivio AWS:
  l'archivio non intercetta tutti i percorsi di raccolta.

## Azioni eseguite il 02/09/2026

- Annullati dalla cronologia i consigli "Massimizza le conversioni", "Partner di
  ricerca di Google" e "Parola chiave ridondante" (4 keyword FR ripristinate).
- Disattivata manualmente l'Espansione alla Rete Display su entrambe le
  campagne, non annullabile dalla cronologia.
- Entrambe le campagne riportate a strategia "Massimizza i clic", sola Rete di
  ricerca, senza partner di ricerca.
- Azione di conversione del sito (ID 7666716440) promossa da secondaria a
  principale.

## Questioni aperte

- Budget: dopo i tagli del 18/08 le campagne stanno a 12 EUR/giorno (IT) e 8
  EUR/giorno (FR). La spesa 01/08-02/09 e' stata 603,42 EUR contro un cap
  contrattuale di 500 EUR/mese: da riallineare con il cliente.
- Governance: l'utenza del cliente applica i consigli Google in autonomia.
  Decidere se revocare il permesso o concordare che passino dall'agenzia.
- Le quattro azioni di conversione sovrapposte vanno razionalizzate: capire
  quale riceve davvero i dati del tag del sito e disattivare i doppioni.
- Verificare da quale percorso entrano i contatti che non finiscono
  nell'archivio AWS, e uniformare la raccolta.
- Serve una vista o una notifica sui lead di ritorno (modifiche a contatti
  esistenti), oggi invisibili nel CRM.

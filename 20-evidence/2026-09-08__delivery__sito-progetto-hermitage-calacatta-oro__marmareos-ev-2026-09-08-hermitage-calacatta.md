---
id: marmareos-ev-2026-09-08-hermitage-calacatta
client_id: marmareos
record_type: evidence
service_path: software
status: proposed
owner: alex-bellesia
authority: alex-bellesia
ip_owner: client
access_scope: internal
sensitivity: internal
source_ref: lovable://projects/a74e6792-69e7-4dc8-a394-d7afbc51e1ff
schema_version: 1.1.0
created_at: 2026-09-08
updated_at: 2026-09-08
---
# Sito marblesmarmareos.it — nuova scheda progetto "Hôtel Hermitage — Calacatta Oro"

## Cosa è stato fatto

- Aggiunta una terza scheda progetto Hermitage al sito Marmareos, slug `hotel-hermitage-calacatta-oro`, nome `HÔTEL HERMITAGE — CALACATTA ORO`, tipologia `Hospitality — Palazzo Storico`, materiale **Calacatta Oro**.
- Convive con le due schede preesistenti: `hotel-hermitage` (scheda generica, Calacatta Oro · Grigio Collemandina, senza gallery) e `hotel-hermitage-2026` (suite SPA in Onice Ivory). Nessuna delle due è stata modificata.
- Ambiti dichiarati nella scheda: rivestimenti a tutta altezza in book-match, lavabi a canale ricavati dal pieno su struttura in ottone, lavabo monolitico sagomato nei servizi ospiti, portali in massello con filo d'ottone, scala interna a gradini monolitici, tappeto a intarsio di marmi policromi a pavimento.
- Gallery di 6 immagini + hero. Asset in `src/assets/hermitage-calacatta-{hero,01..05}.webp`.
- Aggiornati: `src/data/projects.ts`, `src/components/ProjectsPreview.tsx`, `public/sitemap.xml`, `public/llms.txt`, fallback noscript in `index.html`, snapshot statico `public/progetti/hotel-hermitage-calacatta-oro/index.html`.
- Commit Lovable `edc0a23aa82d7039950c1743c49a92c33507e865` — "Aggiunto progetto Calacatta Oro" (08/09/2026).

## Trattamento immagini (metodo, riusabile)

Le 6 foto di partenza erano scatti di cantiere da telefono (1200×1600 / 2218×1476). Pipeline applicata:

1. Upscale a 4K con Higgsfield (`bytedance_image_upscale`, 2 crediti/immagine, 12 crediti totali).
2. Grading editoriale in-house coerente con BRAND-GUIDE light-first: neutralizzazione del cast mantenendo il 35-45% della dominante calda (il Calacatta Oro deve restare dorato), esposizione portata verso l'alto, roll-off delle alte luci sul marmo speculare, curva di contrasto morbida, clarity per far leggere la venatura, micro-sharpening.
3. Ritocchi puntuali: rimozione dei puntini scuri (polvere/insetti) sul marmo nel dettaglio del portale; crop della ferramenta a bordo destro nel bagno ospiti.
4. Export WebP q88, lato lungo 2560 px (hero) / 2200 px (gallery), 200-560 KB per file.

Regola derivata: le foto progetto del sito seguono il trattamento editoriale light-first del brandbook — luce naturale, cast neutro con residuo caldo, nessun filtro pesante, nessuna reinterpretazione generativa della scena.

## Aperto / da confermare

- **Anno dell'intervento**: non dichiarato. La scheda al momento non espone il campo `ANNO` (come `monte-carlo-bay`, `hotel-hermitage`, `private-offices`, `jm-davidson`). Da aggiungere se il dato viene confermato.
- **Location puntuale**: la scheda riporta "Monte-Carlo, Principato di Monaco". `hotel-hermitage-2026` riporta "Place du Casino, Monte-Carlo": da allineare sull'indirizzo corretto dell'Hôtel Hermitage.
- **Scala interna**: nelle foto i gradini sono in marmo bianco (Calacatta/Statuario); confermare che appartenga allo stesso cantiere Hermitage e non a un altro intervento.
- **Pubblicazione**: al 08/09/2026 la modifica è in preview Lovable, non ancora deployata su marblesmarmareos.it.
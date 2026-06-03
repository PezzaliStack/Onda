# ONDA 📻 — La Radio Streaming di PezzaliAPP

PWA (app installabile) per ascoltare radio in streaming: stazioni italiane, internazionali e ricerca live delle radio locali.

## Funzioni
- Player con play/pausa, volume, indicatore **ON AIR** ed equalizzatore animato
- Stazioni **Italia** (RMC, Virgin, 105, RDS, R101, Kiss Kiss, RAI 1/2/3, Deejay, Capital, m2o)
- Stazioni **internazionali** (SomaFM, Radio Paradise)
- **Ricerca** stazioni per città/genere/nome (archivio gratuito radio-browser.info)
- **Installabile** su iPhone/Android come app (icona in home, schermo intero)
- Controlli da **lock screen / cuffie** (Media Session API)
- Funziona **offline** per l'interfaccia (service worker); gli stream richiedono rete

## Pubblicazione su GitHub Pages
1. Carica TUTTO il contenuto di questa cartella nella root della repo `Onda`
   (`index.html`, `manifest.json`, `sw.js` e la cartella `icons/`).
2. Su GitHub: **Settings → Pages → Build and deployment → Source: "Deploy from a branch"**,
   Branch: `main`, cartella `/ (root)`, poi **Save**.
3. Dopo 1–2 minuti l'app sarà online su:
   **https://pezzaliapp.github.io/Onda/**

### Caricare da terminale (se hai clonato la repo)
```bash
# dentro la cartella della repo clonata
cp -r /percorso/onda-pwa/* .
git add .
git commit -m "ONDA PWA: radio streaming installabile"
git push origin main
```

## Installare l'app
- **iPhone (Safari):** apri il link → tasto Condividi → "Aggiungi a Home".
- **Android (Chrome):** apri il link → menu ⋮ → "Installa app".

## ⚠️ Nota importante sugli stream HTTP (mixed content)
GitHub Pages serve il sito in **HTTPS**. I browser **bloccano gli stream audio in HTTP**
per sicurezza. Molte radio italiane trasmettono solo in HTTP: nell'app online appaiono con
il badge **HTTP** e non partono.

Cosa funziona online (HTTPS): Kiss Kiss, SomaFM, Radio Paradise e tutte le radio trovate
con la **ricerca** (filtrata sui soli stream sicuri).

Per ascoltare anche le radio HTTP hai due strade:
1. Aprire `index.html` **in locale** (doppio clic): in locale l'HTTP non viene bloccato.
2. (Avanzato) mettere davvero un piccolo **proxy HTTPS** che riconverte gli stream HTTP —
   richiede un server, non basta GitHub Pages.

## Crediti stream
Gli stream appartengono ai rispettivi emittenti (RAI, RadioMediaset, RDS, SomaFM,
Radio Paradise, ecc.). Ricerca stazioni via radio-browser.info.

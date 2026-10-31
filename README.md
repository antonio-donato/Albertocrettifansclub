# Alberto Cretti Fansclub

Sito statico (HTML + CSS + JavaScript vanilla) che raccoglie le perle, le citazioni e le telefonate leggendarie di Alberto Cretti e colleghi.

**Live:** https://antonio-donato.github.io/Albertocrettifansclub/

Nessun build step, nessuna dipendenza: basta aprire `index.html`.

## Struttura

```
.
├── index.html      # Tutta la pagina: hero, stats, updates, memories, footer
├── css/style.css   # Tema dark, design token in :root, responsive 768/480px
├── js/main.js      # Navbar, menu mobile, reveal on scroll, smooth scroll
└── img/            # Immagini delle card + favicon
```

## Contenuti

- **Updates** (`#updates`): 90 card, perle dal 2005 al 2017 in ordine cronologico inverso.
- **Memories** (`#memories`): 16 card in timeline, telefonate del 1994.

Le card sono `<article class="card card-update">`; quelle con immagine aggiungono `card-with-image` e un `<div class="card-image">`. Le voci della timeline usano `timeline-item` + `timeline-content card`.

## Sviluppo locale

```bash
python3 -m http.server 8000
# poi apri http://localhost:8000
```

## Deploy

Il sito è pensato per GitHub Pages: pubblica il branch `main` dalla root del repository (Settings → Pages → Deploy from a branch → `main` / `/root`).

## Note

- Le animazioni di reveal usano `IntersectionObserver`; senza JavaScript il contenuto resta visibile grazie al fallback `<noscript>`.
- Le immagini hanno `width`/`height` espliciti per evitare layout shift. Se ne aggiungi di nuove, ridimensionale a ~600–700 px di larghezza e dichiara le dimensioni reali.
- `prefers-reduced-motion` è rispettato.

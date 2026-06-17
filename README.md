# Avtonoma — sito statico

Struttura pensata per GitHub + Vercel, con HTML, CSS e immagini separati.

```
avtonoma-site/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── main.js
└── images/
    ├── logo/
    │   ├── logo-white.png   (logo da inserire, vedi sotto)
    │   └── favicon.png      (opzionale)
    └── team/
        ├── alex-giannola.jpg
        └── alberto-monaco.jpg
```

## Immagini da aggiungere

Il sito funziona già senza queste immagini (ci sono dei fallback automatici: il
logo mostra il wordmark testuale "avtOnoma" con la "o" in gradiente, le foto
del team mostrano il placeholder a righe). Appena depositi i file con **esattamente
questi nomi** nelle cartelle giuste, compaiono in automatico, senza toccare il codice.

- `images/logo/logo-white.png` — versione bianca/chiara del logo (per sfondi navy,
  usata sia nel menu che nel footer). Consigliato: PNG trasparente, altezza minima 120px
  reale (verrà mostrato a 32px nel menu e 28px nel footer, quindi serve nitido sui retina).
- `images/logo/favicon.png` — opzionale, icona del browser, 512x512px va benissimo.
- `images/team/alex-giannola.jpg` — foto di Alex, formato verticale (rapporto 3:4
  circa, es. 900x1200px funziona bene).
- `images/team/alberto-monaco.jpg` — foto di Alberto, stesso formato.

## Come caricarlo su GitHub e collegarlo a Vercel

1. Crea un repository su GitHub (puoi anche chiamarlo `avtonoma-site`).
2. Carica tutta questa cartella (struttura compresa) nel repository.
3. Su Vercel, "Add New" → "Project" → importa il repository. Non serve nessun
   build command: è un sito statico, Vercel lo serve così com'è.
4. Una volta deployato, testa su `tuoprogetto.vercel.app` prima di collegare
   il dominio vero.
5. Per collegare avtonoma.com, segui i passaggi DNS che abbiamo già discusso
   (record A sull'apex e CNAME su www verso i valori che Vercel ti indica,
   lasciando intatti i record MX della posta).

## Cosa è cambiato rispetto al file originale

- Logo: percorso pulito + fallback automatico se l'immagine manca.
- Tutti i bottoni "Prenota una call gratuita" puntano ora a Calendly
  (link pulito, senza i parametri di tracciamento legati al singolo click pubblicitario).
- Rimosso il pannello "Tweaks" e lo script collegato: era un residuo dell'ambiente
  di anteprima, inutile (e potenzialmente confuso) in produzione.
- Rimossi tutti gli em dash dal testo, sostituiti con punteggiatura alternativa.
- CSS in `css/styles.css`, JS in `js/main.js`, HTML solo contenuto in `index.html`.

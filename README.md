# Hangar News: guida alla pubblicazione

Il sito si aggiorna da solo e senza costi: ogni 3 ore un piccolo programma legge i feed RSS di siti di aviazione e salva le notizie in `news.json`. La pagina `index.html` legge quel file. Non serve nessuna chiave API.

## Pubblicazione gratuita su GitHub Pages

1. Crea un account su github.com e un nuovo repository pubblico chiamato `hangar-news`.
2. Carica tutti i file di questa cartella (compresa la cartella nascosta `.github`) nel repository.
3. Settings > Actions > General > Workflow permissions: scegli "Read and write permissions".
4. Settings > Pages: Source "Deploy from a branch", branch `main`, cartella `/ (root)`.
5. Vai nella scheda Actions, apri "Aggiorna notizie" e premi "Run workflow" per il primo aggiornamento.

Il sito sarà su `https://TUO-NOME.github.io/hangar-news/`. Per un dominio tuo: Settings > Pages > Custom domain.

## Personalizzare

- Fonti: modifica la lista `FEEDS` in `scripts/update.py`.
- Frequenza: modifica la riga `cron` in `.github/workflows/update.yml`.
- Categorie: le regole con parole chiave sono in `RULES`, sempre in `scripts/update.py`.

## Limiti di questa versione

- Titoli e anteprime restano nella lingua della fonte (di solito l'inglese): l'interfaccia è in italiano, inglese e tedesco, le notizie no.
- Ogni notizia mostra l'anteprima del feed (poche righe) e rimanda all'articolo originale per il testo completo.
- Le categorie sono assegnate con parole chiave, quindi qualche notizia può finire in quella sbagliata.
- Le 7 notizie iniziali scritte a mano restano per 30 giorni, poi vengono sostituite da quelle dei feed.

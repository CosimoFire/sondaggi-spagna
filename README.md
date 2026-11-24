# Spagna, la media dei sondaggi dal voto del 2023

| Dataviz | Cartella |
|---|---|
| Spagna, come cambiano i partiti nei sondaggi | `media-sondaggi/` |

## Dati
- `data/media.csv`: media giornaliera per partito e margine al 95% (±), in %.
- `data/sondaggi.csv`: i singoli sondaggi usati (data = metà del periodo di rilevazione), più il risultato delle elezioni del 23 luglio 2023.

## Fonte e metodo
- Sondaggi: tabelle "Voting intention estimates" di Wikipedia, pagina "Opinion polling for the next Spanish general election" e archivio 2023–2024. Esclusi i sondaggi commissionati dai partiti e le pubblicazioni cumulative intermedie.
- Media: filtro di Kalman (modello "local level", come l'Eurosondaggio di Eunews) con errore di campionamento p(1−p)/n più un errore minimo di metodo, correzione per istituto (house effect, stimata sugli ultimi 18 mesi e centrata sulla media degli istituti pesata per numero di sondaggi) e risultato elettorale come primo punto.
- "Sinistra del PSOE" = Sumar (+ Podemos dopo dicembre 2023); da ottobre 2026 FA + FV + Podemos.
- Il calcolo è in `sondaggi_spagna/wikipedia/kalman_wiki.py` (fuori da questa repository).

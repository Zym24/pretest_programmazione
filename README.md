# Pretest Programmazione

Sito statico pensato per esercitarsi sui pretest del corso di **Programmazione dei Calcolatori** presso l'Università degli Studi di Roma Tor Vergata.

La piattaforma ospita simulazioni di vecchi esami e permette di scegliere un pretest, rispondere alle domande e visualizzare il punteggio finale. Tutti i dati dei test sono salvati in file JSON e caricati direttamente dal sito.

## Sito

È possibile utilizzare il simulatore all'indirizzo:

**https://zym24.github.io/pretest_programmazione/**

## Funzionamento

- [`pretest/listapretest.json`](pretest/listapretest.json) contiene l'elenco dei pretest disponibili.
- La cartella [`pretest`](pretest) contiene i file JSON dei singoli esami.
- Ogni risposta viene confrontata con il campo `risposta_esatta`.
- Le domande possono contenere sia testo sia frammenti di codice.

## Struttura dei file JSON

Ogni file nella cartella `pretest` deve contenere un array di oggetti. Ogni domanda ha questa struttura:

```json
[
  {
    "domanda": "Testo della domanda",
    "codice": null,
    "opzioni": [
      "Prima opzione",
      "Seconda opzione"
    ],
    "risposta_esatta": "Seconda opzione"
  }
]
```

- `domanda`: testo della domanda.
- `codice`: eventuale frammento di codice da mostrare; usare `null` se non è presente.
- `opzioni`: array delle risposte disponibili.
- `risposta_esatta`: testo esatto di una delle opzioni.

## Contribuire

Sono benvenuti nuovi pretest, correzioni e miglioramenti.

Per aggiungere un nuovo file nella cartella [`pretest`](pretest):

1. Creare un nuovo file JSON nella cartella `pretest`.
2. Usare una formattazione **identica** a quella dei file JSON già presenti nella cartella, rispettando i nomi e i tipi dei campi `domanda`, `codice`, `opzioni` e `risposta_esatta`.
3. Verificare che `risposta_esatta` corrisponda esattamente a una delle stringhe presenti in `opzioni`.
4. Aggiungere il nome del nuovo file in [`pretest/listapretest.json`](pretest/listapretest.json), associandolo alla relativa etichetta da mostrare nel sito.

Esempio:

```json
{
  "02-02-26.json": "02-02-26",
  "06-07-20.json": "06-07-20",
  "nuovo-pretest.json": "Nuovo pretest"
}
```

Dopo la modifica, aprire il sito per verificare che il nuovo pretest venga caricato correttamente e che tutte le domande vengano visualizzate senza errori.

## Avviso

I pretest possono contenere errori o inesattezze rispetto agli esami originali. Segnalazioni e contributi correttivi sono quindi benvenuti.

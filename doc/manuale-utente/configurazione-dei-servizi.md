# Configurazione dei servizi

\[\[_TOC_]]

Il processo di registrazione di un nuovo servizio di messaggistica IO prevede i seguenti passaggi:

1. Individuare il servizio sul Backoffice IO di pertinenza del messaggio
2. Definire l'oggetto ed il contenuto del messaggio
3. Configurare l'istanza di servizio su GovIO

## Prerequisiti

Per configurare un nuovo servizio di messaggistica IO, è necessario soddisfare i seguenti prerequisiti:

1. Aver configurato l'organizzazione mittente dei messaggi su GovRegistry.
2. Aver configurato il servizio al quale il messaggio è destinato.
3. Aver censito il servizio sul Backoffice IO e ottenuto la chiave di sottoscrizione (`Subscription Key`) per la spedizione dei messaggi.

Per maggiori informazioni sul terzo punto, si rimanda alla documentazione ufficiale di IO: https://docs.pagopa.it/io-guida-tecnica/funzionalita/pubblicare-un-servizio

## Configurazione del modello

Un modello, o template, permette di definire il contenuto del messaggio che verrà inviato al cittadino, utilizzando parti variabili, o segnaposto, che verranno sostituite con i dati forniti in fase di pianificazione delle spedizioni.

A titolo di esempio, consideriamo un messaggio per la scadenza della Carta di Identità Elettronica:

> Gentile `${full_name}`,
>
> si ricorda che in data `${due_date.date}` scadrà la sua carta di identità n. `${identity_card_number}` rilasciata il `${release_date}`.
>
> È possibile prenotare un appuntamento per il rinnovo del suo documento sul sito dell'[agenda ministeriale](https://www.prenotazionicie.interno.gov.it/cittadino/n/sc/wizardAppuntamentoCittadino/sceltaComune) oppure, se avesse bisogno di assistenza, recandosi presso le sedi URP del comune. Per maggiori informazioni consultare il [sito del Ministero dell'Interno](https://www.cartaidentita.interno.gov.it/cittadini/rilascio-e-rinnovo-in-italia/)

Il modello contiene quattro segnaposto: `full_name`, `due_date`, `identity_card_number` e `release_date`. A eccezione di `due_date` che è già previsto come valore di default nei modelli, gli altri segnaposto sono specifici per questo servizio e devono essere configurati.

Di seguito, viene illustrata la configurazione del servizio corrispondente:

## Segnaposto

Ciascun segnaposto, o placeholder, ha associata una tipologia che ne determina la validazione sintattica quando acquisito e l'uso in fase di sostituzione nel messaggio. Per le stringhe può essere configurata un'espressione regolare di validazione, consigliata per verificare sia il contenuto del testo fornito che la lunghezza.

Di seguito sono indicate le tipologie supportate e l'uso che ne può esser fatto nel messaggio.

### Date

| Nome                             | Descrizione                  | Esempio                             |
| -------------------------------- | ---------------------------- | ----------------------------------- |
| `${nome_parametro}`              | Default                      | 03/12/2027 10:15                    |
| `${nome_parametro.date}`         | Data senza orario            | 03/12/2027                          |
| `${nome_parametro.date.verbose}` | Data con giorno senza orario | Mercoledì 03/12/2027                |
| `${nome_parametro.verbose}`      | Data con giorno e orario     | Mercoledì 03/12/2027 alle ore 10:15 |
| `${nome_parametro.time}`         | Orario senza data            | 10:15                               |

### Stringhe

| Nome                      | Descrizione             | Esempio     |
| ------------------------- | ----------------------- | ----------- |
| `${nome_parametro}`       | Default                 | Lorem Ipsum |
| `${nome_parametro.lower}` | Convertito in lowercase | lorem ipsum |
| `${nome_parametro.upper}` | Convertito in uppercase | LOREM IPSUM |

### Numeri

| Nome                         | Descrizione               | Esempio  |
| ---------------------------- | ------------------------- | -------- |
| `${nome_parametro}`          | Default                   | 123456   |
| `${nome_parametro.currency}` | Serializzato come importo | 1.234,56 |

### Booleani

| Nome                | Descrizione | Esempio          |
| ------------------- | ----------- | ---------------- |
| `${nome_parametro}` | Default     | `True` o `False` |

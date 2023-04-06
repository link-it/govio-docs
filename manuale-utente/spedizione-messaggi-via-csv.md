# Spedizione messaggi via CSV

GovIO consente di pianificare l'invio massivo di messaggi ai cittadini tramite il caricamento di un file CSV. Il formato del file dipende dal modello di messaggio associato al servizio.

Di seguito i campi previsti:

## Campi CSV base senza avviso di pagamento

| # | Nome             | Obb. | Descrizione                       | Esempio             |
| - | ---------------- | ---- | --------------------------------- | ------------------- |
| 1 | taxcode          | si   | Codice fiscale destinatario       | RSSMRO00A00A000A    |
| 2 | expedition\_date | si   | Data di spedizione della notifica | 2027-12-03T10:15:30 |
| 3 | due\_date        | no   | Data scadenza                     | 2027-12-03T10:15:30 |

## Campi CSV base con avviso di pagamento

| # | Nome                      | Descrizione | Esempio                                             |
| - | ------------------------- | ----------- | --------------------------------------------------- |
| 1 | taxcode                   | si          | Codice fiscale destinatario                         |
| 2 | expedition\_date          | si          | Data di spedizione della notifica                   |
| 3 | due\_date                 | no          | Data di scadenza dell'avviso                        |
| 4 | notice\_number            | si          | Numero dell'avviso di pagamento                     |
| 5 | amount                    | si          | Importo in centesimi                                |
| 6 | invalid\_afted\_due\_date | no          | Se true, avviso non valido dopo la data di scadenza |
| 7 | payee\_taxcode            | no          | Codice fiscale dell'ente creditore                  |

## Campi CSV con segnaposto personalizzati

Nel caso in cui il modello di messaggio preveda dei segnaposto aggiuntivi, il CSV dovrà prevedere i campi corrispondenti accodati a quelli base nell'ordine in cui sono stati associati al modello.

## Esempio di CSV

Vediamo come esempio il CSV corrispondente al servizio di notifica della scadenza CIE configurato nel capitolo Configurazione dei servizi

| taxcode          | expedition\_date    | due\_date           | release\_date | full\_name  | identity\_card\_number |
| ---------------- | ------------------- | ------------------- | ------------- | ----------- | ---------------------- |
| AAAAAA00A00A000A | 2025-10-30T12:00:00 | 2025-12-31T00:00:00 | 2020-12-31    | Mario Rossi | AA12345                |

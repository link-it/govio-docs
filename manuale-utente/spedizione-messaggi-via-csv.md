# Spedizione messaggi via CSV

GovNotify consente di pianificare l'invio massivo di messaggi ai cittadini tramite il caricamento di un file CSV. Il formato del file dipende dal modello di messaggio associato al servizio.

Di seguito i campi previsti:

## Campi CSV base

<table><thead><tr><th width="209">Nome</th><th width="100">Obb.</th><th>Descrizione</th><th>Esempio</th></tr></thead><tbody><tr><td>taxcode</td><td>si</td><td>Codice fiscale destinatario</td><td>RSSMRO00A00A000A</td></tr><tr><td>expedition_date</td><td>si</td><td>Data di spedizione della notifica</td><td>2027-12-03T10:15:30</td></tr></tbody></table>

## Con scadenza

<table><thead><tr><th width="209">Nome</th><th width="100">Obb.</th><th>Descrizione</th><th>Esempio</th></tr></thead><tbody><tr><td>due_date</td><td>no</td><td>Data scadenza</td><td>2027-12-03T10:15:30</td></tr></tbody></table>

## Con avviso di pagamento

<table><thead><tr><th width="236">Nome</th><th width="100">Obb.</th><th>Descrizione</th></tr></thead><tbody><tr><td>notice_number</td><td>si</td><td>Numero dell'avviso di pagamento</td></tr><tr><td>amount</td><td>si</td><td>Importo in centesimi</td></tr><tr><td>invalid_afted_due_date</td><td>no</td><td>Se true, avviso non valido dopo la data di scadenza</td></tr><tr><td>payee_taxcode</td><td>no</td><td>Codice fiscale dell'ente creditore</td></tr></tbody></table>

## Campi CSV con segnaposto personalizzati

Nel caso in cui il modello di messaggio preveda dei segnaposto aggiuntivi, il CSV dovrà prevedere i campi corrispondenti accodati a quelli base nell'ordine in cui sono stati associati al modello.

## Esempio di CSV

Vediamo come esempio il CSV corrispondente al servizio di notifica della scadenza CIE configurato nel capitolo Configurazione dei servizi

| taxcode          | expedition\_date    | due\_date           | release\_date | full\_name  | identity\_card\_number |
| ---------------- | ------------------- | ------------------- | ------------- | ----------- | ---------------------- |
| AAAAAA00A00A000A | 2025-10-30T12:00:00 | 2025-12-31T00:00:00 | 2020-12-31    | Mario Rossi | AA12345                |

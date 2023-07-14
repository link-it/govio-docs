---
description: Proprietà di configurazione del Batch
---

# govio-batch.properties

<table><thead><tr><th width="360">Proprietà</th><th>Descrizione</th></tr></thead><tbody><tr><td>govio.batch.verify-messages.delay-mins</td><td>Tempo minimo di attesa, espresso in minuti, prima che il sistema verifichi lo stato di consegna di una notifica. Default 30.</td></tr><tr><td>govio.batch.verify-messages.window-days</td><td>Numero di giorni dalla data di spedizione di un messaggio entro il quale il sistema ne verifica lo stato di consegna. Default 14 </td></tr><tr><td>scheduler.fileProcessingJob.fixedDelayString</td><td>Intervallo di esecuzione del batch di elaborazione messaggi in millisecondi. Default 300000.</td></tr><tr><td>scheduler.sendMessageJob.fixedDelayString</td><td>Intervallo di esecuzione del batch di spedizione messaggi in millisecondi. Default 60000.</td></tr><tr><td>scheduler.verifyMessagesJob.fixedDelayString</td><td>Intervallo di esecuzione del batch di verifica messaggi in millisecondi. Default 600000.</td></tr></tbody></table>

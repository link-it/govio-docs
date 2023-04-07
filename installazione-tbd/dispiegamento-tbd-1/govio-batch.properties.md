---
description: Proprietà di configurazione del Batch
---

# govio-batch.properties

| Proprietà                                    | Descrizione                                                                                                                       |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| govio.batch.verify-messages.delay-mins       | Tempo minimo di attesa, espresso in minuti, prima che il sistema verifichi lo stato di consegna di una notifica. Default 30.      |
| govio.batch.verify-messages.window-days      | Numero di giorni dalla data di spedizione di un messaggio entro il quale il sistema ne verifica lo stato di consegna. Default 14  |
| scheduler.fileProcessingJob.fixedDelayString | Intervallo di esecuzione del batch di elaborazione messaggi in millisecondi. Default 300000.                                      |
| scheduler.sendMessageJob.fixedDelayString    | Intervallo di esecuzione del batch di spedizione messaggi in millisecondi. Default 60000.                                         |
| scheduler.verifyMessagesJob.fixedDelayString | Intervallo di esecuzione del batch di verifica messaggi in millisecondi. Default 600000.                                          |

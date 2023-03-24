---
description: Operazioni autorizzate ai ruoli previsti
---

# Autorizzazioni

Di seguito sono elencati i ruoli previsti dalle API di Backoffice di GovIO, ognuno dei quali fornisce l'autorizzazione per accedere alle risorse specificate, limitatamente alle entità delle organizzazioni e ai servizi associati all'autorizzazione, secondo le regole definite da GovRegistry.

È importante notare che la gestione delle autorizzazioni è una parte fondamentale della piattaforma GovIO e viene rigorosamente controllata per garantire la sicurezza e la privacy dei dati. Ciò significa che gli utenti avranno accesso solo alle risorse per le quali hanno le autorizzazioni appropriate, in base al ruolo assegnato e alle regole di autorizzazione definite da GovRegistry.

<details>

<summary>GovIO Viewer</summary>

Ha visibilità dei file caricati e dello stato di spedizione dei messaggi presenti sulla piattaforma.

Autorizza le risorse:

* `GET /files`
* `GET /files/{id}`
* `GET /messages`
* `GET /messages/{id}`

</details>

<details>

<summary>GovIO Sender</summary>

Estende le autorizzazioni del ruolo GovIO Viewer con la possibilità di inviare messaggi, sia singoli che massivamente tramite upload di file CSV

Autorizza le risorse:

* `POST /files`
* `GET /files`
* `GET /files/{id}`
* `POST /messages`
* `GET /messages`
* `GET /messages/{id}`

</details>

---
description: Operazioni autorizzate ai ruoli previsti
---

# Autorizzazione

Di seguito sono elencati i ruoli previsti dalle API di Backoffice di GovIO, ognuno dei quali fornisce l'autorizzazione per accedere alle risorse specificate. Se la risorsa è autorizzata, viene verificato che l'autorizzazione sia relativa all'organizzazione e servizio oggetto della richiesta.

È importante notare che la gestione delle autorizzazioni è una parte fondamentale della piattaforma GovIO e viene rigorosamente controllata per garantire la sicurezza e la privacy dei dati. Ciò significa che gli utenti avranno accesso solo alle risorse per le quali hanno le autorizzazioni appropriate, in base al ruolo assegnato e alle regole di autorizzazione definite da GovRegistry.

<details>

<summary>GovIO Viewer</summary>

Ha visibilità dei file caricati e dello stato di spedizione dei messaggi presenti sulla piattaforma.

Autorizza le risorse:

* `GET /files/*`
* `GET /messages/*`
* `GET /services/*`
* `GET /organizations/*`

</details>

<details>

<summary>GovIO Sender</summary>

Estende le autorizzazioni del ruolo GovIO Viewer con la possibilità di inviare messaggi, sia singoli che massivamente tramite upload di file CSV

Autorizza le risorse:

* `POST /files`
* `GET /files/*`
* `POST /messages`
* `GET /messages/*`
* `GET /services/*`
* `GET /organizations/*`

</details>

<details>

<summary>GovIO Service Instance Viewer</summary>

Ha visibilità dei servizi di notifica configurati e dei modelli associati

Autorizza le risorse:

* `GET /service-instances/*`
* `GET /placeholders/*`
* `GET /templates/*`
* `GET /services/*`
* `GET /organizations/*`

</details>

<details>

<summary>GovIO Service Instance Editor</summary>

Estende le autorizzazioni del Service Instance Editor con la possibilità di registrare e modificare servizi di notifica ed i relativi modelli di messaggio

Autorizza le risorse:

* `GET,POST,PUT,PATCH,DELETE /service-instances/*`
* `GET,POST,PUT,PATCH,DELETE /placeholders/*`
* `GET,POST,PUT,PATCH,DELETE /templates/*`
* `GET /services/*`
* `GET /organizations/*`

</details>

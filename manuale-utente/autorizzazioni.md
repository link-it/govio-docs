---
description: Operazioni
---

# Autorizzazioni

* `govio_viewer`: Ha visibilità dei file caricati e dello stato di spedizione dei messaggi presenti sulla piattaforma.
* `govio_sender`: Può caricare nuovi file o messaggi sulla piattaforma

| Risorsa            | Ruoli abilitati               |
| ------------------ | ----------------------------- |
| GET /files         | `govio_viewer` `govio_sender` |
| POST /files        | `govio_sender`                |
| GET /files/{id}    | `govio_viewer` `govio_sender` |
| GET /messages      | `govio_viewer` `govio_sender` |
| POST /messages     | `govio_sender`                |
| GET /messages/{id} | `govio_viewer` `govio_sender` |

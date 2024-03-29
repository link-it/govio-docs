---
description: Diagramma relazionale delle entità di GovIO
---

# Database

## Configurazioni

```mermaid
erDiagram

    govhub_organizations |o..o{ govio_templates : ""
    govhub_services }o..|| govhub_organizations : ""
    govhub_organizations |o..o{ govio_placeholders : ""
    govhub_services ||..o| govio_services : ""
    govio_services ||..o{ govio_service_templates : ""
    govio_service_templates }o..|| govio_templates : ""
    govio_templates ||..o{ govio_template_placeholders : ""
    govio_template_placeholders }o..|| govio_placeholders : ""

    govio_services {
        long id_govhub_service FK
        string apikey
        string io_service_id
        boolean enabled
    }

    govio_service_templates {
        long id
        long id_govio_service FK
        long id_govio_template FK
        boolean enabled
    }

    govio_templates {
        long id PK
        long id_govhub_organization FK
        string name
        string description
        string subject
        string message_body
        boolen has_due_date
        boolean has_payment
    }

    govio_template_placeholders {
        long id_govio_template FK
        long id_govio_placeholder FK
        int index "Posizione dopo i valori obbligatori"
        boolean mandatory "Indica se obbligatorio valorizzare"
    }

    govio_placeholders {
        long id PK
        long id_govhub_organization FK
        string name "Codice del placeholder"
        string description "Descrizione"
        string example "Valore di esempio"
        string type "Tipo di valore"
        string pattern "Regex di validazione"
    }
```

## File e Messaggi

```mermaid
erDiagram

    govio_service_templates ||..o{ govio_messages : belongs 
    govio_service_templates ||..o{ govio_files : belongs
    govhub_users ||..o{ govio_files : sends  
    govio_files ||..o{ govio_file_messages : contains
    govio_file_messages o|..|| govio_messages : "" 
    govhub_users ||..o{ govio_messages : sends  
    govio_messages ||..o{ govio_messages_idempotency_keys : ""

    govio_files {
        long id PK
        long id_govauth_user FK "utenza che ha caricato il file" 
        long id_govio_service_template FK
        string name "Nome del file"
        string location "Path del file"
        datetime creation_date "Data di upload"
        datetime processing_date "Data di completata elaborazione"
        string status "Stato di elaborazione"
        string status_detail "Dettaglio sullo stato di elaborazione"
        long size "Dimensione in byte del file"
        long acquired_messages "Numero di messaggi schedulati"
        long error_messages "Numero di messaggi scartati"
    }

    govio_file_messages {
        long id_govio_file fk
        long id_govio_message fk 
        string line_record
        long line_number
        string error
    }

    govio_messages {
        long id PK
        long id_govauth_user FK
        long id_govio_service_template FK
        string subject
        string markdown
        long amount
        string notice_number
        boolen invalid_after_due_date
        datetime due_date
        string payee_taxcode
        string taxcode
        string email
        datetime creation_date
        datetime scheduled_expedition_date
        datetime expedition_date
        datetime last_update_status
        string appio_message_id
        string status
        string status_detail
    }

    govio_messages_idempotency_keys {
        long id PK
        long id_govio_message fk
        uuid idempotencyKey
        integer beanHashcode
    }
```

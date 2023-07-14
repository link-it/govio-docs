---
description: Pianificazione di una notifica da servizi
---

# Spedizione messaggi via API

Le applicazioni che prevedono la spedizione di notifiche tramite l'AppIO possono integrarsi tramite le API di backoffice esposte da AppIO.&#x20;

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete.yaml" path="/messages" method="post" %}
[govio-api-backoffice-complete.yaml](../.gitbook/assets/govio-api-backoffice-complete.yaml)
{% endswagger %}

La richiesta al servizio di pianificazione di una nuova notifica prevede il parametro `idempotency_key` che consente alla piattaforma di riconoscere eventuali richieste duplicate.

Per la consultazione dei messaggi inviati sono disponibili le risorse REST di ricerca e lettura.

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete.yaml" path="/messages" method="get" %}
[govio-api-backoffice-complete.yaml](../.gitbook/assets/govio-api-backoffice-complete.yaml)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete.yaml" path="/messages/{id}" method="get" %}
[govio-api-backoffice-complete.yaml](../.gitbook/assets/govio-api-backoffice-complete.yaml)
{% endswagger %}

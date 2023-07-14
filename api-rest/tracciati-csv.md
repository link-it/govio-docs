---
description: Risorse REST per il caricamento e la consultazione dei tracciati CSV
---

# Tracciati CSV

{% hint style="danger" %}
La risorsa `POST /file` non viene visualizzata correttamente in questa documentazione.&#x20;

La risorsa, come definito nell'OpenAPI, si aspetta una richiesta `multipart/form-data` ed il part `file` con content-type `text/csv`
{% endhint %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete (1).yaml" path="/files" method="post" %}
[govio-api-backoffice-complete (1).yaml](<../.gitbook/assets/govio-api-backoffice-complete (1).yaml>)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete (1).yaml" path="/files" method="get" %}
[govio-api-backoffice-complete (1).yaml](<../.gitbook/assets/govio-api-backoffice-complete (1).yaml>)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete (1).yaml" path="/files/{id}" method="get" %}
[govio-api-backoffice-complete (1).yaml](<../.gitbook/assets/govio-api-backoffice-complete (1).yaml>)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete (1).yaml" path="/files/{id}/content" method="get" %}
[govio-api-backoffice-complete (1).yaml](<../.gitbook/assets/govio-api-backoffice-complete (1).yaml>)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete (1).yaml" path="/files/{id}/file-messages" method="get" %}
[govio-api-backoffice-complete (1).yaml](<../.gitbook/assets/govio-api-backoffice-complete (1).yaml>)
{% endswagger %}

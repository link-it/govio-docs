---
description: Pianificazione di un messaggio da servizi
---

# Spedizione messaggi via API

Le applicazioni che prevedono la spedizione di notifiche tramite l'AppIO possono integrarsi tramite le API di backoffice esposte da AppIO.&#x20;

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete.yaml" path="/messages" method="post" %}
[govio-api-backoffice-complete.yaml](../.gitbook/assets/govio-api-backoffice-complete.yaml)
{% endswagger %}

{% swagger src="../.gitbook/assets/govio-api-backoffice-complete.yaml" path="/messages/{id}" method="get" %}
[govio-api-backoffice-complete.yaml](../.gitbook/assets/govio-api-backoffice-complete.yaml)
{% endswagger %}

## Autenticazione ai servizi

L'accesso ai servizi richiede l'autenticazione del chiamante e verifica che disponga delle autorizzazioni necessarie.&#x20;

Il processo di autenticazione viene gestito con Spring-security e può essere configurato secondo necessità. Sono nativamente disponibili le seguenti modalità di autenticazione:

<details>

<summary>Autenticazione HTTP Header</summary>

Il principal viene individuato dal valore dell'header HTTP `GOVHUB-CONSUMER-PRINCIPAL`.&#x20;

Questa modalità viene utilizzata da GovShell per comunicare l'identità dell'operatore autenticato e deve essere consentita solo da fonti fidate (intranet).

</details>

<details>

<summary>Autenticazione Username/Password</summary>

L'utenza viene identificata tramite username e password comunicate tramite HTTP Basic Autentication come specificato nella [RFC 7617](https://www.rfc-editor.org/rfc/rfc7617)

La modalità predefinita di gestione delle password è In-Memory tramite file di configurazione. Per maggiori informazioni sulle modalità di compilazione del file, fare riferimento alla [documentazione di Spring Security](https://docs.spring.io/spring-security/reference/servlet/authentication/passwords/in-memory.html)

L'uso di questa modalità deve essere prevista solo in comunicazioni cifrate (HTTPS).

</details>

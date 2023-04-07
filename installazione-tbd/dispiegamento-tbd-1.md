---
description: Console di gestione e monitoraggio
---

# Backend

GovIO si compone di tre moduli:

* govio.war: api di backoffice
* govio-batch.war: batch di acquisizione file, spedizione e verifica messaggi
* govio-app: webapp angular di configurazione e monitoraggio

<details>

<summary>Compilazione da sorgenti</summary>

Per la compilazione a partire dai binari, sono richiesti:

* OpenJDK 11
* Maven 3.8.5
* NPM 6.14.16
* NVM 14

è sufficiente eseguire i seguenti comandi:

```bash
mvn package -Pwar
cd webapp
npm run production-govshell
zip -r dist/govio-app.zip dist/govio-app/*
```

per produrre gli artefatti necessari:

* `api/target/govio.war`
* `batch/target/govio-batch.war`
* `webapp/dist/govio-app.zip`

</details>

## Configurazione Nginx

Per l'accesso alla WebApp ed alle API di Backoffice devono essere configurate le seguenti location:

```nginx
location /govio-app {
    error_page 404 =200 /govio-app/index.html;
}

location /govio {
        proxy_set_header X-Forwarded-Host $host:80;
        proxy_set_header X-Forwarded-Server $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto http;

        proxy_redirect http://govhub-backend http://$host:80;
        proxy_pass http://govhub-backend;
}
```

Deploy della WebApp

Per dispiegare la WebApp è sufficiente


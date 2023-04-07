---
description: API di Backoffice e Batch di spedizione
---

# Backend

<details>

<summary>Compilazione da sorgenti</summary>

* Maven 3.8.5
* NPM 6.14.16
* NVM 14

<!---->

* `api/target/govio.war`
* `batch/target/govio-batch.war`
* `webapp/dist/govio-app.zip`

</details>

## Compilazione dei Sorgenti

Per la compilazione a partire dai sorgenti, sono richiesti:

* OpenJDK 11
* Maven 3.8.5

è sufficiente eseguire i seguenti comandi:

```bash
mvn package -Pwar
```

per produrre gli artefatti necessari:

* `api/target/govio.war`
* `batch/target/govio-batch.war`

## Configurazione Nginx

Per l'accesso alle API di Backoffice devono essere configurate le seguenti location:

```nginx
location /govio {
        proxy_set_header X-Forwarded-Host $host:80;
        proxy_set_header X-Forwarded-Server $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto http;

        proxy_redirect http://govhub-backend http://$host:80;
        proxy_pass http://govhub-backend;
}
```

## Dispiegamento in Tomcat

Per il dispiegamento in Tomcat è necessario:

1. Creare la cartella dei log `/var/log/govhub/`
2. Creare la cartella delle configurazioni `/etc/govhub/`
3. Creare la cartella per archiviare i file CSV di upload `/var/govhub/govio/`
4. Creare i file di contesto per Catalina per specificare il file di configurazione Spring esterno:
   * `[catalina-home]/conf/Catalina/localhost/govio.xml`
   * `[catalina-home]/conf/Catalina/localhost/govio-batch.xm`
5. Perfezionare le configurazioni personalizzando le [proprietà di configurazione](./#configurazione) di spring
6. Copiare i file `govio.war` e `govio-batch.war` nella cartella di deploy di Tomcat.

Di seguito un esempio di file di contesto:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Context>
    <Environment name="spring.config.location" value="file:///etc/govhub/" type="java.lang.String"/>
    <Environment name="spring.config.name" value="govio" type="java.lang.String"/>
</Context>
```

{% content-ref url="govio.properties.md" %}
[govio.properties.md](govio.properties.md)
{% endcontent-ref %}

---
description: Console di gestione e monitoraggio
---

# Frontend

## Compilazione dei sorgenti

Per la compilazione a partire dai binari, sono richiesti:

* NPM 6.14.16
* NVM 14

è sufficiente eseguire i seguenti comandi:

```bash
cd webapp
npm run production-govshell
```

l'applicazione è disponibile nella cartella `/dist`

## Configurazione Nginx

Per l'accesso alla WebApp deve essere configurata le seguenti location:

```nginx
location /govio-app {
    error_page 404 =200 /govio-app/index.html;
}
```

## Dispiegamento della WebApp

Per dispiegare la WebApp è sufficiente copiare il contenuto della cartella `/dist` prodotta dalla compilazione dei sorgenti, nella cartella `/usr/share/nginx/html/govio-app/`

## Configurazione

Per il corretto funzionamento deve essere perfezionata la configurazione dell'applicazione nel file `assets/config/app-config.json`, in particolare:

| Proprietà             | Descrizione                               |
| --------------------- | ----------------------------------------- |
| AppConfig.GOVAPI.HOST | Url pubblica di accesso alle api di GovIO |


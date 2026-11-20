# toi-kafkamanager

En instans av [kafka-manager](https://github.com/navikt/kafka-manager) for å administrere topics i team Toi.

Den kjørende løsningen finner du [her](https://toi-kafkamanager.intern.dev.nav.no/index.html) (for dev. Endre URL-en for prod).

## Oppdatere Kafka Manager

Workflowen **Deploy kafkamanager** sjekker siste stabile release av `navikt/kafka-manager` hver morgen. Hvis taggen avviker fra versjonen i prod, deployer Nais samme image-tag til dev og deretter til prod, uten en pull request. Workflowen ser ikke etter endringer i `:latest` uten en ny release.

Ved push til `main` bruker workflowen taggen fra siste vellykkede prod-deploy. GitHub Actions lagrer den som en artefakt og fornyer den ved morgensjekker uten ny versjon. Hvis ingen artefakt finnes, bruker workflowen siste release.

GitHub slår av planlagte kjøringer i offentlige repoer etter 60 dager uten aktivitet. Da stopper de automatiske oppdateringene til noen aktiverer workflowen igjen under Actions.

For rollback, kjør workflowen manuelt fra `main` med forrige `image-tag`. Sett morgensjekken på pause ved å fjerne `schedule` fra workflowen hvis rollbacken skal vare utover neste sjekk.

## Kode generert av GitHub Copilot
Dette repoet bruker GitHub Copilot til å generere kode.

## Henvendelser

### For Nav-ansatte
* Dette Git-repositoriet eies av [team Toi](https://teamkatalog.nav.no/team/76f378c5-eb35-42db-9f4d-0e8197be0131).
* Slack: [#arbeidsgiver-toi-dev](https://nav-it.slack.com/archives/C02HTU8DBSR)

### For folk utenfor Nav
* Teknologiavdelingen i [Arbeids- og velferdsdirektoratet](https://www.nav.no/no/NAV+og+samfunn/Kontakt+NAV/Relatert+informasjon/arbeids-og-velferdsdirektoratet-kontorinformasjon)

# toi-kafkamanager

En instans av [kafka-manager](https://github.com/navikt/kafka-manager) for å administrere topics i team Toi.

Den kjørende løsningen finner du [her](https://toi-kafkamanager.intern.dev.nav.no/index.html) (for dev. Endre URL-en for prod).

## Automatisk deploy av nyeste versjon av kafka-manger

Github Workflow-en i filen deploy.yaml inneholder en schedule som regelmessig sjekker om det er publisert en ny versjon av kafka-manager, og i så fall deployer den.

### Rollback: Hvis vi ønsker å kjøre med en gammel versjon i prod

Det kan tenkes at vi ønsker å IKKE bruke den nyeste versjonen av kafka-manger, f.eks. hvis nyeste versjon har en feil eller sikkerhets-issue.

#### Trinn 1: Angi versjon eksplistitt i manuell deploy
Workflowen i deploy.yaml støttet at vi starter en deploy manuelt i Github web GUI-et hvor vi angir en spesifikk versjon av kafka-manager: Gå til [Actions > Deploy kafkamanager >](https://github.com/navikt/toi-kafkamanager/actions/workflows/deploy.yaml) og klikk på den gønne knappen "Run workflow". Der får du mulighetne til å skrive inn navnet på en Git tag som angir versjon. Versjonstagene finner du [her](https://github.com/navikt/kafka-manager/tags).

#### Trinn 2: Stopp jobben for automatisk deploy av nyeste versjon
Vi må unngå den gamle versjonen blir "overskrevet" neste gang scehdule-en for automatisk deploy av nyeste versjon kjører. Det kan vi gjøre ved å disable hele deploy-workflow-en. Merk at da vil vi heller ikke kunne deploye ved å pushe til main. 

Gå til [workflow-en i GitHub](https://github.com/navikt/toi-kafkamanager/actions/workflows/deploy.yaml). Til høyre for den grønne knappen er en meny-knapp med tre prikker. Velg "Disable workflow".

### OBS: Automatikken kan stoppe av seg selv

GitHub deaktiverer planlagte kjøringer i offentlige repoer etter 60 dager uten commits. Da stopper de automatiske oppdateringene, fram til noen aktiverer workflowen igjen manuelt.


## Kode generert av GitHub Copilot
Dette repoet bruker GitHub Copilot til å generere kode.

## Henvendelser

### For Nav-ansatte
* Dette Git-repositoriet eies av [team Toi](https://teamkatalog.nav.no/team/76f378c5-eb35-42db-9f4d-0e8197be0131).
* Slack: [#team-toi-dev](https://nav-it.slack.com/archives/C02HTU8DBSR)

### For folk utenfor Nav
* Teknologiavdelingen i [Arbeids- og velferdsdirektoratet](https://www.nav.no/no/NAV+og+samfunn/Kontakt+NAV/Relatert+informasjon/arbeids-og-velferdsdirektoratet-kontorinformasjon)

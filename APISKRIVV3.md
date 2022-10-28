# NVDB API Skriv - Endringslogg

Endringsloggen gir oversikt over endringer og feilrettinger som er synlige/merkbare for klienter og brukere, f.eks.:

* kontraktsendringer for API-endepunktene
* regelendringer i valideringsmotoren
* funksjonelle endringer i Generator og Kontrollpanel

Dato for utrulling i produksjon er angitt i parantes.

## Leveranser 2022

### 2022.2.3 (2022-10-28)
* Validering av Z koordinat i geometri
* Utvidet datarettigheter innsikt i kontrollpanel
* Oppdatert avhengigheter
* Rettet opp feil som førte til at arbeidere ikke ble frigjort frigjort fra jobber

### 2022.1.3 (2022-10-04)
* Slått av hendelselogg for GET
* Endret feilmelding for lukkede objekter
* Mulighet for å redigerer på objekter som krysser administrativ grense

### 2022.1.1 (2022-05-03)
* Rettet opp feil med at datterobjekt mister egenskaper etter automatisk oppdatering
* Forbedret håndtering av jobber

### 2022.1.0 (2022-03-29)
* Rettet opp feil ved mangelfull følgeoppdatering for enkelte objekttyper ved snuing av metreringsretning
* Forbedring av feilmelding autorisasjonsfeil

### 2022.0.12 (2022-03-08)
* Retting av feil der ny versjon av vegobjekt blir feilaktig opprettet automatisk etter overlappssjekk

### 2022.0.11 (2022-02-15)
* Rettet opp feil ved følgeoppdatering i forbindelse med reduksjon av stedfesting til overlappede vegobjekter

### 2022.0.9 (2022-02-15)

* Rettet opp versjonskonflikt ved restedfesting av assosiasjoner

### 2022.0.8 (2022-01-28)

* Forbedring av detaljering på feilmelding av overlapp

### 2022.0.6 (2022-01-26)

* Forbedret avvising av endringssett dersom det finnes versjoner som overlapper

### 2022.0.5 (2022-01-14)

* Områdeimport
* Nytt stedfestingsparamter: Trafikkgruppe
* Fikset feil i stedfestingstjenesten
* Entreprenør kan nå registreres
* Vegsystemreferanse blir presentert ved overlapp feil

## Leveranser 2021

### 2021.9.3 (2021-11-30)

* Forbedring av stedfestingsendepunkt

### 2021.9.1 (2021-11-25)

* Strengere autorisering på vegkategorier
* Lagt til følgeoppdatering ved endring av mor-objekt
* Kontrollerer og tilpasser klokkeslett-verdier
* Forbedret feilmelding ved ulik sideposisjon eller feltkode

### 2021.8.2 (2021-11-12)

* Utvidet vegtyper med traktorveg, sti og annet

### 2021.8.1 (2021-11-04)

* Automatisk populering av vegnummer i Vegsystem
* Rettet opp svakhet i autentisering
* Bedret feilmelding for oppdatering av lukkede objekter
* Kontrollerer om ny lenkesekvens ikke er for lang
* Forbedret stedfesting
* Generelle forbedringer i valideringspipelinen

### 2021.6.1 (2021-06-11)

* Feilrettet XML Schema for Transaksjonsliste
* Tilbakemelding på feil stedfesting er korrigert til å vise til riktig veglenkesekvens
* Indikere dryrun i endringssett-status
* Lavre lovlige verdi på nøyaktighet, geometri er endret fra 0 til -1

### 2021.5.0 (2021-04-26)

* Oppdatert bibliotek for behandling av geometri og topologi
* Rettet opp feil i stedfesting som førte til CPU overload
* Forbedret informasjonstekst for søk på transaksjoner i kontrollpanelet
* Fikset feil med innlogging til generator
* Fikset innloggingsproblematikk i docker-image
* Mer brukervennlig feilmelding ved stedfesting på lenkesekvenser

### 2021.4.1 (2021-04-06)

* Rettet opp i OIDC innlogging for eksterne brukere


### 2021.4.0 (2021-03-23)

* Indikere manglende rolle for ny bruker
* I Datarettigheter er det mulig å søke på brukernavn og navn
* Kontroll for å hindre duplikate endringssett
* Vise feilmelding ved innsyn i kontrollpanel
* Batchjobb for endring av over 1000 vegreferanser i samme endringssett


### 2021.3.0 (2021-02-22)

* Geometrivalidering ser på geometriegenskapstypene samlet
* Kontrollerer at nye lenker ikke har sluttdato
* Leverer metrikker som antall behandlede endringssett, behandlingstid for endringssett o.l.
* Dropper kontroll av heldekkende vegreferanse før 2006
* Validerer geometritype i alle vegobjekter
* Ratelimiter satt på alle endepunkt


### 2021.2.0 (2021-02-08)

* Håndhever MinimumPlanarAngle og MinimumVerticalAngle kun for lenker med åpen sluttdato
* Ny fane for å slå opp i /les-endepunkter i Kontrollpanelet for admin brukere
* Fjernet stack trace fra 500-respons
* Overføre vegnummer fra Vegreferanse (532) til Vegsystem (915)
* Rettet opp i at overlapp ved korrigert gyldighetsperiode ikke avvises
* Deassosiering av mor datter, fjerner ikke datter om datter ikke har "må ha mor" egenskapen
* Rettet opp i feil automatisk sideposisjon ved rundkjøring
* Rettet opp i stedfestingsfeil for kontraktsområde oppdages ikke

### 2021.1.0 (2021-01-14)

* Verifiser at kall mot stedfesting gir en gyldig stedfesting tilbake
* Søk med bruker i lower-case i Oppdragsfanen. Skal gi treff på samme måte som upper-case. Prøv også med en blanding.
* Verifiser at prøveinnsjekk av Ulykke gir AVVIST når hendelsesdato og startdato er ulik + UTFØRT når de er like
* Bruk bodies i kommentar og gjenskap resultatet fra UTV i ATM


## Leveranser 2020

### 2020-17.1 (2020-12-22)

* Rettet feil som førte til at vegobjekter som ikke er sideposisjonrelevant fikk beregnet sideposisjon
* Rettet feil som førte til at oppslag i LDAP-API av og til feilet og etterlot endringssett med feil fremdriftskode
* Rettet feil som førte til 500-respons fra stedfestingstjenesten når det ikke var angitt typeVeg som parameter.

### 2020-17.0 (2020-12-09)

* Stedfestingstjenesten kan nå beregne sideposisjon på bestilling.
* Rettet feil som førte til at utstedt OIDC-token ikke ble ansett som gyldig ved bruk i Authorization-header.
* Forbedret stedfestingstjenesten ved å maskere bort overflødige punktsegmenter fra rute beregnet av API Les.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/stedfest/stedfest.xsd

### 2020-16.0 (2020-12-02)

* Endepunktet for transaksjoner tillater nå søk på tjenesteregel. Responsen inkluderer brukerinformasjon.
* Kontrollpanelet er utvidet med ny fane for oppdrag og transaksjoner, med søkemuligheter.
* Rettet feil i stedfestingstjenesten som førte til responskode 500 ved tilpasning av små kurver til minimum stedfestingslengde.

#### Oppdaterte XML-skjemaer
* https://nvdbapiskriv.atlas.vegvesen.no/rest/v1/transaksjon/transaksjon.xsd
  
### 2020-15.3 (2020-11-23)

* Rettet feil som førte til at detaljvisning ble aktivert ved klikk på sletteikon i Låser-fanen i Kontrollpanelet.
* Forbedret håndtering av konnekteringslenker i stedfestingstjenesten.

### 2020-15.2 (2020-11-16)

* Rettet feil som ga responskode 500 når ugyldig refresh-token ble angitt i request til /oidc/forny
* Klienter som bruker tjenestebrukere kan nå anrope APIet i Atlas-miljøet.
* Rettet feil som førte til at endringssett ble avvist fordi det feilaktig ble detektert overlapp mellom mor- og datterobjekt.

### 2020-15.1 (2020-11-06)

* Stedfestingstjenesten produserer nå strekningsstedfesting med konstant trafikantgruppe.
* Rettet feil i kontrollpanelet i Atlas-miljø som gjorde det umulig å åpne endringssettet i ny fane fra endringssettets detaljvisning.

### 2020-15.0 (2020-10-23)

* Utvidet endringssettstatus med notabene ved overlapp i stedfestingen mellom to vegobjekter, når sideposisjon eller kjørefelt er udefinert i ett av dem.
* Rettet feil i Kontrollpanel og Generator i Atlas-miljø som gjorde at BasicAuthProxy avviste requester med utgått iPlanetDirectoryPro-token.
* Validering av at et vegobjekt bare har én mor tar nå hensyn til om det finnes multiple mødre i NVDB (datafeil).
* Stedfestingstjenesten krever ikke lenger at vegfase oppgis sammen med vegkategori.
* Stedfestingstjenesten tillater nå at beregningsparametere angis i payload.
* Rettet feil som førte til databasefeil under behandling av endringssett når det søkes i NVDB etter morobjekter til mer enn 1000 vegobjekter.
 
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/stedfest/stedfest.xsd

### 2020-14.2 (2020-10-13)

* Etablerte OIDC-pålogging i Kontrollpanel og Generator når API Skriv kjører i Atlas-miljø.
* Rettet feil som gjorde at responser med ressurslenker brukte http og ikke https i URLer når API Skriv kjører i Atlas-miljø.
* Forbedret beregning av 'area locations' i grenseområdet mellom to Kommune_2019-objekter, ved å kreve minimum 2 meter geometrisk overlapp. 
* Forbedret ytelse i stedfestingstjenesten ved å redusere punkttetthet for geometrier kortere enn 500 m før beregning av rute.
* Forbedret låsealgoritmen ved behandling av rene fagdata-endringssett slik at det ikke lenger lages sekundærlås for Vegsystem-objekter.

### 2020-14.1 (2020-09-30)

* Rettet feil som førte til havari i stedfestingstjenesten ved beregning av punkttilknytning i sluttposisjonen til en veglenke.
* Endret stedfestingstjenesten til også å bruke punktsegment i rute fra API Les og utvide til minimumslengde for strekningstilknytning.
* Rettet feil som førte til databasefeil ved beregning av statistikk for et endringssett registrert med for lang tekst i X-Client.

### 2020-14.0 (2020-09-23)

* Nytt endepunkt for å etablere OIDC-token gitt brukernavn og passord.
* Rettet feil som førte til havari ved lukking av deassosierte vegobjekter.
* Rettet feil som avviste et endringssett pga. ugyldig overlapp når samme vegobjekt både ble lukket og fikk korrigert stedfesting.
* Rettet feil ved avkoding av rute fra API Les som førte til havari ved beregning av stedfesing på en del av vegnettet.
* Rettet feil som førte til havarert behandling av endringssett når vegnettslukking fører til lukking av vegobjekt som også lukkes i endringssettet.
* Rettet feil som førte til havari når samme vegobjektversjon både delvis korrigeres og delvis oppdateres i et endringssett.
 
### 2020-13.0 (2020-09-14)

* Kan nå både lukke og korrigere samme vegobjektversjon i ett endringssett.
* Rettet feil som hindret henting av brukerprofil fra SoaBasis for brukere med norske tegn i brukernavnet.
 
### 2020-12.1 (2020-09-14)

* Rettet feil som gjorde at søkefeltet for brukernavn og klient i endringssettfanen i Kontrollpanelet ikke ble vist for fagdata-admin-brukere.
* Rettet feil som forårsaket havari ved unødvendig overlappskontroll på vegobjekt som lukkes.

### 2020-12.0 (2020-08-20)

* Kan nå kansellere et endringssett med status BEHANDLES.
* Forbedret beregning av ID-egenskap for Kryssystem- og Sideanlegg-objekter på KPS-veg som er stedfestet på en veglenkes sluttposisjon.

### 2020-11.0 (2020-08-13)

* Stedfestingstjenesten beregner nå stedfesting som er gyldig i vegobjektets levetid.
* Rettet feil i stedfestingstjenesten som gjorde at den havarerte ved store geometrier.
* Feilmelding ved mottak av endringssett med både lukking og delvis korrigering av samme vegobjektversjon beskriver nå hvilken id og versjon det er snakk om.
* Forbedret valideringsmotoren slik at flere valideringsfeil avdekkes og meldes samlet i en behandling.
* Unnlater nå å gi notabene på endret sideposisjon ved restedfesting av vegobjekter ved utskiftning av vegnettsgeometri når datafeil i NVDB hindrer beregning av opprinnelig sideposisjon.
* Kontrollpanel: SVV-logoen kan nå klikkes på og vil i så fall åpne Statens vegvesen sin hjemmeside i en ny nettleserfane.
* Støtter nå rollen nva/5_fagdata_admin. Brukere med denne rollen har samme rettigheter som tjenestebrukere og fagdatabrukere og kan i tillegg se på endringssett uavhengig av eier.
* Rettet feil i valideringen av superstedfestingen til detaljerte veglenker som førte til at rampe på detaljert veglenke superstedfestet på rampe på hovedveglenke ble avvist.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte pga numerisk unøyaktighet rundt lenkeposisjon 1.0.
* Rettet feil ved beregning av ID-egenskap for Kryssystem-objekt på privat veg som er stedfestet på en veglenkes sluttposisjon.

### 2020-10.0 (2020-07-01)

* Støtter nå avkorting av historikk for datterobjekter når assosiasjonen i morobjektet fjernes, uansett levetid i den aktuelle morobjektversjonen.
* Kontrollpanel: Navbar viser nå en lenke til API-dokumentasjonen.
* Kontrollpanel: Redesignet navbar for å unngå at knapper skjules under SVV-logo når nettleserbredden blir liten.
* Kontrollpanel: Rettet feil som gjorde at bare de 1000 første registrerte brukerne ble vist i nedtrekkslisten i fanen 'Datarettigheter'.
* Rettet feil som førte til havari ved lesing av eksisterende Gate-objekter i NVDB.

### 2020-9.1 (2020-06-23)

* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte under beregning av sideposisjon.
* Rettet feil i valideringen av Gate-objekter som førte til avvisning når det ikke var angitt gatenavn.
* Støtter to nye verdier for sideposisjon i stedfestinger: `R0` som er ekvivalent med `R` og `HV` som er ekvivalent med `VH`.
* Rettet feil i registrering av nye vegobjekter med svingstedfesting på nyregistrert node som førte til at nodeId ikke ble angitt i NVDB.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2020-9.0 (2020-06-16)

* Rettet feil i validering av kjørefelt i superstedfestingen til detaljerte veglenker som førte til avvisning når et kjørefelt er ugyldig på sluttdato for veglenken.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte under beregning av sideposisjon.
* Tjenestebrukere kan nå hente status og fremdrift for alle endringssett uavhengig av eier.
* Kontrollpanel: Viser flere detaljer i hendelsesloggen til et endringssett når versjonskontroll fører til at behandlingen restartes.
* Generator: Rettet feil som hindret visning av SQL for gyldige testcase.
* Rettet feil som gjorde at GET mot /rest/v3/endringssett uten å angi requestparameter `sorterPå` havarerte.
* Forbedret responsen fra konverteringsendepunktene ved å levere endringssett i tråd med foretrukne standarder i NVDB og API Skriv.

### 2020-8.0 (2020-06-02)

* ID-egenskapen for vegobjekttypene Kryssystem og Sideanlegg beregnes og påføres nå automatisk under behandling.
* Tillater nå at en delvis oppdatering eller korrigering legger til en ny verdi i en listeegenskap (assosiasjon eller stedfesting) som ikke er populert fra før.
* Gjorde stedfestingstjenesten mer robust når beregnet rute inneholder singulariteter (punkter).
* Rettet feil som gjorde det umulig å lukke vegnett der ikke-versjonerbare vegobjekter er delvis stedfestet.

### 2020-7.0 (2020-06-02)

* Støtte for fjerning av noder:
    * `GET|POST /endringssett/{id}`:
        * Nytt subelement `<vegnett>/<noder>/<node>` *kan* angis under `<fjern>`. 
* Endringssett som avvises etterlater ikke lengre tomme oppdrag i NVDB.
* Forbedret validering av navn og kode for Gate-objekter.
* Kontrollpanel: Rettet feil som gjorde det umulig å bla videre fra side 1 i endringssettoversikten.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2020-6.0 (2020-05-14)

* Nytt endepunkt for å beregne gyldig stedfesting for et vegobjekt med geometri: /rest/v3/stedfest
* Støtte for ekstern referanse for et endringssett:
    * `GET|POST /endringssett/{id}`:
        * Nytt subelement `<eksternRef>` *kan* angis for `<endringssett>`. Verdien er fritekst (255 tegn) og lar klienter
          markere endringssettet med en klientspesifikk eller prosjektspesifikk identifikator. 
* Stedfestingen til Kryssdel-objekter i rundkjøringer blir ikke lengre optimalisert.
* Endringssett kan nå inneholde korrigering og oppdatering på samme vegobjektversjon. Gjelder også delvise varianter.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte pga numerisk unøyaktighet rundt lenkeposisjon 1.0.
* Rettet feil i versjonskontrollen av berikinger i et endringssett som førte til restartet behandling til evig tid.
* Kan nå kansellere et endringssett med status VENTER og venteårsak VENTER_PÅ_LÅS.
* Utvidet feilmelding når et nettelement har ubrukte porter med informasjon om hvilke porter som er ubrukte.
 
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/stedfest/stedfest.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2020-5.0 (2020-04-28)

* Ny valideringsregel som avviser endringssett ved gjensidig overlapp mellom vegobjekttypene Strekning (916), Kryssdel (918) og Sideanleggsdel (920).
* Forbedret valideringsmotoren slik at flere valideringsfeil avdekkes og meldes samlet i en behandling.
* Rettet feil i transaksjonsendepunktet som førte til overforbruk av minne ved anrop uten søkeparameter.
* Rettet feil som førte til avvisning pga. ikke-versjonerbar vegobjekttype ved følgeoppdatering etter vegnettslukking.

### 2020-4.1 (2020-03-26)

* Endringssett som behandles under prøvekjøring etterlater ikke lengre tomme oppdrag i NVDB.
* Ved låsekonflikt omprøves nå behandling etter en pause med randomisert lengde.
* Angir nå flere detaljer i feilmelding når datterobjekt ikke er stedfestet innenfor mor.
* Rettet feil som hindret følgeoppdatering med korrigering på samme vegobjektversjon som blir korrigert i endringssettet.
* Gjorde innhenting av vegkategori for vegnett mer robust når superstedfesting mangler i detaljerte veglenker.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte når deler av samme vegnett lukkes.

### 2020-4.0 (2020-03-16)

* Nytt høydekoordinatsystem i NVDB: NN2000. SRID 6173 (EUREF89 UTM33 NN54) er ikke lenger tillatt og avvises nå med valideringsfeil.
  Eneste tillatte 3D koordinatsystem er SRID 5973 (EUREF89 UTM33 NN2000). Ved bruk av 2D koordinatsystem, forventes at høydekoordinater
  er angitt i tråd med NN2000.  
* Rettet feil som gjorde at lukking av samme vegobjektversjon i to ulike følgeoppdateringer ble avvist som i konflikt med hverandre.
* Rettet feil i oppslag mot SoaBasis som gjorde at nva-roller ikke ble hentet for tjenestebrukere.

### 2020-3.0 (2020-02-27)

* Nytt endepunkt for å hente autorisasjoner (datarettigheter) for en bruker: /rest/v1/autorisasjon/{brukernavn}
    * En fagdatabruker kan bare hente sin egen autorisasjon.
    * Tjenestebrukere og systemadminbrukere kan hente alle autorisasjoner
* Tydeligere feilmelding i 403-respons når bruker mangler rettigheter til å anrope et endepunkt.
* Rettet feil i beregning av Area Locations for Kommune_2019 som etterlot hull i stedfestingen når en veglenkesekvens krysser en kommunegrense.
* Rettet feil som i noen tilfeller med store endringssett førte til tidsavbrudd i koblingen mot NVDB-databasen.
* Rettet feil som førte til avvisning på grunn av manglende sensitiv-rolle ved lukking av vegobjekt.
* Rettet feil som førte til at transaksjonskontroll havarerte når mer enn 500 vegobjekter ble overskrevet i samme endringssett.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/autorisasjon/autorisasjon.xsd
    
### 2020-2.0

* Støtte for delvis oppdatering av multistedfesting:
    * `GET|POST /endringssett/{id}`:
        * Ny attributt `operasjon` *kan* angis på `<stedfesting>` sine subelementer `<punkt>` og `<linje>` når disse opptrer under `<delvisOppdater>` eller `<delvisKorriger>`. Attributten kan gis verdien `ny` dersom et nytt punkt eller linje skal legges til eksisterende verdier,
          eller `slett` dersom den angitte punktet eller linjen skal fjernes fra stedfestingsegenskapen i NVDB. Attributten må angis på *alle* eller *ingen* verdier. Dersom attributten ikke er angitt på noen verdier, erstattes alle gjeldende verdier i NVDB med
          de angitte verdiene (slik det har vært fram til nå).  
    * Det er ikke tillatt å fjerne alle gjeldende verdier fra stedfestingen (uten å legge til minst én ny).
    * Det er ikke tillatt å legge til en verdi som er identisk med eller overlapper en gjeldende verdi.
* Støtte for delvis oppdatering av datterobjektreferanser i assosiasjoner:
    * `GET|POST /endringssett/{id}`:
        * Ny attributt `operasjon` *kan* angis på `<assosiasjon>` sine subelementer `<nvdbId>` og `<tempId>` når disse opptrer under `<delvisOppdater>` eller `<delvisKorriger>`. Attributten kan gis verdien `ny` dersom en ny datterobjektreferanse skal legges til eksisterende verdier,
          eller `slett` dersom den angitte datterobjektreferansen skal fjernes fra assosiasjonen i NVDB. Attributten må angis på *alle* eller *ingen* verdier. Dersom attributten ikke er angitt på noen verdier, erstattes alle gjeldende verdier i NVDB med
          de angitte verdiene (slik det har vært fram til nå).  
    * Dersom alle gjeldende verdier fjernes fra assosiasjonen, fjernes assosiasjonsegenskapen i sin helhet fra NVDB.
    * Det er ikke tillatt å legge til en verdi som er identisk med en gjeldende verdi.
* Det er innført tilgangsbegrensning på vegobjektegenskaper som har sensitivitetskoder i Datakatalogen. For å kunne registrere og oppdatere slike egenskaper
må brukeren nå ha spesifikke roller i LDAP.
* Rettet feil som gjorde at multiple operasjoner på samme vegobjektversjon ble avvist, selv om operasjonene ikke var i konflikt med hverandre.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte under beregning av sideposisjon.
* Rettet feil som førte til responskode 500 ved uthenting av endringssett med delvis oppdatering av strukturert geometriegenskap.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2020-1.4

* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte.
* Rettet feil som førte til at to identiske endringssett med oppdatering av et vegobjekt ble ferdigbehandlet og etablerte to instanser av samme vegobjektversjon i NVDB.  

### 2020-1.3

* Rettet feil som førte til at beregning av Area Location for Fylke_2019 havarerte. 

### 2020-1.2

* Rettet feil som førte til at en node nært opptil svenskegrensen, men på norsk side, ble avvist som utenfor Norge.
* Rettet feil som førte til at beregning av Area Locations havarerte.

### 2020-1.1

* Rettet feil som førte til at overlappsautomatikk ble utført for delvis oppdatert Gate-objekt, selv om stedfestingen var uendret.
* Rettet feil som tillot korrigert Vegsystem-objekt å overlappe med et eksisterende Vegsystem-objekt i NVDB.
* Rettet feil som førte til at restedfesting av vegobjekter ved utskiftning av vegnettsgeometri havarerte.

### 2020-1.0

* Krever ikke lengre at minst én veglenke er oppgitt ved delvis oppdatering av veglenkesekvenser. Det er dermed mulig å angi delvis oppdatering der kun porter endres.
* Tillater nå korrigering uten at bruker har 9_system_admin-rollen
* Tillater nå multippel stedfesting for Strekning (916)
* Rettet feil som hindret delvis oppdatering og delvis korrigering av strukturert geometriegenskap


## Leveranser 2019

### 2019-12.0
* Retning på detaljerte veglenker sin superstedfesting:
    * `GET|POST /endringssett` : 
        * Subelementet `<retning>` under elementet `<veglenkesekvens>/<veglenke>/<superstedfesting>` *må* angis. Lovlige verdier er `MED` og `MOT`. Verdien angir den detaljerte veglenken sin retning relativt til
         hovedveglenkesekvensen den er stedfestet på.

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/veglenke.xsd

### 2019-11.0
* Støtte for fysisk fjerning av vegobjekter og enkeltversjoner av vegobjekter i endringssett:
    * `GET|POST /endringssett/{id}`:
        * Nytt operasjonselement `<fjern>` under `<endringssett>`. Dette elementet forventer subelementer tilsvarende `<lukk>`, altså `<vegobjekter>` med én eller flere `<vegobjekt>` som subelementer. 
          På elementet `<vegobjekt>` *må* attributtene `typeId` og `nvdbId` angis. På elementet *kan* også attributten `versjon` angis. Dersom denne utelates fjernes hele vegobjektet.
          I elementet `<vegobjekt>` *må* subelementet `<kaskadefjerning>` angi hvorvidt fjerning også skal utføres på relevante datterobjektversjoner, tilsvarende `<kaskadelukking>` for `<lukk>`. Tillatte verdier er `JA` og `NEI`.
          Dersom denne settes til `NEI` vil endringssettet avvises hvis vegobjektet som fjernes har sterkt koblede datterobjekter.
    * Det er kun tillatt å fjerne versjoner "bakfra" i historikken til et vegobjekt. Fjerning av v2 fra et vegobjekt med tre versjoner, vil avvises med mindre v3 også fjernes.
    * Det er tillatt å fjerne flere versjoner fra samme vegobjekt så lenge de utgjør et sammenhengende intervall. Fjerning av v1 og v3 fra et vegobjekt med tre versjoner avvises.
    * Ved fjerning vil siste gjenværende (om noen) versjon av vegobjektet få sin sluttdato endret til sluttdatoen fra siste fjernede versjon.
      Dersom siste gjenværende versjon får sin sluttdato endret via en korrigering i samme endringssett, vil denne påføres uavhengig av hvilken sluttdato siste fjernede versjon hadde.
    
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2019-10.0
* Flere opplysninger i elementet `<status>` for endringssett:
    * `GET /endringssett/{id}` og `GET /endringssett/{id}/status`:
        * Nytt subelement `<fremdriftOppdatert>` angir tidspunkt når gjeldende verdi for `<fremdrift>` ble satt.
        * Nytt subelement `<blokkerendeLåser>` angir null eller flere id'er til låser som blokkerer behandling av dette endringssettet. Angis kun når fremdrift=VENTER_PÅ_LÅS. Hver lås angis med subelement `<låsId>`.
        * Nytt subelement `<ressurser>` angir en eller flere lenker til relevante ressurser, f.eks. oppdrag. Hver ressurs angis med subelement `<ressurs>`.
* Nytt gyldig kriterium for å fjerne forhåndslås:
    * `GET|POST /endringssett/{id}`:
        * Ny lovlig verdi for `<låsing>/<slettLåsAutomatiskNår>` under `<endringssett>` er `UTFØRT`.
          Bruk av denne verdien fører til at forhåndslåsen fjernes når (hvis) endringssettet når fremdriftsverdien med samme navn, altså når NVDB er oppdatert, men før NVDB API Les sin indeks er ajour.
                
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2019-9.0
* Mulighet til å bestille automatisk reduksjon av punkttetthet i kurve- og polygongeometri:
    * `GET|POST /endringssett/{id}`:
        * For `<vegobjekt>/<validering>` under `<registrer>`, `<oppdater>`, `<delvisOppdater>`, `<korriger>` og `<delvisKorriger>` *kan* det angis et nytt subelement `<reduserPunkttetthet>`.
          Ved å sette verdien til `JA`, vil nabopunkter i kurve- og polygongeometrier som er tettere enn minsteverdi angitt i Kontrollpanelet bli fjernet, i stedet for å trigge avvisning pga. for tette punkter.
          Om elementet ikke oppgis antas verdien `NEI`.
                       
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2019-7.0
* Versjonskontroll av korrigeringer:
    * `GET|POST /endringssett/{id}`:
        * For `<vegobjekt>/<validering>` under `<korriger>` og `<delvisKorriger>` (samt `<oppdater>`, `<delvisOppdater>` dersom overskriv="JA") *MÅ* det angis et nytt subelement `<lestFraNvdb>`.
          Her må det angis tidspunkt for innlesing av vegobjektet fra NVDB. Tidspunktet må være "NVDB-tid" som kan hentes fra https://\<host\>/nvdb/api/v3/status.
                       
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2019-6.0
* Mulighet til å bestille automatisk håndtering av overlappede vegobjekter:
    * `GET|POST /endringssett/{id}`:
        * For `<vegobjekt>` under `<registrer>`, `<oppdater>`, `<delvisOppdater>`, `<korriger>` og `<delvisKorriger>` *kan* det angis et nytt subelement `<validering>`.
          Under dette elementet *kan* man angi `<overlappsautomatikk>JA</overlappsautomatikk>` dersom man ønsker at eventuelle overlappede vegobjekter skal få sin stedfesting trimmet automatisk,
          i stedet for å trigge avvisning pga. ulovlig overlapp. Om elementet ikke oppgis antas verdien `NEI`.
* Lenker til relevante ressurser for oppdrag og transaksjoner:
    * `GET /oppdrag`:
        * Nytt subelement `<ressurser>` under `<oppdrag>` angir en eller flere lenker til relevante ressurser for oppdraget. Hver ressurs angis med subelement `<ressurs>`.
    * `GET /transaksjon`:
        * Nytt subelement `<ressurser>` under `<transaksjon>` og under `<transaksjon>/<objekttype>` angir en eller flere lenker til relevante ressurser for oppdraget. Hver ressurs angis med subelement `<ressurs>`.
                  
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/oppdrag/oppdrag.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/transaksjon/transaksjon.xsd


## Leveranser under KRR-prosjektet 

### Sprint 21
* Hovedoperasjonen 'slett' (brukes bare av vegobjekter) har fått det litt mer presise navnet 'lukk':
    * `GET|POST /endringssett` :
        * Elementet `<slett>` under `<endringssett>` omdøpt til `<lukk>`
        * Elementet `<kaskadesletting>` under `<slett>/<vegobjekter>/<vegobjekt>` omdøpt til `<kaskadelukking>`
* Harmonisering av ordlyd i APIene:
    * `GET|POST /endringssett` :
        * Attributten `id` på elementet `<veglenke>` er omdøpt til `nummer`. 
        * Subelementet `<lenkeId>` under elementene `<feil>`, `<advarsel>` og `<notabene>` er omdøpt til `<veglenkenummer>`. 
        * Subelementet `<feltkode>` under elementene `<veglenke>/<superstedfesting>`, `<vegobjekt>/<stedfesting>/<punkt>` og `<vegobjekt>/<stedfesting>/<linje>` er omdøpt til `<felt>`. 
        * Subelementet `<kjørefelt>` under elementet `<veglenke>` er omdøpt til `<feltoversikt>`. 
        * Attributten `id` på elementet `<port>` er omdøpt til `nummer`.
        * Subelementet `<portId>` under elementet `<port>/<veglenkesekvenstilkobling>` er omdøpt til `<portnummer>`.
        * Subelementet `<portId>` under elementet `<port>/<nodetilkobling>` er omdøpt til `<portnummer>`.
        * Subelementet `<startportId>` under elementet `<veglenke>` er omdøpt til `<startportnummer>`.
        * Subelementet `<sluttportId>` under elementet `<veglenke>` er omdøpt til `<sluttportnummer>`.
        * Subelementet `<portId>` under elementene `<feil>`, `<advarsel>` og `<notabene>` er omdøpt til `<portnummer>`.
        
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/vegobjekt.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/veglenke.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/veglenkesekvens.xsd

### Sprint 20
* X-Client header kreves ved POST/PUT/PATCH/DELETE mot endepunktene: 
    * /v3/endringssett 
    * /v1/lås 

### Sprint 19
* Støtte for oppdatering uten ny versjon (overskriving av siste versjon):
    * `GET|POST /endringssett` :
        * På elementet `<endringssett>/<oppdater>/<vegobjekter>/<vegobjekt>` *kan* attributten `overskriv` angis. Tillatte verdier er `JA` og `NEI`. Om attributten ikke oppgis antas verdien `NEI`. 
        * På elementet `<endringssett>/<delvisOppdater>/<vegobjekter>/<vegobjekt>` *kan* attributten `overskriv` angis. Tillatte verdier er `JA` og `NEI`. Om attributten ikke oppgis antas verdien `NEI`. 
* TypeVeg "Turveg" omdøpt til "Gatetun":
    * `GET|POST /endringssett` :
        * `TypeVeg.TURVEG` endret til `TypeVeg.GATETUN`
    * `GET /regelsett/veglenke` :
        * `TypeVeg.TURVEG` endret til `TypeVeg.GATETUN`
    * `GET /regelsett/vegnettobjekttype` :
        * `TypeVeg.TURVEG` endret til `TypeVeg.GATETUN`
* Antall låser i låseliste :
    * `GET /lås` :
        * På elementet `<låser>` er det lagt på en ny attributt `totaltAntall` som angir antall låser i NVDB.
* Oppdrag- og transaksjonendepunktene har fått nye URLer:
    * `GET /les/v1/oppdrag` :
        * URL endret til `/v1/oppdrag`
    * `GET /les/v1/transaksjon` :
        * URL endret til `/v1/transaksjon`

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/regelsett/veglenke.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/regelsett/vegnettobjekttype.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/lås/lås-liste.xsd

### Sprint 18
* Ingen kontraktsendringer

### Sprint 17
* Støtte for multiple endringsdatoer i endringssett
    * `GET|POST /endringssett` :
        * Under elementet `<endringssett>` er `<effektdato>` fjernet.
        * Under elementet `<endringssett>/<registrer>/<vegobjekter>/<vegobjekt>` *må* subelementet `<gyldighetsperiode>` angis. Subelementet `<sluttdato>` er fjernet.
        * Under elementet `<endringssett>/<oppdater>/<vegobjekter>/<vegobjekt>` *må* subelementet `<gyldighetsperiode>` angis. Subelementet `<sluttdato>` er fjernet.
        * Under elementet `<endringssett>/<delvisOppdater>/<vegobjekter>/<vegobjekt>` *må* subelementet `<gyldighetsperiode>` angis. Subelementet `<sluttdato>` er fjernet.
        * Under elementet `<endringssett>/<slett>/<vegobjekter>/<vegobjekt>` *må* subelementet `<lukkedato>` angis.
        * Under elementet `<endringssett>/<slett>/<vegobjekter>/<vegobjekt>` *må* subelementet `<kaskadesletting>` angis. Attributten med samme navn er fjernet.
* Innført fullstendige navn på `Detaljnivå`-verdier
    * `GET|POST /endringssett` :
        * VT => VEGTRASE
        * VTKB => VEGTRASE_OG_KJØREBANE
        * KB => KJØREBANE
        * KF => KJØREFELT
* Innført korrekte navn på lenke og lenkesekvens:
    * `GET|POST /endringssett` :
        * lenke(r) => veglenke(r)
        * lenkesekvens(er) => veglenkesekvens(er)
        * lenkesekvensNvdbId => veglenkesekvensNvdbId
        * lenkesekvensTempId => veglenkesekvensTempId
        * lenkesekvenstilkobling => veglenkesekvenstilkobling
    * `GET|POST /lås` :
        * lenkesekvens => veglenkesekvens
        * Lokasjonsrelevans:
            * LENKE => VEGLENKESEKVENS
            * LENKE_ELLER_NODE => VEGLENKESEKVENS_ELLER_NODE
    * `GET /regelsett/lenke` :
        * URL endret til `/regelsett/veglenke`
    * `GET /les/lenkesekvens` :
        * URL endret til `/les/veglenkesekvens`
    * Ordlyd på enkelte feilkoder (String) endret tilsvarende
            
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/vegobjekt.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/veglenke.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/veglenkesekvens.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/lås/lås.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v1/regelsett/veglenke.xsd

### Sprint 16
* To nye endepunkter for å levere gjeldende versjon av valideringsregelsett
    * `GET /regelsett/vegnettobjekttype/versjon` : Responderer med payload som beskriver gjeldende versjon av regelsettet (se XML-skjema for `<versjon>`).
    * `GET /regelsett/lenke/versjon` : Responderer med payload som beskriver gjeldende versjon av regelsettet (se XML-skjema for `<versjon>`).
* `GET /regelsett/vegnettobjekttype` : Rotelementet er omdøpt fra `<regelListe>` til `<regelsett>`. Et nytt subelement `<versjon>` er innført, med samme informasjon som over.
* `GET /regelsett/lenke` : Rotelementet er omdøpt fra `<regelListe>` til `<regelsett>`. Et nytt subelement `<versjon>` er innført, med samme informasjon som over.

### Sprint 15
* Støtte for korrigering av historiske vegobjektversjoner i endringssett
* `GET /les/vegobjekt` : Elementene `<startdato>` og `<sluttdato>` er flyttet inn i et nytt subelement `<gyldighetsperiode>` under `<vegobjekt>`-elementet.
* `GET /les/lenkesekvens` : Elementene `<startdato>` og `<sluttdato>` er flyttet inn i et nytt subelement `<gyldighetsperiode>` under `<lenke>`-elementet.
* `GET /les/node` : Elementene `<startdato>` og `<sluttdato>` er flyttet inn i et nytt subelement `<gyldighetsperiode>` under `<node>`-elementet.
* `GET|POST /endringssett` :
    * Under elementet `<korriger>/<vegobjekt>` *må* `startdato` (obligatorisk) og `sluttdato` (valgfritt) angis i et nytt subelement `<gyldighetsperiode>`.
    * Under elementet `<delvisKorriger>/<vegobjekt>` *kan* `<startdato>` (obligatorisk) og `<sluttdato>`(valgfritt) angis i et nytt subelement `<gyldighetsperiode>`.
    * Under elementene `<lenke>` og `<node>` er elementene `<startdato>` (obligatorisk) og `<sluttdato>` (valgfritt) flyttet inn i et nytt subelement `<gyldighetsperiode>`.
* `GET /endringssett/{id}/status` :
    * Elementet `<resultat>/<vegobjekter>/<vegobjekt>` har fått en ny attributt `versjon`.
       
#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/vegobjekt.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/lenke.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/les/node.xsd
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### Sprint 14
* `POST /lås` : Avvises med 422 og feilkode `FOR_MANGE_LENKESEKVENSER` dersom låsen inneholder mer enn 999 lenkesekvenser.
* Følgeoppdatering (justering av stedfesting) ved geometriutskiftning på veglenker.

### Sprint 13
* `POST /lås` : Innført strukturert payload i 403-responser som inneholder `<fault>` med detaljer dersom bruker
  mangler rettigheter til vegobjekttyper eller kommuner (avledet av veglenker) angitt i låsen, eller mangler rettighet
  til å utføre vegnettsendringer dersom låsen er en vegnettslås.
* Ved oppdatering av nettelementer detekteres hvilke aspekter (geometri, topologi, metadata m.fl.) som er endret og kun
  disse aspektene blir validert. Eventuelle feil i uendrede aspekter fører dermed ikke lenger til at endringssettet avvises.

### Sprint 12
* Ved uregelmessigheter i nettelementers geometri angis dette med subelementet `<geometrideler>` under
  `<feil>`, `<advarsel>` og `<notabene>` i endringssettets status. Her angis koordinatene til den delen av geometrien
  som har uregelmessigheter via `<wkt>`-subelementer, enten som `POINT` eller `LINESTRING` (dersom uregelmessigheten gjelder
  sammenhenger mellom to naboposisjoner).

### Sprint 11
* Nytt subelement `<låsing>` etablert under `<endringssett>`. Tidligere subelement `<låsId>` er flyttet inn hit.
* Klienten kan be om å få forhåndslåsen automatisk fjernet på gitte betingelser ved å angi dette med `<slettLåsAutomatiskNår>`
  under `<låsing>`. Foreløpig kan man kun angi koden `UTFØRT_OG_ETTERBEHANDLET`.
* Innført `<notabene>` som ny alvorlighetsgrad for varsler i endringssettets status i tillegg til `<feil>` og `<advarsel>`.
  Alle følgeoppdateringer som utføres ved behandling av endringsettet beskrives via globale notabene-varsler.
* Ved `GET /endringssett/{id}/status` leveres nå nytt subelement `<etterbehandling>` som angir om transaksjonen er indeksert
  og tilgjengelig i API Les. Tilsvarende subelement i `<endringssett>` er fjernet.

### Sprint 10
* Følgeoppdatering (endret retning på retningssensitive egenskapstyper) ved endret metreringsretning
* Omdøping `<vegobjekt>/<lokasjon>` --\> `<vegobjekt>/<stedfesting>`
* Attributtene `retning` og `sideposisjon` på `<vegobjekt>/<stedfesting>` er gjort om til subelementer
* Attributten `felt` på `<vegobjekt>/<stedfesting>` er erstattet med et subelement `<kjørefelt>` som igjen har en eller flere `<feltkode>`-subelementer
* Omdøping `<lenke>/<lenkesekvensprojeksjon>` --\> `<lenke>/<superstedfesting>`
* Omdøping `<lenke>/<lenkesekvensprojeksjon>/<nvdbId>` --\> `<lenke>/<superstedfesting>/<lenkesekvensNvdbId>`
* Omdøping `<lenke>/<lenkesekvensprojeksjon>/<tempId>` --\> `<lenke>/<superstedfesting>/<lenkesekvensTempId>`
* Elementet `<feltkode>` under `<lenkesekvensprojeksjon>` (nå `<superstedfesting>`) er plassert inne i nytt subelement `<kjørefelt>` og kan repeteres 

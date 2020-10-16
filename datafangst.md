# Datafangst - Endringslogg

## Leveranser 2020

## Oktober
### Datafangst 2020-2.6.1
* Kolonner i kontraktsliste sorteres i stigende rekkefølge ved første klikk
* Mer av Datakatalogen mellomlagres i nettleser, for raskere oppstart
* Det er rettet en feil med kopiering av vegobjekt til ny type når type er låst
* Flere forbedringer for å samkjøre stedfesting for sammenkoblede objekter
* Flere feilrettinger for stedfesting med Skriv API
* Det er rettet en feil som gjorde at fjerning av vegobjekter fra kontrakt feilen noen ganger
* Gammel fane for stedfesting er ikke lengre tilgjengelig
* Bedre håndtering av feil under henting av vegnett

### Datafangst 2020-2.5.0
* Vedlikeholdskontrakt og samlekontrakt er tilgjengelige som nye kontraktstyper
* Alle felter i kontraktsliste sorteres riktig med tall og norske tegn
* Sortering på "Ansvarlig" i kontraktsliste virker igjen
* Markører for stedfesting kan klikkes for å velge en stedfesting
* Markører for valgte stedfestinger er uthevet
* Det er retten en feil med "Skjul koblede" på sammenkobling
* Administrasjon av rettigheter setter nå medlemskap kontraktsgrupper uavhengig av små eller store bokstaver i brukernavn
* Det er retten en feil i "Stedfesting med Skriv" som gjorde at det noen ganger ikke kunne stedfestes til valgt vei

## September
### Datafangst 2020-2.4.1
* Rettet en feil som gjorde at stedfesting av vegobjekter med sammenkoblinger kun til NVDB genererte en feilmelding

### Datafangst 2020-2.4.0
* Manuell stedfesting flytter automatisk seg selv og sine døtre inn til sin mor hvis de er sammenkoblet.
* Kontraktgruppelista i instillinger sorteres alfabetisk.
* Sortering av kontrakter, brukere og kontraktgrupper i admin-grensesnittet .
* Rettet en feil som kunne føre til at nye eller kopierte kontrakter framstod som låst.
* Angir arkiveringsstatus for kontrakter via API.
* parameter for å angi destinasjon ved API-kall for å hente feature collections.
* Revidert tekst på automatisk generert e-post til nye brukere, lenke til hjelpeside.
* aktiverer zoom til senter av kartvinduet ved dobbelklikk for å unngå en feil i kartbiblioteket.
* Setter geodata-kartet som forvalgt på stedfesting fordi norkartene er veldig trege.
* Gjør det mulig å zoome lenger inn på geodata-kartene på bekostning av lavere oppløsning.
* Bedre feilhåndtering i _alternativ stedfesting med API Skriv_ der en stedfestingsfeil ville avbryte alle stedfestinger.

### Datafangst 2020-2.3.1
* Brukere får nå beskjed når innloggingen er utløpt, og de bes logge inn på nytt.
* Knapper på innstillingsfanen har fått bedre universell utforming.
* Bedre feilmelding når vegobjekter blir forkastet ved filopplasting.
* Kontraktgrupper i innstillingsfanen vises riktig for brukere som ikke har rettigheter i gruppen
* Skjuler varsel og lenke til forrige versjon av stedfestingsfanen.

### Datafangst 2020-2.2.2
* Eksisterende sammenkoblinger som fjernes vises på sammenkoblingsfanen til de blir sendt inn, og fjerning kan angres før innsending
* Det er retten en feil med innsending av geometri som har SRID 6173
* Sletting av sammenkobling gir nå riktig tilstand på om vegobjekt er endret eller ikke etter sletting
* Teknisk endring: Datafangst bruker nå AAA-tjeneste for å verifisere brukernavn og passord

### Datafangst 2020-2.1.3
* Det er rettet en feil som gjorde at interne brukere uten fagdata-rolle ikke fikk logget inn

### Datafangst 2020-2.1.2
* Det er rettet en teknisk feil med applikasjonslogg

### Datafangst 2020-2.1.0

* Når en kontrakt har vegobjekter med sensitive egenskaper må den som skal invitere brukere inn på kontrakten ha rettigheter til å se disse egenskapene
* Hvis prosjektreferanse settes ved innsending til NVDB, så vil også vegobjektene i Datafangst vise prosjektreferansen etter at innsending er godkjent
* I administrasjonssiden for kontraktsgrupper vises nå kontrakter, grupper og brukere sortert
* Sjekk for gyldig e-postadresse eller brukernavn når det legges til deltaker i kontrakt er forbedret
* Tekst i veileder for innloggingsproblemer er forbedret

## August

### Datafangst 2020-2.0.2

* Alle kartlag kan nå vises som gråtonekart i datafanen og stedfestingsfanen ved å klikke på ikonet nederst til venstre i kartet
* La til støtte for tastenavigasjon og skjermleser i kontraktlisten
* Rettet en feil i eksport-fanen som gjorde at vegobjekter importert fra NVDB ikke vistes i listen over andre vegobjekttyper som må sendes inn samtidig
* Fjernet kontroll av FKB-objekter, samt informasjon som forteller at FKB-objekter ikke vil bli kontrollert.
* Rettet en feil i eksportfanen som gjorde at funksjonen som skal vise bare uregistrerte vegobjekttyper, istedet viste bare registrerte vegobjekter

### Datafangst 2020-1.14.0
* Stedfesting for kurve er forbedret, sånn at den oftere gir resultater som passer med punkt
* Kontraktsliste laster mye raskere for brukere som er i kontraktsgrupper med mange kontrakter
* Status på innsendt endringssett til NVDB blir sjekket selv om bruker som sendte det ikke er logger inn
* Endringssett som får systemfeil i NVDB for status "avvist" i Datafangst i stedet for at den blir hengende på "venter"
* Forbedret sjekk og feilmelding på manuelle ankerpunkter når veg ikker er valgt
* Toppmeny har fått bedre støtte for skjermleser

### Datafangst 2020-1.13.0
* Datafangst forstår nå status "kansellert" ved innsending til NVDB
* Tomme verdier for nye vegobjekter blir filtrert ut ved innsending, sånn at endringssett ikke blir avvist
* Tomme eller slettede verdier blir ikke med når eksisterende vegobjekt kopieres til nytt vegobjekt
* Det er rettet en feil som gjorde at logg ikke ble oppdatert etter kopiering av vegobjekt

### Datafangst 2020-1.12.1
* Prosjektreferanse settes nå kun på vegobjekter i kontrakten, og ikke som tidligere også mor i NVDB (når det er en kobling til mor fra kontrakten)
* Etter utført stedfesting eller godkjenning av stedfesting nullstilles valgte vegobjekter
* Tydeligere beskjed om hva som forventes når bruker legges til i kontrakt
* Ved oppretting av ny kontrakt varsles det hvis noen av feltene har for mye tekst
* Responstid skal nå være på nivå med 2020-1.10.0, vi har kompensert for databaseendring som gjorde 2020-1.11.0 tregere
* Det er rettet en feil med at innhold ikke kommer opp på delingslenke (feilen ble introdusert i 2020-1.11.0)
* Knappen "Skjul registrerte" på datafanen virker nå igjen
* Det er rettet en feil med at "Marker som feil" ikke var tilgjengelig på nye kommentarer (feilen ble introdusert i 2020-1.11.0)

## Juni

### Datafangst 2020-1.11.1
* Det er rettet en feil som gjorde at deltakere på kontrakt ikke kunne importere vegobjekter fra NVDB (feilen ble introdusert i 2020-1.11.0)
* Status for innsending til NVDB beholdes når det lastes opp en ny objektliste for kontrakt
* Det er rettet en feil med at automatisk zoom alltid ble aktivert etter geometriredigering

### Datafangst 2020-1.11.0
* Datafangst støtter nå fullt ut lagring av samiske tegn, og en lang rekke spesialtegn som tidligere ikke var støttet
* Stedfesting virker nå også for store linjegeometrier som skal ha punktstedfesting
* Det er laget en veiledning for brukere som har glemt passord eller mangler tilgang, sånn at de får hjelp på riktig sted
* Nyeste objektliste for Nye veier er nå også støttet for opplasting
* Det vises nå hvilken kolonne det sorteres på i datafanen
* Bedre tilbakemelding ved fjerning av flere vegobjekter fra kontrakt
* Det er rettet en feil som gjorde at "kopier til alle" på datafanen ikke alltid virket
* Det er rettet en feil med endring av kontraktsgruppe for kontrakt
* Administrator kan nå endre kontraktsgruppe for en kontrakt som allerede har en gruppe
* Det er rettet feil i hvilke brukere som skal ha tilgang til enkelte funksjoner
* Datafangst API: Mellomrom på starten og slutten av innsendte verdier blir nå bevart

## Mai

### Datafangst 2020-1.10.0
* Det er rettet en feil som gjorde at vegobjekter som har endring i sammenkobling ikke kunne sendes inn igjen etter første innsending
* Det er retten en feil med innsending av vegobjekter der enkelte attributter mangler verdi
* Mer robust håndtering av interne feil ved innsending til NVDB
* Stedfestingsfane vil nå fullføre lasting selv om ikke alle datakilder er tilgjengelige
* Bedre tilbakemelding ved feil med endring av ansvarlig for kontrakt
* Det er rettet en feil med tilgang for noen få brukere som har dobbel registrering av roller
* Datafangst API: Det er nå mulig å legge til vegobjekter i samlinger som har en feilstatus


### Datafangst 2020-1.9.2
* Rettet en feil i stedfesting som blant annet gjorde at mødre feilaktig ble tolket som for langt unna sine døtre
* Ny versjon av Stedfestingsfanen settes nå som standard etter en periode med utprøving (meld fra om feil!)
* Ny versjon av stedfestingsalgoritme (API Skriv istedet for VVI) tilgjengelig for utprøving via admin
* Toppmenyen har fått seg en ansiktsløftning (takk, Rikke!)
* Personnavn vises istedet for brukernavn for de brukerne vi har mulighet til å hente det ut for
* Kontrakter er nå søkbare på personnavn der det er mulig
* Zoom-nivå i kartet på stedfestingsfanen kan nå låses
* Opplastinger vi API skal nå ikke like lett havne i blokkerende ERROR-tilstand når baksystemer feiler eller timer ut
* Duplikate innslag i objektlista skal nå filtreres bort
* Diverse mindre justeringer og feilrettinger

### Datafangst 2020-1.8.2
* Rettet en feil der importering av mor og datter fra NVDB i noen tilfeller kunne skape duplikate sammenkoblinger, som førte til feil ved registrering i NVDB
* Rettet en feil som gjorde at man ikke fikk med valideringsfeil ved opplasting av enkeltobjekter via API
* Det er nå mulig å sende med høydereferanse på featurecollections i API
* Innsendinger til Datafangst som inneholder geometrifeil som ikke kan rettes i datafangst, vil nå bli avvis med feilmelding
* Feilmeldinger som vises i Datafangst kan nå markeres, slik at teksten kan kopieres
* Feilmeldinger som vises i Datafangst kan nå lukkes med en egen knapp istedet for klikk på teksten
* Import fra URL, f.eks fra vegkart, vil nå fungere selv om URL-en inneholder linjeskift eller mellomrom
* Rettet en feil som gjorde at skiltplater med tekst der teksten ikke var satt kunne føre til systemfeil
* Rette en feil som gjorde at datafanen av og til kunne gå i hvitt

## April

### Datafangst 2020-1.7.0
* Det er nå mulig å velge flere kjørefelt i avkryssingsmodal (på objekter som kan ha kjørefelt).
* Et problem med stedfestning med datter innenfor mor på enkelte objekter er nå rettet
* Gruppering av kartmarkører fungerer nå på zoom-nivåer
* Et problem med tilganger og flytting av kontrakter er rettet
* Et problem med endring innsending med endret prosjektreferanse er rettet.
* Data med valideringsfeil som ikke kan rettes i Datafangst blir avvist ved import
* Rettet en feil der man kan sette sideposisjon og felt på objekter som ikke kan ha det 

## Mars

### Datafangst 2020-1.6.0
* Nå er det mulig å gjøre automatisk stedfesting på bare noen typer av gangen.
* Feilmeldinger på innsending viser nå navn på vegobjekt i stedet for intern id.
* Nå virker import av API-url også fra nyeste versjon av vegkart (Atlas).
* Rettet feil som gjorde at man ikke kunne sende inn vegobjekt med kobling til mor i NVDB.
* Diverse forbedringer på utprøvingsversjon av ny stedfestingsfane.

### Datafangst 2020-1.5.2
* Eksport av SOSI-filer fra Datafangst har nå høydereferanse NN2000.
* Det er rettet en feil som ble introdusert i 2020-1.5.0 med at innsendinger til NVDB alltid overskriver eventuelle nye versjoner av eksisterende vegobjekter.
* En opppusset versjon av stedfestingsfanen er tilgjengelig for begrenset utprøving.

### Datafangst 2020-1.5.0
* Kvalitetsparametre for høyde er nå tilgjengelig sammen med andre kvalitetsparametre.
* Administratorer for kontraktsgrupper har nå tilgang til funksjonen "Overskriv NVDB" ved innsending av endringsett.
* Geometri for låste vegobjekter kan nå kopieres.
* Det er rettet en feil som ble introdusert i 2020-1.4.0 med at det ikke kom opp dialog for import når man klikket på kurve- eller flate-objekter.
* Datafangst er endret til å bruke API Les på Atlas.

### Datafangst 2020-1.4.0
* En feil gjorde at man ikke fikk sendt inn lukkinger på en objekttype mer enn
  én gang. Denne er rettet.
* En feil gjorde at man ikke fikk sendt inn noen geometrier over APIet.
* Kartet hadde en feilvisning av objekter langt øst. (spesielt i Finnmark) Dette
  er rettet.
* Nå skal tilbakestilte sammenkoblinger vises som "ikke endret", og ikke bli
  kandidat for lagring.
* Fikset en feil som gjorde at kartet lastet på nytt når "importer fra NVDB"-
  boksen dukket opp.

### Datafangst 2020-1.3.0
* Datafangst støtter både NN54 og NN2000 som høydesystem inn til NVDB, og er klar for NVDBs overgang til NN2000.
* Stedfesting bruker nå maks 8 desimaler på posisjon, slik at det blir mindre konflikt med stedfesting som allerede er i NVDB.
* Automatisk fjerning av for tette punkter er skrudd på for innsending til NVDB, også for gamle data som ikke fikk dette gjort ved første import til Datafangst."
* Det er rettet en feil med innsending til NVDB når lukkede vegobjekter for en vegobjekttype allerede var sendt inn.
* Egenskaper som sendes inn via Datafangs API med tom verdi blir nå ikke registrert som egenskaper, dette gjør at det blir færre valideringsfeil når vegobjektere skal redigeres.
* Det er rettet en feil som gjorde at markering av endring på kontrakt ikke ble borte etter visning av kontrakt.

## Februar

### Datafangst 2020-1.2.0
* Vi har fikset en feil som gjorde at kartet viser feil ved oppstart.
  Kartet hadde en tendens til å vise tilsynelatende tilfeldige kartfliser
  fra Azerbaijan/Georgia.
* Rettighetssystemet hadde en feil som gjorde at brukere, i enkelte
  situasjoner, ikke fikk korrekte rettigheter. Dette gjaldt blant annet
  funksjonen "Kopier sideposisjon fra mor". Feilen er nå rettet.

### Datafangst 2020-1.1.0
* Import av objektliste fra Excel-fil skal nå fungere for alle nye
  listeversjoner (v4.1-v4.8) og gamle versjoner ( fra v3.1-v4.0).
* Vi har gjeninnført støtten for å hente data fra Vegkart v2.
  (Importere data fra Les API v2.)
* Enkelte vegobjekter vises nå med mer utfyllende (beskrivende) navn på sammenkoblings- og
  stedfestingsfanen. (Skiltplate, Kabel, Rørledning og Kum)
* Ved sammenkobling med mor i NVDB, vil mor nå lagres som OPPDATER og ikke som
  KORRIGER, og dermed bl.a. få nytt versjonsnummer.
* Den gamle kontraktslisten er nå helt borte fra Datafangst, og kan ikke
  lenger aktiveres.

## Januar

### Datafangst 2020-1.0.4
* Det er rettet en feil fra 2020-1.0.3 som gjorde at det ikke var mulig å sende inn endringsett med operasjon "korriger".

### Datafangst 2020-1.0.3
* Overlapp med eksisterende vegobjekter blir nå håndtert automatisk ved innsending til NVDB.
* Administratorer kan nå endre ansvarlig bruker for en kontrakt.
* Det er et nytt menyvalg på datafanen for å kopiere sideposisjon fra mor.
* Ikon for endringslogg vil nå ha en markering når det er lagt ut en ny versjon.
* Datafangst er oppdatert til å bruke versjon 3 av NVDB Les API.
* Det er gjort en endring på hvordan Datafangst hånterer versjon av datakatalogen, sånn at det ikke lengre kommer advarsel om feil versjon selv om nyeste versjon brukes.
* Kartet som vises for vegobjekttype på status-fanen er endret slik at knapp for eksisterende objekter ikke lenger er tilgjengelig.
* Det er ikke lengre mulig å registrere ekstern bruker fra innloggingsside, nye eksterne brukere må inviteres inn på en kontrakt for å bruke Datafangst.
* Det er rettet en feil med manuell stedfesting på lange vegsegmenter.
* Det er rettet en feil som kunne gi systemfeil ved innsending når kobling til datter var fjernet i kontrakt.
* Det er rettet en feil som gjorde at enkelte endringsett innsendt med Datafangst 2019-8.1.6. ikke ble markert som fullført.
* Det er rettet en feil med at endringsett som ble opprettet med Datafangst 2019-8.0.3 og tidligere ikke ble satt som fullført på Datafangst 2019-8.1.6.
* Lenke til Sintefs datakatalog skal nå virke.


### Datafangst 2019-8.1.6
* Det er nå mulig for administratorer å arkivere og de-arkivere andres kontrakter.
* Datafangst bruker nå NVDB Skriv Endringssett API v3. For å passe med endringer i API
  så brukes nå "lukk" på vegobjekter som skal avsluttes, i stedet for "slett".

## Leveranser 2019

## Desember

### Datafangst 2019-8.0.3

* Rettet en feil som gjør at man ikke kan ta en kontrakt ut av en
  kontraktsgruppe. Denne feilen oppstår spesielt ved overflytting av kontrakter
  til nye kontraktsgrupper.
* Rettet en feil som gjør at man ikke kan kopiere tomme felter til valgte/alle
  i datafanen.

### Datafangst 2019-8.0.2

En stor endring i denne versjonen er at det nå er mulig å endre vegobjekter etter at de første gang er sendt inn til 
NVDB, og siden sende inn endringer på nytt. Dette gjelder både egenskaper, stedfesting og sammenkobling. På fanen for
innsending til NVDB vil det vises oppdatert status for innsending, så den har fått noen endringer. Ikonet for at 
endringer er lagret i NVDB er litt endret for å harmonere bedre med ikonet for innsending. 

Dette er en komplisert endring, så det er mulig at det vil dukke opp feil som vi ikke har funnet under testing.
I så fall, gi oss beskjed på datafangst-support@vegvesen.no.

Andre endringer i denne versjonen:
* Internet Explorer tom. versjon 11 og enklete andre gamle nettlesere er sperret fra å logge inn i Datafangst
* Viser sideposisjon i info for eksisterende NVDB-objekter
* Viser enheter for attributter på vegobjektfanen
* Fikset feil med at søk ikke vises når bruker kommer tilbake til kontraktslista
* Fikset en visningsfeil for markører på stedfestingskart
* Fikset kopiering av sideposisjon på vegobjektfanen
* Fikset en feil med sortering på vegobjektfanen
* Hindrer redigering av sideposisjon når objekt ikke er stedfestet
* Beskrivende navn for vegobjekter er tilgjengelig på visningsmenyen på vegobjektfanen for enkelte vegobjekttyper


## November

### Datafangst 2019-7.1.0
* Manuell stedfesting for punktobjekter er endret slik at disse kan stedfestes selv om avstand til valgt vei er stor.
* Klipping av geometri i nye linjeobjekter i kontrakt er nå tilgjengelig for alle.
* Det er mulig å sette dato for endringssett som sendes inn til NVDB.
* Fikset en feil som gjør at bruker blir kastet ut av kontrakt og havner tilbake på kontraktsliste.
* Fikset feil i tilbakemelding ved arkivering av kontrakt.
* Sperre for å endre attributter på vegobjekter som skal slettes.
* Visning av eksisterende vegobjekter i kart oppdaterer seg når kartet flyttes.

### Datafangst 2019-6.4.10
* Forbedret dialog for å fjerne vegobjekter fra kontrakten.
* Byggeleder er nå søkbar i ny kontraktsliste.

### Datafangst 2019-6.4.8
* Det er ikke lengre nødvendig å stedfeste vegobjekter før de kan sammenkobles. Dette medfører også at automatisk sammenkobling virker uten at det er stedfestet først.
* Automatisk sammenkobling med mor i NVDB skal nå virke bedre.
* Kontraktslista har fått en visuell overhaling.
* Funksjon for å automatisk fjerne for tette punkter er forbedret.
* Det er rettet flere feil med data som ikke laster på nettleseren Edge.
* Det er gjort tekniske endringer som gjør at Datafangst startet litt raskere.

## Oktober

### Datafangst 2019-6.3.4
* Eksterne programmer (f.eks. Sinus) får ikke lenger legge til vegobjekter til
  SOSI-importer. Dette førte tidligere til at objekter fra eksterne programmer
  ble slettet sammen med SOSI-filer.
* "Ukjent feil ved stedfesting" på grunn av lenkeposisjon over 1,0 er rettet.
* Rettet en mengde mindre feil i stedfesting, spesielt i sammenheng med
  konnekteringslenker.
* Loggen viser nå objekttype på slettede objekter.

### Datafangst 2019-6.1.0
* Endringslogg (denne siden) tilgjengelig som lenke fra Datafangst.
* Endret e-postadresse for kontakt.
* Fikse feil i kart ved visning av sverm (multipoint).
* Fikse feil som gjør at kontrakts-ID og brukernavn noen ganger blir feil i applikasjonslogg.

## September

### Datafangst 2019-5.6.1
* Rettet feil hvor endring i sideposisjon eller felt ikke kunne lagres alene.
* Rettet feil hvor man ikke kunne kopiere geometrier til enkelte vegobjekttyper.
* Datafangst logger metrikker som gjør arbeidet med feilretting og prioritering av saker enklere.

## August

### Datafangst 2019-5.5.0
*	Ny implementasjn av kontraklisten. Aktiveres fra /admin, eller via https://datafangst.kantega.no/#!/contract2
*	Eksternt API forteller hvilken featureCollection som benyttes (bug via SINUS)
*	Klipping av vegobjekter støtter multiline-objekter
*	raskere og mer effektiv import av GeoJson
*	Fikset en feil der importerte objekter fra vegkart ikke lot seg eksporte til SOSI
*	Støtte for SRID 6173 og håndtering av ukjente SRIDer
*	CORS config på alle endepunkter.

### Datafangst 2019-5.4.0
*	Flyttet høyreklikk meny "kopier vegobjekt" til verktøymenyen i datafanen.
*	Ny kontraktliste: raskere og mer effektive API-endepunkter
*	Bug fiks: Lås alle fungerte ikke som forventet
*	Global administratorer vil nå lage nye kontraktgrupper uten at kontraktgruppe er satt
*	Helsesjekk-feilmeldingen flyttes til nederst i skjermen
*	Klipping av vegobjekttype som Eksperimentell funksjonalitet (via admin-fanen)
*	Bugfiks: Kopiering av en kontrakt kunne i enkelte tilfeller sette feil eier


## Juni

### Datafangst 2019.5.1.3
*	Utvidelse av roller, rettigheter og tilgangskontroll for å gjøre det mulig for firmaer å ha sine egne grupper med kontrakter og brukere.
*	Administrasjonverktøy på /admin for forvaltning av grupper
*	Automatisk fjerning av for tette punkter i geometrier -> notabene
*	Viser hvilke andre objekttyper som må velges og lagres i eksportfanen
*	Lenke til endringssett oppdatert med ny adresse
*	Mer robust caching av datacatalog, henter ny datacatalog også ved id-endringer (mindre endringer)
*	Metrikk for bruk av 3D-fanen
*	Valgte objekttyper blir automatisk valgt bort ved lagring i eksportfanen
*	ferdigsstillelsesdato og kontrakttype ble ikke med ved kopiering av kontrakt.

### Datafangst 2019.4.4.2
*	Henter datakatalogen fra Les, mer stabilt og med bedre caching
*	Nytt felt på kontrakt: Ferdigstillelsesdato
*	Nytt felt på kontrakt: Kontrakttype
*	Nye felter er filtrerbare og sorterbare i kontraktlista
*	Forbedring: innsending av objekter via API, med lik tag, resulterte i at kontrakten blir låst.

## Februar

### 2019-2 Vis tidsstempel for vegnett
* Viser sist oppdatert dato for vegnettet på stedfestingsfanen

## Januar

### 2019-1 Vaffel 3
* Gammel vaffelfane fjernes
* Ny vaffelfane tas i bruk
  * Mulighet for å låse objekttype
  * Filtrering på objekt navn / alias
  * rettet feil med ingen verdi
  * kopier til alle skal ikke kopiere til allerede registrerte
* ingen dimming av bakgrunn ved dialogbokser
* Automatisk stedfesting krever egen knapp (skjer ikke lengre automatisk ved opplasting)

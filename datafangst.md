# Datafangst - Endringslogg

## Leveranser 2020

## Februar

### Datafangst 2020-1.1.0
* Vi har gjeninnført støtten for å hente data fra Les API v2.
* Import av objektliste fra Excel-fil skal nå fungere for alle nye
  listeversjoner (v4.1-v4.8) og gamle versjoner ( fra v3.1-v4.0).
* Vegobjekter har fått beskrivende navn på sammenkoblings- og
  stedfestingsfanen.
* To nye objekttyper har fått beskrivende navn (Rørledning og Kum)
* Ved sammenkobling med mor i NVDB, vil mor nå lagres som OPPDATER og ikke som
  KORRIGER, og dermed bl.a. få nytt versjonsnummer.
* Den gamle kontraktslisten er nå helt borte fra Datafangst, og kan ikke
  lenger sjaltes inn.

## Januar

### Datafangst 2020-1.0.3
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

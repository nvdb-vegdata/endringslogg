# Datafangst - Endringslogg
## Leveranser 2019

## November

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

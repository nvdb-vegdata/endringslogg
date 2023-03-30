# Vegkart - Endringslogg

# 2023.1.8 (30.03.23)
### Endringer
* Ved systemfeil vises lenke til NVDB Status
----

# 2023.1.7 (30.03.23)
### Feilretting
* Vegkart har bedre støtte for visning av lange vegsystemreferanser
### Endringer
* Vegobjekter som ikke er innenfor kartutsnittet markeres nå med 'Utenfor kartvindu' i stedet for 'skjult i kart'

----

# 2023.1.6 (17.03.23)
### Feilretting
* Rettet kobling mot eiendomsgrenser i enkelte nettlesere

----

# 2023.1.5 (17.03.23)
### Endringer
* Eiendomsgrenser fra Kartverket kan nå vises i Vegkart

----

# 2023.1.4 (03.03.23)
### Endringer
* Vegsystemreferansen kan nå filtreres på kommune (samme vegnummer kan finnes i flere kommuner)
* Vegkart viser ny geometrikvalitetsparameter *datafangstmetode*
### Feilretting
* Gjenbruk av vegkart-url med vegsystemreferanse er igjen mulig
* Rettet krasj ved visning av kvalitetsparameter

----

# 2023.1.3 (10.02.23)
### Feilretting
* Søk basert på dato reagerer når man trykker enter eller når fokus endres fra datofelt

----

# 2023.1.2 (27.01.23)
### Endringer
* Vegkart henter kartlag med BAAT Token 
* Tydeligere symbol i tegnforklaringen for strekningsdata

----

# 2023.1.0 (16.01.23)
### Ny funksjonalitet
* Mulighet for å slå av- og på søkeområde (f.eks kommuner og vegsystemreferanser)
### Endringer
* Endret rekkefølge på farger for valg av flere vegobjekttyper
* Feilmeldingen som kommer når Vegkart krasjer inneholder nå løsningstips
### Feilrettinger
* Forbedret tolking av riksvegruter i url

----

# 2022.7.0-HOTFIX
### Feilretting
* Rettet feil ved "trykk-i-kart" for meterverdier og Vegbilder
* Forbedret håndtering av skjermede objekttyper


----


# 2022.7.0 (02.01.23)
* Nytt design på søkeresultater!
### Ny funksjonalitet
* Legg til kommunefilter ved å søke på kommunenummer; f.eks. 5001, i stedet for Trondheim
* Tegn polygon for å filtrere området! Slå opp 'Polygonsøk' i søkefeltet for å tegne polygon.
### Endringer
* Vegkart er mer forutsigbar i fargevalg for kategoriserte vegobjekter

----


# 2022.6.6-HOTFIX (08.12.22)
### Feilretting
* Rettet systemkrasj knyttet til kartlagsvelgeren
----

# 2022.6.5 (07.12.22)
### Endringer
* Forbedret tilgjengelighet for dialoger
* Forbedret tilgjengelighet for bryterknapper
----

# 2022.6.4 (07.12.22)
### Ny funksjonalitet
* Kvalitetsparametere kan nå vises, endres i innstillinger
### Endringer
* Zoom-knapp lagt til for mobilbrukere
----

# 2022.6.3 (24.10.22)
### Feilrettinger
* Gjennopprettet gråtonekartet
----


# 2022.6.2 (07.10.22) 
### Endringer
* Vegkart viser dato i versjonslogg for nye utgivelser
* Nytt skjermbilde når vegkart støtter på problemer
### Feilrettinger
* Vegkart tømmer lagrede data dersom det oppstår feil
----

# 2022.6.0 (19.09.22)
### Ny funksjonalitet
* **Innstillinger!** Brukere kan nå justere noe vegkartfunksjonalitet etter egne behov
  * Velg om man skal inkludere trafikangruppe i vegsystemreferanser.
  * Vis fullstendig geometri for mindre strekningsobjekter, eller klynge de sammen for å forbedre ytelse.

### Endringer 
* Søk- og visning av koordinater er gjort mer synlig
* Fjernet lenke til vegkart-2019

### Feilrettinger 
* Gjenopprettet 'Min posisjon' funksjonen
* Vegkart er mer forsiktig med å hente ut mange vegobjekt når områdefilter er aktivt

----

# 2022.5.6
### Feilrettinger
* Vegkart er mer robust mot vegobjekter uten geometri

----
# 2022.5.5
### Feilrettinger
* Vegkart krasjer ikke lengere når man velger 'ingen kategori'

----
# 2022.5.4
### Endringer
* Mulig å endre kommune på vegsystereferansefilter
* Enklere navigasjon mellom mor-barn objekter
* Synliggjort kobling mellom vegsystemreferansefilter og kommune
* Vegkart viser overlappende vegobjekttyper (f.eks. skiltplater og skiltpunkt)
* Måleredskapet tas med ved uttak av kartbilde

### Feilrettinger
* Tillater søk på vegsytemreferanse med strekning/dekstrekning/meter intervaller

----
# 2022.5.3
### Endringer
* Optimalisert innlasting av statisk data
### Feilrettinger
* Vegobjektklynger blir plassert i sine respektive kommuner når kommunefilter er aktivt

----
# 2022.5.2
### Endringer
* Lagre bilde av vegkart fra høyreklikk-meny
* Støtter eksport med vegobjekt-relasjoner i csv
* Mindre endringer til fargepalett for kategorisering

----
# 2022.5.1
### Feilrettinger
* Rettet kartprojeksjon for måleredskap

----
# 2022.5.0
### Ny funksjonalitet
* **Måleredskap!** Trykk på linjal-ikonet til venstre for å starte en måling.
* Vegkart tillater oppslag på koordinater (UTM33)
* Høyreklikk i kartet for å hente ut koordinatene til et punkt
* Lenke for å laste ned valgt vegnett til CSV og JSON

### Endringer
* Forbedret feilmelding ved søk på ikke-indekserte vegobjekttyper

----
# 2022.4.5
### Endringer
* "Ingen verdi" vegobjekter vises under egen kategori ved intervall-kategorisering

----
# 2022.4.4
### Endringer
* Vegobjektrelasjoner er sortert alfabetisk
* Vegkart viser antall mor- og datterobjekter
* Forbedret visning av vegobjekt-lengder i sammendrag

----
# 2022.4.3
### Feilrettinger
* Vegkart fjernet områdefilter fra URL dersom vegsystemreferanse var satt

----
# 2022.4.2
### Endringer 
* Nytt utviklerverktøy (Vite) for bedre og raskere utvikling.

----
# 2022.4.1
### Endringer
* Ny 'zoom-til' knapp på område-filter og vegsystemreferanser
* Zoom-til funksjon for vegsystemreferanser krever ikke lengere delstrekning
* Forbedret felt for endring av vegsystemreferanser

----
# 2022.4.0
### Ny funksjonalitet
* Man kan nå trykke på vegsystemreferanser for å zoome til de i kartet. (Krever strekning og delstrekning er oppgitt)

----
# 2022.3.5
### Endringer 
* Endret "Skogsbilveg" ➔ "Skogsveg"

### Feilrettinger 
* Rettet feil knyttet til overlappende vegobjekter
* Datosøk-parameter i URL dato bruker fastsatt datoformat

----
# 2022.3.4
### Endringer 
* Eksporterte sosifiler får '.sos'-filtype.

### Feilrettinger
* Visningsvalg i kategorivisning forblir ved endring i kartet.

----
# 2022.3.3
### Endringer
* Det 'Nye vegreferansesystemet' er nå omtalt som 'vegreferansesystemet'.

----
# 2022.3.2
### Endringer
* Vegnettlenker vises med meteringsretning som standard retning.
* Datobestemt oppslag kan skrus av/på.
* Vegkart URL kan inneholde datobestemt oppslag

### Feilrettinger
* Vegnett hentes med tidspunkt-parameter dersom det er satt

----
# 2022.3.1
### Ny funksjonalitet
* Vegkart tillater søk i tid! 

    Bruk feltet 'begrens søk til startdato' for å hente ut historiske data på en gitt dato.
        
### Endringer: 
Feilmeldinger logges i Loggsentralen

----
# 2022.1.1

### Ny funksjonalitet
* Vegkart benytter Content-Security-Policy header for forbedret sikkerhet

### Feilrettinger
* Støtter gammelt format for vegkart lenker

----
# 2022.1.0

### Ny funksjonalitet
* Åpner en liste med overlappende vegobjekter
* Vegkart tillater filtering og kategorisering på sensitive egenskaper dersom brukeren har tilgang
* Støtter vegobjekter uten stedfesting

### Feilrettinger
* Forbedret feilmeldinger ved ugyldige filtre
* Utløpte feilmeldinger fjernes

----
# 2021.9.1

### Endringer
* Fjernet unødvendig henting av BAAT Tokens, bruker åpne kartlag
* Optimalisert ytelse ved endring av kartutsnittet

----
# 2021.9.0

### Ny funksjonalitet
* Vegkart kan vise veger uten vegsystemreferanser
* Veglenker viser "Medium" egenskap dersom det er tilgjengnelig

----
# 2021.8.1

* Sender radius og requester parameter til Vegbilder
* Bruker oppdatert API fra Geonorge for oppslag på stedsnavn

----
# 2021.8.0

### Ny funksjonalitet
* Oppdatert direkte søk på NVDBID
* Innlogging til Vegkart (Ikke tilgang til sensitiv data, kommer i neste versjon)
* Kan nå kategorisere på negative verdier
* Kategoriserings-interval kan beskrives med usorterte tall og med absolutte verdier
* Viser sluttdato på vegobjekter hvor det er aktuelt


### Feilrettinger
* Vegobjektvindu med lang tekst gjorde at exit-knappen forsvant
* Ny versjon popup wil ikke fjerne state beskrivelse fra URL
* Forbedret filtrering på egenskaper
* Feilmeldinger forsvinner ikke dersom flere menyer er åpne
* Kategorisering popup lukkes etter valgt kategori

----
# 2021.7.0

### Ny funksjonalitet
* Linker til vegbilder
* Fjernet intervall-kategorisering for typer med definerte tallverdier


### Feilrettinger
* Fikset kombinasjon av flere områdefilter sammen med riksveg
* Viser nå verdier som har verdien 0

----
# 2021.6.0

### Feilrettinger
* Fikset fjerning av et vegreferanse-filter fjerner alle
* Fikset går ikke å velge flere kontraktsområder

----
# 2021.5.0

### Ny funksjonalitet
* Sensitive data har ny info melding
* Ikke indekserte data har ny info melding
* Lagt til bruk av data og brukerveiledning i infovindu
* Flere filtreringsmulighter: >, <, >=, <=
* Viser bare gjeldende (tidsrelevante) vegobjekter, selv om det ikke er siste versjon
* Fullstendig endringslogg flyttet. Vegkart viser bare nyeste endringslogg.

### Feilrettinger
* Fikset utvidning av objekter under kontraktsområde

# 2021.4.1

### Feilrettinger
* Søk på kontraktområde trigger ikke kommunesøk lenger

----
# 2021.4.0

### Ny funksjonalitet
* Synligjort søk på vegreferanse og NVDB-ID med alternativer
* Søk med KPS-referanse med kommune
* Vegsystemreferanse for KPS er utvidet med kommunenummer
* Ny versjon tvinger fram endringslogg ved første besøk på siden

### Feilrettinger
* Sortering og filtrering ved søk er fikset

----
# 2021.3.0

### Ny funksjonalitet
* "Kunne ikke motta vegobjekt" forsvinner etter 2.5 sekunder

### Feilrettinger
* "Kunne ikke motta vegobjekt" dukket opp selv ved riktig søk.

----
# 2021.2.0

### Ny funksjonalitet
* Valg for Gang- og sykkelveg
* Søke på NVDB-ID i Vegkart
* Egen feilmelding på ugyldige søk
* Viser startdato for vegobjekt istede for sist redigert
* Link til support på feilmelding

### Feilrettinger
* Gang- og sykkelveg er ikke inkludert under søk med bare gangveg eller sykkelveg

----
# 2020.9.0

### Ny funksjonalitet
* Splash kan styres fra url
  * /splash:main - Hovedsplash
  * /splash:policy - Personvernerklæring
  * /splash:about - Om Vegkart
  * /splash:changelog - Versjonslogg
  * /splash:none - Tvinger at splash ikke vises
  
### Feilrettinger
* Egen posisjon mer stabil
* Kategorisering med intervaller virket i noen tilfeller ikke

### Annet
* Sensitive vegobjekttyper og egenskaper markert og ikke velgbare 
* Laster mindre data om vegobjekter i vanlig søkemodus

----
# 2020.8.0

### Ny funksjonalitet
* Å skru av vegnettet skal avbryte søk

### Feilrettinger
* Feil i sortering av kategori


----
# 2020.7.1

### Ny funksjonalitet
* Kategoriserte vegobjekttyper med linjegeometri
  vil nå vise meterverdi i resultat for de ulike kategoriene.

### Feilrettinger
* Flere visningsfeil for vegsystemreferanser er fikset.
* Flere filtreringsfeil for vegobjekttyper er fikset.
* Eksport av vegobjekter vil nå ha en kolonne for hver mulige egenskap –
  dette fikser også en feil der ikke alle egenskapene ble inkluderte.
* Ved kombinering av vegobjekttype og ett eller flere områder i søk
  skal nå egengeometrien vises dersom den eksisterer, i stedet for vegnettsgeometrien.
* Vegnettsfilteret for konnektering inkluderer nå detaljerte lenker både i valg UTEN og valg MED.

### Annet
* Der det tidligere har eksistert en mulighet for
  URL-er på formen «/vegobjekter/id» oppfordres det nå til å bruke direktelenker med «/#valgt:vegobjektID:typeID» i stedet. Se [vegdata.no](https://www.vegdata.no/2020/09/23/ny-funksjon-erstattar-redirect-url-for-vegobjekter-id/) for mer informasjon.


  ----
  # 2020.6.0
  
  ### Ny funksjonalitet
  * Denne versjonen inneholder flere ytelsesforbedringer som vil forbedre brukeropplevelsen.
  * En enkel oppstartsbeskjed vil nå vises mens Vegkart laster initiell data.
  
  ### Feilrettinger
  * Flere visningsfeil for vegsystemreferanser er fikset.


  ----
# 2020.5.3

### Feilrettinger
* Brukere vil ikke lenger få applikasjons-kræsj ved åpning av resultatliste.
* Direktelenking av filtre med tekst og tall skal nå fungere som forventet.
* Statistikkpunkter for vegobjekter og vegnett skal nå kun vises for områder i søket.
* Oversveving og klikk på objekter fører ikke lenger til at uthevingen henger seg opp.


----
# 2020.5.0

### Ny funksjonalitet
* Påslått vegnett med flere ulike områdetyper i søk vil nå vise vegnettet i alle relevante områder 
i stedet for å vise vegnett kun i overlappende områder. Dette er konsekvent med måten vegobjekter har blitt vist.
* Ved søk etter riksvegruter og kontraktsområder vil det nå zoomes til disse områdene 
(selv om de ikke er synlige på kartet).
* Det er ikke lenger mulig å legge til vegobjekttyper i søk som allerede ligger i søket.

### Feilrettinger
* Klikk på mor/datter-relaterte objekter skal nå gi riktig farge i rammen til valgt vegobjekt.
* Klikk på relaterte objekter skal nå gi riktig hovedfarge i header dersom vegobjekttype er i søk.
* Det vises nå riktig områdestatistikk i resultatlisten for vegobjekttyper når det er for mange treff.
* Søk med filter eller kategorisering og område vil ikke lenger vise treff utenfor området.
* Hyperlenker fungerer nå både for egenskapsverdier og binære referanser.


----
# 2020.4.0

### Ny funksjonalitet
* Endringslogg implementert.
* Det vil nå dukke opp en kort bekreftelses-melding ved eksport av vegobjekter.
* Justeringer i vegnettfilteret:
   * Når alle valg fjernes fra en hel gruppe, vil ikke vegnettet lenger vises.
   * Tri-state-toggles rullerer nå først til «Uten», deretter «Med», og så tilbake til nøytral.
   * Det er lagt til linjer for å tydeligere markere grupperinger.
   * Valgene «Vegtrase og kjørebane» og «Gang- og sykkelveg» er fjernet, 
   og er nå automatisk inkludert i henholdsvis valgene «Vegtrase», «Kjørebane», og «Gangveg», «Sykkelveg».
* I visning av valgt vegnettlenke og valgt vegobjekter det nå lagt til grupperinger 
med tydelig markerte linjer og overskrifter.
* Det er lagt til støtte for visning av egenskapene «Måledato» og «Topologinivå».
* Knappene for «Legg til i søk» og «Zoom til» i valgt objekt-visning 
er lagt inn i headeren i stedet for informasjonsboksen.

### Feilrettinger
* Klikk på relaterte objekter skal nå gi nyeste versjon i stedet for versjon 1.
* Klikk på relaterte objekter og direktelenking av vegobjekter i Edge-nettleseren skal ikke lenger gi feilmelding.
* Valgt vegnettlenke skal nå vise korrekt retning dersom lenken er kryssystem eller sideanlegg.
* Cluster-punkter skal nå vises riktig både på kart og i valgt-boks dersom man klikker på et.


----
# 2020.3.0

### Ny funksjonalitet
* Vegobjekter lastes nå på samme måte som vegnett, 
og allerede lastede objekter vil ikke forsvinne mellom hver oppdatering.
* Vegobjekt-listen for vegobjekttypene viser nå objekt-id-er og en kortere oversikt over vegsystemreferansene, 
i stedet for alle vegsystemreferansene. Det vil si at listen nå viser samme antall objekter som nummereringen tilsier.
* Vegsystemreferanse-visningen for valgte vegobjekter 
viser kollapsede grupperinger dersom det eksisterer flere innenfor samme strekning og delstrekning.

### Feilrettinger
* Søkeboksen forsvinner ikke ved å legge til objekttyper i søket fra datakatalogen.
* Det er nå mulig å klikke på clusters igjen uten å få feilmelding.
* Appkræsj ved fjerning av kategorisering for en vegobjekttype er fikset.
* Eksportering av SOSI med områder i søket skal igjen fungere som normalt. 


----
# 2020.2.0

### Ny funksjonalitet
* Vegnettfilteret har fått mer intuitive tri-state-toggles for boolske egenskaper.
* Vegkart har en ny og tematisk 404-side.
* Visning av relaterte objekter for valgt vegobjekt er forbedret.
* Assosierte egenskaper er skjult fra visning, da relaterte objekter har samme funksjonalitet.

### Feilrettinger
* Fikset feil med endrede vegnettsparametre i direktelenking.
* Det er nå mulig å legge til flere vegsystemreferanser i søket igjen.
* Dersom en veglenke har flere kilder for retning, vil kryssystem eller sideanlegg nå ta presedens over strekning.
* Å avhuke «Adskilte løp» i vegnettfilteret gir ikke lenger feilmelding.
* Fikset flere visningsfeil på mobile enheter.


----
# 2020.1.0

### Ny funksjonalitet
* Eksporttjenesten for CSV og SOSI er skrudd på for alle miljøer.
* Det er nå mulig å direktelenke til et valgt veglenkesegment.
* Velkomstvinduet er oppdatert med egne bokser for «Om Vegkart» og «Personvernerklæring».
* Kategorisering på vegobjekttype viser nå også lasteindikatorer.

### Feilrettinger
* Resultat av søk på vegobjekttyper med linjegeometri viser nå også antall meter.
* Klikk på clusters med et underliggende vegobjekt av en annen type fører nå til korrekt oppførsel (zoom til clusterets objekter).
* Ved fjerning av hele søketeksten mens man er i Datakatalogen, gir listen deg nå hele Datakatalogen igjen.
* Fikset bug i direktelenking av vegsystemreferanse-popups.
* Kategorisering med egne intervaller er nå mulig igjen.
* Åpning av objekttyper i datakatalogen kræsjer ikke lenger applikasjonen.
* Automatiske innzoominger til valgte objekter, områder, og direktelenking til kartutsnitt fungerer nå som forventet.


----
# 2019.11.0

### Ny funksjonalitet
* Visuelle endringer i dialogboks for vegnett.
* Det er nå mulig å benytte notasjon for trafikantgruppe i søk på vegsystemreferanse.
* Det er nå mulig å velge retningsgrunnlag ved visning av vegnett.
* Farger for objekttyper og ved kategorisering er nå statiske.
* Det er nå mulig å linke til enkeltobjekter på kortformen {kontekst}/vegobjekt/{vegobjekt-id}.

### Feilrettinger
* Kategoriseringsboks utenfor skjerm på mobil.
* Vegobjektlag blir tegnet på kartet i tilfeldig rekkefølge.
* Popups for stedsnavn og vegsystemreferanse henger igjen.
* Klikk på overlappende punkt fører til feil i lasting av objekter.
* Cluster-markør henger igjen ved innzooming på cluster-elementer.
* Appkræsj ved valgt veglenke av type «detaljert» uten superstedfesting.


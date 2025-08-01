# Vegkart - Endringslogg

# 2025.06.25-328
### Feilrettinger
* Rettet feil der vegkategori ikke ble redusert på lavere zoomnive der det blir for mange objekter om man har med alle.

----

# 2025.06.11-322
### Forbedringer
* Les API-v4 er nå standard API-versjon i Vegkart.

----

# 2025.05.27-314
### Forbedringer
* Vegkart bruker nå nyeste versjon av Kartverkets karttjeneste.
* Nye kartlag er tilgjengelige i kartlagvelgeren i venstre marg.
### Feilrettinger
* Valgt kartlag vises nå i kartlagvelgeren når man er zoomet langt inn.
* Rettet feil ved valg av samme kartlag når man er zoomet langt inn.

----

----

# 2025.04.09-286
### Forbedringer
* Mer universell utforming på knapper og lenker.
### Feilrettinger
* Formatering av koordinater rettet fra EU89 til EUREF89.
* Rettet feil der "total lengde" for vegobjektspørringer ble vist eller skjult feilaktig.
* Rettet feil der SOSI-eksport av vegobjekter filtrert på område ikke fungerte.


----

# 2025.03.13-268
### Forbedringer
* Varselboksen  vil nå inneholde mer detaljert info ved driftsfeil.
* Uleste varsler markeres med rød prikk i Varselboksen.
* Infoboksen inneholder nå "Tilgjengelighetserklæring".

----

# 2025.02.26-257
### Feilrettinger
* Checkbokser og radioknapper er nå synlige under "Velg vegnett".
* Måling av areal fungerer nå med kryssende linjer.

----

# 2025.02.21-250
### Forbedringer
* Forbedringer av universell utforming i innloggingsvinduet og andre små forbedringer på verktøylinjen.
### Feilrettinger
* Tilkobling til eiendomsgrense-tjeneste oppdatert. Eindomsgrenser vises nå igjen når innstillingen er valgt.

----

# 2025.02.11-241
### Ny funksjonalitet
* Søkefeltet viser nylige søk hvis søkefeltet er tomt og brukeren har klikket i søkefeltet.
* CSV-Eksport gir mulighet for visning av datoen et objekt ble opprettet. Valget gjøres i innstillingsvinduet for eksport.
### Forbedringer
* Kontaktinformasjon vises i informasjonsvinduet.
* Forbedringer av universell utforming i innstillinger og ved eksport.
* Endret ordbruk fra "notifikasjoner" til "varslinger".
### Feilrettinger
* Vegkart vil ikke lenger gi feilmelding hvis bruker trykker pil ned i søkefeltet når søkeressultatet er tomt.
* Vegkart vil ikke lenger gi feilmelding hvis bruker trykker tab i søkefelt med tekst.

----

# 2025.01.22-228
### Feilrettinger
* Fikset feil hvor resultater fra tidligere søk ble vist i stedet for gjeldende søk.
* Fikset kritisk V4 feil som gjorde det umulig å søke opp vegobjekttyper.
* Fikset plassering av vegsystemreferansemarkør for referanser med meterverdier som inneholder "m0".

----

# 2025.01.10-221
### Ny funksjonalitet
* Det er nå mulig å søke gjennom mulige verdier for egenskapsfilter av typen tekst, tall og dato.
* Det er lagt til informasjon om bruk av * ved søk i egenskapsfilter av typen tekst. Se informasjonen ved å holde musepekeren over informasjon-ikonet ved siden av tekstfeltet.
* Valg av API-versjon i innstillinger blir nå brukt ved eksport.
### Forbedringer
* Forbedring av universell utforming på bryterknapper.
* Klikk i kartet for å vise vegsystemreferanse tar nå hensyn til søk basert på dato.
* Personvernerklæringen er oppdatert.
* Ubrukte lenker på informasjonssiden er fjernet.
* Informasjonssiden viser nå oppdateringsdato for datagrunnlag.
* Tittelen på instillingen for API-versjon er endret fra "Velg API-versjon (lagres ikke på tvers av økter)" til "API-versjon (kun relevant for testing)".
### Feilrettinger
Vegkart klarer nå å håndtere ugyldige kvalitetsverdier. Slike verdier vises nå som "Ugyldig verdi".

----

# 2024.12.04-197
### Ny funksjonalitet
* Brukere av Vegkart på mobil og nettbrett får spørsmål om de ønsker å forlate programmet.
### Forbedringer 
* Filter for vegobjekter har fått et visuelt løft.
### Feilrettinger
* Henting av segmentert vegnett med store kartutsnitt, feiler ikke lenger (gjelder API-v3).

----

# 2024.11.27-190
### Endringer
* Eksport av vegobjekter med sensitive data, fungerer nå for brukere utenfor vegvesenet sitt interne nett.
* Filnavn ved eksport av vegobjekter har fått ny navngiving.
* Progresjon ved eksport av vegobjekter vises ikke lenger av nettleseren.
* I dennne sammenheng har varselet "Nedlasting startet ...", blitt endret til "Nedlasting pågår" og vises nå helt til nedlastingen er ferdig.

----

# 2024.11.25-184
### Endringer
* Vegnett for API v4 hentes raskere enn før.
* Nettsiden lastes ikke lenger inn på nytt ved bytte av API-versjon.
* Valgt veglenkesekvens lagres i url
* Søk på riksvegruter med EnumID eller rute-navn

----

# 2024.11.06-172
### Ny funksjonalitet
* Innstillinger: Det er mulig å velge API-versjon (v3 eller v4), men standard API-versjon er fortsatt v3.
* Feilmeldingsikon for advarsel og info er forbedret.
* Man får tilbakemelding/info dersom det ikke fins vegsystemreferanser i nærheten av søk.
* Forbedret tabellvisning som viser vegobjekter per fylke.
* Tabellvisning vises kun når man er zoomer ut i API-v4.
* Tabellvisningen i API-v4 viser oppsummering for hele Norge, tabellen fra API-v3 viser oppsumering over kartutsnittet.

----
# 2024.10.30-162
### Feilrettinger
* Rettet feil ved åpning av høyreklikksmenyen.

# 2024.10.18-2
### Feilrettinger
  
# 2024.10.10-151
### Endringer
* Areal vises i km² fra 0.1 km² og oppover.
* Tittel ved mus over måleknappene viser nå riktig tekst.
* Vegreferanseboks åpnes ikke lenger i løpet av måling.
* Nytt design og innhold på informasjonsboks.

# 2024.10.01-143
### Feilrettinger
* Lenker med mange vegobjekttyper tolkes nå riktig.

# 2024.09.25-134
### Ny funksjonalitet
* Søkefeltet støtter nå søk på WGS84 koordinater, både nord/øst og øst/nord.

### Forbedringer
* Migrert til ny karttjeneste for henting av topologiske og gråtone kart.

### Feilrettinger
* Farger blir ikke lenger like når søk i vegkart åpnes fra lenke.

# 2024.09.11-123
### Ny funksjonalitet
* Det er nå mulig å utføre UTM33-koordinatsøk både i lon/lat- og lat/lon-format.

### Endringer
* Standard bakgrunnskart endret fra Norgeskart til Standard. Endret rekkefølgen i kartvalg for bedre brukervennlighet.
* Lagt til informasjonsknapp for absoluttverdier i kategoriseringspanelet.
* Diverse språk- og tilgjengelighetsforbedringer.
  
# 2024.08.15-107
### Ny funksjonalitet
* Implementert funksjonalitet som lar brukeren velge mellom fire ulike visningsalternativer for tillatte verdier i SOSI-filer.
* Brukeren kan nå slå av og på disse alternativene i innstillingene.

# 2024.08.07-3
### Feilrettinger
* Forbedret konvertering av vegnett-applikasjonstilstand til URL.

# 2024.07.09-80
### Feilrettinger
* Rettet feil der filtre ikke ble tolket korrekt når URL ble delt.
  
# 2024.06.03-71
### Endringer
* Endret behandling av URL-er (merk: gamle bokmerker og lenker fungerer ikke lenger).
* Lagt til Traktorveg, Sti og Annet i kategorivalgene.

# 2024.04.24-60
### Endringer
* Forbedret fargekontrast og nyanseforskjeller mellom alle kategorier for å øke synligheten og skille tydeligere mellom dem.

# 2024.04.11-57
### Endringer
* Lagt til hvit bakgrunn for koordinatvisning i nedre høyre hjørne for forbedret synlighet.

# 2024.04.04-51
### Endringer
* Når retningsgrunnlaget er satt til Veglenkes retning, vises nå alle lenker i grått og med pil, uavhengig av andre faktorer.
* Når retningsgrunnlaget er satt til Metreringsretning vises kun metrerte veger med pil. Veger metrert i samme retning som lenkeretning vises i grått, mens der metreringsretning er motsatt lenkeretning vises disse i rødt. Umetrerte veglenker vises uten pil.

# 2024.03.18-46 (18.03.24)
### Feilrettinger
* Rettet feil der vegnettet ble tegnet oppå objektene.

### Ny funksjonalitet
* Projeksjon for CSV/SOSI eksport kan nå velges i innstillinger. (UTM32-UTM35, UTM33 er standard)
----

# 2023.02.27-38 (27.02.24)
### Endringer
* Oppdatert styling for fortau, trapper og gangfelt.
----

# 2024.01.16 (16.01.24)
### Endringer
* Oppdatert "Be om tilgang"-lenken under pålogging for korrekt informasjon om tilgang.
----

# 2023.12.27 (11.01.24)
### Feilrettinger
* Rettet feil der assosiert tunnelovervåking feilaktig ble vist som en egenskap.

----

# 2023.12.21 (11.01.24)
### Feilrettinger
* Rettet feil der kategorisering ga varierende antall objekter for samme kategori med forskjellige operatorer.

----

# 2023.1.28 (20.12.23)
### Feilrettinger
* Rettet feil der endring av URL krevde to trykk på "Enter"-knappen
* Rettet feil der kartlag ikke ble bevart når vegkart åpnes fra URL

----

# 2023.1.25 (15.11.23)
### Feilrettinger
* Rettet feil der flere objekter åpnet seg ved overlappende posisjoner.

----

# 2023.1.24 (06.11.23)
### Endringer
* Vegkart benytter nå Kartverkets nyeste og mest oppdaterte bakgrunnskart.

----

# 2023.1.23 (31.10.23)
### Endringer
* Dersom punktobjekter ligger tett, kan man velge å vise geometri som separate punkter, i stedet for punktgrupper. 
* Valget gjøres under "Innstillinger".

----



# 2023.1.22 (25.10.23)
### Feilrettinger
* Rettet feil der områdefilter dupliseres ved lagring og åpning av lenker til Vegkart.
* Rettet feil der valgt objekt med langt typenavn håndteres dårlig.

----
  
# 2023.1.21 (02.10.23)
### Feilrettinger
* Valgte objekter blir nå korrekt merket med hvitt.

----

# 2023.1.20 (20.09.23)
### Endringer
* Du må nå bekrefte endrede innstillinger for at de skal tre i kraft i innstillingsdialogen.

----

# 2023.1.19 (08.09.23)
### Feilrettinger
* Rettet feil der Vegkart krasjer ved interaksjon med vegobjekter uten geometri.
* Rettet feil der flateobjekt tar fokus og gjør det umulig å velge andre objekter.
* Rettet feil der søk på Vegsystemreferanse med 3 siffer i kommunenummer feiler.

----

# 2023.1.18 (28.08.23)
### Endringer
* Viser nå målestokkstall i kartet.

### Feilrettinger
* Rettet feil der Vegkart krasjer ved klikk på enkelte veglenker.
* Rettet feil der deler av URL forsvinner når url er limt inn.

----

# 2023.1.17-HOTFIX (18.08.23)
### Feilrettinger
* Nå vises egengeometri for objektene igjen (hvis den finnes).

----

# 2023.1.17 (15.08.23)
### Feilrettinger
* Rettet feil der sluttnode ikke vises på veglenke.
* Rettet feil der feltoversikt ikke vises for veglenker på detaljnivå “Vegtrasé” eller “Vegtrasé og kjørebane”.

----

# 2023.1.16 (15.08.23)
### Endringer
* Innstillinger slettes ikke lenger når applikasjonsfeil oppstår.

### Feilrettinger
* Rettet feil ved visning av kontraktsobjekt der navnet inneholder komma.

----

# 2023.1.15 (15.08.23)
### Endringer
* Bruker nå det detaljerte kartet på et lavere zoomnivå.
* Det finnes nå en spesifikk URL for veglenke, /veglenke:id:lenke:segment
* Viser egengeometri for vegobjekter dersom den er tilgjengelig.

### Feilrettinger
* Rettet feil hvor informasjon fra tidligere valgt vegsegment henger igjen i visning.

----

----

# 2023.1.14 (07.07.23)
### Feilrettinger
* Viser kvalitetsinformasjon som egen del av objektinformasjonen.

----

# 2023.1.13 (07.07.23)
### Endringer
* Metadata er nå skjult som standard. Klikk på innstillinger for å endre.

### Feilrettinger
* Vegobjekt uten vegsystemreferanse vises uten feilmelding.

----

# 2023.1.12 (03.07.23)
### Endringer
* Endret symbolisering av Gangfelt, Gangvei, Fortau, Trapp og Konnektering ved bruk av "Velg vegnett".
* Feltoversikt er nå synlig for Kjørebane og Kjørefelt.

----

# 2023.1.11 (12.06.23)
### Endringer
* Kvalitetsinformasjon er nå synlig som standard. Klikk på innstillinger for å endre.
* Standard bakgrunnskart er nå kalt Norgeskart.

### Feilrettinger
* Det er nå mulig å logge inn igjen.
* Rettet feil hvor lenker til søk i Vegkart med vegsystemreferanse uten strekning (f.eks. E39) forårsaket feil.

----

# 2023.1.10 (12.06.23)
### Endringer
* Vegnettslenker viser nå *feltoversikt* i sin info-boks. Feltoversikten vises alltid med utangspunkt i lenkeretningen.

----

# 2023.1.9 (02.05.23)
### Ny funksjonalitet
* **Nytt måleredskap!** Vegkart kan nå måle areal og omkrets. Verktøyet finner du under linjal-ikonet.
* Rapporter feil på vegobjekt og langs veg ved hjelp av ny lenke til Fiksvegdata. 
Bruk utropstegnknappen i vegobjekt og i vegsystemreferansevinduet.

### Endringer
* "Zoom til" funksjonen på vegsystemreferanse viser nå hele den valgte strekningen. 
Tidligere har den kun vist det første punktet.

### Feilrettinger
* Rettet feil hvor det vises `undefined` under noen egenskapsverdier. Feilen oppsto på egenskapsverdier med oppgitt enhet, men hvor enheten mangler kortform.

----

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


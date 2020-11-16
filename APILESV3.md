# NVDB API LES V3 - Endringslogg og implementasjonsplan
Dette er endringer vi har gjort i hver sprint som er synlige for konsumenter av V3.

Oversikt over hvilken installasjon som er installert i hvilket miljø:
* UTV - https://nvdbapiles-v3.utv.atlas.vegvesen.no/status/versjoner
* STM - https://nvdbapiles-v3-stm.utv.atlas.vegvesen.no/status/versjoner
* ATM - https://nvdbapiles-v3.test.atlas.vegvesen.no/status/versjoner
* PROD - https://nvdbapiles-v3.atlas.vegvesen.no/status/versjoner

# Fullførte versjoner


### 2020.19.0 (10.11.2020)
* Forbedring av ruteberegning

### 2020.17.0 (15.10.2020)
* Forbedring av ruteberegning

### 2020.16.0 (15.10.2020)
* Forbedring av ruteberegning
* Vegsystemreferanse ble ikke slått sammen for segmenterte vegobjekter

### 2020.15.0 (22.09.2020)
* Forbedring av ruteberegning

### 2020.14.0 (01.09.2020)
* Forbedre tilfeller der `/veg` veksler mellom flere responser ved re-lastinger.
* Fikset at `/vegobjekter/X?veglenkesekvens=Y` ikke returnerte objekter dersom vegobjekt var stedfestet mot veglenkeretning.
* Respons fra ruteberegning endret til [å inneholde et statusfelt](https://github.com/nvdb-vegdata/nvdb-api-client/commit/2932d0b9c28eb1e182b028dbeaab87ed3c9765a3#diff-f457b5f7152c9026cd604bc51abf9eab)
* `/omrader/kontraktsomrader` og `/omrader/riksvegruter` inkluderer kommuner og fylker på returnerte objekter.
* Fikset at `/veglenkesekvenser/segmentert/X` returnerte objekt dersom det var kun ett segment.

### 2020.13.0 (18.08.2020)
* Mulig å ekskludere assosiasjon- og stedfestingsegenskap. (`?inkluder_egenskaper=alle|basis|geometri|assosiasjon|stedfesting`)
* Ta imot veglenketype som liste i vegnettssøk. (`?veglenketype=hoved,detaljert`)
* Fjern støtte for responsrevisjon 0
* `objekt.geometri` vil alltid være egengeometri dersom objektet har dette.

### 2020.12.0 (25.06.2020)
* Intern begrensning på antallet samtidige forespørsler som behandles. Klienter kan få 503 `Behandlingen av forespørselen kunne ikke fullføres innen rimelig tid.`

### 2020.11.0 (23.06.2020)
* Fikset at noen objekter manglet segmentert geometri

### 2020.10.0 (16.06.2020)
* Fikset manglende geometrifelt i lokasjon
* Fikset vegsystemreferanse mangler i lokasjonsobjekt for vegobjekter-søk

### 2020.9.0 (02.06.2020)
* Fikset søk på vegobjekt med dybde>=2 gir ukomplette relasjoner

### 2020.7.0 (17.05.2020)
* Fikset manglende vegsegmenter ved inkludering av vegsegmenter

### 2020.6.0 (17.03.2020)
* Fikset feil ved summering av strekningslengde med egenskapsfilter

### 2020.5.0 (05.03.2020)
* Overgang fra NN 1954 til NN2000

### 2020.3.0 (11.02.2020)
* `Geometri.kvalitet.medium_nvdb` lagt til for å gi ut verdi lagres i NVDB

### 2020.2.0 (24.01.2020)
* Vekslende svar fra `/posisjon` for nærliggende lenker
* Verdier i `Geometri.kvalitet` har ikke rett verdi.

### 2020.1.0 (14.01.2020)
* `X-Client`-`User-Agent`-kombinasjoner vi mener ikke er gode nok vil bli blokkert
* Bugfikser for /veg og /posisjon

### 2019.17.0 (20.12.20219)
* Det gjøres ikke lengre snuing av segmenter der Strekning(916) er stedfestet mot lenkeretningen. Se https://api.vegdata.no/v3/retning.html

### 2019.16.0 (15.11.2019)
* /vegnett/elementer fjernet

### 2019.15.0 (23.10.2019)
* Ikke feil med HTTP 500 når det er feil i egenskapsfilter

### 2019.14.0 (11.10.2019)
* Meterverdier rundes av til tre desimaler. For geometri på UTM33-format er det også tre desimaler, WGS84-geometri rundes til åtte desimaler.

### 2019.13.0 (08.10.2019)
* Fikset duplikater ved paginering av transaksjoner

### 2019.12.0 (16.09.2019)
* Fikset at trafikantgruppe ble ignorert i vegsystemreferanse-filter
* Antall 0 ved statistikkspørring med egenskap=area(x)
* Primitivt endepunkt for finne rute mellom to veglenkesekvensposisjoner/koorinater 

### 2019.11.0 (3.9.2019)
* Response fra `/veg` har riktig kommune (var alltid 0)
* Stedfesting for `Svingerestriksjon` er komplett representert
* [Responsrevisjon 1](https://api.vegdata.no/v3/responsrevisjoner.html)
* Første versjon av [referanseklient i java](https://github.com/nvdb-vegdata/nvdb-api-client/tree/V3) releaset. 

### 2019.10.0 (8.8.2019)
* Stedfestingsegenskaper har fått nytt felt: `stedfestingstype`: `Punkt|Linje|Sving`

### Sprint 22
* `transaksjon.tidspunkt` hadde format `yyyy-MM-dd HH:mm:ss` - dette er endret til ISO-8601.
* `metadata.sidestørrelse` er lagt til i responsen for å signalisere faktisk sidestørrelse ved paginering.

### Sprint 20
* Avansert spørring virker igjen

### Sprint 21
* `/status` gir ut informasjon om hva NVDBIND gjør.
* Retning på stedfestingen av `Strekning`, `Kryssystem` og `Sideanlegg` gis ut i segmentert vegnett.
* `/vegobjekter/X`, `/vegobjekter/X/statistikk`, og `/vegnett/veglenkesekvenser/segmentert` støtter parametret `?tidspunkt`. Dette filtrer ut de vegobjektene/vegnettsegmentene som var åpne på det gitte tidspunkt. Dersom segmentering er aktivert for vegobjekter vil vegobjektenes geometri- og `lokasjons`-egenskap ha innhold basert på de segmentene for objektet som var aktiv på dette tidspunktet.
* Det er mulig å hente ut vegobjekter som er oppdatert etter et gitt tidspunkt med `/vegobjekter/X?endret_etter={ISO-tidspunkt}`. Som i V2 er denne litt sensitiv, så det er ikke nødvendigvis synlig forskjell på et objekt selv om det dukker opp med denne filtreringen.
* `/vegobjekter/X`, `/vegobjekter/X/statistikk`, og `/vegnett/veglenkesekvenser/segmentert` har fått flere muligheter for å filtrere på egenskaper fra vegsystemreferansen. Se `arm`, `veglenketype`, `adskiltelop`, `typeveg`, `detaljniva`, `kryssystem`, `sideanlegg`, `trafikantgruppe` i [dokumentasjonen](https://nvdbapilesv3.docs.apiary.io/#reference/0/vegobjekter-av-type/list-vegobjekter)

#### Responsendringer
* [kvalitet.synlighet endret til synbarhet](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c2ca89ed3d4e1bdce5a67af3101c1d265b05b672#diff-b0c26f22455c2a62f30cb6a568c7f955L15)
* [stedfesting.feltoversikt endret til kjørefelt](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c2ca89ed3d4e1bdce5a67af3101c1d265b05b672#diff-b5f334c16ceccbb3987030524a0e828cL50)
* [veglenkesekvens.måleMetode,måleDato endret til målemetode,måledato]()
* Porttilkobling på veglenkesekvens/node: [portid endret til portnummer](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c2ca89ed3d4e1bdce5a67af3101c1d265b05b672#diff-6f9ed187bf7b5d1c57ca059ef52bc580L13), [netelementid endret til nodeid om port peker på node](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c2ca89ed3d4e1bdce5a67af3101c1d265b05b672#diff-6f9ed187bf7b5d1c57ca059ef52bc580L14), [netelementid endret til veglenkesekvensid om port peker på node](https://github.com/nvdb-vegdata/nvdb-api-client/commit/051b9892b84525016afa0e6c26c7ed6fbf186920#diff-b0c26f22455c2a62f30cb6a568c7f955R22) [netelementtype og netelementtype_tekst fjernet](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c2ca89ed3d4e1bdce5a67af3101c1d265b05b672#diff-6f9ed187bf7b5d1c57ca059ef52bc580L15)

### Sprint 19
* /omrader/regioner, /omrader/vegavdelinger er fjernet
* Fylker og kommuner hentes fra objekttype 945 og 946
* ?segmentering=true med områdefilter virker igjen.
* /veg virker igjen

### Sprint 18.1
* Felt på vegobjekttype for å vise at det skal kun eksistere én versjon av et vegobjekt.

#### Responsendringer
* [vegobjekttype.en_versjon](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c4f3db325e96fca97c6d0653c0bb4ae811c1364f#diff-27353fb10dea09a01ca0fd1f557abb65)

### Sprint 18
* Autentisering for tilgang til sensitive datatyper og egenskaper. (https://apilesv3.utv.atlas.vegvesen.no, kun personlige brukere)
* Vegkart støtter å filtrere på vegsystemreferanse

### Sprint 17
* Funksjonalitet for autentisering og eksponering av sensitive vegobjekttyper og egenskaper
* Filtrere usegmentert vegnett basert på vegreferanse
* srid=32633 erstattet med 6173

#### Responsendringer
* [vegobjekttype.sensitiv](https://github.com/nvdb-vegdata/nvdb-api-client/commit/23cbd8b41db66486fafa7d227e262d2c2e6476fa#diff-27353fb10dea09a01ca0fd1f557abb65)

### Sprint 16 
* Filtering av vegobjekter med vegsystemreferanse
* Segmenter inkluderer kontraktsområde og riksvegrute
* Meterverdier for objekters vegsystemreferanse var ikke tilpasset objektets stedfesting
* Maks sidestørrelse ved paginering er økt til 50 000

#### Responsendringer
* [feltoversikt](https://github.com/nvdb-vegdata/nvdb-api-client/pull/39/commits/88c7ff0c267834a4b5254fb90e1cab80d1981b06#diff-6f9ed187bf7b5d1c57ca059ef52bc580)
* [kontraktsområder og riksvegruter](https://github.com/nvdb-vegdata/nvdb-api-client/pull/40/commits/9b360b427edef8f219608f2f987eb48ab0ed6c78#diff-b0d53d0a9e6e6803388e704a4fb2ced9)
* [typeVeg_sosi for segmenter](https://github.com/nvdb-vegdata/nvdb-api-client/commit/dd8574c9aa300bedb75a6190c16cdf70faf691aa)

### Sprint 15
* Endepunktet `/posisjon` virker med vegsystemreferanse.
* Filtrering på vegsystemreferanse implementert.
* Vegkart: Klikk i kart viser vegsystemreferanse i punkt.
* Vegkart: Vegsystemreferanse vises i treffliste. 

#### Responsendringer
* [Veglenkesekvenser](https://github.com/nvdb-vegdata/nvdb-api-client/commit/0835b98deac4bdc39c16fc0e57ba8130f4c3525e#diff-6f9ed187bf7b5d1c57ca059ef52bc580) 
* [Segmentert vegnett](https://github.com/nvdb-vegdata/nvdb-api-client/compare/25a40c9d461df1cb4be3bcee1603915865a08c1f...bc4cedfbf160fd01054963a317bef630eb023e28#diff-aa744b112391254b8ac2f40dab92f673)
* [Vegobjekter](https://github.com/nvdb-vegdata/nvdb-api-client/compare/5d0d1612909b18fd933f8739eaaf3adb933a2d8d...6bf51df#diff-b5f334c16ceccbb3987030524a0e828c)
* [Statistikk](https://github.com/nvdb-vegdata/nvdb-api-client/compare/5d0d1612909b18fd933f8739eaaf3adb933a2d8d...6bf51df#diff-0532efd44a5bb56170adcd5e71e91b59) (`strekningslengde` er endret til `lengde`)

### Sprint 14
* Gir ut segmentert vegnett
* Gir ut segmenter og vegsystemreferanser for vegobjekter
* Vegkart-versjon som bruker Les V3

#### Responsendringer
* [Veglenkesekvenser](https://github.com/nvdb-vegdata/nvdb-api-client/commit/8a2909537090c42caabf4d74336cce7de957af20) 
* [Segmentert vegnett](https://github.com/nvdb-vegdata/nvdb-api-client/commit/286ca561abb46f33d20218e17f4d0d96e9032e8c)
* [Vegobjekter](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c51c9a2d054b13b13c36fa955e6f8af63f27cef5)

For oversikt over mulige verdier for feltene i responsen se [API-dokumentasjonen](https://nvdbapilesv3.docs.apiary.io)

### Sprint 13
* Segmentering av vegnett og vegobjekter
* Antallet desimaler i koordinater er begrenset til åtte.

### Sprint 12
* Segmentering av vegnett og vegobjekter

### Sprint 11
* /vegobjekter/#?id=x,y,z og /vegnett/...?id=x,y,z er endret til `?ider=x,y,z`
* Gir endelig ut struktur, liste, liste med struktur, assosiasjon og liste med assosiasjoner.
* Takler `/` i navn for kontraktsområde og riksvegrute. 
* egenskapen `styringsparametere` er fjernet fra vegobjekttyper og dems egenskaper. Mange av feltene under vegobjekttypens styringsparametre kommer fra dets lokasjonsegenskap. Alle verdiene vil bli listet ut der de kommer fra.
* Datakatalogverdier som ikke gis ut fordi de skal ut av datakatalogen eller alle instanser mangler verdi:
   * vegobjekttype.,tillattverdi.illustrationid
   * featuretype.filterOn
   * featuretype.coverage (alle instanser har verdi `1`)
   * featurettype.context.description
   * featurettype.context.indexon
   * egenskapstype.no
   * lokasjonsegenskap.suppleringslengde (UPDATE_LENGTH)
   * lokasjonsegenskap.ajourhold_i (UPDATE_I)
   * lokasjonsegenskap.retning_relevant (DIR)
   * lokasjonsegenskap.flyttbar (transferable_between_levels)
   * lokasjonsegenskap.høyde (HEIGHT_LEVEL) / .høyde_relevant (heightlevel)
* Egenskaper som har endret navn:
   * ajourhold_splitt -> vegnettsajourhold_splitt
   * dekningsgrad -> overlappsautomatikk
   * overlapp -> overlapp_ok
   * sektype2_Ok -> konnekteringslenke_ok

### Sprint 10 
* Gir ut Turnextent
* Segmentering påbegynt
* /vegobjekter/#?id=x,y,z

### Sprint 9. 4. september
* Lokasjons- og assosiasjonsegenskapene for et vegobjekt blir gitt ut som egenskaper i tillegg til den forenklede representasjonen vi allerede har.
* egenskap.datatype_tekst er fjernet, egenskap.datatype har verdien datatype_tekst hadde.
* egenskap.viktighet_tekst fjernet, egenskap.viktighet har verdien egenskap.viktighet_tekst hadde.
* transaksjonsobjekt.transaksjonstype_tekst fjernet, transaksjonsobjekt.transaksjonstype har verdien transaksjonstype_tekst hadde.
* veglenke.topologinivå_tekst fjernet, veglenke.topologinivå har verdien veglenke.topologinivå_tekst hadde.
* veglenke.detaljnivå har tekstverdier
* veglenke.typeVeg har tekstverdier
* veglenke.typeVeg_sosi har tekstverdier
* veglenke.målemetode har tekstverdier
* lenkesekvens, lenke er endret til veglenkesekvens og veglenke.
* stedfesting.felt er endret fra tekst til liste av tekst. (feltet kunne før være `"1#2"`, dette er nå `["1", "2"]`)
* Felter lagt til i datakatalogen: 
    * Assosiasjonsegenskaper med alle sine egenskaper. (grunnverdier + affiliation, feature_type_id, inside_parent, start_date, end_date, association_requirement, association_requirement_comment)
    * baseegenskaper: sosinavn, caption, readOnly, complementaryattrtypeid, plainviewreftext, heightreftext, reqheightref, reqaccuracyplan, reqaccuracyheight, referencesosi,  referencegeometry, conditionalRequiremens.
    * Blobegenskap.blobformat
    * featuretype.state, category, simpleversionon, coverage, additionalinfo
    * Tekst. dato.-, tidegenskap.format
    * Integer., Real.complementarysign 
    * Enum.isDefault
    * Localtional.movable, insideparent
    * PrimitiveAttribute.isdirectionsensitive, isextentsensitive
    * Spatial.insideparent

Navn i apiet:
* affiliation - tilknytning
* inside_parent - innenfor_mor
* association_requirement,
* association_requirement_comment
* sosinavn - sosinavn
* caption - ledetekst
* readOnly - skrivebeskyttet
* complementaryattrtypeid - komplementær_egenskapstype
* plainviewreftext - grunnrissreferanse
* heightreftext - høydereferanse
* reqheightref - høydereferanse_tall (tror dette er href, vil helst ikke brukt href siden det har annen mening i api)
* reqaccuracyplan - nøyaktighetskrav_grunnriss
* reqaccuracyheight - nøyaktighetskrav_høyde
* referencesosi - sosi_referanse
* referencegeometry - referansegeometri_tilstrekkelig
* conditionalRequirements - tilleggskrav
* blobformat - mediatype
* state - status (Mangler tekstverdier for denne)
* category - CATEGORY (Mangler tekstverdier for denne) Burde det vi allerede kaller kategorier kalles grupper?
* simpleversionon - simpleversionon (Trenger navn)
* coverage - dekning
* additionalinfo - tilleggsinformasjon
* format - feltmønster
* complementarysign - fortegnsendring_snu
* isDefault - standardverdi
* movable - flyttbar
* isdirectionsensitive - ajourhold_snu
* isextentsensitive - lengdeavhengig_verdi

### Sprint 8. 14. august
* Støtte spørring med polygon
* /vegobjekter/{id} oppe med reelle data. Kontraktsområde har ikke historikk. Søkeparametre for vegsystemreferanse og avanserte spørringer virker ikke.
* Begrepsendring for vegnettet. Referanselenk -> Lenkesekvens, Dellenke -> Lenke
* I datakatalogen har vegobjekttypenes kategorier fått informasjon om primærkategori.
* Lenker har fått `måledato`, `målemetode`, `typeVeg` og `detaljnivå`
* Egenskaper som ligger inni geometrien blir eksponert.

### Sprint 7. 26. juni
* Vegnettsgeometri og egengeomtri normaliseres til `LINESTRING`(Gis ut som `MULTILINESTRING` siden typen i NVDB er dette)
* Forbedringer av spørreparametre for noder
* Gi ut definisjonen av objekters geometriattributt i datakatalog. : vegobjekttype.stedfesting er lagt til denne gir informasjon om stedfestingen for vegobjekttypen. Dette feltet kan være et listeattributt som inneholder selve stedfestingsattributtet.
* `attributtype.liste` - felt er fjernet. `attributetype.type` er lagt til. Denne vil inneholde beskrive hvilken type attributtypen er, eks `Liste`.
* `Datatype` Liste, id 38 er lagt til for Listeattributter.
* vegobjekttype.relasjonstyper er endret slik at det vil komme et liste-nivå dersom den aktuelle assosiasjonen er en liste.

### Sprint 6. 5. juni
* Definisjon av liste- og strukturattributter i datakatalog.

### Sprint 5. 15. mai
* Innslag i `tillatte_verdier` har fått feltet `navn` endret til `verdi` Dersom det er et tall-enum er dette ikke lengre en streng.
* For et attributt på en vegobjekttype i datakatalogen manglet kortnavn og attributtypekategori. Dette er lagt til.
* Alle attributtyper listes ut på `/vegobjekttyper/attributtypekategorier`
* Geometriattributtyper manglet dimensjon. Dette er lagt til.
* Dersom et objekt er slettet fra NVDB gir apiet status 410 i stedet for 404.

### Sprint 4. 24. april
* Indeksering og eksponering av objektert binær-egenskaper
* Eksponering av NVDB transaksjonslogg
* Indekserer lenker der alle lenker har sluttdato

### Sprint 3. 3. april
* Parametre for filtrering av usegmenter vegnett
* Innføre segmentert vegnett (likt det i V2)

### Sprint 2. 6. mars
* Indeksering og endepunkt for usegmentert vegnett

### Sprint 1. 13. februar
* Dokumentasjon og spesifisering av endepunkter og responser
* Endepunker med blanding av reelle og dummy-data.
## Grov forventet fremdrift

### Fremtid
* Gi ut informasjon om objekter som er oppdatert på grunn av endringer i vegsystemreferanse, kontraktsområde, eller riksvegrute.
* Alle endepunkter støtter POST der det er hensiksmessig
* Mulighet for å finne rute mellom to punkter på vegnettet.
* GeoJSON-respons
* Respons for vegobjekt-egenskaper reduseres til kun data, ikke felter for datatype, egenskapstypenavn.

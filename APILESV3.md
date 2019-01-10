# NVDB API LES V3 - Endringslogg og implementasjonsplan
Dette er endringer vi har gjort i hver sprint som er synlige for konsumenter av V3.

# Fullførte sprinter
### Sprint 1. 13. februar
* Dokumentasjon og spesifisering av endepunkter og responser
* Endepunker med blanding av reelle og dummy-data.

### Sprint 2. 6. mars
* Indeksering og endepunkt for usegmentert vegnett

### Sprint 3. 3. april
* Parametre for filtrering av usegmenter vegnett
* Innføre segmentert vegnett (likt det i V2)

### Sprint 4. 24. april
* Indeksering og eksponering av objektert binær-egenskaper
* Eksponering av NVDB transaksjonslogg
* Indekserer lenker der alle lenker har sluttdato

### Sprint 5. 15. mai
* Innslag i `tillatte_verdier` har fått feltet `navn` endret til `verdi` Dersom det er et tall-enum er dette ikke lengre en streng.
* For et attributt på en vegobjekttype i datakatalogen manglet kortnavn og attributtypekategori. Dette er lagt til.
* Alle attributtyper listes ut på `/vegobjekttyper/attributtypekategorier`
* Geometriattributtyper manglet dimensjon. Dette er lagt til.
* Dersom et objekt er slettet fra NVDB gir apiet status 410 i stedet for 404.

### Sprint 6. 5. juni
* Definisjon av liste- og strukturattributter i datakatalog.

### Sprint 7. 26. juni
* Vegnettsgeometri og egengeomtri normaliseres til `LINESTRING`(Gis ut som `MULTILINESTRING` siden typen i NVDB er dette)
* Forbedringer av spørreparametre for noder
* Gi ut definisjonen av objekters geometriattributt i datakatalog. : vegobjekttype.stedfesting er lagt til denne gir informasjon om stedfestingen for vegobjekttypen. Dette feltet kan være et listeattributt som inneholder selve stedfestingsattributtet.
* `attributtype.liste` - felt er fjernet. `attributetype.type` er lagt til. Denne vil inneholde beskrive hvilken type attributtypen er, eks `Liste`.
* `Datatype` Liste, id 38 er lagt til for Listeattributter.
* vegobjekttype.relasjonstyper er endret slik at det vil komme et liste-nivå dersom den aktuelle assosiasjonen er en liste.

### Sprint 8. 14. august
* Støtte spørring med polygon
* /vegobjekter/{id} oppe med reelle data. Kontraktsområde har ikke historikk. Søkeparametre for vegsystemreferanse og avanserte spørringer virker ikke.
* Begrepsendring for vegnettet. Referanselenk -> Lenkesekvens, Dellenke -> Lenke
* I datakatalogen har vegobjekttypenes kategorier fått informasjon om primærkategori.
* Lenker har fått `måledato`, `målemetode`, `typeVeg` og `detaljnivå`
* Egenskaper som ligger inni geometrien blir eksponert.

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

### Sprint 10 
* Gir ut Turnextent
* Segmentering påbegynt
* /vegobjekter/#?id=x,y,z

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

### Sprint 11
* Segmentering av vegnett og vegobjekter

### Sprint 12
* Segmentering av vegnett og vegobjekter
* Antallet desimaler i koordinater er begrenset til åtte.

### Sprint 14
* Gir ut segmentert vegnett
* Gir ut segmenter og vegsystemreferanser for vegobjekter
* Vegkart-versjon som bruker Les V3

#### Responsendringer
* [Veglenkesekvenser](https://github.com/nvdb-vegdata/nvdb-api-client/commit/8a2909537090c42caabf4d74336cce7de957af20) 
* [Segmentert vegnett](https://github.com/nvdb-vegdata/nvdb-api-client/commit/286ca561abb46f33d20218e17f4d0d96e9032e8c)
* [Vegobjekter](https://github.com/nvdb-vegdata/nvdb-api-client/commit/c51c9a2d054b13b13c36fa955e6f8af63f27cef5)

For oversikt over mulige verdier for feltene i responsen se [API-dokumentasjonen](https://nvdbapilesv3.docs.apiary.io)

### Sprint 15
* Endepunktet `/posisjon` virker med vegsystemreferanse.
* Filtrering på vegsystemreferanse implementert.
* Vegkart: Klikk i kart viser vegsystemreferanse i punkt.
* Vegkart: Vegsystemreferanse vises i treffliste. 

#### Responsendringer
* [Veglenkesekvenser](https://github.com/nvdb-vegdata/nvdb-api-client/commit/0835b98deac4bdc39c16fc0e57ba8130f4c3525e#diff-6f9ed187bf7b5d1c57ca059ef52bc580) 
* [Segmentert vegnett](https://github.com/nvdb-vegdata/nvdb-api-client/commit/25a40c9d461df1cb4be3bcee1603915865a08c1f)
* [Vegobjekter](https://github.com/nvdb-vegdata/nvdb-api-client/compare/5d0d1612909b18fd933f8739eaaf3adb933a2d8d...6bf51df#diff-b5f334c16ceccbb3987030524a0e828c)
* [Statistikk](https://github.com/nvdb-vegdata/nvdb-api-client/compare/5d0d1612909b18fd933f8739eaaf3adb933a2d8d...6bf51df#diff-0532efd44a5bb56170adcd5e71e91b59) (`strekningslengde` er endret til `lengde`)


## Grov forventet fremdrift

### Q1 2019
* Autentisering for tilgang til sensitive datatyper og egenskaper.
* Respons for vegobjekt-egenskaper reduseres til kun data, ikke felter for datatype, egenskapstypenavn.
* Historiske objekter refererer til vegreferanse
* Gi ut informasjon om objekter som er oppdatert på grunn av endringer i vegsystemreferanse, kontraktsområde, eller riksvegrute.

### Fremtid
* Filtrere usegmentert vegnett basert på vegreferanse
* Avansert spørring virker igjen
* Alle endepunkter støtter POST 
* Mulighet for å finne rute mellom to punkter på vegnettet.
* Vise vegobjekter og vegnett som er gyldig på et gitt tidspunkt.
* GeoJSON-respons

# NVDB API Skriv V3 - Endringslogg

Oversikt over kontraktsendringer for NVDB API Skriv som er synlige for konsumenter av V3.


## Fullførte versjoner

### 2020-4.0

* Nytt høydekoordinatsystem i NVDB: NN2000. SRID 6173 (EUREF89 UTM33 NN54) er ikke lenger tillatt og avvises nå med valideringsfeil.
  Eneste tillatte 3D koordinatsystem er SRID 5973 (EUREF89 UTM33 NN2000). Ved bruk av 2D koordinatsystem, forventes at høydekoordinater
  er angitt i tråd med NN2000.  

### 2020-3.0

* Nytt endepunkt for å hente autorisasjoner (datarettigheter) for en bruker: /rest/v1/autorisasjon/{brukernavn}
    * En fagdatabruker kan bare hente sin egen autorisasjon.
    * Tjenestebrukere og systemadminbrukere kan hente alle autorisasjoner

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

#### Oppdaterte XML-skjemaer
* https://www.utv.vegvesen.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### 2020-1.0

API Skriv krever ikke lengre at minst én veglenke er oppgitt ved delvis oppdatering av veglenkesekvenser. Det er dermed mulig å angi delvis oppdatering der kun porter endres.

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

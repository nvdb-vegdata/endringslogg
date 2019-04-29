# NVDB API SKRIV V3 - Endringslogg og implementasjonsplan

Dette er endringer vi har gjort i hver sprint som er synlige for konsumenter av V3.


## Fullførte sprinter

### Sprint 10
* Følgeoppdatering (endret retning på retningssensitive egenskapstyper) ved endret metreringsretning
* Omdøping `<vegobjekt>/<lokasjon>` --\> `<vegobjekt>/<stedfesting>`
* Attributtene `retning` og `sideposisjon` på `<vegobjekt>/<stedfesting>` er gjort om til subelementer
* Attributten `felt` på `<vegobjekt>/<stedfesting>` er erstattet med et subelement `<kjørefelt>` som igjen har en eller flere `<feltkode>`-subelementer
* Omdøping `<lenke>/<lenkesekvensprojeksjon>` --\> `<lenke>/<superstedfesting>`
* Omdøping `<lenke>/<lenkesekvensprojeksjon>/<nvdbId>` --\> `<lenke>/<superstedfesting>/<lenkesekvensNvdbId>`
* Omdøping `<lenke>/<lenkesekvensprojeksjon>/<tempId>` --\> `<lenke>/<superstedfesting>/<lenkesekvensTempId>`
* Elementet `<feltkode>` under `<lenkesekvensprojeksjon>` (nå `<superstedfesting>`) er plassert inne i nytt subelement `<kjørefelt>` og kan repeteres 

### Sprint 11
* Nytt subelement `<låsing>` etablert under `<endringssett>`. Tidligere subelement `<låsId>` er flyttet inn hit.
* Klienten kan be om å få forhåndslåsen automatisk fjernet på gitte betingelser ved å angi dette med `<slettLåsAutomatiskNår>`
  under `<låsing>`. Foreløpig kan man kun angi koden `UTFØRT_OG_ETTERBEHANDLET`.
* Innført `<notabene>` som ny alvorlighetsgrad for varsler i endringssettets status i tillegg til `<feil>` og `<advarsel>`.
  Alle følgeoppdateringer som utføres ved behandling av endringsettet beskrives via globale notabene-varsler.
* Ved `GET /endringssett/{id}/status` leveres nå nytt subelement `<etterbehandling>` som angir om transaksjonen er indeksert
  og tilgjengelig i API Les. Tilsvarende subelement i `<endringssett>` er fjernet.

### Sprint 12
* Ved uregelmessigheter i nettelementers geometri angis dette med subelementet `<geometrideler>` under
  `<feil>`, `<advarsel>` og `<notabene>` i endringssettets status. Her angis koordinatene til den delen av geometrien
  som har uregelmessigheter via `<wkt>`-subelementer, enten som `POINT` eller `LINESTRING` (dersom uregelmessigheten gjelder
  sammenhenger mellom to naboposisjoner).

### Sprint 13
* `POST /lås` : Innført strukturert payload i 403-responser som inneholder `<fault>` med detaljer dersom bruker
  mangler rettigheter til vegobjekttyper eller kommuner (avledet av veglenker) angitt i låsen, eller mangler rettighet
  til å utføre vegnettsendringer dersom låsen er en vegnettslås.
* Ved oppdatering av nettelementer detekteres hvilke aspekter (geometri, topologi, metadata m.fl.) som er endret og kun
  disse aspektene blir validert. Eventuelle feil i uendrede aspekter fører dermed ikke lenger til at endringssettet avvises.

### Sprint 14
* `POST /lås` : Avvises med 422 og feilkode `FOR_MANGE_LENKESEKVENSER` dersom låsen inneholder mer enn 999 lenkesekvenser.
* Følgeoppdatering (justering av stedfesting) ved geometriutskiftning på veglenker.

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
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/vegobjekt.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/lenke.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/node.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd

### Sprint 16
* To nye endepunkter for å levere gjeldende versjon av valideringsregelsett
    * `GET /regelsett/vegnettobjekttype/versjon` : Responderer med payload som beskriver gjeldende versjon av regelsettet (se XML-skjema for `<versjon>`).
    * `GET /regelsett/lenke/versjon` : Responderer med payload som beskriver gjeldende versjon av regelsettet (se XML-skjema for `<versjon>`).
* `GET /regelsett/vegnettobjekttype` : Rotelementet er omdøpt fra `<regelListe>` til `<regelsett>`. Et nytt subelement `<versjon>` er innført, med samme informasjon som over.
* `GET /regelsett/lenke` : Rotelementet er omdøpt fra `<regelListe>` til `<regelsett>`. Et nytt subelement `<versjon>` er innført, med samme informasjon som over.

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
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/vegobjekt.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/veglenke.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/les/veglenkesekvens.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v1/lås/lås.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v1/regelsett/veglenke.xsd

### Sprint 18
* Ingen kontraktsendringer

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
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v3/endringssett/endringssett.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v1/regelsett/veglenke.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v1/regelsett/vegnettobjekttype.xsd
* https://nvdbw01.kantega.no/nvdb/apiskriv/rest/v1/lås/lås-liste.xsd

### Sprint 20
* X-Client header kreves ved POST/PUT/PATCH/DELETE mot endepunktene: 
    * /v3/endringssett 
    * /v1/lås 


## Grov forventet fremdrift

### 2019
* Operasjonen "slett" omdøpes til "lukk"

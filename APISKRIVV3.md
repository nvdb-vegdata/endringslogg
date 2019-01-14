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



## Grov forventet fremdrift


### Q1 2019
* Validering av unikhet for vegsystemreferanser (Vegsystem og Strekning)
* Støtte for multiple effektdatoer i endringssett
* Trigge statistikkberegning

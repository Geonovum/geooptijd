# Overzicht: Oude LPO / LPF vs Nieuwe LPO-Draft (2024)

---

## Conceptueel niveau

| Thema | Oud model *(LPO v1.1 / LPF 2019)* | Nieuw model *(LPO draft 2.0 2024)* | Wat betekent dit praktisch |
|:------|:----------------------------------|:-------------------------------|:----------------------------|
| Hoofdentiteit | `geojson:Feature` + `lpo:Setting` + `lpo:Timespan` | één `lpo:Place` als hoofdobject | `Place` vervangt `Feature` als centraal knooppunt |
| Substructuur | Tijd, naam, type, geometrie via losse *attestaties* (`NameAttestation`, `TypeAttestation`, `Setting`, enz.) | Tijd, naam, type, geometrie via *modules* (`PlaceName`, `PlaceType`, `PlaceGeom`, enz.) | Alles zit onder `lpo:Place` met geneste blokken |
| Attestaties | Vier afzonderlijke attestatie-klassen | Eén uniforme structuur: elk aspect is een eigen “PlaceXxx”-klasse | Minder fragmentatie |
| Tijd | `lpo:when → lpo:Timespan` met `lpo:in` of `lpo:has_start/end` | `lpo:hasWhen → lpo:When → lpo:PlaceWhen → lpo:Timespan` | Tijd krijgt meer detail en kan meerdere periodes bevatten |
| Ruimte | `geojson-t:geometry → lpo:Setting → geojson:Point` | `lpo:hasGeom → lpo:PlaceGeom` met `geo:asWKT`, `lpo:geoType`, `lpo:coordinates` | Geen aparte `Setting` meer nodig |
| Type | `lpo:TypeAttestation` + `dct:subject` naar CHT/AAT | `lpo:PlaceType` met `lpo:typeLabel`, `lpo:sourceUri` | Type-info explicieter, los van `dct:` |
| Naam | `lpo:NameAttestation` met `lpo:toponym`, `lpo:source_label` | `lpo:PlaceName` met `lpo:toponym`, `lpo:language`, `lpo:hasCitation` | Meer nadruk op taal + bron |
| Links & Relaties | `lpo:link_attestation`, `lpo:rel_attestation` | `lpo:PlaceLink`, `lpo:PlaceRelation` | Uniformer patroon |
| Periodes | `lpo:PeriodDefinition`, `lpo:period` | `lpo:Period` met `lpo:periodName`, `lpo:periodURI` | Klaar voor PeriodO-integratie |
| Doel | Historisch gazetteer, sterk RDF-technisch | Modulair JSON-LD-formaat voor WHG/Pelagios | Eenvoudiger voor API’s en serialisatie |

---

## Technisch niveau – RDF / JSON-LD-structuur

| Aspect | Oud | Nieuw | Belangrijk verschil |
|:-------|:----|:------|:--------------------|
| Hoofdklasse | `geojson:Feature` | `lpo:Place` | Nieuwe centrale klasse |
| Geometry-property | `geojson-t:geometry` | `lpo:hasGeom` | Nieuwe propertynaam |
| Geometry-class | `lpo:Setting` + `geojson:Point` | `lpo:PlaceGeom` | Gecombineerde klasse |
| Naam-property | `lpo:name_attestation` | `lpo:hasName` | Nieuwe naamgeving |
| Type-property | `lpo:type_attestation` | `lpo:hasType` | idem |
| Link / Relatie | `lpo:link_attestation` / `lpo:rel_attestation` | `lpo:hasLink` / `lpo:hasRelation` | Samengevoegd patroon |
| Tijd-property | `lpo:when` / `lpo:timespan` | `lpo:hasWhen` / `lpo:whens` | Nieuwe hiërarchie |
| Certainty | `lpo:has_certainty` = "certain"/"uncertain" | `lpo:certainty` (op `PlaceWhen`) | Zelfde semantiek, andere plek |
| Citation | `lpo:source_label` (string) | `lpo:hasCitation → lpo:Citation → lpo:labelValue` | Bron = eigen object |
| Taal | geen expliciet veld | `lpo:language` binnen `PlaceName` | Nieuw veld |
| JSON-containers | losse objecten | veel `@list`-containers (namen, types, geoms, whens) | Andere JSON-LD-weergave |
| Namespace | `http://linkedpasts.org/ontology#` | `https://raw.githubusercontent.com/kgeographer/_graph/main/lpo/lpo_draft_YYYYMMDD.ttl#` | Nieuwe prefix-URI |

---

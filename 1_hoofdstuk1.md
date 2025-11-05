# Inleiding op het toepassingsprofiel

## Aanleiding
Erfgoedinstellingen beheren waardevolle informatie die sterk verbonden is met specifieke locaties, in specifieke momenten in de tijd. Voor een effectieve ontsluiting en benutting van deze data is het noodzakelijk om erfgoedinformatie te koppelen aan geografische locaties uit het verleden (historische geo-informatie), waarbij de historische context van die locatie geborgd blijft. Moderne plaatsnamen-databanken (gazetteers) zoals <a href='https://geonames.org/' target='_blank'>GeoNames</a>, <a href='https://www.getty.edu/research/tools/vocabularies/tgn/index.html' target='_blank'>Getty TGN</a>, <a href='https://wikidata.org/' target='_blank'>Wikidata</a> of de <a href='https://www.kadaster.nl/zakelijk/registraties/basisregistraties/bag' target='_blank'>BAG</a> bieden wel veel plaatsen, maar zijn beperkt bruikbaar voor historische aanduidingen zoals oude gemeentenamen, spellingsvarianten, verdwenen dorpen, of administratieve eenheden uit het verleden. Tien jaar geleden is in het kader van het project <a href='http://erfgoedenlocatie.nl' target='_blank'>Erfgoed & Locatie</a> al een poging gedaan om te voorzien in de behoefte om historische geografische informatie in Nederland beter te ontsluiten, maar dit project wordt niet meer onderhouden. 

Het op een juiste manier ontsluiten van historische geo-informatie maakt het mogelijk om historische gegevens effectief ruimtelijk te verkennen en zogenaamde tijdreizen op locatie uit te voeren, waarbij gebruikers van bijvoorbeeld de 
<a href='https://www.cultureelerfgoed.nl/onderwerpen/bronnen-en-kaarten/overzicht/erfgoedatlas' target='_blank'>Erfgoedatlas</a>, <a href='https://hisgis.nl/' target='_blank'>HisGIS</a>, of de vele verschillende lokale Time Machines door verschillende historische datasets heen kunnen navigeren en zo het verleden geografisch kunnen ervaren en analyseren. 

In dit kader hebben het <a href='https://netwerkdigitaalerfgoed.nl/wat-wij-doen/' target='_blank'>Netwerk Digitaal Erfgoed</a>, de <a href='https://www.cultureelerfgoed.nl/over-ons' target='_blank'>Rijksdienst voor het Cultureel Erfgoed</a>, het <a href='https://huc.knaw.nl/about-us/' target='_blank'>KNAW Humanities Cluster</a> en <a href='https://www.geonovum.nl/over-geonovum' target='_blank'>Geonovum</a> de handen ineen geslagen om het digitaal erfgoed domein en geo-informatie domein met elkaar te verbinden. Door middel van een focusweek is er gewerkt aan voorbeelden en de basis voor standaardisatie en architectuur. Dit document, het Nederlands Profiel voor Linked Places, is gebaseerd op de internationale standaard voor <a href='https://github.com/LinkedPasts/linked-places-format' target='_blank'>Linked Places</a>. 


## Afbakening en uitgangspunten
Er is in Nederland veel digitale erfgoedinformatie beschikbaar. Veel van deze informatie over een cultuurhistorisch object of erfgoedobject heeft een locatieaanduiding en een tijdaanduiding. Deze locatieaanduiding is nog niet eenduidig gestandaard beschikbaar is waardoor het ruimtelijk te verkennen en zogenaamde tijdreizen op locatie niet mogelijk is. 
Daar waar standaardisatie in het geo-informatie veelal vanzelfsprekend is, vaak zelfs via wet- en regelgeving verplicht is om het gebruiken, is dat niet het geval voor digitale erfgoedinformatie. Om digitale erfgoedinformatie met een locatie op een eenduidige manier houdbaar, bruikbaar en zichtbaar te maken is gezocht naar een verbinding tussen de geo-standaarden en digitaal erfgoed. De standaard Linked Places lijkt hierin een verbindende rol te kunnen vervullen. De Linked Places standaard geeft voor het cultuurhistorisch object of erfgoedobject context voor de locatie en in de tijd: wie, wat waar en wanneer? De standaard maakt het mogelijk op verschillende manieren een locatieaanduiding toe te voegen, inclusief wanneer. 

Uitgangspunten bij het opstellen van het Nederlands toepassingsprofiel voor Linked Places zijn: 
- aansluiting op (inter)nationale standaarden en architectuur; 
- voor de inhoudelijk verbinding in het digitaal erfgoeddomein zijn de gedeelde terminologiebronnen leidend; 
- scheiden van data en visualisatie;
- data bij de bron:
- gebruik van persistente identifiers,
- publiceren van erfgoed data als Linked Data,
- datasets zodanig publiceren zodat zij via het Datasetregister vindbaar zijn,
- personen, plaatsen, onderwerpen, gebeurtenissen koppelen aan gedeelde definities in terminologiebronnen in het Termennetwerk,
- afbeeldingen publiceren op basis van de IIIF standaard.


## Uitgangsbronnen en inspiratie
Ongeveer tegelijkertijd met het ontstaan van Erfgoed en Locatie en haar '[Places in Time](https://netwerkdigitaalerfgoed.nl/wp-content/uploads/2021/01/historische_geocoderhackalod2021_jvand.pdf)' model, werkte de Pelagios Gazetteer (een internationale digitale plaatsnamendatabank voor de antieke wereld) aan het [Pelagios Gazetteer Interconnection Format](https://github.com/pelagios/pelagios-cookbook/wiki/Pelagios-Gazetteer-Interconnection-Format). Beide projecten werkten met enigszins vergelijkbare uitgangspunten om historische plaatsen te ontsluiten. Darabij is bijvoorbeeld te denken aan de volgende elementen die een 'plaats in tijd' heeft of kan hebben:
* Een titel of _preferred label_
* Een (arbitraire) naam (vermelding, attestatie, of (spellings)variant)
* Provenantie (een link naar de bron)
* Een unieke identifier
* Een plaatstype (de _plaats_ Groningen, de _gemeente_ Groningen, de _provincie_ Groningen, de _rivier_ de Hunze, de _straat_ Astraat)
* Een periode of tijdsaanduiding, die zowel op de plaats als op attributen kan slaan
* Een of meerdere geometrieën
* Een of meerdere relaties (hiërarchisch, ruimtelijk) met andere plaatsen
* Een of meerdere links met andere terminologische bronnen (veelgebruikt zijn GeoNames, Wikidata, Getty TGN) 

Het _Pelagios Gazetteer Interconnection Format_ (PGIF) is inmiddels doorontwikkeld en volledig vervangen door het Linked Places format (LPF), dat in de laatste jaren internationaal veel tractie heeft gekregen. In die zin is het ook de logische opvolger geworden van het in Nederland ontwikkelde 'Places in Time' van Erfgoed en Locatie. Ten opzichte van het PGIF zijn de volgende wijzigingen doorgevoerd:
* Het is ontworpen rondom de JSON-LD syntax, waardoor het zowel valide RDF (XML, Turtle, etc.) als JSON oplevert
* Het is valide GeoJSON en daardoor snel in verschillende web mapping applicaties weer te geven. Meer precies, het is een implementatie van GeoJSON-T, een experimentele extensie op GeoJSON die de representatie van tijdsaanduidingen standaardiseren
* Het voegt de mogelijkheid toe om verschillende attributen (naamsaanduidingen, geometrie, plaatstype, en plaatsrelaties) te koppelen aan een tijdsaanduidingen

Het Linked Places format is voortgekomen uit de bijeenkomsten van [Linked Pasts](https://linkedpasts.hcommons.org), een jaarlijks symposium met internationale professionals en wetenschappers die werken op het snijvlak van erfgoed en Linked Open Data. Het Linked Pasts symposium is formeel partner van het [Pelagios Network](https://pelagios.org/about-us/), het internationale netwerk waarin de meeste van deze professionals aan verbonden zijn. Dit netwerk is, zoals de naam al doet vermoeden, voortgekomen uit de hierboven genoemde Pelagios Gazetteer. 

Een andere grote partner in het Pelagios Network, en bovendien de grote aanjager van het Linked Pasts format, is de [World Historical Gazetteer](https://whgazetteer.org) (WHG). Dit project wordt vanuit het [Institute of Spatial History Innovations](https://www.ishi.pitt.edu) van de University of Pittsburgh geleid, maar kent een brede groep gebruikers _en_ partners, waaronder het KNAW Humanities Cluster. De WHG is een platform waar records over historische plaatsen kunnen worden samengebracht en uitgewisseld. 

Het Linked Places format niet is uitontwikkeld of formeel als standaard is vastgelegd. De Github van Linked Pasts bevat een uitgebreide beschrijving van het [Linked Places Format](https://github.com/LinkedPasts/linked-places-format?tab=readme-ov-file) (LPF) alsmede een bestand met de [Linked Places Ontology](https://github.com/LinkedPasts/linked-pasts-ontology/blob/main/lpo_latest.ttl#) (LPO). Voor beide bestaan ook versies met enkele aanpassingen op de Github van World Historical Gazetteer: [LPO](https://github.com/WorldHistoricalGazetteer/website/blob/staging/validation/static/lpo_v2.0.jsonld) en [LPF](https://github.com/WorldHistoricalGazetteer/website/blob/staging/validation/static/lpf_v2.0.jsonld). De laatste omvangrijke wijzigingen zijn in de zomer van 2024 doorgevoerd. 

Ondanks deze doorlopende ontwikkeling is het Linked Placed Format in de afgelopen jaren wel tot een _de facto_ standaard uitgegroeid en wordt het breed gedragen en geïmplementeerd door de verschillende partners aangesloten op het Pelagios Network. De World Historical Gazetteer heeft een eigen validator ontwikkeld om JSON-LD bestanden te [valideren](https://github.com/WorldHistoricalGazetteer/website/tree/staging/validation/static). 

## Belangrijkste uitbreidingen

Voor het Nederlands toepassingsprofiel Linked Places is er voor gekozen de standaard Linked Places op de volgende punten uit te breiden c.q. te beperken:
- voor het attribuut fclasses de lijst van waarden van aansluiten op de stereotypen zoals gebruikt door NEN 3610;
- voor het attribuut types wordt een Nederlandse ontologie gemaakt op basis van os de Getty Institute Art and Architecture Thesaurus (AAT) en INSPIRE zodat deze aansluit op de Nederlandse praktijk;
- voor het attribuut geometry wordt geen gebruik gemaakt van het geometrietype GeometryCollection. 


## Modellering en keuzes
Voor de Nederlandse toepassing van het  Linked Places format is een modellering gekozen die aansluit op het Metamodel Informatiemodellering (MIM) LINK: https://www.geonovum.nl/geo-standaarden/metamodel-informatiemodellering-mim. Daarnaast zijn er keuzes gemaakt voor de bruikbaarheid , interoperabiliteit en op de architecturen en standaarden voor digitaal erfgoed en geo-informatie. 

In het Nederlands toepassingsprofiel zijn een aantal elementen (attributen) als verplicht te gebruiken opgenomen. In het Linked Places format zijn deze als aanbevolen en facultatieve elementen in Linked Places. 

<p>
    Het Nederlands profiel voor Linked Places (NL-LP) bouwt voort op de 
    <a href="https://github.com/LinkedPasts/linked-pasts-ontology">Linked Pasts Ontology (LPO v1.1)</a>.
    De LPO biedt een formele RDF-laag bovenop het <a href="https://purl.org/geojson/vocab#">GeoJSON-model</a>,
    waarmee historische en geografische gegevens semantisch en temporeel kunnen worden beschreven.
    Het profiel gebruikt deze ontologie om historische plaatsgegevens uit het Nederlandse erfgoeddomein 
    als Linked Data te publiceren.
  </p>

  <h3>Kernprincipes</h3>
  <ul>
    <li>
      Een plaats of ander geografisch object wordt gemodelleerd als een 
      <code>geojson:Feature</code> binnen een <code>geojson:FeatureCollection</code>.
    </li>
    <li>
      De ruimtelijke en temporele reikwijdte van een object wordt vastgelegd als een
      <code>lpo:Setting</code>. Deze kan een geometrie, een tijdsinterval of beide bevatten.
    </li>
    <li>
      Tijd wordt gemodelleerd via <code>lpo:when</code> dat verwijst naar een
      <code>lpo:Timespan</code>, een subklasse van <code>time:ProperInterval</code>.
    </li>
    <li>
      Attestaties (bewijzen of vermeldingen) zijn afgeleid van 
      <code>lawd:Attestation</code> en geven context aan namen, typen en relaties.
      De LPO onderscheidt vier hoofdvormen:
      <ul>
        <li><code>lpo:NameAttestation</code> – koppelt een naam (<code>lpo:toponym</code>) aan een bron of periode;</li>
        <li><code>lpo:TypeAttestation</code> – legt vast welk type (bijv. stad, rivier) een plaats had;</li>
        <li><code>lpo:RelAttestation</code> – beschrijft relaties tussen plaatsen (zoals “onderdeel van”);</li>
        <li><code>lpo:LinkAttestation</code> – verbindt een entiteit met een externe bron of gazetteer.</li>
      </ul>
    </li>
  </ul>

  <h3>Temporalisering</h3>
  <p>
    De eigenschap <code>lpo:when</code> kan aan vrijwel elk element worden toegevoegd om de periode 
    van geldigheid of bestaan aan te geven. Een <code>lpo:Timespan</code> kan grenzen hebben
    (<code>lpo:earliest</code>, <code>lpo:latest</code>) of een expliciete start- en eindtijd
    (<code>lpo:has_start</code>, <code>lpo:has_end</code>).
    Ook relaties en naamattestaties kunnen een eigen tijdsbereik hebben.
  </p>

  <h3>Geometrie</h3>
  <p>
    De eigenschap <code>geojson-t:geometry</code> (uit GeoJSON-T) is een uitbreiding van 
    <code>geojson:geometry</code> die toelaat om een geometrie te koppelen aan een
    <code>lpo:Setting</code>, inclusief temporele context (<code>lpo:when</code>).
  </p>

  <h3>Gebruik binnen NL-LP</h3>
  <p>
    In het Nederlands profiel worden deze LPO-constructies toegepast op erfgoedlocaties, 
    historische administratieve eenheden en andere plaatsen met ruimtelijke en temporele variatie. 
    Elke historische naam of afbakening wordt vastgelegd als een afzonderlijke
    <code>lpo:NameAttestation</code> of <code>lpo:TypeAttestation</code> met eigen periode en bron.
  </p> 

## Technische keuzes

TO DO 

## Conclusie



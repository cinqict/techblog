---
title: "Release vs Performance met Splunk"
date: 2018-07-10T10:00:00+02:00
tags: [ "splunk", "performance", "monitoring"]
draft: false
author: "Stefan Koppelaar"
authoravatar: "https://octodex.github.com/images/stormtroopocat.png"
authorbio: "Managing Consultant Splunk"
authorlocation: "Amsterdam, Netherlands"
image: "images/nieuwerelease.png"

---
#### Waar of niet waar?
 
>_De meeste IT performance verstoringen worden veroorzaakt door eigen aanpassingen op de IT omgeving._

Wij denken dat dit vaak _waar_ is. 
Of het nu een nieuwe release of deployment betreft: een fout zit in een klein hoekje. Automatisch testen ten spijt, is het helaas moeilijk dit volledig te voorkomen. Behalve het voorkomen, is de oplostijd ook een factor. Ieder uur dat verstrijkt in het vinden van de oorzaak brengt serviceverlies met zich mee. 

CINQ heeft hier iets op gevonden: wij brengen de performance met behulp van Splunk op functioneel niveau in kaart, en zetten deze af tegen infra releases en applicatie deployments.
Het dashboard ziet er als volgt uit:  

<img src="/images/overzichthosts.png" alt="overzicht hosts" width="1000" height="450">

#### Wat levert dit dashboard mij op?

- Transparant inzicht in de staat van de infrastructuur én applicaties
- Vermindering van incidenten
- Identificeer trends over tijd

Met dit dashboard is direct zichtbaar welke release of deployment de verstorende factor is en is lang zoeken naar de oorzaak verleden tijd. Er kan direct worden begonnen met oplossen of zelfs tijdelijk terug worden gegaan naar een vorige goed werkende versie.

Onderstaande grafiek geeft bijvoorbeeld duidelijk aan dat er na een release verhoogde latency optreedt. Hiervoor wordt gebruik gemaakt van verschillende informatie bronnen, die door Splunk worden geaggregeerd waardoor de relatie tussen release en verstoring duidelijk wordt.

<img src="/images/nieuwerelease.png" alt="latency na release" width="750" height="450"> 

Omdat Splunk de logs van hardware, data, middleware en applicaties kan lezen en samen brengen in dit dashboard, is er makkelijk inzicht in staat van de omgeving op ieder moment. Daardoor zijn verstoringen op de IT-dienstverlening sneller te lokaliseren en te verhelpen. 

#### Samenvattend
De voordelen van deze oplossing nog een keer op een rijtje: 

- Monitor beschikbaarheid, performance in één dashboard
- Impact van deployment en release direct zichtbaar
- Vind problemen voordat deze impact hebben op de applicatie 
- Verkort oplostijden door snelle lokalisatie van verstoringen
- Werk proactief aan een betrouwbare en wendbare omgeving 
- Stel slimme alerting in en maak functionele rapportages 

##### Meer weten over deze oplossing? 
Wij maken graag een demo! 
Laat een bericht achter in de comments of neem direct contact op met [Stefan Koppelaar](https://www.linkedin.com/in/stefan-koppelaar-92967b13/).
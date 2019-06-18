---
title: "Dockerfile on a Diet"
date: 2017-12-12T14:26:26+02:00
tags: [ "Docker", "dockerfile", "dockercon"]
draft: false
author: "Christian Kewerkopf"
authoravatar: "https://octodex.github.com/images/topguntocat.png"
authorbio: "Devops Cloud Engineer, Open source enthusiast. Pilot"
authorlocation: "Amsterdam, Netherlands"
authorwebsite: "www.github.com/christiankewerkopf"
image: "images/docker-cover1.jpg"
---

Op de eerste dag van DockerCon EU, een paar maanden geleden, was ik aanwezig bij een sessie van [Abby Fuller](https://twitter.com/abbyfuller) (senior technical evangelist, AWS) over hoe efficiënte Docker files geschreven kunnen worden. Dat klinkt misschien niet heel erg spannend, maar was zowel voor de beginnende als de iets meer gevorderde Docker user handig om te volgen. 
Er wordt namelijk vaak vergeten dat de opzet van een Dockerfile een groot verschil kan maken op de omvang van een Docker image. En dit heeft dus ook een behoorlijke impact op de download en opstart tijden van een image. Nu ben ik zelf ook al een paar jaar met Docker bezig en gaande weg zie ook ik steeds meer dat het belangrijk is om de build van Docker images en de daarmee gepaard gaande diskspace onder controle te houden. Abby benadrukte dit nog eens door te zeggen dat deze sessie over diskspace zou gaan.

Bij het bouwen van een image begin je altijd met een base layer. Denk aan een CentOS, Ubuntu of Alpine. De layers uit het base image zijn read-only container layers en kan je verder niet aanpassen. Het is dus van belang om rekening te houden met de grootte van het OS en of dit aan de minimale eisen voldoet. Hoe kleiner het base image, des te kleiner zal het uiteindelijke resultaat uitvallen.

Bovenop het base image zitten een aantal thin layers waar je zelf de aanpassingen op maakt bij het bouwen van een Docker image. Hier ga je dus invloed op hebben. Hoe meer layers je in jouw image hebt, hoe groter deze wordt. Hierdoor duurt het langer om te pushen en te pullen vanuit een registry en zal het builden en deployen ook langer duren. Dit maakte in een oude monolitische omgeving misschien niet zoveel uit, maar in de wereld van microservices en veelvoudige builds en deployments maakt dit een groot verschil.

Hoe bouw ik dan een image die zo min mogelijk ruimte in zal gaan nemen?

* Hergebruik je base images.
* Limiteer de data die je naar jouw image schrijft. Gebruik alleen de data die je echt nodig hebt
* Chain je RUN statements. Gebruik bijvoorbeeld 1 RUN statement om meerdere packages te installeren.
* Zorg dat je Docker image zoveel mogelijk gebruik maakt van caching. Bewaar je run statements voor het einde en zorg dat de wijzigingen die je moet maken aan je image zo ver mogelijk in jouw image worden uitgesteld. Hier zijn uiteraard uitzonderingen op.
* Wisselen van gebruikers voegt layers toe. Mocht je een bepaalde user moeten gebruiken voor een package/app. Probeer dan het wisselen van user te voorkomen.
* Vermijdt het toevoegen van grote files. Install packages kunnen worden uitgepakt, geinstalleerd en worden verwijderd in 1 RUN statement.
* Gebruik een base image die past bij je container. Een minimale base image zoals Alpine kan veel disk space besparen maar is niet altijd de beste keuze in verband met security, packages en functionaliteit.

Als je deze regels goed hanteert ben je verzekerd van de snelst mogelijke Docker workflow in het geval van een pull/build of run.

Tot slot nog een paar tips van Abby om te zorgen dat een Docker eco-systeem valide blijft:

* Implementeer een container scanner op de (private) Docker repository.
* Zorg dat oude images uit de repo worden verwijderd.
* Wanneer je base images van de publieke Docker repositories gebruikt, houd dan in de gaten dat deze continu worden verbeterd en zorg dat je bij blijft.

Happy Dockering !!

Bekijk de hele presentatie van Abby Fuller terug op YouTube:
![Abby Fuller op Dockercon](http://img.youtube.com/vi/pPsREQbf3PA/0.jpg)
---
title: "Dockercon EU 17 update: Docker goes Kubernetes"
date: 2017-10-18
tags: [ "Docker", "Dockercon", "Kubernetes", "swarm" ]
draft: false
author: "Wian Vos"
authoravatar: "https://octodex.github.com/images/dojocat.jpg"
authorbio: "Devops Cloud Engineer, Open source enthusiast."
authorlocation: "Amsterdam, Netherlands"
authorwebsite: "www.github.com/wianvos"
image: "images/dockercon1.png"
---
De grootste aankonding tijdens de Dockercon EU 2017 general session was de integratie van Kubernetes in de Docker EE en CE toolstacks. 
Waarom is dit een grootte aankonding? Omdat het feitelijk betekend dat Docker afstapt van de hechte integratie met zijn eigen product Swarm en gaat bijdragen aan het Kubernetes project. Wat vooral verrassend is, is dat deze integratie al in Q1 van 2018 beschikbaar is in de productie versie van Docker EE. 

Dit nieuws kwam echt als een complete verrassing aangezien in het verleden Docker swarm lijnrecht tegenover Kubernetes stond beide gepositioneerd als _het_ orchestratie platform voor container workloads. 

Het nieuws dat Docker Kubernetes gaat ondersteunen als orchestration framework is alweer een aankondiging van een grote speler in het container werkveld dat het voor orchestratie overstapt naar de Google orchestatie oplossing. Eerder deze maanden deden ook [Rancher](http://rancher.com) en [Pivotal](https://pivotal.io) (beide beschikkend over eigen orchestration frameworks) aankondigingen van dezelfde strekking. 

Voor Docker betekend het waarschijnlijk het winnen van de strijd met [_rkt_](https://coreos.com) aangezien Kubernetes lang gezien werd als de mogelijke gateway voor bedrijven om over te stappen van Docker naar _rkt_. Ze geven dus duidelijk onderscheidend vermogen in de orchestration space op om zo hun concurrentie positie aanzienlijk te versterken. 

Het is nog wel even afwachten hoe de integratie zich zal manifesteren. Tot nu toe wordt vrij duidelijk gecommuniceerd dat de Kubernetes ondersteuning aanwezig zal zijn in Docker EE en Docker CE for Mac en Windows alsmede het Moby project. Wat nog niet duidelijk is is of de integratie ook in Docker CE for Linux aanwezig zal zijn. Het zou dus nog zomaar kunnen zijn dat je voor de Kubernetes integratie aangewezen bent op docker EE.

Inschrijven voor de open beta van kubernetes support in Docker kan [hier](http://www.docker.com/kubernetes).

![](/images/dockercon_kube1.jpg)

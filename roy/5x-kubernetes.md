---
title: "5 x aan de slag met Kubernetes"
date: 2018-11-20T14:00:00+02:00
tags: [ "kubernetes", "containers", "howto"]
draft: false
author: "Roy Kliment"
authoravatar: "https://octodex.github.com/images/topguntocat.png"
authorbio: "DevOps Engineer"
authorlocation: "Amsterdam, Netherlands"
image: "images/k8s.png"
---


Container orchestration met [Kubernetes](https://kubernetes.io) (k8s) is hot, we kunnen er gewoonweg niet meer omheen. Hieronder vind je 5 manieren om te beginnen met het opzetten van je eigen clusters, zodat je kunt starten met je eigen onderzoek naar container orchestration met Kubernetes.

### Minikube

[Minikube](https://github.com/kubernetes/minikube) is een open-source project van Kubernetes en eigenlijk de snelste en meest eenvoudige manier om Kubernetes uit te proberen. Je download een binary en daarmee zet je op je eigen machine een klein maar volledig functioneel Kubernetes cluster op. Perfect als lokale development omgeving maar niet meer dan dat.

### Hosted

Inmiddels zijn er legio oplossingen om in de cloud managed k8s clusters af te nemen. Een paar voorbeelden zijn [Amazon EKS](https://aws.amazon.com/eks/), [Microsoft AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/) en [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/). Het mooiste aan deze oplossingen is dat je niets hoeft mee te nemen behalve een creditcard. Met een paar simpele kliks of API calls staat er een werkend cluster voor je klaar en kun je meteen aan de slag en je hoeft je niet druk te maken over het cluster zelf want dat wordt gemanaged door de leverancier. Wil je echter met de latest and greatest mogelijkheden van een nieuwe k8s versie aan de slag dan gaat dat wat moeilijker, de meeste managed oplossingen draaien niet de laatste versie van Kubernetes.

Meer hosted en andere k8s distributies zijn te vinden op de [partner pagina](https://kubernetes.io/partners/#conformance) van Kubernetes.

### Rancher 2.0

[Rancher](https://rancher.com) is al een aantal jaar een speler op het gebied van container orchestration. In eerste instantie met hun eigen orchestrator (Cattle) en ondersteuning voor een aantal andere (Mesos, Kubernetes) maar sinds versie 2.0 richten ze zich volledig op Kubernetes. 

Rancher draait in een container waar je maar wil en kan zelf clusters aanmaken op verschillende manieren. Je kunt gebruik maken van allerlei cloud providers waar Rancher dan zelf een k8s cluster op installeert of je laat Rancher managed clusters aanmaken bij Amazon AWS, Microsoft Azure of Google.

Het mooie is dat Rancher je in staat stelt om meerdere clusters te beheren ongeacht locatie of onderliggend platform. Daarnaast biedt Rancher build pipelines, centrale opslag van logs uit je cluster  en integratie met [Helm](https://helm.sh/) om snel applicaties vanuit Helm charts te draaien. Daarnaast is Rancher volledig open-source met mogelijkheden om support af te nemen.

### Docker EE 2.0

Sinds de komst van [Docker Enterprise Edition 2.0](https://www.docker.com/products/docker-enterprise) biedt ook Docker (naast swarm) een mooie Kubernetes distributie. Het Docker Universal Control Plane kan je eigen maar ook cloud infrastructuur op simpele wijze inrichten als Kubernetes cluster. Wat handig is aan Docker EE is dat je zowel Docker Swarm als Kubernetes naast elkaar kunt gebruiken. Swarm is een uitstekende manier om te starten met container orchestration en ook voor productie workloads heel goed bruikbaar. Mocht je tegen de beperkingen van swarm (vaak later dan je denkt, swarm is krachtiger dan algemeen wordt aangenomen!) aan lopen, dan kun je binnen dezelfde omgeving snel overstappen naar Kubernetes. Je hebt echter wel een (trial)licentie nodig om Docker EE te gebruiken. Voordeel is wel dat je naast Universal Control Plane voor cluster management ook Docker Trusted Registry (DTR) kunt gebruiken, waarmee je een hele krachtige oplossing in handen hebt voor het opslaan van je Docker images. 

### The Hard Way

Als je het hebt over Kubernetes kun je haast niet om de repo [Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) van Kelsey Hightower heen. Deze repo geeft je een handleiding om volledig met de hand een k8s cluster op te bouwen. Dit is lang niet voor iedereen interessant maar wil je echt alles weten over de ins en outs van k8s dan is dit een leuke besteding van een paar uur.
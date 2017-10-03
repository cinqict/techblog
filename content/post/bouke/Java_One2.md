---
title: "Java One Update 2: De toekomst van Java"
date: 2017-10-03T10:12:37+02:00
tags: [ "java", "java one", "cool" ]
draft: false
author: "Bouke Nijhuis"
authoravatar: "https://octodex.github.com/images/class-act.png"
authorbio: "Boss-level Java Developer"
authorlocation: "Amsterdam, Netherlands"
image: "images/javaone.jpg"
---

De chief architect of Java (Mark Reinhold) heeft tijdens de keynote de grootste veranderingen in Java 9 laten zien. Voor mensen die de ontwikkeling van Java een beetje bijhouden, weten dat de grootste wijziging project Jigsaw is. Het is nu mogelijk om je software in modules op te hakken, waarbij een module een groepering van packages is. Dit mechanisme kan je gebruiken naast het al bestaande (inferieure) classpath mechanisme. Tevens zijn alle bestaande java packages opgedeeld in 25 optionele en 1 verplichte module. Dat betekent dat je nu veel kleinere deployment units kan hebben, want alle ongebruikte, optionele modules heb je niet meer nodig. Precies wat je wilt in deze tijden van microservices en serverless computing. 

Daarnaast komt er nu elke zes maanden een nieuwe versie van Java. De vorige versie van Java (8) is namelijk alweer drie jaar geleden gereleased. Dit releaseschema kun je je als zelfrespecterende taal eigenlijk niet meer veroorloven. Oftewel in maart kunnen we Java 10 verwachten. Eén van de zaken die er zo goed als zeker in zit is Local Variable Type Inference. Je kent het principe waarschijnlijk al uit andere (script)talen. Dit kunnen we het beste uitleggen aan de hand van een voorbeeld.

```java
var list = new ArrayList<String>();
var stream = list.stream();
```

Wat je hier ziet is dat de compiler in staat is om zelf het type van de variable af te leiden. Dit kun je namelijk makelijk uit de gegevens aan de rechterkant van het statement halen. De eerste variable zal als type ArrayList<String> hebben en de tweede Stream<String>. De tweede is iets lastiger, maar dit is simpelweg het returntype van de stream methode.

Daarnaast zit Generic Specialization eraan te komen. Dit houdt in de we straks ook Collections van primitieven kunnen hebben. Het is nu alleen mogelijk om de Collections API op objecten te gebruiken en dus niet op simpele waarden zoals int, boolean en char. In code ziet dit er dan alvolgt uit:

```java
List<char> charList = new ArrayList<char>();
```

Tot slot was het ook interessant om te horen dat alle verschillen tussen OpenJDK en de Oracle JDK gaan verdwijnen. Oftewel alle extra tools (zoals Mission Control en daarin de Flight Recorder) zijn straks zonder lastige Oracle restricties te gebruiken door iedereen.

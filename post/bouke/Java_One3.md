---
title: "Java One Update 3: Java 8 Program Idioms"
date: 2017-10-04T10:12:37+02:00
tags: [ "java", "java one", "cool","idioms", "java 8"]
draft: false
author: "Bouke Nijhuis"
authoravatar: "https://octodex.github.com/images/class-act.png"
authorbio: "Boss-level Java Developer"
authorlocation: "Amsterdam, Netherlands"
image: "images/javaone.jpg"
---
De meest interessante sessie van vandaag was Java 8 Program Idioms door Venkat Subramaniam. In razend tempo en met veel humor sneed hij een aantal interessante onderwerpen aan waarvan ik er hier een drietal zal behandelen.

Het eerste is dat declaratief programmeren vaak superieur is aan functioneel programmeren. Dat laat zich het beste uitleggen aan de hand van een voorbeeld. Hieronder staan twee stukken code die precies hetzelfde doen.

```java
people.stream()
        .filter(person -> person.getAge() > 25)
        .map(Person::getName)
        .map(String::toUpperCase)
        .forEach(System.out::println);

for (Person person : people) {
    if (person.getAge() > 25) {
        String name = person.getName();
        String toUpperCase = name.toUpperCase();
        System.out.println(toUpperCase);
    }
}
```

De eerste is declaratief en de tweede is functioneel. Bij declaratief vertel je de compiler wat je wil en bij functioneel vertel je hoe het moet. De eerste variant is beknopter en makkelijker te lezen. Verder is het meestal makkelijker om aan te geven wat je wil dan te vertellen hoe iets moet. Tot slot is declaratieve variant sneller uit te voeren door de CPU. Oftewel declaratief programmeren is beter dan functioneel programmeren.

De tweede interessante stelling gaat over het gebruik van lambdas. Als je code leesbaar wilt houden dan gebruik je alleen de simpelste varianten. Alleen de volgende twee constructies zijn dan toegestaan: 

* een method reference welke te herkennen is aan de '::' zoals in Person::getName 
* een lambda zonder accolades, return statement en een puntkomma zoals person -> person.getAge()

Alle andere varianten zijn te ingewikkeld en maken daardoor de code minder goed leesbaar. 

Tot slot zijn kortere lambda's de beste lambda's. Dit laat zich wederom het beste uitleggen met voorbeelden. De volgende drie regels code doen exact hetzelfde.

```java
(Person person) -> { return person.getName(); }
(Person person) -> person.getName();
Person::getName
```

Elke regel is een beetje korter dan zijn voorganger. De laatste regel is het makkelijkst te interpreteren en daardoor het snelst te begrijpen. Oftewel korter is beter. Van de vorige stelling hadden we al geleerd dat de eerste variant sowieso uit den boze is. 

Voor meer informatie over dit onderwerp is onderstaande *[blogpost](http://blog.agiledeveloper.com/2015/06/lambdas-are-glue-code.html)* van Venkat Subramaniam een aanrader. 

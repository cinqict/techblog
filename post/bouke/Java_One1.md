---
title: "Java One Update: Preventing Errors Before They Happen"
date: 2017-10-03T10:12:37+02:00
tags: [ "java", "java one", "cool" ]
draft: false
author: "Bouke Nijhuis"
authoravatar: "https://octodex.github.com/images/class-act.png"
authorbio: "Boss-level Java Developer"
authorlocation: "Amsterdam, Netherlands"
image: "images/javaone.jpg"
---
Dit is de eerste blog van een serie updates live vanaf de JavaOne in San Francisco. 

Vanochtend hebben we een sessie bijgewoond met de interessante titel: Preventing Errors Before They Happen. De presentatie ging voornamelijk over een uitbreiding op de static type checking die standaard al in Java zit. Een voorbeeld hiervan is dat je geen String kan toewijzigen aan een integer variable. Je krijgt dan namelijk een foutmelding van de compiler. Dit mechanisme zorgt ervoor dat je veel fouten al afvangt op compile time in plaats van op runtime. Er zijn weinig dingen vervelender dan software die wel werkt op jouw computer, maar niet op andermans computer. 

Eén van de meest interessante voorbeelden was het gebruik van de @NotNull annotatie. Deze zit al een tijdje standaard in Java (uit mijn hoofd sinds versie 6) en hij gooit een runtime error als je een argument voorziet van deze annotatie en toch een aanroep doet met een null reference. Dit is handig, maar het is handiger als je deze informatie al tijdens het compileren krijgt.

Voorbeeld dat een NullPointerException gooit tijdens het draaien:

```java
void doFoo(@NotNull String argument) { ... }

void doBar() {
   doFoo(null);
}
```

De eerder genoemde uitbreiding op de standaard static type checking zorgt ervoor dat je deze informatie wel op runtime beschikbaar hebt. De uitbreiding heet The Checker Framework en dit is nog maar één voorbeeld. In principe is de software geschikt om alle soorten runtime checks al op compile time af te vangen. De meest voorkomende runtime errors zitten al in het framework. Echter als je een zelf gedefinieerde error hebt die je van runtime naar compile time wil verplaatsen dan kan je makkelijk het framework uitbreiden met je eigen checks.

Meer informatie en de downloads vind je op *[checkerframework](https://checkerframework.org/)*
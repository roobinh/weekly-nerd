

# Hoe beinvloed ik de performance van mijn website?

## Introductie
"Website performance" verwijst naar de de tijd dat het duurt om een website te downloaden en op het scherm weer te geven. Tegenwoordig verwachten bezoekers van websites dat websites zo goed mogelijk zijn geoptimaliseerd. Als je een bezoeker te lang laat wachten op het laden van de pagina, bestaat er een grote kans dat de bezoeker liever de website van je concurenten gebruikt. Als de bol.com website extreem langzaam laadt, gebruiker mensen liever coolblue.com, best logisch.

Het is daarom extreem belangrijk dat de performance van je website zo goed mogelijk geoptimaliseerd is, maar hoe doe je dat? Dat lees je in het volgende hoofdstuk.

## Hoe kan je de web-performance verbeteren?
### Oorzaak achterhalen
Om de performance van je website te verbeteren zijn er extreem veel technieken die je kunt gebruiken. Het is echter wel belangrijk om eerst te kijken wat de oorzaak van de lange wachttijd is, en dus welke technieken je het beste op jouw site kan toepassen. Een handige tool hiervoor is de 'Google Chrome Lighthouse tool'

### Hoe gebruik ik de Lighthouse tool?
Ga in Google Chrome naar de website waarvan je de performance wil verbeteren (in de voorbeelden hieronder gebruik ik de Volkswagen website). Na het laden van de website, klik 'rechtermuisknop' in het Chrome venster en klik op 'Inspecteren'. Vervolgens ga je naar het tabje 'Audits' en druk je op 'Audit', dit kan even duren. Wat je dan ziet is het volgende:

<img src="https://i.ibb.co/HgfWn8C/image.png">

 Na de audit kan je precies zien hoe lang het duurt om jouw website te laden. Zo zie je hierboven dat het 4.0 seconden duurt om de 'First Meaningfull Paint' op het scherm weer te geven. 

Daaronder kan je precies zien welke factoren grote invloed hebben op de performance van jouw website. Zo kan je op de volkswagen site al 3 seconden besparen door de afbeeldingen slimmer te sturen. Dit kan je bijvoorbeeld doen door de grootte aan te passen aan de site grootte, en de bestandstype te updaten naar een nieuwer en kleiner bestandstype. 

In het hoofstuk hieronder worden 5 optimalisaties behandeld die de performance van jouw website drastisch kunnen verbeteren!

## Verschillende optimalisaties
In dit hoofdstuk worden de volgende onderwerpen behandeld:
- Server Side Renderen
- Filegrootte verminderen
- Caching
- Afbeelding bestandstypen
- First View

### Server Side Renderen
Wanneer een gebruiker een website opvraagt in zijn browser, vraagt zijn browser een aantal bestanden van de server. Deze bestanden (HTML & CSS) zijn nodig om de content op het scherm weer te geven. HTML is de programmeertaal die voor de lay-out van de pagina zorgt en CSS voor de opmaak.

Tegenwoordig gebruiken heel veel websites dynamische data (data dat kan veranderen). Vroeger werd deze data altijd vanaf de client ingeladen door een Javascript of PHP bestand uit te voeren. Tegenwoordig kan dit ook al vanaf de server gebeuren, door middel van server-side rendering.

Als de gebruiker een website (server-side-rendering) opvraagt, rendert de server alle data alvast in de HTML, waardoor de gebruiker dit niet hoeft te doen. Dit kan enorm veel invloed hebben als de gebruiker een langzame processor of een langzame internetverbinding heeft.

### Minification (Filegrootte verminderen)
Minification is het minimaliseren van het aantal bytes dat de gebruiker moet downloaden. Dit heeft als invloed dat de gebruiker minder lang hoeft te downloaden en dus tijd bespaard.

Voorbeeld: Een gebruiker vraagt de website youtube.com op. De originele code dat Youtube zelf heeft geschreven is 1000 KBytes, maar na de minification nog maar 300 KBytes. Dit zorgt ervoor dat de client maar 30% zo lang hoeft te wachten op zijn download

Minifien gebeurt door middel van code te herschrijven in voor 'mensen' onleesbare text, maar voor de computer net zo begrijpelijk als de originele. Een voorbeeld hiervan is hieronder te zien.

Origineel:
```Javascript
  
 // return random number between 1 and 6
function dieToss() {
  return Math.floor(Math.random() * 6) + 1;  
}

// function returns a promise that succeeds if a 6 is tossed
function tossASix() {
  return new RSVP.Promise(function(fulfill, reject) {
    var number = Math.floor(Math.random() * 6) + 1;
    if (number === 6) {
      fulfill(number);
    } else {
      reject(number);
    }
  });
}
// display toss result and launch another toss
function logAndTossAgain(toss) {
  console.log("Tossed a " + toss + ", need to try again.");
  return tossASix();
}

function logSuccess(toss) {
  console.log("Yay, managed to toss a " + toss + ".");
}

function logFailure(toss) {
  console.log("Tossed a " + toss + ". Too bad, couldn't roll a six");
}
// use promise paradigm to try three times to toss a 6
tossASix()
  .then(null, logAndTossAgain)   //Roll first time
  .then(null, logAndTossAgain)   //Roll second time
  .then(logSuccess, logFailure); //Roll third and last time
  ```

Minified:
```javascript
function dieToss(){return Math.floor(6*Math.random())+1}function tossASix()
{return new RSVP.Promise(function(a,b){var 
c=Math.floor(6*Math.random())+1;6===c?a(c):b(c)})
}function logAndTossAgain(a){return console.log(
"Tossed a "+a+", need to try again."),tossASix()}function logSuccess(a){console.log("Yay, managed to toss a 
"+a+".")}function logFailure(a){console.log("Tossed a "+a+". Too bad, couldn't roll a 
six")}tossASix().then(null,logAndTossAgain).
then(null,logAndTossAgain).then(logSuccess,logFailure);
```

### Caching
Caching is het tijdelijk opslaan van bestanden (zoals CSS en afbeeldingen) van een website, zodat deze bij het opnieuw bezoeken van de pagina niet meer gedownload hoeven te worden. Dit heeft als voordeel dat gebruikers die een pagina twee keer laden, veel minder lang hoeven te wachten.

### Afbeeldingen bestandstype
Een bestandstype is wat een computer gebruikt om bits (1 & 0) te lezen. Zo weet een computer bijvoorbeeld hoe hij een .jpeg bestand (die bestaat uit 1 en 0'en) kan omtoveren naar pixels met kleuren. Omdat .jpeg al een oud bestanstype is bestaan er tegenwoordig nieuwere bestandstypen, die minder bits nodig hebben voor hetzelfde resultaat (pixels). Een voorbeeld hiervan is .webp. Het enige nadeel hieraan is dat deze nog niet door elke browser ondersteund wordt. 

### First view
Een nieuwere technologie is First View. Dit zorgt ervoor dat de gebruiker al wel de site te zien krijgt, zonder dat deze compleet geladen is. Stel dat een pagina uit 10.000 pixels hoogte bestaat, maar er maar 700 pixels hoog op een telefoon passen. Dan heeft het geen zin om alle 10.000 pixels eerst te laden, maar is het veel sneller om eerst de eerste 700 pixels hoogte te laden en weer te geven, en dan pas de rest.

## Conclusie
Er zijn een hoop technieken om de performance van je website te verbeteren. Dit doe je door eerst te kijken waar het probleem (de lange laadtijd) aan ligt, en dan te kijken hoe je dit gaat oplossen. Als je op je website veel afbeeldingen gebruikt, is het verstandig om te switchen naar een modernere bestandstype.

Al met al is het heel belangrijk om de performance van je website te verbeteren. Hoe beter de performance, hoe meer bezoekers
 
###  Recourses
- [https://www.imperva.com/learn/performance/minification/](https://www.imperva.com/learn/performance/minification/)
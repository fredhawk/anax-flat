Snabbhet och användbarhet
============================

### Urvalet

Jag valde de tre sidorna som jag har i färganalysen. Har lagt till en extra större mediasida för att se hur belastningen ökar. Hoppas kunna få en djupare förståelse för skillnaderna mellan dem, vad de gör bra och vad de kan arbeta mer med.

Har använt Chrome Audits tab för att ta reda på hur lång tid det faktiskt tar innan användaren ser något på skärmen och kan börja använda sidan. Den ger också en del förbättringsförslag. Har också använt Google Pagespeed Insight för att se vad den ger för värden.
Använde Chrome Devtools för att se hur många requests den gör till servern och på hur mycket.
Laddar allt på 3G för att ha en bas och mer realistisk test hastighet eftersom många är på mobiler världen över med inte så snabbt internet.
Gjorde 3 mätningar per hemsida och tog sedan genomsnittet.

[Raw data](https://docs.google.com/spreadsheets/d/1ZwXArCIgMIgqP_Bzh38s8F7E1plsD__mO3l47RDH-3A/edit?usp=sharing)

--------------------------------------

## [Aftonbladet](https://aftonbladet.se)

[FIGURE src="image/aftonbladet.jpg?w=c12&cf" class="center"]

|                                                            | Betyg Desktop | Betyg Mobil | First Render time | First interactive time | Antal Requests | Total Storlek |
|------------------------------------------------------------|:-------------:|:-----------:|:-----------------:|:--------------------:|:--------------:|:----------------:|
|[aftonbladet.se](https://aftonbladet.se)|72.7|62.7|2.19s|16.69s|191|3.53MB|
|[Artikel med text](https://www.aftonbladet.se/bil/a/Kv3aWe/sa-mycket-dyrare-blir-formansbilen)|74.0|62.7|2.12s|8.21s|88|1.1MB|
|[Artikel med text och video](https://www.aftonbladet.se/nyheter/a/MgRepB/snon-slar-till-mot-landvetter--flygtrafiken-stangdes-av)|73.7|62|2.03s|8.32s|94|1.17MB|

#### Förbättringsförslag
Sidan laddar någorlunda snabbt med tanke på att det är en mediasida. Dock kan de optimera bilderna mycket mer och minifiera sin HTML. Vidare så kan de göra något åt de scripten som blockerar renderingen av sidan.

## [Microsoft](https://www.microsoft.com/sv-se/)

[FIGURE src="image/microsoft.jpg?w=c12&cf" class="center"]

|                                                            | Betyg Desktop | Betyg Mobil | First Render time | First interactive time | Antal Requests | Total Storlek |
|------------------------------------------------------------|:-------------:|:-----------:|:-----------------:|:--------------------:|:--------------:|:----------------:|
|[microsoft.com](https://www.microsoft.com/sv-se/)|86|67|2.13s|6.71s|51|0.67MB|
|[Produktsida](https://www.microsoft.com/sv-se/store/d/xbox-one-x-1tb-console/8NQ33JVV1S9V?WT.mc_id=XB1X_PO_092017)|51|41|3.19s|14.08s|102|4.1MB|
|[/windows/](https://www.microsoft.com/sv-se/windows/)|53.3|42.7|5.89s|18.11s|58|2.5MB|

#### Förbättringsförslag
Sidan laddar någorlunda snabbt med tanke på att det är en mediasida. De kan optimera bilderna mycket mer och minifiera sin HTML. Vidare så kan de göra något åt de scripten som blockerar renderingen av sidan. Man kan också aktivera komprimering på en del av deras resurser för att minska storleken på requests.

## [Sarah Drasner](https://sarahdrasnerdesign.com/)

[FIGURE src="image/sadrasner.jpg?w=c12&cf" class="center"]

|                                                            | Betyg Desktop | Betyg Mobil | First Render time | First interactive time | Antal Requests | Total Storlek |
|------------------------------------------------------------|:-------------:|:-----------:|:-----------------:|:--------------------:|:--------------:|:----------------:|
|[sarahdrasnerdesign.com](https://sarahdrasnerdesign.com/)|89|84|2.14s|4.26s|11|0.7MB|

#### Förbättringsförslag
Man kan använda cache för att snabba på laddningen vid besök 2 och framåt. Använda mindre renderingsblockerande script kan vara bra.
Detta är en single page application så allt visas på första sidan. Finns inga länkar till undersidor. Det kan göra att första renderingen blir lite långsammare men navigering runt på sidan blir snabbare. Väldigt bra resultat överlag på denna sidan och den är märkbart snabb.

## [Helsingborgs Dagblad](https://www.hd.se/)

[FIGURE src="image/hd.jpg?w=c12&cf" class="center"]

|                                                            | Betyg Desktop | Betyg Mobil | First Render time | First interactive time | Antal Requests | Total Storlek |
|------------------------------------------------------------|:-------------:|:-----------:|:-----------------:|:--------------------:|:--------------:|:----------------:|
|[hd.se](https://www.hd.se/)|59.7|49|4.09s|35.67s|36|1.1MB|
|[Artikelsida](https://www.hd.se/2017-12-10/1500-dags-for-festernas-fest-folj-nobelfesten-direkt)|79|52.7|2.41s|23.86s|181|5.73MB|
|[/helsingborg/](https://www.hd.se/helsingborg)|71.3|54|3.19s|3.5s|35|0.69MB|

#### Förbättringsförslag
Sidan laddar snabbt med tanke på att det är en mediasida. Men så fort det är något med video med i bilden så går det avsevärt långsammare. De kan göra något åt de scripten som blockerar renderingen av sidan. De kan använda caching

------------------------------

### Sammafattning

De vanligaste förbättringsförslagen är att optimera bilder, använda caching och att inte använda script som blockerar rendering

1. [microsoft.com](https://www.microsoft.com/sv-se/)
2. [sarahdrasnerdesign.com](https://sarahdrasnerdesign.com/)
3. [aftonbladet.se](https://aftonbladet.se)
4. [hd.se](https://www.hd.se/)

Snabbast laddade Microsfts sida. Verkligen imponerande med tanke på att det är mycket som händer på sidan. Det ska dock nämnas att Sarah Drasner har väldigt höga poäng i övrigt och slår alla på alla andra mätningar så kanske den sidan borde vara överst.
Ingen sida tog sig under barriären på 2 sekunder till första rendering.

Ungefär 1 sekund till första rendering tycker jag är vad man ska sikta på men 2 sekunder anser jag vara ok på en 3G uppkoppling.

Jag har arbetat själv.
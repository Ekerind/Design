---
Title: Laddningstid
Description: Laddningstid
Template: analysis-single
---

<div class="nav">
    <ul class="submenu">
        <li><a href="./01_colors">FÄRGANALYS</a></li>
        <li class="active"><a href="./02_load">LADDNINGSTID</a></li>
        <li><a href="./03_design_principles">DESIGNPRINCIPER</a></li>
    </ul>
</div>

# Analys av laddningstider

I rapporten analyseras tre webbplatser gällande hur snabbt de laddar. Vad är det som tar längst tid? Vilken är snabbast? Hur skulle webbplatserna kunna förbättras?

## Urval

Webbplatserna som ligger till grund för rapporten är av olika karaktär. Det är en personlig blog, en företagssida och en kommunal sida. Urvalet är gjort för att kunna jämföra hur aktörer med olika syften prioriterar utvecklandet av en snabbladdad webbplats. Den personliga bloggen, *Underbara Clara*, valdes ut slumpmässigt från en lista över de 10 mest populära bloggarna i Sverige. Företagssidan tillhör min arbetsgivare *RISE* och valdes för att ge mig inblick i hur den presterar. Den kommunala hemsidan som till hör *Malmö Stad* valdes för att det var den första kommunala sidan som dök upp som hade flera olika element och bilder. En ganska påklädd webbplats jämfört med många andra avskalade kommunala webbplatser.

## Metod

Analysen utförs genom att testa tre olika sidor på respektive webbplats mot Google [*PageSpeed*](https://pagespeed.web.dev/). Testerna utförs både för mobil och dator. Via fliken *nätverk* i utvecklingsmodulen i Chrome sammanställs hur lång tid det tar för varje sida att ladda samt mängden data som hämtas. Varje test görs tre gånger och resultatet presenteras i tabell 1. Webbplatserna rangordnas baserat på poängen de får. Eventuella förbättringsåtgärder presenteras utifrån presenterade resultat med utgångspunkt på PageSpeed Insights Rules[1].

## Resultat

Här följer en sammanställning av resultatet. Respektive webbplats finns representerad i en separat flik i tabell [1]. Länkar till respektive webbsida finns längst till höger i tabellen.  

**Tabell 1.** Tre försök per sida där medelvärdet presenteras i de vita raderna.
<iframe width=100% height=370px src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRnFG3HBoB1pJjcMKhWzt1wZfvt48vaL1Afh5pykFQouZjRhtYK1kqwudNfZ6TDydkHki6hMW0JSsSo/pubhtml?widget=true&amp;headers=false"></iframe>

Samtliga sidor kunde förbättre sin prestanda genom att uppdatera till modernare bildformat. Vid närmare inspektion i Chrome så använder *Underbara Clara* och *RISE* sig till stor det av webp så det är troligen främst *Malmö Stad* som kunde tjäna på att uppdatera bildformat. Det tillsammans med att reducera JavaScript som inte används var de åtgärder som kunde snabba upp hämtningen av webbsidan mest. *Malmö Stad* skulle även kunna skjuta upp inläsning av bilder som inte visas på skärmen samt aktivera text-komprimering.

## Analys

Ett genomgående tema var att den mobila hemsidan fick betydligt lägre poäng än sidan anpassad för en dator. Anledningen till att poängen skiljer sig så mellan mobil och dator för samma sida kan vara kopplat processorkraft för JavaScript och liknande, eller CSS-regler som *media*, val av rätt storlek på bilder osv. Jag är förvånad över hur snabbt sidorna ändå laddas. Samtliga låg under tre sekunder, vilket jag nog skulle säga är en gräns man vill uppnå.

### Rangordning:

**1. RISE**

![Bild på hemsidan RI.SE](%base_url%/image/rise.png?width=30%&save-as=jpg)

*RISE* var den sidan som fick bäst betyg från PageSpeed. Generellt verkar webbplatsen använda sig av bra anpassade bilder och utan onödiga tillägg. Det var få resurser som hämtades på samtliga sidor vilket gjorde processen snabb. Det kan vara ett smart val, särskilt på landningssidan. Då får besökaren ett bra första intryck. Även mängden data som hämtades var relativ liten sett till sidans utseende. Även det snabbar såklart på hemsidan och är bra i miljösynpunkt. Samtliga sidor som valts ut på webbplatsen laddade på omkring en sekund. Det känns orimligt att begära kortare laddningstid än så.  

<br>
<br>
<br>

**2. Malmö Stad**

![Bild på hemsidan för Malmö Stad](%base_url%/image/malmostad.png?width=40%&save-as=jpg)

*Malmö Stad* hamnar på en andra plats. Det var ganska jämt mellan dem och bloggen *Underbara Clara* vad gäller prestanda på datorer, men Malmö Stad fick klart högre betyg när det kom till användning på mobilen. Jag är förvånad över att webbplatsen är så snabb på att ladda som den är. Det känns som att det är mycket som händer på den, men många bilder och grafik. De verkar ha gjort ett bra arbeta med att hålla nere datamängden och laddningstiderna. I dagsläget använder de sig av jpg och det verkar fungera relativt bra. Möjligen skulle en uppdatering till bildformatet webp göra webbplatsen ännu lite bättre. En sak som utmärkte webbplatsen var att både den mobila sidan och den för datorer kunde spara in laddningstid genom att aktivera textkomprimering.

<br>

**3. Underbara Clara**

![Bild på hemsidan Underbara Clara](%base_url%/image/underbaraclara.png?save-as=jpg)

På tredje plats kom bloggen *Underbara Clara*. Det var ändå bättre resultat än vad jag hade förväntat mig med tanke på alla bilder som presenteras. Webbplatsen verkar ha löst det med att sidan laddas in lite i taget varpå besökaren rör sig ner i flödet. Bilderna verkar i stort utsträckning vara i formatet webp vilket hjälper till att hålla storleken på hemsidan nere. Vid närmare inspektion så använder sig webbplatsen av responsiva bilder med hjälp av &lt;picture&gt; och srcset. På så sätt väljs en anpassad bild för varje skärm, både estetiskt tilltalande och för att hålla nere mängden data. Trots det var det den här webbplatsen som hämtade hem mest data. Det är nog svårt att undvika när det rör sig om en foto-blogg. Det som gör att webbplatsen hamnar sist är de låga poängen från PageSpeed för mobil. Jag är lite förvånad över att det var så lågt men i efterhand så tror jag att en bidragande orsak kan vara mängden CSS-regler som ändrar bilder. PageSpeed uppmanar dock att använda bilder av rätt storlek, så kanske kan det bara så att webbplatsen är mer anpassad för surfplattor och datorer snarare än mobiler.

## Referenser

[1] https://developers.google.com/speed/docs/insights/rules 2022-12-04

## Övrigt

Skrivet av Mattias Ekerind.

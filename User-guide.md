 
FleetOptimiser Brugervejledning
Denne vejledning gennemgår de væsentligste funktioner i FleetOptimiser trin for trin. Vejledningen gennemgår de to simuleringsværktøjer, automatisk- og manuel simulering, samt Dashboards, som er et Business Intelligence-modul, hvor kørselsdata udstilles i forskellige visninger. 
Brugervejledningen opdateres løbende, efterhånden som der tilføjes ny og ændret funktionalitet i FleetOptimiser.
Har du spørgsmål eller forslag til forbedring af brugervejledningen? Send en mail til fleetoptimiser@aarhus.dk. 
1. Indholdsfortegnelse
2. Login til FleetOptimiser
3. Simuleringssetup
Under simuleringssetup bliver du introduceret til FleetOptimisers hovedside, hvor du vælger lokationen du gerne vil simulere på, samt indstiller den dataperiode du gerne vil simulere på.
4. Manuel simulering
Her kan du læse mere om hvordan du laver manuelle simuleringer på en bestemt lokation, hvor du selv tilføjer og fjerner køretøjer i en simulering.
5. Automatisk simulering
Her kan du læse mere om hvordan du bruger målsimuleringen, hvor den kunstige intelligens foreslår den mest optimale flådesammensætning på en given lokation ud fra nogle parametre du selv kan indstille
6. Simuleringshistorik
Her kan du læse om hvordan du finder tidligere simuleringer frem igen, som FleetOptimiser har gemt for dig, både fra flådesammensætning og målsimuleringer.
7. Dashboards
Her kan du læse mere om business intelligence-modulet i FleetOptimiser, hvor kørselsdata udstilles i forskellige visninger.
8. Konfiguration
Her kan du læse mere om konfigurationspanelet, hvor du opretter nye køretøjer, kan tilføje og rette metadata på køretøjerne, f.eks. mærke og model, brændstofforbrug, CO2-udledning og omkostninger.


Du kan navigere mellem kapitlerne ved at klikke på knappen i nederste højre hjørne af skærmen.
 
2. Login til FleetOptimiser
FleetOptimiser er webbaseret og tilgås via din browser, f.eks. Microsoft Edge, Google Chrome, Firefox osv. 
Du modtager et link fra Droids Agency, med følgende adresse: https://[myndighed].fleetoptimiser.droidsagencyai.com/https://[myndighed].fleetoptimiser.droidsagencyai.com/
FleetOptimiser er for de fleste integreret til KOMBITs administrationsmodul/adgangsstyring, med single sign-on, som gør at du ikke skal indtaste en adgangskode, så længe du tilgår FleetOptimiser via din arbejds-PC. Benytter du Firefox som browser, skal du dog taste din adgangskode hver gang.
Er din myndighed ikke integreret til KOMBITs adgangsstyring, skal du indtaste brugernavn (e-mail) og adgangskode i felterne.
[FOR MYNDIGHEDER MED KOMBIT SSO] Har du kolleger, som skal have adgang til FleetOptimiser, skal du kontakte jeres lokale brugeradministration, som kan tildele rettigheder til systemet via KOMBITs adgangsstyring.
 
1 - Klik på knappen Sign in with Keycloak
 
2 - Indtast brugernavn og adgangskode eller vælg KOMBIT SSO, hvis din myndighed har valgt login til FleetOptimiser via KOMBITs adgangsstyring.
 
3 - KUN FOR KOMBIT SSO
1.	Find din myndighed på listen
2.	Klik på OK.
3. Simuleringssetup
Den første side man møder i FleetOptimiser, er Simuleringssetup. Her vælger du de(n) lokation(er) du gerne vil simulere på, simuleringsperioden samt hvis du kun vil simulere på specifikke køretøjer på den valgte lokation. Hvis du simulerer på flere lokationer på samme tid, vil algoritmerne betragte det som værende én fælles flåde, hvor alle ture kan fordeles mellem alle køretøjer i simuleringen uanset deres faktiske start- og slutlokation.
Sådan kommer du i gang:
1.	Vælg de(n) lokation(er) du gerne vil simulere på.
2.	Indstil simuleringsperioden. Du kan simulere på data op til to år tilbage i tid.
3.	Vælg de biler du vil medtage i simuleringen, ved at klikke på knappen vælg alle eller vælg specifikke biler ved at sætte flueben i kolonnen medtag i simulering. 
4.	Vælg om du vil lave manuelle simuleringer, hvor du selv kan tilføje og fjerne køretøjer eller automatiske simuleringer, hvor værktøjet kommer med et forslag til sammensætningen af køretøjer.
 
4. Manuel simulering
I manuel simulering kan du manuelt tilføje og fjerne køretøjer i simuleringerne. Udgangspunktet for simuleringen er de køretøjer, som er på lokationen/-erne i forvejen. I dette simuleringsværktøj kan du f.eks. undersøge om der er overkapacitet ved at fjerne en eller flere køretøjer, se hvor stor en del af turene der kan køres på cykel ud fra en række parametre du selv kan indstille, eller teste nye bilmodeller, som I overvejer at anskaffe ift. bl.a. rækkevidde, ladetid, CO2-udledning og økonomi.
Sådan kommer du i gang:
1.	Klik på simulér, for at få et overblik over de ture der bliver kørt i dag, med den nuværende flådesammensætning.
2.	I kolonnen antal i simulering, kan du prøve at fjerne en eller flere biler fra delflåden. Klik herefter igen på simulér for at få simuleringsresultatet på baggrund af den nye simulerede flådesammensætning.
3.	Her kan du indstille vagtlag for simuleringerne, hvor en bil "låses" til hele det tidsrum du vælger, således at simuleringerne i højere grad afspejler virkeligheden hvor medarbejderne ikke nødvendigvis kan bytte bil hver gang bilen er på hjemlokationen i løbet af en vagt.
4.	Her kan du tilføje testkøretøjer til simuleringen, hvis du vil prøve at simulere med cykler eller andre bilmodeller end dem der er på lokationen i forvejen. Du kan oprette nye biler under fanebladet konfiguration i venstre side.
5.	Hvis du vil simulere med cykler, kan du indstille en række parametre for disse, bl.a. maksimal rutelængde, gennemsnitshastighed, samt indstille hvilke tidsrum ruter må tildeles til cykler, f.eks. hvis cykler kun må tildeles til ruter i dagtimerne.
6.	Intelligent allokering og begræns km/år
a.	Hvis du aktiverer intelligent Allokering, aktiveres en optimeringsalgoritme, der forsøger at planlægge allokeringen af køretøjer på den mest optimale måde. Dvs. en måde hvor der både spares på økonomi og CO2e udledning. Der laves så og sige en afvejning mellem udledning og omkostning, eksempelvis ved at allokere de køretøjerne med den laveste CO2-udledning og laveste omkostning til de længste ture. 
b.	Hvis du aktiverer begræns km/år, vil simuleringen tage højde for at kilometertallet pr. år ikke overstiger det tilladte, for køretøjer med et max antal km/år på leasingaftalen. Du kan indtaste oplysninger om max km/år under fanebladet konfiguration.
7.	Her kan du ændre værdierne der danner grundlaget for udregning af de samlede omkostninger samt CO2-udledningen.
 
Simuleringsindstillinger
Simuleringsindstillingerne danner grundlag for udregning af de samlede omkostninger samt udledning af CO2-ækvivalenter (CO2e). Du kan selv ændre værdierne samt vælge om ændringerne kun skal gælde for den aktuelle simulering eller for alle lokationer. CO2e for el, benzin og diesel er taget fra Miljøstyrelsens/SKI's TCO-værktøj til grønne indkøb af køretøjer.
•	Udledning, CO2e afhængige variabler: definerer hvor mange kg CO2e hhv. én kWh, én liter benzin og én liter diesel udleder.
•	Drivmiddel priser: definerer hvor meget én kWh, én liter benzin og én liter diesel koster
•	Samfundsøkonomiske omkostninger (klimaafgift): Værdisætning af CO2 / omkostning pr. ton CO2e udledt pba. afledte effekter.
•	Køretøjsskifte: Minimumstiden der skal gå fra en tur slutter og til en ny kan starte på et køretøj.
•	Medarbejderbil: de ukørte ture der måtte være i simuleringerne allokeres til en medarbejderbil, som sikrer at det ikke er gratis på hverken omkostning eller CO2-udledningen at have ukørte ture. I indstillingerne kan du bestemme, hvor meget medarbejderen kompenseres pr. kørt km. samt hvilken type bil (benzin, diesel, el) medarbejderen kører i. 
 
Datavisualiseringer Manuel simulering
I bjælken over diagrammerne, kan du se konsekvenserne af den ændrede allokering af køretøjer til ruterne samt den ændrede flådesammensætning ift. antallet af ruter som evt. ikke vil blive kørt med den ændrede flådesammensætning, potentiel besparelse eller øgede omkostninger samt den ændrede CO2-udledning pr. år.
1.	Antal ture uden køretøj: Viser antallet af ture på en given dag, som ikke vil blive kørt med den aktuelle flådesammensætning i simuleringen. Ved at trykke på Skift graf, vises antallet af de ikkeallokerede ture nu fordelt på ugedage.
2.	Turfordeling for nuværende flåde: Viser hvordan turene er blevet kørt i virkeligheden, fordelt på gennemsnitlig rutelængde og type af køretøj. X-aksen viser den gennemsnitlige rutelængde. Y-aksen viser antallet af ture af en given gennemsnitlig rutelængde.
3.	Turfordeling for simuleret flåde: Viser fordelingen af ture, som algoritmerne vil foreslå at turene var blevet kørt ud fra en klimamæssig og økonomisk mest hensigtsmæssig betragtning samt eventuelle ture som ikke kan køres med den ændrede sammensætning og allokering af køretøjer.
4.	Download resultater: Her kan du downloade simuleringsresultaterne til Excel. Filen indeholder både den faktiske kørsel samt simuleringsresultaterne, så du f.eks. kan sammenligne direkte mellem dem.
 
5. Automatisk simulering
På denne side foretages den automatiserede simulering, der på baggrund af det faktiske kørselsmønster vil foreslå de mest optimale flådesammensætninger. Formålet er at tilfredsstille kørselsbehovet, men med en grønnere og/eller mere økonomisk bæredygtig flådesammensætning. Optimeringsalgoritmen vil forsøge at finde frem til løsninger og præsentere de op til fem bedste løsninger ud af potentielt flere tusinde forskellige kombinationer.
Sådan kommer du i gang med den automatiske simulering:
1.	Her kan du styre hvad algoritmerne skal prioritere: Mest mulig CO2-reduktion (10) eller størst mulig økonomisk besparelse (0) eller 50/50 mellem de to parametre.
2.	Algoritmen i målsimulering vil ikke skifte biler med gyldig leasingaftale ud, medmindre de er i overkapacitet. Du kan manuelt vælge specifikke køretøjer, som gerne må skiftes ud med andre alternativer, og på den måde give algoritmen mere råderum. 
3.	Her kan du lave de samme indstillinger, som i manuel simulering, f.eks. tilføje en specifik bilmodel eller cykler, som du gerne vil teste i simuleringen. Hvis ikke du foretager nogle ændringer, vil alle køretøjer i din database blive en del af simuleringen. 
4.	Klik på optimér, når du har lavet dine indstillinger for målsimuleringen.
5.	Når simuleringen er slut, præsenteres op til fem forskellige forslag til en ændret flådesammensætning, med udgangspunkt i den faktiske kørsel og ud fra de indstillinger du har lavet. Du har for hvert forslag mulighed for at hente resultaterne ned i excel.
 
Scenarier for resultater af den automatiske simulering
Løsningerne indeholder færre køretøjer
Algoritmen har regnet sig frem til at kørselsbehovet kan tilfredsstilles med færre køretøjer end der er i den nuværende delflåde.
Sker dette scenarie i din optimering, er det et tegn på, at der i flåden har overkapacitet. Eller i hvert fald kan turene planlægges på en anden måde med færre tilgængelige køretøjer. Du kan gå til manuel simulering og forsøge at justere antallet af køretøjer en for en for at undersøge nærmere, hvornår du rammer punktet for underkapacitet på lokationen.
Der er ingen ændringer
Hvis simuleringen foreslår blot en enkelt løsning (eller få løsninger med en/flere cykler), som er en-til-en den samme som den nuværende flåde, er det et tegn på, at der mangler fleksibilitet i opsætningen. Det vil typisk skyldes, at kørselsbehovet lige netop kan tilfredsstilles af den mængde køretøjer, der er i den nuværende flåde. Derfor er den nuværende flådesammensætning umiddelbart den rette.
Ønsker du stadig, for den pågældende lokation, at få forslået andre løsninger, kan du frigøre køretøjer fra simuleringen (se pkt. 4 ovenfor).
Løsningen indeholder flere køretøjer
I tilfælde hvor du har slået 'begræns km/år' til, kan du risikere, at simuleringsresultatet bliver dyrere og udleder mere co2.  Det skyldes, at den faktiske kørsel overstiger de angivne km på leasing-aftalerne. I en sådan situation vil algoritmen tilføje ekstra køretøjer, så kørselsbehovet dækkes uden at overskride de angivne km-værdier. 
Problemet kan løses ved at justere køretøjernes km-antal i konfigurationen.
Datavisualiseringer i automatisk simulering
Værdier:
1.	Besparelse (DKK/år): Den samlede økonomiske besparelse for den højest rangerede løsning. 
2.	Reduktion udledning (Ton Co2e/år): Den samlede årlige CO2e-besparelse for den højeste rangerede løsning. Tallet er beregnet vha. miljøstyrelsens TCO-værktøj, hvorfra det udvalgte køretøjs allokerede ture, er udgangspunkt for det enkelte køretøjs årlige CO2e. 
3.	Årlig omkostning i kr.: Oversigt over totale omkostninger for den nuværende flåde samt de forslåede løsninger. Der vises de samlede omkostninger inkl. omkostninger til drivmiddel.
4.	Årlig udledning ton CO2e: Oversigt over CO2e-udledningen for den nuværende flåde  og de foreslåede løsninger. Udledningen er summeret til et helt år, uanset valg af dataperiode i simuleringssetup. De allokerede ture til de forskellige køretøjer ligger til grund for udregningen.
 
6. Simuleringshistorik
I simuleringshistorik, kan du finde tidligere simuleringer frem igen, hvis du har brug for at vende tilbage og finde nogle tidligere scenarier. I historikken gemmes også de indstillinger du måtte have lavet i simuleringerne.
1.	Klik på simuleringshistorik
2.	Vælg den simulering du gerne vil arbejde videre på. Simuleringerne er opdelt i flådesammensætning og målsimulering i oversigten.
 
7. Dashboards
Her kan du læse mere om business intelligence-modulet i FleetOptimiser, hvor kørselsdata udstilles i forskellige visninger. Du kan blandt andet se CO2-udledningen i en given periode fra samtlige køretøjer der er oprettet i FleetOptimiser, hvor mange procent af kørslen der er kørt i elbil, antal km pr. vagtlag for en lokation eller et specifikt køretøj, samt få et overblik over anvendelsesgraden udstillet som et heat map. 
I barren over graferne kan du indstille filtre for visninger af data, herunder dataperiode og lokation. For kørsel, køretøjsaktivitet og turoverblik kan du desuden filtrere på køretøjer, afdelinger og vagtlag.
Overblik
I overblik kan du finde tre grafer. Den øverste graf viser CO2-udledningen pr. dag, den midterste viser hvor stor en procentdel af kørslen, som er kørt i elbil, mens den nederste graf viser det samlede antal kørte km. Fælles for de tre grafer gælder at du kan få vist data for alle køretøjer der er oprettet i FleetOptimiser, eller en eller flere specifikke lokationer i den valgte dataperiode.
 
4 - Dashboard Overblik
Kørsel
I kørsel kan du få overblik over det gennemsnitlige antal kørte km pr. dag pr. bil i den valgte dataperiode på en given lokation eller afdeling, hvis der er flere afdelinger på samme lokation. Du kan også få overblik over antal km i et givent tidsrum, fx pr. vagtlag i hjemmeplejen.
Herudover kan du se det samlede antal kørte km pr. måned, samt antal km pr. dag pr. vagtlag på lokationen, afdelingen eller for specifikke køretøjer.
 
5 - Dashboard Kørsel
Køretøjsaktivitet
I køretøjsaktivitet kan du få et hurtigt overblik over hvor meget køretøjerne er i brug på daglig basis, og dermed hvor godt flåden er udnyttet. Data er udstillet som et heat map, hvor  farven bliver mørkere jo tættere antallet af kørte km kommer på 0, og køretøjerne dermed ikke udnyttes optimalt. 
Du kan selv indtaste en grænseværdi for hvad der er optimal udnyttelse af køretøjerne og farverne justeres herefter. Du kan få vist data pr. lokation, afdeling, forvaltning eller specifikke køretøjer. Køretøjsoverblik kan trækkes ud som Excel-fil, baseret på de valgte filtre.
 
6 - Dashboard Køretøjsaktivitet
Tidsaktivitet
I tidsaktivitet kan du, ligesom i køretøjsaktivitet, få et hurtigt overblik over hvor meget køretøjerne er i brug på daglig basis, men baseret på tid i stedet for antal kørte km. Data er udstillet som et heat map, hvor farven bliver mørkere jo tættere antallet af kørte km kommer på den valgte grænseværdi eller overstiger grænseværdien. Jo højere tallet er, jo bedre udnyttes køretøjet.
Du kan selv indtaste en grænseværdi for hvad der er optimal udnyttelse af køretøjerne og farverne justeres herefter. Du kan få vist data pr. lokation, afdeling, forvaltning eller specifikke køretøjer. 
 
7 - Dashboard Tidsaktivitet
Turoverblik
Her kan du få overblik over ruternes længde, varighed, antal stop på ruten og hvor stor en del af tiden køretøjerne holder stille på ruten. Indtast maks. distance, for at filtrere lange ruter fra og minimum parkeringstid for at filtrere ruter fra med korte pauser, fx ruter i hjemmeplejen med mange korte stop.
 
8 - Dashboard Turoverblik
Ledighed
Her kan du få en grafisk repræsentation af ledige køretøjer i en given tidsperiode, dvs. hvor mange køretøjer har stået stille og ikke været i gang med en rundtur. Det anbefales at sætte tidsperioden til en, maks. to dage, da visualiseringen ellers bliver uoverskuelig. 
 
9 - Dashboard: Ledighed
8. Konfiguration
Under fanen Konfiguration finder du indstillinger for Køretøjer og Lokationer. Vær opmærksom på, at ændringer i disse moduler vil medføre ændringer for samtlige brugere i din organisation. 
Køretøjer
Her vises et overblik over alle de køretøjer, der er oprettet i FleetOptimiser. Her kan du både finde de køretøjer, der er hentet via integrationen til jeres flådestyringssystem, samt de testkøretøjer I selv har oprettet. Det er også i konfiguration, at I kan udfylde og rette i metadata på køretøjerne, samt flytte et køretøj fra én lokation til en anden. Det er ikke alle flådestyringssystemer, som udstiller metadata på køretøjerne. Derfor kan det være nødvendigt selv at udfylde de manglende data. 
Sådan gør du:
1.	Klik på konfiguration
2.	Hvis du vil søge et specifikt køretøj frem, kan du enten åbne søgefeltet ved at klikke på søgeikonet, eller aktivere filterfunktionen ved at klikke på filtreringsknappen
3.	Vælg køretøjet du gerne vil redigere, ved at klikke på blyantsikonet.
4.	Indtast de nødvendige metadata i felterne og klik opdater. Du kan se en oversigt over nødvendige metadata i afsnittet nedenfor
5.	Hvis I har udfaset et køretøj, men fortsat gerne vil kunne simulere på historiske data, kan I deaktivere hentning af nye GPS-data ved at klikke på det grønne elstik.
6.	Er en bil blevet flyttet fra én lokation til en anden, men I har glemt at rette det, kan I flytte turene til den nye lokation, fra en given dato ved at klikke på waypoint-ikonet.
7.	Hvis du vil tilføje et testkøretøj eksempelvis hvis I står overfor et udbud på nye biler eller vil simulere med cykler, kan I oprette nye køretøjer ved at klikke på knappen.
8.	Ønsker du at slette et køretøj, gøres det ved at trykke på skraldespandsikonet. Køretøjet bliver ikke slettet før, du bekræfter ved at trykke på Gem ændringer. Her kan du vælge om du også vil slette alle køretøjets ture.
9.	FleetOptimiser sletter automatisk ture der er over to år gamle. Hvis I vil ændre til at slette ture efter kortere tid, kan I ændre indstillingerne ved at klikke på knappen slet tur.
 
 
Oversigt over nødvendige data for at kunne simulere med FleetOptimiser
•	Mærke: mærket på køretøjet. Minimum en karakter.
•	Type: Vælg mellem 4 kategorier; cykel, elcykel, elbil eller fossilbil fra dropdown-menuen
•	Drivmiddel: Vælg mellem benzin, diesel, el, brint, hybrid, plug-in hybrid, HVO. Hvis det er en cykel, vælg da kategorien bike, som findes nederst i menuen.
•	WLTP: Her udfyldes blot én af de to; WLTP (fossil), WLTP (el). Her er enheden hhv. km/L og Wh/km. Er køretøjet en cykel skriv da 0 i et af felterne.
•	Omkostninger pr. år: Den årlige faste omkostning på køretøjet. Her er snak om alle de udgifter man er sikker på at have, men eksklusiv omkostninger til brændstof/el (meget vigtigt, da det beregnes af FleetOptimiser). Det er vigtigt, at der på tværs af køretøjerne indregnes de samme ting, f.eks. leasingydelse, forsikring, afgift for at have et godt sammenligningsgrundlag.
•	Lokation: Hvilken lokation køretøjet er tilknyttet. Dette er ikke nødvendigt for testkøretøjer 
Der er ikke mulighed for selv at indtaste lokationer, da det sker ifm. implementering af datajob. Hvis I ønsker at tilføje en lokation i FleetOptimiser, kontakt da supporten hos Droids Agency.
Har man udfyldt et Excel-ark med det påkrævede metadata, kan dette let kobles med data fra flådestyringssystemerne, såfremt at man i systemet har indtastet f.eks. nummerplade eller et id det kan linkes op på. Send Excel-arket til supporten i Droids Agency hvis I vil indlæse data på denne måde.
Du kan få et overblik over køretøjerne i Excel ved at trykke på linket over tabellen; Download til .xlsx.
Lokationer
Det primære formål med lokations-indstillingerne er at få et overblik over aggregerings-præcisionen, dvs. hvor mange % af kørslen på en given lokation der samles til færdiggjorte rundture. Alle kørte km samles og medregnes i simuleringer, men når kørsel samles til rundture, bliver resultaterne mere præcise. Præcisionen dækker over den seneste måneds data, og opdateres hver gang, du logger ind. Ved ændringer kan der gå op til en måned, før du kan se den fulde effekt. 
En lav præcision kan bl.a. skyldes, at lokationer ligger for tæt på hinanden geografisk, at parkeringspunktet er sat forkert, eller at køretøjet har flere parkeringspunkter på en given lokation, som ikke er markeret. I konfigurationen har du mulighed for at tilføje og ændre parkeringspunkter, og teste om det vil påvirke præcisionen. I eksemplet nedenfor er der indsat ét parkeringspunkt og der har den seneste måned været en rundturspræcision på 48%. Ved at indsætte et parkeringspunkt på en stikvej ved siden af lokationen, øges rundturspræcisionen til 69%. Dette vil påvirke simuleringers præcision, fordi flere kørte km vil være bundet til en færdiggjort rundtur. 
 
10 - Konfiguration af lokationer: Forbedret rundturspræcision

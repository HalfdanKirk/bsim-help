<link rel="stylesheet" href="../style.css">

# Eksport til Be10

<span id="gray_background">

#### **Forbehold:**

Funktionen "Eksport til Be10" er udelukkende et hjælperedskab som kan benyttes i forbindelse med eksport af en bygningsmodel fra BSim til Be10. Det skal derfor altid checkes at "oversættelsen" er foretaget korrekt. SBi påtager sig intet ansvar for eventuelle fejl i forbindelse med oversættelsen eller brugen af bygningsmodeller som er eksporteret fra BSim til brug i Be10.

#### **Kendte problemer:**

Beregning af arealer kan indeholde mindre fejl i og omkring uopvarmede rum.

</span>

### **Generelt**

Bygningens navn, opvarmede etageareal og rotation overføres direkte. For temperaturer benyttes standardværdierne, dvs. setpunkter Opvarm. = 20 °C, Ønsket = 23 °C, Nat. vent. = 24 °C og Køling = 25 °C samt dimensionerende temperaturer Rumtemp. = 20 °C og Udetemp. = -12 °C.

Samtidig antages det at varmekapacitet er 120 Wh/K m² og at normal brugstid er 168 timer med start 0 og slut 24, dvs. svarende til en bolig.

*   For Bygningstype vælges <u>**altid** </u>"Fritliggende bolig".

*   For beregningsbetingelser vælges <u>**altid** </u>"BR: Aktuelle forhold".

*   Varmeforsyning sættes som standard til "Kedel".

### **Klimaskærm: Ydervægge, tage og gulve**

For ydervægge, tage og gulve overføres alle data.

Benævnelse: Konstruktionernes navne fastlægges på baggrund af navnet fra BSim. Hvis der er flere ens konstruktioner navngives de samlet efter navnet for den første forekomst af konstruktionen.

*   *Areal*: For lofts- og tagkonstruktioner beregnes arealet ved udvendige mål, dvs. bruttoarealet fra BSim bruges direkte.

For ydervægge beregnes arealet fra overside af gulv til overside af isolering i loft/etageadskillelse. Hvis ydervæggen er tilknyttet et rum hvor det underliggende rum er uopvarmet, regnes arealet fra underside af etageadskillelse til overside isolering i loft/etageadskillelse.

For terrændækkonstruktioner/etageadskillelser/kældergulve mv. beregnes arealet fra indvendig side af ydervæg/kælderydervæg. Hvis der er tale om en etageadskillelse over uopvarmet rum, regnes arealet fra udvendig side af ydervæg.

*   *U-værdi*: Tages direkte fra databasen i BSim.

*   *b-faktor*: b-faktorer overføres efter princippet at værdien er 1,0 for alle konstruktionstyper med undtagelse af terrændæk (konstruktionens hældning er mindre end eller lig 30 og peger mod udeklima eller jord), hvor værdien fastsættes som 0,7 (dvs. svarende til en konstruktion uden gulvvarme). Brugeren må altså selv sikre at de benyttede b-faktorer er korrekte.

*   *Klimaskærm*: Fundamenter mv. Der kan endnu ikke defineres kuldebroer mv. i BSim, og derfor overføres ingen data til dette skema i Be10.

### **Klimaskærm: Vinduer og yderdøre**

For vinduer og yderdøre kan stort set alle data fra BSim-modellen overføres direkte til Be10.

*   *Benævnelse*: Vinduer og yderdøre benævnes "WinDoor" efterfulgt af målene svarende til bredde og højde af vinduet/yderdøren.

*   *Antal*: Antallet af ens vinduer/yderdøre optælles automatisk. For at to vinduer/yderdøre er ens, skal også deres skyggeforhold være identiske.

*   *Orientering*: Orienteringen overføres direkte og angives i .

*   *Hældning*: Hældningen overføres direkte og angives i .

*   *Areal*: Arealet af vinduer/yderdøre overføres direkte.

*   *U-værdi*: U-værdien haves direkte fra databasen i BSim.

*   *b-faktor*: b-faktorer overføres altid med værdien 1,0.

*   *Ff (glasandel)*: Glasandelen beregnes direkte på baggrund af databasen.

*   *g-værdi*: g-værdien haves direkte fra databasen i BSim.

*   *Fc (solafskærmningsfaktor)*: Solafskærmningsfaktoren aflæses direkte i BSim, hvis der er defineret solafskærmning. Faktoren korrigeres ikke i forhold til et eventuelt Schedule.

#### **Klimaskærm: Vinduer og yderdøre: Skygger**

Skygger overføres mere eller mindre direkte fra BSim. De data som Be10 skal bruge er: horisontvinkel (°), udhæng (°), venstre skygge (°), højre skygge (°) og vindueshul (%).

*   *Benævnelse*: Skygger benævnes ved et tal (fortløbende startende med 1) efterfulgt af "Shading".

*   *Horisontvinkel*: Horisontvinklen tages direkte fra BSim. Den er defineret generelt under Site og kan herefter være overskrevet for hvert enkelt vindue/dør ved en horisontangivelse for den konstruktion hvori vinduet/døren er placeret (under finish). Sidstnævnte benyttes altid hvis den forekommer.

*   *Udhæng*: Udhæng bestemmes ved at hente de to værdier i Overhang; "Distance (m)" og "Depth (m)" samt vinduets/dørens højde. Herefter er udhænget i Be10 bestemt som:

$$  
\text{Udhæng} = \text{Arctan}\left(\frac{\text{Depth}}{\text{Distance} + \frac{1}{2} \cdot \text{Height}}\right) [^\circ]  
\tag{1} $$

Venstre- og højreskygger: Venstre og højreskygger overføres analogt med udhæng. Nu bruges blot "Distance (m)" og "Depth (m)" samt vinduets/dørens bredde. Formlerne som benyttes er:

$$  
\text{Venstre} = \text{Arctan}\left(\frac{\text{Depth}}{\text{Distance} + \frac{1}{2} \cdot \text{Width}}\right) [^\circ] \tag{2}  
$$

$$  
\text{Højre} = \text{Arctan}\left(\frac{\text{Depth}}{\text{Distance} + \frac{1}{2} \cdot \text{Width}}\right) [^\circ] \tag{3}  
$$

Vindueshul i %: Vindueshul i % haves stort set direkte fra BSim. I BSim hedder faktoren Recess, og beskriver hvor meget ruden er trukket tilbage i forhold til ydervæggens udvendige side. Omregningen fra BSim til Be10 er således; Vinduets bredde og højde haves fra BSim, og i formlen nedenfor indsættes den mindste værdi af disse:

$$  
\text{Vindueshul} = \frac{\text{Recess}}{\text{Min}(\text{Height}, \text{Width})} \cdot 100 [\%] \tag{4}  
$$

### **Klimaskærm: Uopvarmede rum**

For uopvarmede rum kan overføres stort set alle data.

*   *Navn*: Zonens navn tages direkte fra BSim.

*   *Bruttoareal*: Bruttoarealet tages direkte fra BSim.

*   Ventilation: Ventilationen er ikke defineret i BSim og derfor fastsættes værdien ud fra SBi-anvisning 213, hvor der skrives "Der regnes normalt med et udeluftskifte på mindst 0,3 l/s pr. m² bruttoareal i uopvarmede rum.". Værdien sættes altså lig med 0,3 l/s pr. m².

*   *Transmissionstab fra bygningen*: Bygningsdel: Navnet på bygningsdelen tages direkte fra BSim.

*   *Areal*: Arealet af bygningsdelen tages direkte fra BSim.

*   *U*: U-værdien for bygningsdelen tages direkte fra BSim.

*   *Transmissionstab til omgivelserne*: Bygningsdel: Navnet på bygningsdelen tages direkte fra BSim.

*   *Areal*: Arealet af bygningsdelen tages direkte fra BSim.

*   *U*: U-værdien for bygningsdelen tages direkte fra BSim.

### **Ventilation**

Ventilationen i Be10 er væsentligt simplificeret i forhold til i BSim.

I BSim er den samlede ventilation fordelt på systemerne Venting, Infiltration og Ventilation.

*   *Zone*: I Be10 opdeles bygningen i de termiske zoner som er benyttet i BSim modellen.

*   *Areal*: Bruttoarealet af zonen overføres direkte fra BSim.

*   *F0 (benyttelsesfaktor)*: I BSim kan der ikke angives en benyttelsesfaktor, og derfor sættes denne altid til 1,0 i Be10.

*   *qm (mekanisk ventilation om vinteren i brugstiden)*: Dette felt udfyldes kun hvis der i BSim modellen for den pågældende zone foretages indblæsning. Værdien bestemmes ved at tage indblæsningen fra BSim (m³/s), gange med 1000 (omregning fra m³ til l) og så dividere med bruttoarealet af zonen.

*   *n vgv (temperaturvirkningsgraden)*: Hvis der i BSim er angivet en maksimum temperaturvirkningsgrad for et mekanisk ventilationsanlæg, overføres denne værdi til Be10, og der tages ikke højde for minimumsværdien.

*   *ti (indblæsningstemperaturen)*: Indblæsningstemperaturen fastsættes altid som 0 °C, dvs. svarende til at anlægget er uden varmeflade og med ureguleret varmegenvinder. Brugeren må altså specificere værdien hvis anlægget ikke følger denne sammensætning.

*   *El-VF (elvarmeflade)*: Hvis der i BSim er angivet en værdi (forskellig fra 0) for Heating Coil Max Power, angives tilstedeværelsen af en varmeflade i Be10 med et 1-tal - ellers indsættes 0.

*   *qn (naturlig ventilation om vinteren i brugstiden)*: Hvis der er naturlig ventilation i bygningen, angives denne værdi som den samlede ventilation. Hvis der i stedet er balanceret mekanisk ventilation, angives alene infiltrationen. Naturlig ventilation er ikke defineret i BSim på en måde som umiddelbart kan oversættes simpelt i Be10, og derfor antages der altid i oversættelsen at der er balanceret mekanisk ventilation, og qn sættes altså lig infiltrationen alene.

*   *qi,n (infiltration om vinteren, udenfor brugstiden)*: Denne værdi benyttes kun såfremt der er tale om andet end bolig. Værdien fastsættes ud fra en eventuelt defineret infiltration udenfor brugstiden i BSim.

*   *SEL (specifikt elforbrug til lufttransport)*: SEL-værdien for ventilationsanlægget bestemmes ved den totale trykstigning (Pa) over ventilatoren divideret med den totale virkningsgrad for ventilatoren. Idet der udelukkende angives mekanisk ventilation for zoner hvor der forekommer indblæsning, vil der også kun laves beregning af SEL-værdien i disse tilfælde.

*   *qm,s (mekanisk ventilation om sommeren i brugstiden)*: Den maksimale ventilation som det mekaniske ventilationsanlæg kan yde på varme sommerdage fremgår ikke umiddelbart af beskrivelsen i BSim, og derfor sættes denne værdi lig med qm, dvs. den mekaniske ventilation om vinteren i brugstiden.

*   *qn,s (naturlig ventilation om sommeren i brugstiden)*: Den maksimale naturlige ventilation om sommeren i brugstiden bestemmes via systemet Venting i BSim. Her er angivet en værdi for Max AirChange (/h), og denne værdi omregnes til l/s pr. m² for den pågældende zone.

*   *qm,n (mekanisk ventilation om natten om sommeren)*: Mekanisk ventilation om natten om sommeren er kun relevant i forbindelse med bygninger som ikke er boliger. Værdien bestemmes ligesom den mekaniske ventilation om sommeren i brugstiden, dvs. som samme værdi som qm, dvs. den mekaniske ventilation om vinteren i brugstiden.

*   *qn,n (naturlig ventilation om natten om sommeren)*: Den naturlige ventilation om natten om sommeren er kun relevant i forbindelse med bygninger som ikke er boliger. Værdien angiver den maksimale naturlige ventilation som kan opnås om natten i varme sommerperioder. Værdien bestemmes ligesom qn,s, dvs. ud fra Max AirChange i BSim's Venting system.

### **Internt varmetilskud**

Det interne varmetilskud, som i Be10 dækker over personer og udstyr, er i BSim opdelt i to separate systemer hhv. Equipment og PeopleLoad. I BSim kan der for både Equipment og PeopleLoad defineres et Schedule som beskriver hvornår de forskellige belastninger er aktuelle. I Be10 regnes med konstante værdier dog med opdeling mellem nat og dag for apparatur når der er tale om andre bygninger end boliger. Derfor må de værdier der overføres til Be10 korrigeres tilsvarende, og det gøres som beskrevet i det følgende.

For personer fastlægges den gennemsnitlige belastning i W/m² for hver enkelt zone over året. Hvis man i BSim f.eks. har en varmeafgivelse fra personer på 350 W for et 100 m² rum, og en tidsangivelse som angiver denne belastning som værende 12 timer pr. dag alle hverdage, vil dette resultere i en fast belastning på:

$$  
Q_{\text{pers}} = \frac{350\,\text{W} \cdot 12\,\text{timer} \cdot 5\,\text{dage}}{100\,\text{m}^2 \cdot 24\,\text{timer} \cdot 7\,\text{dage}} = 1{,}25\,\text{W}/\text{m}^2 \tag{5}  
$$

For apparatur fastlægges den gennemsnitlige belastning i W/m² for hver enkelt zone over året, og hvis brugstiden er mindre end 168 timer/uge fastlægges både en værdi for brugstiden og en værdi for udenfor brugstiden. Hvis man i BSim f.eks. har en varmeafgivelse fra udstyr på 600 W for et 100 m² rum, og en tidsangivelse som angiver denne belastning som værende 10 timer pr. dag alle hverdage, og endvidere har angivet at den resterende del af tiden er belastningen 25 % af dette, vil det resultere i faste belastninger på:

$$  
Q_{\text{app}} = \frac{600\,\text{W}}{100\,\text{m}^2} = 6{,}00\,\text{W}/\text{m}^2 \text{, i brugstiden - og} \tag{6}  
$$

$$  
Q_{\text{app,net}} = \frac{600\,\text{W} \cdot 25\%}{100\,\text{m}^2} = 1{,}50\,\text{W}/\text{m}^2 \text{, udenfor brugstiden.} \tag{7}  
$$

 

### **Belysning**

Belysningen kan i et vist omfang overføres fra BSim til Be10.

*   *Zone*: I Be10 opdeles bygningen i de termiske zoner som er benyttet i BSim modellen.

*   *Areal*: Bruttoarealet af zonen overføres direkte fra BSim.

*   *Eleffekt til almenbelysning i brugstiden, minimum*: Fra BSim benyttes Task Lighting, som ganges med 1000 (omregning fra kW til W) og divideres med bruttoarealet af den pågældende zone.

*   *Installeret eleffekt til almenbelysning i brugstiden*: Fra BSim benyttes General Lighting, som ganges med 1000 (fra kW til W) og divideres med brutto-arealet af den pågældende zone.

*   *Belysningsniveau*: Gen. Lighting Level (lux) overføres direkte fra BSim til Be10.

*   *Dagslysfaktor*: Dagslysfaktoren er ikke specificeret i BSim og derfor fastsættes den i Be10 som 2 %.

*   *Dagslysstyring*: I BSim er ikke defineret hvorledes der styres i forhold til dagslyset, og derfor sættes denne værdi altid til "U", dvs. Uden Dagslysstyring i Be10.

*   *Benyttelsesfaktor*: Belysningens nominelle brugstid i forhold til bygningens brugstid er ikke defineret i BSim, og derfor fastsættes denne faktor altid til 1,0 i Be10, svarende til at belysningens og bygningens brugstid er den samme.

*   *Eleffekt til arbejdslamper i brugstiden*: Denne værdi er ikke defineret direkte i BSim. I SBi anvisning 213 er imidlertid givet, at "… Der kan normalt antages et elforbrug til arbejdslamper på 1,0 W pr. m² opvarmet etageareal i gennemsnit for bygningen i brugstiden", og derfor sættes denne værdi fast til 1,0 W pr. m².

*   *Eleffekt til anden belysning i brugstiden*: Denne værdi er ikke specificeret i BSim og derfor fastsættes den som 0 W/m² i Be10.

*   *Stand by effekt til almenbelysning udenfor brugstiden*: Denne værdi er ikke specificeret i BSim og derfor fastsættes den som 0 W/m² i Be10.

*   *Eleffekt til belysning udenfor brugstiden*: Denne værdi er ikke specificeret i BSim og derfor fastsættes den som 0 W/m² i Be10.

### **Andet elforbrug**

Denne del kan ikke overføres fra BSim.

*   Udebelysning (dagslysstyret): Værdien fastsættes som 0 W.

*   Særligt apparatur (i brugstiden): Værdien fastsættes som 0 W.

*   Særligt apparatur (altid i brug): Værdien fastsættes som 0 W.

### **Forsyning: Varmepumpe**

Denne del kan delvist overføres direkte fra BSim til Be10. Varmepumpemodellen som benyttes i Be10 er den samme som benyttes i BSim og derfor vil de data som angives i BSim kunne overføres direkte.

*   *Beskrivelse*: Fra BSim overføres varmepumpens navn til dette felt.

*   *Type*: Overføres direkte.

*   *Andel af etageareal (-)*: Overføres direkte.

*   *Rumopvarmning*: Overføres direkte.

*   *Rumopvarmning*: *Nominel COP (-)*: Overføres direkte.

*   *Rumopvarmning: Rel. COP ved 50 % last*: Overføres direkte.

*   *VBV: Nominel effekt (kW)*: Overføres direkte.

*   *VBV: Nominel COP (-)*: Overføres direkte.

*   *VBV: Rel. COP ved 50 % last:* Overføres direkte.

*   *Test-temperaturer: Rumopvarmning: Kold side:* Overføres direkte.

*   *Test-temperaturer: Rumopvarmning: Varm side:* Overføres direkte.

*   *Test-temperaturer: VBV: Kold side:* Overføres direkte.

*   *Test-temperaturer: VBV: Varm side:* Overføres direkte.

*   *Rumopvarmning: Kold side: Jordslange, aftræk eller udeluft:* Overføres direkte.

*   *VBV: Kold side: Jordslange, aftræk eller udeluft:* Overføres direkte.

*   *Rumopvarmning: Varm side: Rumluft, indblæsning eller varmeanlæg:* Overføres direkte.

De resterende angivelser i Be10 (elbehov til særligt hjælpeudstyr og automatik samt data vedrørende varmepumper tilknyttet ventilationen) kan ikke overføres fra BSim.

<link rel="stylesheet" href="../style.css">

# Fejlmeddelelser

Fejlmeddelelser i *ModelList* vise med en foranstillet ikon <img src="./assets/18SimView - Udskrift af model.png" width=20>. Ved dobbelt-klik eller Ctrl-klik på linien i *ModelList* med fejlen flyttes fokus til det pågældende objekt i den hierarkiske træ-oversigt i *SimView*. Højre-klik på objektet i træet for at rette eller tilføje data.

Fejlmeddelelser optræder følgende steder:

*   Termisk simulering med tsbi5 og ModelList

*   Simulering af direkte sol med XSun

### **tsbi5 / ModelList**

| **Fejlmeddelelse** | **Mulig årsag** |
|---|---|
| No current building selected | Der er mere end en bygning defineret i modellen og det er ikke valgt hvilken der skal simuleres.<br>Højre-klik på bygningen (<img src="./assets/20SimView - Udskrift af model.png" width=20> i træet), vælg *Properties* og sæt "hak" ud for *Current building*. |
| No weather file | Der er ikke valgt en fil med klimadata som grundlag for simuleringen.<br>Højre-klik på *Site* (<img src="./assets/17SimView - Udskrift af model.png" width=20> i træet) og klik på *Browse*-knappen for at lokalisere en fil med klimadata (*.dry eller *.try). |
| Geometry incomplete | Geometrien for den termiske zone definerer ikke en lukket celle. |
| No rooms | Den termiske zone indeholder ikke mindst et rum.<br>Hold venstre knap på musen nede mens det ønskede rum trækkes til den tomme termiske zone eller slet den overflødige termiske zone. |
| No construction type | Fladen har ikke tilknyttet en konstruktion (materialelag).<br>Der kan tilknyttes [standardkonstruktioner](https://bsim.outseta.com/support/kb/articles/y9gBKGQM/standardkonstruktioner) til en flade eller [frit valgte konstruktioner](https://help.bsim.dk/support/kb/articles/rmklGkQg/simview---ikke-standard-konstruktioner) fra databasen. |
| No windoor type | Der er ikke tilknyttet materialegenskaber til WinDoor'en.<br>Der kan tilknyttes materialeegenskaber som [standardkonstruktioner](https://bsim.outseta.com/support/kb/articles/y9gBKGQM/standardkonstruktioner) eller som [frit valg fra databasen](https://help.bsim.dk/support/kb/articles/rmklGkQg/simview---ikke-standard-konstruktioner). |
| Unknown geometry | WinDoor'ets geometri er udefineret, hvis fx restarealet når beregningen af rammens areal bliver negativt. Geometrien beregnes af rammens bredde og evt. fyldningsprocenten. |
| No component | Systemets fysiske egenskaber er ikke defineret.<br>Højre-klik på systemet og definer dets fysiske egenskaber på første fanablad. |
| No schedule | Systemet som er oprettet har ikke fået tilknyttet en [tidsplan](https://help.bsim.dk/support/kb/articles/79O3DZ9E/systemer---schedule).<br>Højre-klik på systemet i træet, skift til *Schedule*-fanebladet og definer en tidsplan for reguleringen af systemet. Hvis systemet ikke skal bruges i denne simulering kan det i stedet slås fra ved at højre-klikke på den termiske zone og markere systemet med et gråt "hak". |
| No control | Systemet som er oprettet har ikke fået tilknyttet en regulering.<br>Højre-klik på systemet i træet, skift til *Control*-fanebladet og definer en reguleringen for systemet. Hvis systemet ikke skal bruges i denne simulering kan det i stedet slås fra ved at højre-klikke på den termiske zone og markere systemet med et gråt "hak". |
| No time | Systemet som er oprettet har ikke en tilknyttet [tidsangivelse](https://bsim.outseta.com/support/kb/articles/VmAOwo9a/tidsangivelse).<br>Højre-klik på systemet i træet, skift til *Time*-fanebladet og definer en tidsangivelse for systemet. Hvis systemet ikke skal bruges i denne simulering kan det i stedet slås fra ved at højre-klikke på den termiske zone og markere systemet med et gråt "hak". |
| Unknown (Mixing) | Kilden for luft ind i den termiske zone ved [*Mixing*](https://bsim.outseta.com/support/kb/articles/Rm8JEd94/mixing) er udefineret. |
| General Lux | Det generelle belysningsniveau (Gen. Lighting Level) i lux er udefineret (<= 0). |
| Unknown (Ventilation &#124; Natkøling) | Sensorzonen for regulering af natkøling er udefineret.<br>Højre-klik på systemet i træet, skift til [*NightCoolCtrl*-fanebladet](https://help.bsim.dk/support/kb/articles/L9nrXz9Z/ventilation---natkoling-ventilation) og definer en sensorzone for ventilationssystemet. |
| Thickness = x m | Tykkelsen af et materialelag i konstruktionen er mindre end 0,0001 m. |
| Missing material | Materialeegenskaber er ikke defineret - termiske- og/eller fugtegenskaber. |
| Spacer = x | Længden af afstandsprofilet i WinDoor er mindre end 0. |
| Frame = x | Arealet af rammen i WinDoor er mindre end 0. |
| Panel = x % | Fyldningsarealet i WinDoor er mindre end 0. |
| Dens = x kg/m³ / Cp = x J/kgK / lambda = x W/mK | Egenskaberne for materialet er ikke defineret korrekt. |
| U = x W/m²K | U-værdien for rammen i WinDoor er ikke defineret |
 

### **XSun**

| **Fejlmeddelelse**         | **Mulig årsag** |
|---------------------------|-----------------|
| Face sides degenerated |??? |



<style>
  :root{
    --blue-border:#1f4e8a;   /* frame + row rules */
    --blue-link:#1f4e8a;     /* link color like screenshot */
    --band-gray:#d9dee6;     /* title band */
    --cell-bg:#ffffff;
    --text:#111;
  }

  .panel{
    border:3px solid var(--blue-border);
    border-radius:2px;
    width: 900px; /* adjust as needed */
    border-collapse:separate;
    overflow:hidden;
  }

  .panel thead .title{
    background:var(--band-gray);
    border-bottom:1px solid var(--blue-border);
  }
  .panel thead .title th{
    padding:12px 14px;
    font-weight:700;
    text-align:left;
  }

  /* Explanatory row lives in thead so there’s no “line” gap */
  .panel thead .explainer td{
    background:var(--cell-bg);
    padding:10px 14px 12px;
    border-bottom:1px solid var(--blue-border);
  }

  .panel tbody td{
    background:var(--cell-bg);
    padding:8px 14px;
    border-bottom:1px solid var(--blue-border);
  }

  /* First column looks like a label */
  .panel tbody td:first-child{
    width: 180px;
    font-weight:700;
    white-space:nowrap;
  }

  /* Remove last inner rule to match screenshot feel */
  .panel tbody tr:last-child td{
    border-bottom:0;
  }

  a{
    color:var(--blue-link);
    text-decoration:underline;
  }
</style>

  <table class="panel">
    <thead>
      <tr class="title">
        <th colspan="2">Parametre i gruppen <em>Outdoors</em></th>
      </tr>
      <tr class="explainer">
        <td colspan="2">
          Inddata fra klimafil og beregnet position af solen.
          <br>
          Disse parametre er <strong>kun</strong> tilgængelige i resultatloggen hvis der er sat “hak” ud for
          <a href="#">Weather</a> på <a href="#">Options fanebladet</a> før simuleringen.
        </td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>AtmPres</td>
        <td>
          Lufttrykket, Pascal<br>
          Hvis lufttrykket er konstant 0 kan der stadig simuleres naturlig ventilation med
          <a href="#">multizone-modellen</a>, men med reduceret præcision.
        </td>
      </tr>
      <tr>
        <td>CldCover</td>
        <td>Skydække, ottendedele (8 = helt overskyet, 0 = skyfrit)</td>
      </tr>
      <tr>
        <td>DifRad</td>
        <td>Diffus solstråling på vandret, kW/m²</td>
      </tr>
      <tr>
        <td>ExtTmp</td>
        <td>Temperaturen af udeluften (tør), °C</td>
      </tr>
      <tr>
        <td>HumRatio</td>
        <td>Absolut fugtindhold i udeluften, kg/kg tør luft</td>
      </tr>
      <tr>
        <td>NormRad</td>
        <td>Direkte solindfald ved vinkelret indstråling, kW/m²</td>
      </tr>
      <tr>
        <td>RelHumid</td>
        <td>Relativ fugtighed i udeluften, %</td>
      </tr>
      <tr>
        <td>SkyTemp</td>
        <td>Himmeltemperatur, °C</td>
      </tr>
      <tr>
        <td>SunAz</td>
        <td>Solens position regnet fra nord (nord = 0°) og positiv mod øst (øst = 90°), grader</td>
      </tr>
      <tr>
        <td>SunH</td>
        <td>Solhøjde i forhold til vandret (zenit = 90°), grader</td>
      </tr>
      <tr>
        <td>WindDir</td>
        <td>Vindretning (nord = 0°), grader</td>
      </tr>
      <tr>
        <td>WindSpeed</td>
        <td>Vindhastighed, m/s</td>
      </tr>
    </tbody>
  </table>

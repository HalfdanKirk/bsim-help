<link rel="stylesheet" href="../style.css">

# SimDB - BuildingMaterial, Moisture
Fanebladet Moisture indeholder oplysninger om materialets fugtegenskaber.

<div id="gray_background">
Oprettes der nye materialer i en database med information om egenskaber for fugttransport <u>skal</u> der angives data for fugttransporten, også selvom der ikke skal simuleres fugttransport. <a href="https://help.bsim.dk/support/kb/articles/rQV5b8m6/begransninger">Se begrænsninger</a>.
</div>


<figure id="center_img">
<img src="./assets/DB-FUGT.JPG " alt="Fugtegenskaber for bygningsmateriale.">
<figcaption>Fugtegenskaber for bygningsmateriale.</figcaption>
</figure>

I fanebladet *Moisture* angives fugtegenskaber for et materiale. I fanebladet kan angives en række data, som er medtaget til fremtidig brug.

<div id="gray_background">
Lambda er varmeledningsevnen for materialet som anvendes når "Moisture Transport" er slået TIL under options for simuleringer med tsbi5. Se også "<a href="https://help.bsim.dk/support/kb/articles/y9q8b2QA/simdb---buildingmaterial-thermal">Thermal</a>."
</div>
<br>

**Kun værdien Lambda anvendes endnu, samt de tabeller som defineres under Absorption, Desorption og DeltaRh.**

*Absorption/Desorption*: Klikkes på Absorption (*Desorption*) knappen [åbnes en tabel](https://help.bsim.dk/support/kb/articles/y9gBGVQM/sorptiondesorption), hvori der indtastes sammenhørende værdier af relativ fugt (-) og fugtindhold (kg/kg) for punkter på absorptions (desorptions) kurven for materialet. Første punkt antages altid at være (0, 0), og det kan udelades. Værdierne indtastes i rækkefølge med stigende relativ fugtighed.

*DeltaRH*: Klikkes på *DeltaRH* knappen åbnes en tabel, hvori der indtastes værdi(er) for materialets kurve for det hygroskopiske område, som sammenhørende værdier af relativ fugt (-) og fugt permeabilitet (kg/m s Pa).

 

Se også:

*   [Faneblad Material](https://help.bsim.dk/support/kb/articles/4966z49X/simdb---buildingmaterial-material)

*   [Faneblad Thermal](https://help.bsim.dk/support/kb/articles/y9q8b2QA/simdb---buildingmaterial-thermal)

*   [Faneblad PCM](https://help.bsim.dk/support/kb/articles/dQG26zm4/simdb---buildingmaterial-pcm)

*   [Faneblad Moisture](https://help.bsim.dk/support/kb/articles/wQXx4nQK/simdb---buildingmaterial-moisture)

*   [Faneblad Glazing](https://help.bsim.dk/support/kb/articles/7maw2j9E/simdb---buildingmaterial-glazing)

*   [Faneblad UserDefined](https://help.bsim.dk/support/kb/articles/xmerM5QV/simdb---buildingmaterial-userdefined)

*   [Faneblad Frame](https://help.bsim.dk/support/kb/articles/ZmNreEm2/simdb---buildingmaterial-frame)

*   [Faneblad Finish](https://help.bsim.dk/support/kb/articles/BWzdbgQE/simdb---buildingmaterial-finish)


 

*   [Godt i gang med BSim2000](https://bsim.outseta.com/support/kb/articles/y9q8azQA/opbygning-af-model)

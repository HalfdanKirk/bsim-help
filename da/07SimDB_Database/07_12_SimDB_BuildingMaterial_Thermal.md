<link rel="stylesheet" href="../style.css">

# SimDB - BuildingMaterial, Thermal

Fanebladet *Thermal* indeholder oplysninger om materialets termiske egenskaber, og vises for alle andre materialer end dem som er beliggende i [SfB-grupperne](https://bsim.outseta.com/support/kb/articles/DQ2xwBWV/sfb-i-bsim) a, b, c og 0, 1, ... .

De termiske egenskaber er den termiske kapacitet C<sub>p  </sub>[J/kg K] og varmeledningsevnen l [W/m K]. Disse informationer benyttes kun, hvis materialet indgår i en bygningskonstruktion (ikke *WinDoor*), som benyttes i en simulering med *tsbi5*.

<div id="gray_background">
Uanset om "Moisture Transport" er slået til eller fra på "Options" fanebladet under simuleringer med tsbi5, benyttes den lambda-værdi som er givet på dette faneblad. Se også <a href="https://help.bsim.dk/support/kb/articles/wQXx4nQK/simdb---buildingmaterial-moisture">Moisture</a>

<br>
Oprettes der nye materialer i en database med information om egenskaber for fugttransport <u>skal</u> der angives data for fugttransporten, også selvom der ikke skal simuleres fugttransport.<a href="https://help.bsim.dk/support/kb/articles/rQV5b8m6/begransninger"> Se begrænsninger</a>. 
</div>  

<figure id="center_img">
<img src="./assets/dbthermal.gif " alt="Termiske data (ud over densiteten) for materialet på Edit Material | Thermal. Edit Material | Thermal.">
<figcaption>Termiske data (ud over densiteten) for materialet på Edit Material | Thermal. Edit Material | Thermal.</figcaption>
</figure>

 
Se også:

*   [Faneblad Material](https://help.bsim.dk/support/kb/articles/4966z49X/simdb---buildingmaterial-material)

*   [Faneblad PCM](https://help.bsim.dk/support/kb/articles/dQG26zm4/simdb---buildingmaterial-pcm)

*   [Faneblad Moisture](https://help.bsim.dk/support/kb/articles/wQXx4nQK/simdb---buildingmaterial-moisture)

*   [Faneblad Environment](https://help.bsim.dk/support/kb/articles/nmDBzx9y/simdb---buildingmaterial-environment)

*   [Faneblad Glazing](https://help.bsim.dk/support/kb/articles/7maw2j9E/simdb---buildingmaterial-glazing)

*   [Faneblad UserDefined](https://help.bsim.dk/support/kb/articles/xmerM5QV/simdb---buildingmaterial-userdefined)

*   [Faneblad Frame](https://help.bsim.dk/support/kb/articles/ZmNreEm2/simdb---buildingmaterial-frame)

*   [Faneblad Finish](https://help.bsim.dk/support/kb/articles/BWzdbgQE/simdb---buildingmaterial-finish)


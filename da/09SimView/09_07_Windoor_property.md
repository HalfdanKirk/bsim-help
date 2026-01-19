<link rel="stylesheet" href="../style.css">

# WinDoor Property

<figure id="center_img">
<img src="./assets/WindoorProperty.gif " alt="Dialog (Windoor Property) for beskrivelse af geometri, glasareal og skyggegivere for en WinDoor.">
<figcaption>Dialog (Windoor Property) for beskrivelse af geometri, glasareal og skyggegivere for en WinDoor.</figcaption>
</figure>


I feltet *Area* vises de oplysninger som programmet har beregnet af åbningens geometri og information fra databasen. De beregnede størrelser er: åbningens areal (*Opening*), glassets areal (*GlassArea*), rammens areal (*FrameArea*), fyldningens areal (*PanelArea*) som benyttes i forbindelse med simuelring af døre og længden af afstandsprofilet (*SpacerLength*).

Bemærk, at første gang dialogen åbnes, vil informationen *Impossible Geometry* fremkomme i stedet for *SpacerLength* og der vises et stopsignal til højre for *Override*-knappen hvis åbningen ikke er en rektangel eller der ikke er valgt et vindue fra databasen. Ved klik på [knappen *Override*](https://help.bsim.dk/support/kb/articles/A93zORQ0/windoor-override) kan arealet for rammen og fyldningen samt afstandsprofilets længde ændres. Fra disse data beregnes arealet af glasset.

Meddelelsen *Impossible Geometry* kan også skyldes at den aktuelle Windoor er placeret så den strækker sig ind over *Inner Shell*, dvs. konstruktionerne i de flader som støder op til den fladen hvori Windoor placeret. Kan opstå hvis tykkelsen af modellens konstruktioner forøges fx ved valg af nye konstruktioner. Det vil ikke være muligt at gennemføre en simulering så længe Windoors geometri er umulig.

Oplysningsfelterne under *Area* beskriver U-værdien for det WinDoor der er tilknyttet, samt dets indgang i databasen (SfB-nummer og navn).

*   *Recess (m)*: Glassets tilbagetrækning i forhold til ydersiden af væggen i meter. Hvis der angives en Recess på 0, bliver afskygningen behandlet svarende til at glasset er placeret plant med konstruktionens <u>**indvendige** </u>overflade. Ønskes glasset placeret i plan med facadens udvendige overflade skal der angives en værdi større end 0,0001.   
<span id="red_text"> **NB:** Recess fungerer <u>kun</u> hvis [XSun solfordeling](https://help.bsim.dk/support/kb/articles/nmDBKR9y/tsbi5---options) er slået til. </span>

*   *Select Systems*: Der kan vælges tre systemer som knytter sig til objektet:   
Regulering ([Regulation](https://help.bsim.dk/support/kb/articles/y9gB57QM/regulation)),  
Skodder ([*Shutter*](https://help.bsim.dk/support/kb/articles/ZmNrMxm2/shutter-system)) og   
solafskærmning ([*SolarShading*](https://help.bsim.dk/support/kb/articles/7maw8X9E/shading-system)).   
Systemerne defineres ved at højre-klikke i træ-oversigten, hvorved den tilhørende dialog kaldes frem

*   *DayLight*: Giver mulighed for manuel indtastning af sollysfaktorerne [Sf1](https://help.bsim.dk/support/kb/articles/49EdwkQ7/sollysfaktorer-for-windoors), [Sf2](https://help.bsim.dk/support/kb/articles/49EdwkQ7/sollysfaktorer-for-windoors) og [Sf3](https://help.bsim.dk/support/kb/articles/49EdwkQ7/sollysfaktorer-for-windoors) for et vindue. Det er også muligt at beregne og overføre dagslysfaktorerne automatisk fra [SimLight](https://help.bsim.dk/support/kb/articles/DQ2xz6WV/dagslysberegning-i-et-punkt) programmet.

*   [*Sidefin* og *Overhang*](https://help.bsim.dk/support/kb/articles/ZmNrw7m2/udhang-og-sidefinner): Den lokale geometri omkring objektet kan beskrives ved klik på knapperne [*Left*, *Right* og *Top*](https://help.bsim.dk/support/kb/articles/ZmNrw7m2/udhang-og-sidefinner), som kalder dialoger frem til definition af geometrien for sidefinner og udhæng.   
<span id="red_text">**NB:** Overhang og Sidefin fungerer **nu** også sammen med [XSun solfordeling](https://help.bsim.dk/support/kb/articles/nmDBKR9y/tsbi5---options) men vises ikke i [XSun](https://help.bsim.dk/support/kb/articles/amRGdMQJ/analyse-af-solindfald-med-xsun). Hvis et udhæng over eller langs et vindue skal simuleres med XSun solfordeling bør disse opbygges geometrisk i modellen.   
Hvis Overhang eller Sidefin benyttes **sammen med** XSun solfordeling, er der risiko for dobbelt afskygning på Windoor og dermed stærkt reduceret solindfald. </span>

På baggrund af disse oplysninger beregner programmet ramme-/karmarealet og fyldningsarealet samt arealet af kalfatringsfugen. Den samlede U-værdi for en *WinDoor* beregnes i henhold til anvisningerne i tillægget til [DS418](https://help.bsim.dk/support/kb/articles/A93zbqQ0/litteratur) om beregning af varmetabet gennem vinduer og døre.

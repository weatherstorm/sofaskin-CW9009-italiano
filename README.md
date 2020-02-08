# Sofaskin-CW9009
CW9009 Meridian sono le meofiche al codice della pagina web Sofaskin per Weewx originalmente sviluppata da Sven su http://neoground.com/projects/weewx. Consultare il file Leggimi per i requisiti di dipendenza per utilizzare questa skin. Una versione Italiana di queste directorysono disponibili su  http://micae.it/2017/12/28/sofaskin-italiano/. 

Sofaskin V1.1 è stato sviluppato da Sven su Neoground: https://neoground.com/portfolio/neowx/. ***Sven da tempo non supporta lo skin originale.*** Questo è un gran template but I ho implementato delle modifiche che mi confacevano. Ho anche aggiunto del codice da un altro template di <a href="http://www.dajda.net">dajda.net</a> per fare una cronologia delle tabelle NOAA. Ci sono altre righe di codice addizionali da <a href=http://www.torkel.se/weather/index.html> Björn Torkelsson</a>. Una lista dei cambiamenti è elencato sotto con le istruzioni per il setup delle tabelle cronologiche. 

- Aggiunte altre variabili nello file skin.conf per personalizzare le pagine. 
- Rimosse le tabelle mensili e settimanali dalla pagina ed aggiunte in nuove pagine. 
- Usati i record di tutti i tempi di weewkx per creare una tabella dei record.
- Aggiunta una pagina Stazione per le informazioni sulla stazione cpn i link delle pagine meteo dove i dati sono inviati.  
- Aggiunto un bottone Menu per gli schermi più piccoli.
- Refresh automatico della pagina ogni dieci minuti.
- Aggiunto del codice da dajda.net per produrre delle tabelle storiche.Lo script historygenerator.py deve essere aggiunto a WeeWx per funzionare.
- Creata una pagina PHP per vedere i file del NOAA.
- Aggiunto un warning se i fati della pagina non sono aggionati (più di 30 minuti). (Scritto da Björn Torkelsson) 
- Riscritto il codice javascript nella sezione web camera della pagina index.html con lo Slideshow per abilitare più di due webcam.

<b>Responsive Menu:</b><br>
Ho aggiunto un migliore sistema responsive menu che usa meno spazio verticale per gli schermi piccoli.

![screenshot_20161127-062548](https://cloud.githubusercontent.com/assets/22601363/20864991/f2f14eb8-b9c2-11e6-8bba-b4043f425bbb.png)
![screenshot_20161201-124209](https://cloud.githubusercontent.com/assets/22601363/20864992/f4b96654-b9c2-11e6-8346-650fee6db484.png)
<br><br>
<b>History Table:</b><br>
The historygenerator.py script was part of a template developed by http://www.dajda.net/index.html. More information on the template is available at http://www.dajda.net/about.html and the original template is available on GitHub at 
https://github.com/brewster76/fuzzy-archer. I modify the code in historygenerator.py to create the right html links in the NOAA climate summary table and wrote a php page to view the summary. 

![template](https://cloud.githubusercontent.com/assets/22601363/20864962/3f40b91c-b9c2-11e6-8298-75bec529dc40.jpg)
<br><br>
<b>Old Data Alert:</b><br>
Displays an alert message in the header when weather data is X minutes old. The default is 30 minutes but this can be adjusted in the checkdiff.js file in the js folder. 

![olddata](https://cloud.githubusercontent.com/assets/22601363/21075763/496c385c-bed7-11e6-82e8-789ffa300601.jpg)
<br><br>
<b>Installation instructions:</b><br>
Installing the template is just like installing most other skins. You need to place the skin files in it’s own folder in the /etc/weewx/skins directory. You also need to change the skin variable to the new skin directory name in the weewx.conf file under Standard Reports. 

Example:<br>
[[StandardReport]]
skin = Sofaskin 

You also need to put the historygenerator.py python script, in the /usr/share/weewx/user directory. The skin.conf already has the code to use the tables so you don’t need to mess with that unless you want to change the colors. More information on historygenerator.py and how to use the tables is available through the links below.
https://github.com/brewster76/fuzzy-archer/blob/master/INSTALL

<b>IMPORTANT:</b>
You should update the variables in the EXTRA section of the skin.conf file to match your station information. Example section below:

```
[Extras]
    # Template Extras
 
    # Website URL
    #web_url = 

    # radar
    #radar = '<iframe class="iframe" src="https://embed.windy.com/embed2.html?lat=43.555&lon=-116.348&zoom=9&level=surface&overlay=radar&menu=&message=&marker=&calendar=&pressure=&type=map&location=coordinates&detail=&detailLat=43.555&detailLon=-116.348&metricWind=default&metricTemp=default&radarRange=-1"></iframe>'

    # Lightning map and hyperlink
    #lightning_map = http://images.lightningmaps.org/blitzortung/america/index.php?map=usa&period=0.25
    #lightning_url = http://www.lightningmaps.org/realtime 

    # You. Only shows up in footer
    #you = 
    #emailname = 
    #email =  
   
    # Camera link
    # camera and cameratitle are arrays of the camera links and camera names. 
    #cameratitle = "Hwy 69 - Amity", "Victory - Five Mile", "Reflection Ridge", "Bridgeview South"
    #camera = http://www.achdidaho.org/ATIS/CCTV/CCTV_588.jpg, http://www.achdidaho.org/ATIS/CCTV/CCTV_649.jpg, https://icons.wunderground.com/webcamramdisk/l/a/lakearrowheadnw/3/current.jpg?1535944393, https://icons.wunderground.com/webcamramdisk/m/i/miralem77/4/current.jpg?1536106630  
    
    # Google Analytics ID
    #googleAnalyticsId = 

    #CWOP
    #cwop = 
    #cwop_url = 
```
If you have problems, you can email me at josh@cw9009.x10host.com  

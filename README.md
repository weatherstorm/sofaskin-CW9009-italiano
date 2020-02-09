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
<b>Tabella storico:</b><br>
Lo script historygenerator.py era una parte del template sviluppato da http://www.dajda.net/index.html. Altre informazioni sul template sono disponibili su http://www.dajda.net/about.html e il template originale è disponibile su GitHub a 
https://github.com/brewster76/fuzzy-archer. Ho modificato il codice historygenerator.py per creare il giusto link html nel sommario NOAA e scrive una pagina php per vedere la tabella. 

![template](https://cloud.githubusercontent.com/assets/22601363/20864962/3f40b91c-b9c2-11e6-8298-75bec529dc40.jpg)
<br><br>
<b>Old Data Alert:</b><br>
Mostra un messaggio di alert nell'header quando i dati sono vecchi di X minuti. Il default è di 30 minuti ma questo può essere modificato nel file checkdiff.js nella cartella js. 

![olddata](https://cloud.githubusercontent.com/assets/22601363/21075763/496c385c-bed7-11e6-82e8-789ffa300601.jpg)
<br><br>
<b>Istruzioni di installazione:</b><br>
Installare il template è come per la maggior parte degli skin. Devi mettere i file dello skin in una propria cartella nella cartella /etc/weewx/skins. Devi anche cambiare la variabile nel file weewx.conf sotto Standard Reports. 

Esempio:<br>
[[StandardReport]]
skin = Sofaskin 

Devi anche mettere lo script python historygenerator.py, nella directory /usr/share/weewx/user. Il file skin.conf ha già il codice per usare le tabelle, quindi non è necessario rovinarlo a meno che non si desideri cambiare i colori. Altre informazioni sullo script historygenerator.py e come usare le tabelle sono disponibile nel link di seguito.
https://github.com/brewster76/fuzzy-archer/blob/master/INSTALL

<b>IMPORTANTE:</b>
Devi aggiornare le variabili nella sezione EXTRA del file skin.conf file per abbinare le informazione della tua stazione. Di  seguito l'esempio della sezione:

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
Se hai dei problemi, puoi scrivermi a josh@cw9009.x10host.com
Ulteriori informazioni al traduttore italiano info@meteopaupisi.it

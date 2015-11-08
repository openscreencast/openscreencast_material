# momentaner Arbeitsablauf um ein Screencast zu veröffentlichen

1. sich für ein Thema entscheiden
2. Recherche, Ausprobieren, Texte suchen
3. Ablaufplan, Text erstellen (Ausprobieren)
4. Umfeld entsprechend konfigurieren
   - momentan: Linux Mint 17.2 cinnamon (andere möglich)
   - Auflösung auf 1920x1200
   - Symbole und Schrift größer einstellen
* einfarbiger Hintergrund (blau)
* Schrift im Terminal und im Texteditor größer einstellen
* eventuell key-mon oder screenkey starten
* wenn angebracht dann erklärendes Hintergrundbild erstellen und einsetzen
5. Aufnahme des Screencasts (mit simplescreenrecorder: 25fps, Stereo, 44100 Hz)
6. Kontrolle 
* ob alles aufgenommen wurde
* ob Fehler vorhanden sind
* ob Audio und Video synchron sind
7. Outro erstellen
* Outro für Video erstellen per Inkscape (als .svg speichern)
8. Videobearbeitung
* momentan hauptsächlich per Flowblade
* Aufnahmevideo, Outro (bei Demos auch noch Hintergrundmusik hinzufügen)
* Rendern in Ogg Theora HD 720p 25fps, mit maximaler Qualität (40MB/s), Audio: 192000 Bit
9. Kontrolle
10. Video hochladen
* bei youtube, bei vimeo
11. neuen Eintrag bei tumblr, twitter, geraspora
12. Video bei data.json hinzufügen
13. aus data.json die *.md-Dateien für pelican generieren
14. per pelican die Webseite generieren
15. Webseite aktualisieren
16. data, md, video bei github aktualisieren


# alter Arbeitsablauf um ein Screencast zu veröffentlichen

1. sich für ein Thema entscheiden
2. Recherche, Ausprobieren, Texte suchen
3. Ablaufplan, Text erstellen (Ausprobieren)
4. Umfeld entsprechend konfigurieren
* momentan: BS: Linux Mint 15 cinnamon (andere möglich)
* Auflösung auf 1920x1200
* Symbole und Schrift größer einstellen
* einfarbiger Hintergrund (blau)
* Schrift im Terminal und im Texteditor größer einstellen
* eventuell key-mon oder screenkey starten
* wenn angebracht dann erklärendes Hintergrundbild erstellen und einsetzen
5. Aufnahme des Screencasts
* mit recordmydesktop: 25fps, Stereo, 44100 Hz
6. Kontrolle ob alles aufgenommen wurde, ob Fehler vorhanden sind
* ob Audio und Video synchron sind
7. Outro erstellen
* Outro für Video erstellen per Inkscape (als .svg speichern)
8. .mpg-Video für Videobearbeitung erstellen
* ffmpeg -i recordmydesktop.ogg -b 6000000 -ab 224000 -s 1280x720 x.mpg
* die letzten Sekunden durch -t weglassen, bei Demos den richtigen Teil herausschneiden
9. Videobearbeitung
* momentan per OpenShot Videoeditor
* (Intro, Aufnahmevideo, Outro), bei Demos auch noch Hintergrundmusik hinzufügen
* Rendern in Ogg Theora HD 720p 25fps, mit maximaler Qualität (40MB/s), Audio: 192000 Bit
10. ogg in webm umwandeln
ffmpeg -i 'i.ogg' -b:v 6000000 -b:a 192000 -metadata title="Fedora 20 Beta LXDE - Demo" -metadata artist="heiko" -metadata interpret="heiko" -metadata album="www.openscreencast.de" -metadata location="germany" -metadata license="http://creativecommons.org/licenses/by/3.0/" -metadata copyright="http://creativecommons.org/licenses/by/3.0/" -metadata contact="info@openscreencast.de" -metadata date="13.11.2013" fedora20lxde.webm
11. Videos hochladen
* bei youtube (.webm-Variante)
* bei vimeo (.ogg-Variante)
12. Alles für die Veröffentlichung vorbereiten
* Video-Screenshot per Totem machen (.png)
* .srt-Datei (Untertitel) erstellen wenn möglich
13. Dateien überprüfen und auf den Server hochladen
14. neuen Eintrag bei tumblr, google plus, twitter, geraspora
15. neuen CMS-Video-Eintrag erstellen, Video auf Website veröffentlichen


# ganz alter Arbeitsablauf um ein Screencast zu veröffentlichen

1. sich für ein Thema entscheiden
2. Recherche, Ausprobieren, Texte suchen
3. Ablaufplan, Text erstellen (Ausprobieren)
4. Umfeld entsprechend konfigurieren
* momentan: BS: Fedora 15 Gnome3, Ubuntu 10.10 Gnome 2.32 (andere möglich)
* Auflösung auf 1360x768 (Ubuntu 10.10), 1920x1200 (Fedora 15)
* bei Fedora 15 Symbole und Schrift größer einstellen
* einfarbiger Hintergrund (blau)
* Schrift im Terminal und im Texteditor größer einstellen
* eventuell key-mon oder screenkey starten
* wenn angebracht dann erklärendes Hintergrundbild erstellen und einsetzen
5. Aufnahme des Screencasts
* mit recordmydesktop: 25fps, Stereo, 44100 Hz
6. Kontrolle ob alles aufgenommen wurde, ob Fehler vorhanden sind
* ob Audio und Video synchron sind
7. Intro und Outro erstellen
* unterschiedliche Outros für Video mit und ohne Hintergrundmusik
* mit Inkscape erstellen, .png-Export
* aus den .png-Bildern .mpg-Videos machen
* (#!/bin/bash \ for i in `seq 001 250`; \ do \ cp ./x.png x$i.png \ done)
* (ffmpeg -b 10000000 -i %d.png x.mpg       Bilder in Video umwandeln)
8. .mpg-Video für Videobearbeitung erstellen
* ffmpeg -i recordmydesktop.ogg -b 6000000 -ab 224000 -s 1280x720 x.mpg
9. Hintergrundmusik vorbereiten
* Musikdatei heraussuchen
* per Audacity Musik leiser machen
10. Videobearbeitung
* momentan per cinelerra Video erstellen (1280x720, 48000, Stereo, 16:9, 25fps)
* (Intro, Aufnahmevideo, [Outro1, Outro2, Outro3 Musik])
* Rendern in Ogg Theora, mit maximaler Qualität, Audio: 224000 Bit
* andere Programme sind möglich z.B. pitivi, kdenlive, openshot video editor
* Erfahrungen: kdenlive, openshot - Audio und Video sind nicht synchron, 
* Outro wird vergessen, wird nicht mitgerendert
11. die beiden Videos (mit Musik, ohne Musik) mit Metadaten versehen
* (Varianten: .webm 700k 3000k .mp4 .ogg (mit, ohne Musik))
ffmpeg2theora  o.avi -v 10 -V 16000 -a 10 -A 224 --artist "heiko" --title "Passwort  aendern" --date "01.10.2008" --location "Germany" --organization  "www.openscreencast.de" --license "http://creativecommons.org/licenses/by-sa/3.0/" --contact "info@openscreencast.de" -o passwort_aendern_short_047.ogg  
ffmpeg  -i om.ogg -b 3000000 -ab 192000 -year 2011 -metadata  title="Python-Programmierung - while-Schleife" -metadata artist="heiko"  -metadata interpret="heiko" -metadata album="www.openscreencast.de"  -metadata location="germany" -metadata license="Creative Commons by-sa  3.0" -metadata copyright="Creative Commons by-sa 3.0" -metadata  contact="info@openscreencast.de" -metadata date="03.05.2011" o.webm
ffmpeg  -i om.ogg -b 3000000 -ab 192000 -year 2011 -metadata  title="Python-Programmierung - while-Schleife" -metadata artist="heiko"  -metadata interpret="heiko" -metadata album="www.openscreencast.de"  -metadata location="germany" -metadata license="Creative Commons by-sa  3.0" -metadata copyright="Creative Commons by-sa 3.0" -metadata  contact="info@openscreencast.de" -metadata date="03.05.2011" -vcodec  libx264 -crf 22 -threads 0 o2.mp4
12. Videos hochladen
* bei youtube (.webm-Variante)
* bei vimeo (.mp4-Variante)
13. Alles für die Veröffentlichung vorbereiten
* xspf-Datei erstellen, xspf-Datei bearbeiten
* Video-Screenshot per Totem machen (.png)
* .srt-Datei (Untertitel) erstellen 
14. Dateien überprüfen und auf den Server hochladen
15. neuen CMS-Video-Eintrag erstellen, Video veröffentlichen
16. neuen Eintrag bei identi.ca


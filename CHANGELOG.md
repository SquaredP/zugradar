# Was ist neu

Neue Funktionen und Korrekturen am Zugradar. Neueste Einträge oben.
Die Seite liest diese Datei selbst und zeigt nach einem Update einmalig einen Hinweis an.

## 2026-11-23

- Verkehrsarten als aufklappbares Menü (wie im Flug- und Schiffsradar) statt vier einzelner Chips. Dort gibt es auch „Stehende Züge (im Halt)“ zum Ausblenden; stehende Züge sind gedimmt. Der Hinweis „näher heranzoomen“ steht jetzt im Menü
- Gleisnetz umschaltbar: „Gleise: alle“, „Gleise: Hauptnetz“ (ohne Bahnhofs- und Nebengleise, beim Hineinzoomen unschärfer) oder „Gleise: aus“. Die Wahl bleibt gespeichert
- Bahnhöfe auf der Karte antippen: ab Zoomstufe 10 erscheinen Bahnhöfe (ab Stufe 14 auch Tram-, U-Bahn- und Bus-Haltestellen). Ein Tipp öffnet die Tafel mit je 5 Abfahrten und Ankünften, auf- und zuklappbar, mit „5 frühere“ und „5 spätere“. Ein Eintrag antippen folgt dem Zug
- Neues Symbol: ein stilisierter Radar mit Zug im Browser-Tab und auf dem Home-Bildschirm. Der Hintergrund im Browser-Tab ist transparent, das Symbol sitzt mittig
- Mein Bahnhof: Ein kleines × am Ende des Feldes setzt den Bahnhof zurück

## 2026-11-22

- Handy: Das Detailblatt öffnet kompakt und lässt sich über den Griff oben (antippen oder ziehen) auf halbe und volle Höhe bringen. Solange es offen ist, blenden sich Filterleiste und Statuszeile aus, die Karte bleibt größer sichtbar
- Gleiskarte: Die Seite sendet den von OpenRailwayMap verlangten Referer wieder mit. Vorher wurde dieser aus Datenschutzgründen unterdrückt, und die Gleiskacheln wurden deshalb vermutlich abgelehnt.
- Im Querformat auf Notebook und iPad erscheint das Detailblatt rechts neben der Karte statt darunter, wie im Flugradar. Die Karte behält so die volle Höhe; auf dem Handy bleibt alles unverändert
- Gleiskarte wieder zuverlässiger: Die Seite nutzt jetzt die aktuelle Adresse von OpenRailwayMap, die alten Zusatzadressen werden dort abgeschaltet
- Fällt die Gleiskarte aus, steht ein Hinweis in der Statuszeile, statt dass die Gleise still fehlen

## 2026-11-21

- Doppeltipp auf die Karte zoomt eine Stufe näher, wie beim Schiffsradar. Beim Verfolgen bleibt der Zug dabei in der Mitte.
- Züge erscheinen nur noch in sinnvollen Zoomstufen: Fernverkehr für das ganze Land, Regional für ein Bundesland, S-Bahn für die Region, Tram, U-Bahn und Bus für die Stadt. Auf großen Bildschirmen greift das etwas später.
- Zugnamen überdecken sich nicht mehr. Was nicht Platz hat, wird ausgeblendet; die Statuszeile sagt, wie viele, und mit mehr Zoom erscheinen sie.
- Zu weit herausgezoomte Verkehrsarten sind oben gestrichelt, die Seite fragt dann keine Daten dafür ab
- Bei Fehlern oder „zu viele Anfragen“ wartet die Seite länger, bevor sie neu versucht, und zeigt weiter die letzten Züge
- Navi-Ansicht für den verfolgten Zug: Strecke voraus kräftig, gefahrener Teil grau
- Nächster Halt und Ziel stehen mit Uhrzeit direkt auf der Karte
- Neuer Knopf „Strecke voraus“ zeigt den restlichen Weg bis zum Ziel
- „Was ist neu?“ unter „Meine Linien“ informiert über neue Funktionen
- Neu: „Über Zugradar“ unter „Meine Linien“ erklärt Datenquellen, Genauigkeit und Datenschutz
- Karte und Schrift werden jetzt direkt von dieser Seite geladen, ohne Anfrage an Google oder andere Drittanbieter

## 2026-11-15

- Züge erscheinen nicht mehr doppelt, wenn sie aus zwei Fahrplanquellen kommen

## 2026-11-14

- Halte sind antippbar, auf der Karte und in der Liste, und zeigen die nächsten Abfahrten dort
- Bahnhofsnamen mit Ort, z. B. „Mannheim Hbf“ statt nur „Hauptbahnhof“
- „Mein Bahnhof“ lässt sich zurücksetzen
- Haltestellennamen erscheinen in der Sprache deines Browsers

## 2026-11-12

- Geschwindigkeit des verfolgten Zuges im Infoblatt
- Verfolgung läuft beim Schließen des Infoblatts weiter, oben bleibt eine Kapsel mit Zug und Tempo
- Verfolgter Zug bleibt beim Zoomen sichtbar
- Liniensuche findet Zugnummern wie „ICE 774“, Enter sucht im ganzen Netz

## 2026-11-11

- Erste Version: Karte mit Gleisnetz und Zügen, Filter nach Verkehrsart, Abfahrten an meinem Bahnhof, Zug verfolgen, Linien merken

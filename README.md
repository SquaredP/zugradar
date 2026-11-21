# Zugradar

Mobile Live-Karte, die zeigt, wo sich Züge gerade auf der Strecke befinden – damit man weiß, wo die nächste Bahn bleibt.

**Live:** https://squaredp.github.io/zugradar/

## Funktionen

- **Karte mit Gleisnetz** (OpenRailwayMap) und allen Zügen im Ausschnitt, mit Verspätung am Zugsymbol. Gestrichelte Symbole fahren nur nach Fahrplan, ohne Echtzeit.
- **Filter** nach Fernverkehr, Regionalverkehr, S-Bahn und Tram/U-Bahn sowie Suche nach Linie oder Zugnummer (z. B. `ICE 774`). Enter sucht im ganzen Netz.
- **Mein Bahnhof:** nächste Abfahrten an einem gewählten Bahnhof, optional nur diese Züge auf der Karte. Zurücksetzbar.
- **Zug verfolgen:** Die Karte folgt dem Zug. Wie bei einem Navi ist die Strecke voraus kräftig, der gefahrene Teil grau, nächster Halt und Ziel sind mit Uhrzeit beschriftet. „Strecke voraus“ zeigt den ganzen restlichen Weg.
- **Fahrtverlauf:** alle Halte mit Ankunft, Abfahrt, Gleis und Verspätung. Halte sind antippbar und zeigen die nächsten Abfahrten dort.
- **Geschwindigkeit:** Durchschnitt zwischen zwei Halten aus Strecke und Echtzeit-Fahrzeit.
- **Meine Linien:** Linien für tägliche Fahrten merken, mit Einstiegshalt. Gespeichert lokal im Browser.
- Hell- und Dunkelmodus, Haltestellennamen in der Browsersprache.

## Wie genau sind die Positionen?

Die Positionen sind **berechnet, nicht per GPS gemessen**. [Transitous](https://transitous.org) liefert Fahrpläne mit Echtzeit-Prognosen (in Deutschland aus dem DELFI-Datensatz, etwa minütlich aktualisiert). Die Seite setzt den Zug anhand der prognostizierten Abfahrts- und Ankunftszeiten zwischen zwei Halten auf die Strecke. Bei Störungen, die noch nicht in der Prognose stehen, kann die Anzeige vom tatsächlichen Standort abweichen.

## Technik

- Eine einzelne statische Datei (`index.html`) mit Vanilla JavaScript, kein Build-Schritt.
- [Leaflet](https://leafletjs.com) für die Karte, Grundkarte von Esri, Gleise von OpenRailwayMap.
- Daten über die öffentliche [MOTIS-API](https://api.transitous.org) von Transitous (`map/trips`, `trip`, `stoptimes`, `geocode`).
- Einstellungen und gemerkte Linien liegen im `localStorage` des Browsers, es gibt kein Backend.

Lokal ausprobieren: `index.html` über einen beliebigen Webserver ausliefern, z. B. `python3 -m http.server`, und `http://localhost:8000` öffnen.

## Daten und Nutzungsbedingungen

- Zugdaten: © Transitous und die jeweiligen Datenquellen. Transitous ist ein gemeinschaftlich betriebener, nicht-kommerzieller Dienst – bitte die [Nutzungsbedingungen](https://transitous.org/api/) beachten und die API nicht übermäßig belasten.
- Kartendaten: © OpenStreetMap-Mitwirkende, Esri, OpenRailwayMap.

## Lizenz

Der Code steht unter der [MIT-Lizenz](LICENSE). Die angezeigten Karten- und Fahrplandaten unterliegen den Lizenzen ihrer jeweiligen Anbieter.

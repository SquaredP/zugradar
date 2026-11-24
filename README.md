# Zugradar

Mobile Live-Karte, die zeigt, wo sich Züge gerade auf der Strecke befinden – damit man weiß, wo die nächste Bahn bleibt.

**Live:** https://squaredp.github.io/zugradar/

## Funktionen

- **Karte mit Gleisnetz** (OpenRailwayMap) und allen Zügen im Ausschnitt, mit Verspätung am Zugsymbol. Gestrichelte Symbole fahren nur nach Fahrplan, ohne Echtzeit.
- **Datensparsam nach Zoomstufe:** Fernverkehr ab Länderebene, Regional ab Bundeslandebene, S-Bahn ab Regionsebene, Tram/Bus nur in der Stadt (auf größeren Bildschirmen etwas später). Es werden nur Züge im Bild geladen und gezeichnet, überlappende Namen werden ausgeblendet.
- **Filter** im Menü „Typen“ (Fernverkehr, Regional, S-Bahn, Tram/U-Bahn/Bus, dazu stehende Züge im Halt ein- oder ausblenden) sowie Suche nach Linie oder Zugnummer (z. B. `ICE 774`). Enter sucht im ganzen Netz.
- **Mein Bahnhof:** nächste Abfahrten an einem gewählten Bahnhof, optional nur diese Züge auf der Karte. Zurücksetzbar.
- **Bedienung:** Doppeltipp (Doppelklick) auf die Karte zoomt eine Stufe näher.
- **Zug verfolgen:** Die Karte folgt dem Zug. Wie bei einem Navi ist die Strecke voraus kräftig, der gefahrene Teil grau, nächster Halt und Ziel sind mit Uhrzeit beschriftet. „Strecke voraus“ zeigt den ganzen restlichen Weg.
- **Bahnhofstafel:** Bahnhöfe auf der Karte antippen (Bahn ab Zoomstufe 10, Tram, U-Bahn und Bus ab 14). Je 5 Abfahrten und Ankünfte, auf- und zuklappbar, mit 5 früheren und 5 späteren. Ein Eintrag folgt dem Zug.
- **Hinweise:** Meldungen zu Störungen und Sperrungen, soweit Transitous sie für eine Fahrt, einen Halt oder einen Bahnhof liefert. Es gibt keine eigene Sperrungsquelle; ob und wie viele Meldungen erscheinen, hängt von den Daten ab.
- **Fahrtverlauf:** alle Halte mit Ankunft, Abfahrt, Gleis und Verspätung. Halte sind antippbar und zeigen die nächsten Abfahrten dort.
- **Geschwindigkeit:** Durchschnitt zwischen zwei Halten aus Strecke und Echtzeit-Fahrzeit.
- **Meine Linien:** Linien für tägliche Fahrten merken, mit Einstiegshalt. Gespeichert lokal im Browser.
- Hell- und Dunkelmodus, Haltestellennamen in der Browsersprache.
- **Über Zugradar:** Herkunft der Daten, Genauigkeit und Datenschutz in der App.
- **Was ist neu:** Nach einem Update erscheint einmalig ein Hinweis, die ganze Liste steht unter „Meine Linien“ → „Was ist neu?“.

## Wie genau sind die Positionen?

Die Positionen sind **berechnet, nicht per GPS gemessen**. [Transitous](https://transitous.org) liefert Fahrpläne mit Echtzeit-Prognosen (in Deutschland aus dem DELFI-Datensatz, etwa minütlich aktualisiert). Die Seite setzt den Zug anhand der prognostizierten Abfahrts- und Ankunftszeiten zwischen zwei Halten auf die Strecke. Bei Störungen, die noch nicht in der Prognose stehen, kann die Anzeige vom tatsächlichen Standort abweichen.

## Neuerungen

Alle Änderungen stehen in [CHANGELOG.md](CHANGELOG.md). Die Seite liest diese Datei selbst. Neue Einträge kommen oben als `## JJJJ-MM-TT` mit Stichpunkten darunter; nur dieses Format wird angezeigt.

## Technik

- Eine statische Seite (`index.html`) mit Vanilla JavaScript, kein Build-Schritt.
- [Leaflet](https://leafletjs.com) (BSD-2) und die Schrift Barlow (SIL OFL) liegen in `vendor/`, mit ihren Lizenzen. Beim Laden der Seite gibt es dadurch keine Anfrage an Drittanbieter-CDNs oder Google Fonts.
- Grundkarte von Esri, Gleise von OpenRailwayMap.
- Eine Content-Security-Policy im HTML erlaubt Verbindungen nur zu `api.transitous.org` und den beiden Kartenanbietern.
- Daten über die öffentliche [MOTIS-API](https://api.transitous.org) von Transitous (`map/trips`, `trip`, `stoptimes`, `geocode`).
- Einstellungen und gemerkte Linien liegen im `localStorage` des Browsers, es gibt kein Backend.

Lokal ausprobieren: `index.html` über einen beliebigen Webserver ausliefern, z. B. `python3 -m http.server`, und `http://localhost:8000` öffnen.

## Datenschutz

Kein Konto, keine Cookies, kein Tracking, kein eigener Server. Bahnhof, Filter, Kartenausschnitt und gemerkte Linien bleiben im Browser. Beim Benutzen sehen Transitous (Kartenausschnitt, Zug-ID, Suchtext), Esri und OpenRailwayMap (Kartenkacheln) sowie GitHub Pages (Auslieferung der Seite) die IP-Adresse. Details stehen in der App unter „Meine Linien“ → „Über Zugradar“.

## Daten und Nutzungsbedingungen

- Zugdaten: © Transitous und die jeweiligen Datenquellen. Transitous ist ein gemeinschaftlich betriebener, nicht-kommerzieller Dienst – bitte die [Nutzungsbedingungen](https://transitous.org/api/) beachten und die API nicht übermäßig belasten.
- Kartendaten: © OpenStreetMap-Mitwirkende, Esri, OpenRailwayMap.

## Lizenz

Der Code steht unter der [MIT-Lizenz](LICENSE). Die angezeigten Karten- und Fahrplandaten unterliegen den Lizenzen ihrer jeweiligen Anbieter.

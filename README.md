# Landewiesen · GPS

PWA für Segelflug- und Gleitschirm-Piloten: zeigt die nächsten Außenlande­plätze im Alpen­raum anhand der aktuellen GPS-Position an — mit Karte, Distanz, Höhe, Kurs, Fotos und Details.

**Live**: https://alexott1977.github.io/landewiesen/

## Features

- Live-GPS: Position, Höhe (MSL), Geschwindigkeit, Kurs
- Karte mit 771 Landewiesen (Kategorie A + B), OpenStreetMap-Tiles
- Flugzeug-Marker rotiert mit dem GPS-Kurs
- Liste mit den 50 nächsten Landewiesen, sortiert nach Luftlinie
- Detail-Sheet pro Landewiese: Fotos, Landerichtung, Länge/Breite, Oberfläche, MSL-Höhe, Anmerkungen
- Filter nach Kategorie A / B
- Umschalter km / mi
- Follow-Mode: Karte folgt Position
- **Fake-Position bei Füssen**, falls kein GPS-Fix
- Als App installierbar (PWA), Offline-Betrieb nach erstem Laden

## Bedienung

1. App-URL öffnen (auf HTTPS oder localhost — GPS erlaubt nichts anderes).
2. "Standort freigeben" tippen. Alternativ "Ohne GPS · Füssen" für Fake-Position.
3. Karte zeigt Flugzeug + die 5 nächsten Landewiesen; Liste zeigt Top 50.
4. Landewiese in der Liste oder auf der Karte antippen → Detail-Sheet mit allen Infos + Fotos.
5. Rechts oben "🎯" springt zurück auf die eigene Position.

## Datenquelle

Daten und Fotos stammen aus dem Bestand von [landewiesen.streckenflug.at](https://landewiesen.streckenflug.at) und wurden aus einer offline verfügbaren HTML-Karten-Sammlung in eine schlanke PWA-Struktur überführt.

## Aufbau

| Datei / Ordner | Inhalt |
|---|---|
| `index.html` | UI, GPS-Logik, Karte, Detail-Sheet |
| `fields.js` | 771 Landewiesen (Metadaten + Foto-Referenzen) |
| `photos/` | 1620 JPEGs (on-demand via SW-Cache) |
| `leaflet.js` / `leaflet.css` | Kartenbibliothek, lokal eingebunden |
| `sw.js` | Service-Worker: Cache-first, Photos on-demand |
| `manifest.webmanifest` | PWA-Manifest |
| `icon.svg` | App-Icon |

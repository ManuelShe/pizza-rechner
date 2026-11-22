# 🍕 Pizzaabend-Rechner

Eine kleine Web-App für den Pizzaabend mit vielen Gästen: Personenzahl eingeben, und die App berechnet Teig, Beläge, Einkaufsliste und einen Zeitplan bis zur ersten Pizza aus dem Gas-Pizzaofen.

<!-- DEINNAME durch den eigenen GitHub-Namen ersetzen -->

---

## Funktionen

- **Teigrechner:** Neapolitanischer Pizzateig mit 63 % Wasser und 20 h kalter Gare. Die App berechnet die Mengen für die eingestellte Personenzahl (Erwachsene und Kinder) und den Hunger.
  - **Teiglinggewicht:** Wird automatisch passend zu Gästezahl und Ofengröße (12 oder 16 Zoll) gewählt oder lässt sich frei einstellen.
  - **Salz:** üblich (30 g pro kg Mehl) oder weniger (20 g pro kg).
  - **Hefe:** Trockenhefe oder Frischhefe.
  - **Kneten:** mit Maschine, aufgeteilt in mehrere Durchgänge, oder von Hand.
- **Teigboxen:** Zeigt, wie die Teiglinge gleichmäßig auf die vorhandenen Boxen verteilt werden, und meldet fehlende Boxen.
- **Pizzasorten:**
  - Die Sorten werden je nach Personenzahl automatisch ausgewählt, von Margherita bis Hawaii, mit Dessertpizza zum Schluss.
  - Die Anzahl pro Sorte lässt sich manuell festlegen; die übrigen Pizzen werden automatisch auf die anderen Sorten verteilt.
  - Eigene Pizzen mit eigenen Zutaten lassen sich anlegen.
  - Unter „Details“ stehen die Zutatenmengen pro Pizza und insgesamt.
  - Käse: Fior di Latte, geriebener Pizzakäse oder gemischt.
- **Einkaufsliste:**
  - Mengen in Packungsgrößen, zum Abhaken.
  - Eigene Einträge sind möglich.
  - Die Liste lässt sich kopieren.
- **Zeitplan:**
  - Alle Schritte vom Einkaufen bis zur letzten Pizza mit Uhrzeit. Voreingestellt ist der nächste mögliche Samstag.
  - Einzelne Schritte lassen sich verlängern, aber nicht unter ihre Mindestzeit kürzen.
  - Schritte werden abgehakt. Der erste offene Schritt ist hervorgehoben, beim Öffnen scrollt die App direkt dorthin.
  - Links führen zu Einkaufsliste, Rezept und Mise en place.
- **Rezept und Mise en place** als Checklisten zum Abhaken.
- **Druckansicht** auf 4 Seiten: Überblick mit Zeitplan, Einkaufsliste, Teigrezept, Pizzen mit Mise en place.
- **Speichern:** Einstellungen bleiben auf dem Gerät gespeichert. Mit „Neu“ gelten wieder die Standardwerte.
- **Offline nutzbar** und als App installierbar.

## Als App installieren

| Gerät                  | So geht's                                                                            |
| ---------------------- | ------------------------------------------------------------------------------------ |
| Android (Chrome)       | Seite öffnen → Menü ⋮ → **App installieren** bzw. **Zum Startbildschirm hinzufügen** |
| iPhone / iPad (Safari) | Seite öffnen → Teilen → **Zum Home-Bildschirm**                                      |
| PC (Chrome / Edge)     | Installations-Symbol rechts in der Adressleiste                                      |

Nach dem ersten Öffnen mit Internet funktioniert die App auch ohne Netz.

## Dateien

| Datei                                          | Zweck                                                       |
| ---------------------------------------------- | ----------------------------------------------------------- |
| `index.html`                                   | Die komplette App (HTML, CSS und JavaScript in einer Datei) |
| `manifest.webmanifest`                         | App-Name, Farben und Icons für die Installation             |
| `sw.js`                                        | Service Worker: speichert die App für die Offline-Nutzung   |
| `icon-192.png`, `icon-512.png`, `icon-180.png` | App-Icons (Android bzw. iOS)                                |

## Veröffentlichen mit GitHub Pages

1. Alle Dateien in das Repository hochladen, direkt ins Hauptverzeichnis und nicht in einen Unterordner.
2. **Settings → Pages**: als Branch `main` und als Ordner `/ (root)` wählen, dann **Save**.
3. Nach 1–2 Minuten ist die App unter `https://DEINNAME.github.io/REPO-NAME/` erreichbar.

## Aktualisieren

Um die App zu aktualisieren, reicht es, die neue `index.html` hochzuladen und die alte zu überschreiben. Die App holt sich die neue Version beim nächsten Öffnen mit Internet von selbst. Sollte das einmal nicht klappen, die Versionsnummer in `sw.js` erhöhen (`pizzaabend-v1` → `pizzaabend-v2`).

## Datenschutz

Die App hat kein Konto und keinen Server und erfasst keine Daten. Einstellungen und Häkchen werden nur im Browser des jeweiligen Geräts gespeichert (`localStorage`). Jedes Gerät hat deshalb seinen eigenen Stand.

## Grundrezept

| Zutat                         | Menge pro 1 kg Mehl |
| ----------------------------- | ------------------- |
| Mehl Typ 00 (11–15 % Protein) | 1000 g              |
| Wasser                        | 630 g               |
| Salz                          | 30 g (oder 20 g)    |
| Trockenhefe / Frischhefe      | 1 g / 3 g           |

Kneten → dehnen und falten → 15 min ruhen lassen → portionieren → 20 h im Kühlschrank → 3 h bei Raumtemperatur → bei 400–450 °C 60–90 s backen.

Die Belagsmengen sind Richtwerte für eine Pizza aus einem 280-g-Teigling und werden an das gewählte Teiglinggewicht angepasst.

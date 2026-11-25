# 🍕 Pizzaabend-Rechner

**Version 1.5**

Eine kleine Web-App für den Pizzaabend mit vielen Gästen: Personenzahl eingeben, und die App berechnet Teig, Beläge, Einkaufsliste und einen Zeitplan bis zur ersten Pizza aus dem Gas-Pizzaofen.

**Zur App:** https://DEINNAME.github.io/pizza-rechner/
<!-- DEINNAME durch den eigenen GitHub-Namen ersetzen -->

---

## Funktionen

- **Navigationsleiste:** Bleibt oben stehen und führt direkt zu Einstellungen, Pizzen, Zeitplan, Einkauf, Rezept, Mise en place und Hinweisen; der aktuelle Bereich ist markiert.
- **Teigrechner:** Neapolitanischer Pizzateig mit 63 % Wasser und 20 h kalter Gare. Die App berechnet die Mengen für die eingestellte Personenzahl (Erwachsene und Kinder) und den Hunger.
  - **Teiglinggewicht:** Wird automatisch passend zu Gästezahl und Ofengröße (12 oder 16 Zoll) gewählt oder lässt sich frei einstellen.
  - **Salz:** üblich (30 g pro kg Mehl) oder weniger (20 g pro kg).
  - **Hefe:** Trockenhefe oder Frischhefe.
  - **Kneten:** mit Maschine, aufgeteilt in mehrere Durchgänge, mit Anzeige der erwarteten Knetzeit, oder von Hand mit eigener Knetzeit pro Portion.
- **Teigboxen:** Zeigt, wie die Teiglinge gleichmäßig auf die Boxen verteilt werden. Reichen die Boxen nicht, werden die vorhandenen voll belegt und die fehlenden gemeldet.
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
- **Automatisches Speichern:** Jede Eingabe wird sofort auf dem Gerät gespeichert. Mit „Neu“ gelten wieder die Standardwerte.
- **Als Datei speichern / Datei öffnen** (Menü „Datei“): Einstellungen samt Häkchen als `.json`-Datei sichern, auf ein anderes Gerät übertragen oder an andere weitergeben.
- **Teilen:** Link oder QR-Code erzeugen. Wer ihn öffnet, bekommt dieselben Einstellungen samt Termin, auf Wunsch auch die Häkchen; sie ersetzen dort die gespeicherten Einstellungen. Die Daten stecken komprimiert im Link (hinter dem `#`) und werden an keinen Server geschickt.
- **Offline nutzbar** und als App installierbar.

## Als App installieren

| Gerät | So geht's |
|---|---|
| Android (Chrome) | Seite öffnen → Menü ⋮ → **App installieren** bzw. **Zum Startbildschirm hinzufügen** |
| iPhone / iPad (Safari) | Seite öffnen → Teilen → **Zum Home-Bildschirm** |
| PC (Chrome / Edge) | Installations-Symbol rechts in der Adressleiste |

Nach dem ersten Öffnen mit Internet funktioniert die App auch ohne Netz.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App (HTML, CSS und JavaScript in einer Datei, inkl. QR-Code-Bibliothek *qrcode-generator* von Kazuhiko Arase, MIT-Lizenz) |
| `manifest.webmanifest` | App-Name, Farben und Icons für die Installation |
| `sw.js` | Service Worker: speichert die App für die Offline-Nutzung |
| `icon-192.png`, `icon-512.png`, `icon-180.png` | App-Icons (Android bzw. iOS) |

## Veröffentlichen mit GitHub Pages

1. Alle Dateien in das Repository hochladen, direkt ins Hauptverzeichnis und nicht in einen Unterordner.
2. **Settings → Pages**: als Branch `main` und als Ordner `/ (root)` wählen, dann **Save**.
3. Nach 1–2 Minuten ist die App unter `https://DEINNAME.github.io/REPO-NAME/` erreichbar.

## Aktualisieren

Um die App zu aktualisieren, reicht es, die neue `index.html` hochzuladen und die alte zu überschreiben. Die App holt sich die neue Version beim nächsten Öffnen mit Internet von selbst. Sollte das einmal nicht klappen, die Versionsnummer in `sw.js` erhöhen (`pizzaabend-v1` → `pizzaabend-v2`).

## Datenschutz

Die App hat kein Konto und keinen Server und erfasst keine Daten. Einstellungen und Häkchen werden nur im Browser des jeweiligen Geräts gespeichert (`localStorage`). Jedes Gerät hat deshalb seinen eigenen Stand.

## Grundrezept

| Zutat | Menge pro 1 kg Mehl |
|---|---|
| Mehl Typ 00 (11–15 % Protein) | 1000 g |
| Wasser | 630 g |
| Salz | 30 g (oder 20 g) |
| Trockenhefe / Frischhefe | 1 g / 3 g |

Kneten → dehnen und falten → 15 min ruhen lassen → portionieren → 20 h im Kühlschrank → 3 h bei Raumtemperatur → bei 400–450 °C 60–90 s backen.

Die Belagsmengen sind Richtwerte für eine Pizza aus einem 280-g-Teigling und werden an das gewählte Teiglinggewicht angepasst.

## Versionen

Die Änderungen lassen sich auch in der App nachlesen: unten auf die Versionsnummer tippen.

| Version | Datum | Änderungen |
|---|---|---|
| 1.5 | 26.11.2026 | Navigationsleiste mit Markierung des aktuellen Bereichs · neue Reihenfolge der Bereiche · „Zurück zum Zeitplan“ entfällt · Datei-Menü nicht mehr abgeschnitten |
| 1.4 | 25.11.2026 | Teilen per Link und QR-Code (auf Wunsch mit Häkchen) · Ausdruck zeigt abgehakte Einträge, Häkchen in der Datei mitgespeichert · automatisches Speichern · Symbole für Teilen, Drucken, Neu und Datei · Teigboxen: vorhandene zuerst voll belegen · anklickbare Versionsnummer mit Änderungsübersicht |
| 1.3 | 22.11.2026 | „Zurück zum Zeitplan“ nach einem Sprung aus dem Zeitplan |
| 1.2 | 22.11.2026 | Kneten von Hand mit eigener Knetzeit; erwartete Knetzeit bei Maschine |
| 1.1 | 22.11.2026 | Button „Zum Zeitplan“ |
| 1.0 | 22.11.2026 | Erste Version |

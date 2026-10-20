# WerkHub

Ein unabhängiges, mobiloptimiertes Web-Portal für zwölf Websites: die beiden bereits bestehenden Projekte **FormatWerk** und **KI-Finder** sowie zehn neue, direkt nutzbare Browser-Tools.

## Starten

`index.html` öffnen. Für die veröffentlichte Version den **gesamten** Inhalt dieses Verzeichnisses (inklusive `assets/`) bei einem statischen Website-Hostingdienst veröffentlichen, zum Beispiel Netlify Drop oder GitHub Pages. Weder Serverprogrammierung noch Datenbank oder Registrierung sind erforderlich.

## Enthaltene Websites

| Website | Nutzbare Funktionen |
| --- | --- |
| LernWerk | Karteikarten, Antworten umdrehen, Fokus-Timer |
| DesignWerk | Poster-Generator mit 3 Layouts, Text- und Farbanpassung, PNG-Export |
| QRWerk | Webseiten-/Text- und WLAN-QR-Codes, Farbauswahl, PNG-Export |
| FinanzWerk | Einnahmen/Ausgaben, Kategorien, Übersicht, CSV-Export |
| KarriereWerk | Lebenslauf-Editor, Live-Vorschau, Drucken/als PDF speichern |
| BildWerk | JPG/PNG/WebP öffnen, Helligkeit, Kontrast, Sättigung, Filter, Rotation, PNG |
| PlanWerk | Dreispaltiges Aufgabenboard, Fälligkeit, erledigte Aufgaben |
| RechenWerk | Prozentwert, Zinseszins, verschiedene Einheiten |
| SpielWerk | Memory-Spiel und Reaktionsspiel |
| WebWerk | JSON-Formatierer/Minimierer, CSS-Gradient- und Radiusgenerator |

Die bereits vorhandenen Websites **FormatWerk** und **KI-Finder** sind als funktionierende externe Links im Portal eingetragen. Die Originalseiten werden nicht überschrieben oder kopiert.

## FormatWerk und KI-Finder – bereits verknüpft

Die zwei veröffentlichten Originalseiten sind **fest im WerkHub hinterlegt**:

- **FormatWerk:** https://formatwerk.ablerain7.chatgpt.site/
- **KI-Finder:** https://ki-finder.ablerain7.chatgpt.site/

Kacheln und App-Menü führen direkt zu den beiden Websites. Diese Adressen stehen in `assets/config.js` und gelten damit nach Veröffentlichung von WerkHub für alle Besucher. Es sind externe Links – keine Kopien der Originalseiten. Das Öffnen erfolgt in einem neuen Tab, damit WerkHub als Ausgangspunkt erhalten bleibt.

Über »Apps → Links« können Besucher die URLs lokal im jeweiligen Browser überschreiben. Das ändert die öffentlichen Standardlinks nicht.

## Auf FormatWerk und KI-Finder dieselbe Navigation anzeigen

Damit man von **jeder** Website auf alle anderen wechseln kann, diese Zeile in den HTML-Code **beider vorhandenen Websites** unmittelbar vor `</body>` einfügen und beide Websites erneut veröffentlichen:

```html
<script defer src="https://DEINE-WERKHUB-DOMAIN/assets/site-switcher.js"></script>
```

Die URL muss an die Adresse der veröffentlichten WerkHub-Website angepasst werden. Das Script fügt oben rechts ein Menü für alle 12 Websites ein und lädt die über `config.js` festgelegten URLs. **Wichtig:** Die Live-Links reichen aus, um die beiden Seiten **von WerkHub aus** zu öffnen. Ein Wechselmenü **direkt auf** FormatWerk und KI-Finder erfordert Änderungen an deren Originalcode oder eine Bearbeitung im jeweiligen Website-Editor. Nur durch Kenntnis der öffentlich sichtbaren URLs kann WerkHub diese fremden Seiten nicht verändern.

## Datenschutz und technische Grenzen

- Alles arbeitet statisch im Browser, ohne integrierten KI-Dienst, Server-Login oder eigene Datenbank.
- Gespeicherte Karten, Buchungen, Aufgaben und Designfelder verwenden `localStorage` des Browsers. **Keine Synchronisierung** zwischen Geräten, Browsern oder Domains. Cache-/Browserdaten-Löschung kann sie löschen.
- Dateien in BildWerk werden im Browser verarbeitet und nicht hochgeladen.
- Der Lebenslauf verwendet für PDF den Browser-Druckdialog (Option „Als PDF speichern“), kein direktes PDF-Backend.
- Es sind **funktionierende Grundversionen**, nicht vollständig ausgebaute Alternativen zu Canva, Photoshop oder einem Online-Banking-Programm.
- Die QR-Bibliothek basiert auf dem MIT-lizenzierten `QRCode for JavaScript` von Kazuhiko Arase; Hinweis im Bundle enthalten.
- Kostenloses Hosting ist bei entsprechenden Gratis-Tarifen möglich. Eigene Premium-Domains können Kosten verursachen.

## Dateien

- `index.html` – Startseite
- `*.html` – die zehn neuen Browser-Tools
- `assets/app.js` – gemeinsame Navigation und Tool-Logik
- `assets/style.css` – responsive Oberflächengestaltung, Dark-/Light-Mode
- `assets/config.js` – die beiden bereits eingetragenen öffentlichen Website-Adressen
- `assets/site-switcher.js` – Navigationsmenü zum Einbauen auf bestehenden Websites
- `assets/qr-bundle.js` – lokal enthaltene QR-Code-Bibliothek

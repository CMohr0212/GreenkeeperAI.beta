# Pflanzenglossar — als App veröffentlichen

Dieser Ordner ist fertig zum Hochladen. Sobald er über eine Internetadresse
erreichbar ist, lässt sich die App auf dem Startbildschirm installieren und
läuft danach offline weiter.

## Was drin ist

| Datei | wofür |
|---|---|
| `index.html` | die komplette App, ein einziges Dokument |
| `manifest.webmanifest` | Name, Farben, Symbole, Schnellzugriffe |
| `sw.js` | Offline-Betrieb und Aktualisierungen |
| `icon-192.png`, `icon-512.png` | Symbole für Startbildschirm und Menü |
| `icon-maskable.png` | Symbol für Android, das eigene Formen zuschneidet |
| `apple-touch-icon.png` | Symbol für iPhone und iPad |

## Einmalig einrichten

1. Bei GitHub ein neues Projekt anlegen, zum Beispiel `pflanzenglossar`.
   Sichtbarkeit **public** — bei privaten Projekten funktioniert Pages nur
   mit kostenpflichtigem Konto.
2. Alle Dateien aus diesem Ordner hochladen. Nicht den Ordner selbst,
   sondern seinen Inhalt — `index.html` muss ganz oben liegen.
3. Im Projekt auf **Settings**, links **Pages**.
4. Bei *Source* **Deploy from a branch** wählen, Branch `main`, Ordner `/ (root)`,
   dann **Save**.
5. Nach ein bis zwei Minuten steht die Adresse oben auf derselben Seite:
   `https://DEINNAME.github.io/pflanzenglossar/`

## Installieren

- **Android, Chrome:** Beim Öffnen erscheint meist von selbst eine Einladung.
  Sonst unter *Mehr → Als App installieren*, oder im Browsermenü
  „Zum Startbildschirm hinzufügen“.
- **iPhone, Safari:** Teilen-Symbol antippen, dann „Zum Home-Bildschirm“.
  Safari zeigt keine eigene Einladung, das ist normal.
- **Rechner, Chrome oder Edge:** Symbol in der Adressleiste, oder Menü →
  „Installieren“.

Danach startet die App ohne Browserleiste, mit eigenem Symbol, und funktioniert
ohne Internet.

## Eine neue Fassung veröffentlichen

1. In `sw.js` die Zeile `const VERSION = 'pflanzenglossar-v1';` hochzählen,
   also `v2`, `v3` und so weiter. **Das ist der wichtige Schritt** — ohne ihn
   halten die Geräte an der alten Fassung fest.
2. Die neue `index.html` und die geänderte `sw.js` hochladen.
3. Fertig. Jedes Gerät bekommt beim nächsten Öffnen den Streifen
   „Eine neue Fassung ist da“ mit einem Knopf zum Laden.

Eine dauerhaft geöffnete App sieht alle sechs Stunden selbst nach.

## Was mit den Daten passiert

Pflanzen, Fotos, Räume und Einstellungen liegen im Browser des jeweiligen
Geräts, nicht auf dem Server. Eine neue Fassung rührt sie nicht an.

Trotzdem: **vor größeren Umstellungen eine Sicherung herunterladen**, unter
*Mehr → Sicherung*. Wer die App vom Startbildschirm löscht, löscht je nach
Gerät auch die Daten.

Wichtig zu wissen: Jede Adresse hat ihren eigenen Speicher. Wer die App bisher
als Datei aus dem Download-Ordner benutzt hat, findet unter der neuen
Internetadresse zunächst eine leere Sammlung. Der Weg dorthin:
Sicherung in der alten Fassung herunterladen, neue Adresse öffnen,
unter *Mehr → Sicherung laden* einlesen.

## Wenn etwas klemmt

- **Seite bleibt weiß:** Pages braucht nach dem ersten Einrichten ein paar
  Minuten. Adresse mit `/` am Ende aufrufen.
- **Keine Einladung zum Installieren:** Die Adresse muss mit `https` beginnen.
  Über `file://` aus dem Download-Ordner geht es nicht.
- **Alte Fassung bleibt hartnäckig:** Wurde die Zahl in `sw.js` erhöht?
  Zur Not im Browser die Seitendaten für diese Adresse leeren — vorher sichern.

# Pocket Pong · SAMIX

Tischtennis gegen die KI – Wischen zum Schlagen, wer zuerst 7 Punkte hat, gewinnt.
**GAMES · APPS · INNOVATION – CREATED BY SAMI**

## Auf GitHub Pages veröffentlichen

1. ZIP entpacken.
2. Auf github.com ein Repository öffnen (oder neu anlegen) → **Add file → Upload files**.
3. Diese Dateien hochladen (alle liegen direkt im Ordner, **keine Unterordner nötig**):
   - `index.html` ← das ganze Spiel steckt in dieser einen Datei (Pflicht)
   - `sw.js` ← Offline-Modus
   - `manifest.webmanifest`, `favicon.png`, `apple-touch-icon.png`, `icon-512.png` ← Homescreen-Icon
   - `.nojekyll` (leere Datei; auf dem iPhone nicht sichtbar, darf fehlen)
   
   Der Ordner `quellcode/` ist nur für die Weiterentwicklung und muss **nicht** hochgeladen werden.
4. **Commit changes** → im Repository **Settings → Pages → Branch: main, Ordner: / (root) → Save**.
5. Nach 1–2 Minuten ist das Spiel unter `https://<dein-name>.github.io/<repository>/` erreichbar.

Ein Update funktioniert genauso: Dateien erneut hochladen (gleiche Namen ersetzen die alten).
Bei neuer Version in `sw.js` die Zahl bei `VERSION` erhöhen, damit alte Offline-Kopien ersetzt werden.

## Offline spielen

Es werden keine CDNs, Schriftarten oder Online-Dienste verwendet. Einmal mit Internet öffnen – danach
startet das Spiel auch ohne Verbindung (Safari: Teilen → „Zum Home-Bildschirm“ für Vollbild).
Ohne Server (Doppelklick auf `index.html` am Computer) läuft es ebenfalls, nur ohne Offline-Cache.

## Wenn es nicht startet

Der Ladebildschirm zeigt unter „Neu laden“ eine kurze Fehlernotiz. „Neu laden“ löscht außerdem eine
mögliche kaputte Offline-Kopie. Hilft das nicht: Screenshot der Notiz schicken.

## Weiterentwickeln

Der Spielcode liegt in `quellcode/` (`main.js`, `scenes/`, `systems/`, `ui/` …, Design in `styles.css`,
Seite in `index.template.html`). Nach Änderungen `index.html` neu erzeugen (Node.js 18+):

    cd quellcode
    sh build/build.sh

`index.html?tune` öffnet das Tuning-Panel (KI- und Ballparameter live ändern).
Engine: Phaser 3.70.0 (MIT-Lizenz, unverändert, Lizenztext in `quellcode/vendor/`).

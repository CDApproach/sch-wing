# Sch-Wing

Weltraum-Raumkampf im Stil von X-Wing (1993) für das Smartphone, direkt im Browser.

**Spielen:** https://cdapproach.github.io/sch-wing/

## Steuerung

- Handy **quer wie ein Lenkrad** halten
- **Drehen** (wie ein Lenkrad) lenkt nach links und rechts
- **Kippen**: Oberkante zu dir zieht die Nase hoch, Oberkante von dir weg drückt sie runter
- **FEUER**-Knöpfe unten links und rechts
- Beim Start und nach jeder Pause wird die aktuelle Handhaltung als Nullstellung übernommen
- Im Pausemenü lassen sich Hoch/Runter umkehren, die Empfindlichkeit und der Ton einstellen
- Am PC: Pfeiltasten/WASD, Leertaste, P für Pause

Tipp: Über „Zum Startbildschirm hinzufügen“ läuft das Spiel als Vollbild-App ohne Browserleiste.

## Technik

Eine einzige `index.html` mit [Three.js](https://threejs.org/) (WebGL). Die Steuerung nutzt
`DeviceOrientationEvent` und wertet nur die Lage relativ zur Schwerkraft aus, deshalb driftet
die Steuerung nicht, wenn man sich mit dem Handy dreht. Alle Sounds werden per Web Audio erzeugt.
Bei jedem Push auf `main` veröffentlicht GitHub Actions das Spiel auf GitHub Pages.

Lokal testen: `python3 -m http.server` im Ordner starten. Mit `?debug` in der URL steht
`window.sw` für Tests in der Konsole bereit.

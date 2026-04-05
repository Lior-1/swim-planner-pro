# Lior's Swim Planner Pro

Ein professioneller Schwimmtrainingsplaner als Single-Page-Webanwendung. Erstelle, bearbeite und teile Trainingspläne mit PDF-Export, QR-Codes und Druckfunktion.

**Live:** [lior-1.github.io/swim-planner-pro](https://lior-1.github.io/swim-planner-pro/)

---

## Features

- **Editor** — Abschnitte (Einschwimmen, Hauptteil, Ausschwimmen, ...) mit beliebig vielen Zeilen, Drag & Drop zum Umsortieren
- **Vorschau** — Druckfertige Dokumentansicht mit automatischer Seitenaufteilung
- **PDF-Export** — Pixelgenaue A4-PDFs mit eingebettetem QR-Code und Plandaten
- **Drucken** — Optimiertes Print-Layout mit mehrseitigem Support
- **Word-Export**(in arbeit) — Trainingspläne als Word-Dokument (.docx)
- **QR-Code-Sharing** — Kompletter Trainingsplan im QR-Code, kein Server nötig
- **Kompression** — Deflate-Komprimierung für kompaktere QR-Codes (Z.-Prefix)
- **Dark Mode** — Umschaltbar zwischen Hell und Dunkel
- **Passwortschutz** — SHA-256-basierter Zugangsschutz mit Anti-Tamper-Schutz
- **Offline** — Komplett clientseitig, keine Serveranbindung, keine Datenbank
- **Gruppen** — Vordefinierte Schwimmgruppen (Robben, Delphine, Haie, TGB)
- **Materialien** — Brett, Flossen, Pullbuoy, Paddles, Schnorchel
- **Tempo-Rechner** — Geschätzte Trainingszeit basierend auf einstellbarem Tempo
- **Import/Export** — `.swimplan`-Dateien per Drag & Drop laden und speichern

## Technologien

| Bibliothek | Zweck |
|---|---|
| [jsPDF](https://github.com/parallax/jsPDF) | PDF-Generierung |
| [html2canvas](https://html2canvas.hertzen.com/) | HTML-zu-Bild-Konvertierung |
| [QRCode.js](https://github.com/davidshimjs/qrcodejs) | QR-Code-Erzeugung |
| [PDF.js](https://mozilla.github.io/pdf.js/) | PDF-Parsing beim Import |
| Web Crypto API | SHA-256-Passwort-Hashing |
| CompressionStream API | Deflate-Komprimierung der QR-Daten |

**Fonts:** EB Garamond (Serif), DM Mono (Monospace) via Google Fonts

## Dateien

| Datei | Beschreibung |
|---|---|
| `index.html` | Hauptanwendung (passwortgeschützt) |
| `viewer.html` | Viewer für QR-Code-Links |
| `apple-touch-icon.png` | App-Icon |

## Passwortschutz

Die Anwendung ist passwortgeschützt. Der Schutz basiert auf:

- **Template-Gate:** Der gesamte App-Inhalt liegt in einem `<template>`-Element und wird erst nach korrekter Passworteingabe in den DOM injiziert
- **SHA-256-Hash:** Kein Klartext-Passwort im Quellcode
- **Anti-Tamper:** MutationObserver erkennt Manipulation des Passwort-Overlays via DevTools


## Lizenz

Dieses Projekt ist privat und nicht zur Weiterverbreitung bestimmt.

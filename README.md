# EarnTrack – Handwerkersoftware (Website)

Dieses Repository enthält die statische Website von **EarnTrack** (https://earntrack.de) –
eine Handwerkersoftware für kleine und mittlere Betriebe in Deutschland (1–50 Mitarbeiter).
Deployment: Cloudflare Pages. Inhalt: SEO-Seiten, Ratgeber und Vergleichsseiten als
selbstgehostete, DSGVO-freundliche HTML-Dateien (keine Drittanbieter-Schriftarten, keine Tracking-Pixel).

## Produkt

EarnTrack („EarnTrack Business Manager") ist die digitale Betriebsführung fürs Handwerk:

- **Projekte, Kunden, Termine & Kalender**
- **Mobile Zeiterfassung** mit Pausen (Clock-In auf der Baustelle)
- **Rechnungen, Angebote & Kostenvoranschläge**, Mahnwesen (1. & 2. Mahnung)
- **ZUGFeRD-E-Rechnung**, DATEV-Export, sevDesk- & Lexware-Office-API
- **Profit Score A+ bis F** – Profitabilität pro Auftrag, Termin und Mitarbeiter
- **Lagerverwaltung** mit QR-Scan, Mindestbestand und Bestellvorschlag
- **DATANORM-Import** (Business-Plan)

Plattformen: Web-App, iOS (App Store), Android. 14 Tage kostenlos testbar, ohne Zahlungsdaten.
Entwickelt und gehostet in Deutschland, DSGVO-konform.

## Preise

| Plan | Preis/Monat | Features |
|---|---|---|
| Solo | 27,99 € (statt 39,99 €) | bis 2 Mitarbeiter, Kernfunktionen inkl. Profit Score |
| Team | 49,99 € | bis 5 Mitarbeiter, + DATEV-Export |
| Business | 79,99 € | unbegrenzt Mitarbeiter, + DATANORM-Import |

Monatlich kündbar, keine Mindestlaufzeit, alle Preise öffentlich.

## Website-Struktur

- `index.html` – Startseite
- `handwerker-software-vergleich.html` – EarnTrack vs. Plancraft vs. WinWorker
- `plancraft-alternative.html`, `tooltime-alternative.html`, `winworker-alternative.html` – Einzelvergleiche
- Ratgeber: Zeiterfassung, E-Rechnung, Kostenvoranschlag, Lagerverwaltung, Kalkulation, Stundenzettel
- Rechtliches: Impressum, Datenschutz, AGB
- `sitemap.xml`, `robots.txt`, `llms.txt`, `_headers`, `_redirects` – technische SEO/Deploy-Dateien

## Deployment

```bash
npx wrangler pages deploy . --project-name earntrack-website --branch main
```

## Status

- Live: https://earntrack.de
- Web-App: https://app.earntrack.de

Alle Markennamen der genannten Wettbewerber gehören ihren jeweiligen Eigentümern.

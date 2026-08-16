# SEO-Plan earntrack.de

Stand: 16.08.2026

---

## 1. Cloudflare robots.txt-Konflikt beheben (PRIORITÄT 1)

**Problem:** Cloudflare prependet eine "Managed robots.txt" mit `Disallow: /` für
GPTBot, Google-Extended, CCBot, ClaudeBot, Applebot-Extended u. a. Diese Regeln
stehen VOR den eigenen Allow-Regeln und gewinnen daher (RFC 9309). Die gewollte
AI-Zugänglichkeit ist damit komplett deaktiviert.

**Fix im Cloudflare Dashboard:**
1. Cloudflare Dashboard → **Security → Bots** (bzw. unter "Settings").
2. "Managed robots.txt" / AI-Bot-Blockierung **deaktivieren** – oder die gewünschten
   Crawler dort explizit **allowlisten** (GPTBot, OAI-SearchBot, ChatGPT-User,
   Google-Extended, ClaudeBot, Claude-Web, CCBot, PerplexityBot, Applebot).
3. Verifizieren: `curl https://earntrack.de/robots.txt`
   → Es darf nur noch die eigene Datei erscheinen (kein "BEGIN Cloudflare Managed content").
4. Anschließend in Google Search Console "Seitenabruf" für `https://earntrack.de/robots.txt` auslösen.

Die lokale `robots.txt` wurde bereits um die fehlenden Tokens ergänzt
(`ClaudeBot`, `OAI-SearchBot`, `ChatGPT-User`, `Applebot`, `Applebot-Extended`).

---

## 2. Content-Expansionsplan

### Strategie
EarnTrack ist neu und hat kaum Backlinks → **Nicht gegen die Platzhirsche (Meisterbock,
Plancraft) auf Head-Terms antreten, sondern mit "Alternative-zu"-Seiten und
vergleichbaren Long-Tail-Themen einsteigen.** Das Muster `handwerker-software-vergleich`
(Transparenz-Disclosure + echte Vergleiche) funktioniert und wird als Vorlage genutzt.

### Priorisierte Content-Pipeline (Phase 1 – sofort, ~4–6 Wochen)

#### A. "Alternative-zu"-Vergleichsseiten (höchster kommerzieller Intent)
| Seite | Ziel-Keyword | Suchintent |
|---|---|---|
| `/plancraft-alternative` | plancraft alternative | Wechselwillige Plancraft-Nutzer |
| `/winworker-alternative` | winworker alternative | Wechselwillige WinWorker-Nutzer |
| `/meisterbock-alternative` | meisterbock alternative | Größter Konkurrent, hohes Volumen |
| `/handwerkersoftware-test` | handwerkersoftware test / Vergleich | Entscheidungsphase |

Pro Seite: gleiche Struktur wie der bestehende Vergleich (Disclosure, Tabelle,
"Für wen lohnt sich Wechsel", FAQ + FAQPage-Schema, SoftwareApplication-Schema).
Keine Keyword-Kannibalisierung: Alternative-Seiten fokussieren den **Wechsel**,
die Vergleichsseite bleibt der generische 3-Wege-Vergleich.

#### B. Modul-Ratgeber (Middle-of-Funnel, Features)
| Seite | Ziel-Keyword | Anmerkung |
|---|---|---|
| `/rechnungsprogramm-handwerker` | rechnungsprogramm handwerker | Hohes Volumen |
| `/angebotssoftware-handwerker` | angebotssoftware handwerker | Hohes Volumen |
| `/mahnwesen-handwerker` | mahnung erstellen / mahnwesen software | Feature Mahnwesen |
| `/baustellen-app` | baustellen app handwerker | Mobile Unique Selling Point |
| `/stundenzettel-digital` | digitale stundenzettel / stundenzettel app | Überschneidung Zeiterfassung beachten |
| `/arbeitszeiterfassung-handwerker` | arbeitszeiterfassung pflicht 2026 | Topical-Moment (EuGH/BAG) |
| `/handwerker-software-kosten` | handwerkersoftware kosten | Preis-Recherche, Conversion |

#### C. Branchen-Spezialseiten (Long-Tail, pro Gewerk)
`/elektriker-software`, `/sanitaer-software`, `/malerbetrieb-software`,
`/dachdecker-software`, `/galabau-software` – je Gewerk eine Seite mit eigenem
Workflow, eigener FAQ. Volumen einzeln klein, summiert relevant; stärkt
Topical Authority der ganzen Domain.

#### D. Informations-/Glossar-Seiten (Top-of-Funnel + AI-SEO)
- `/lexikon` (kleines Handwerker-Software-Lexikon: ZUGFeRD, XRechnung, DATEV-Export, GAEB)
- `/was-ist-e-rechnung` / `/zugferd-erklaert` (eigenständige FAQ-Artikel)
- llms.txt regelmäßig pflegen (neue Seiten ergänzen)

### Interne Verlinkung
- **Jede neue Seite** in die "Weitere Ratgeber"-Sektion aller bestehenden Guides aufnehmen.
- Vergleichsseite bleibt Hub: Alternative-Seiten verlinken auf sie und umgekehrt.
- Ziel: Jede Seite ≤ 3 Klicks von der Startseite. Keine Orphan Pages.
- Anchor-Texte natürlich, nicht exakt-match-überladen.

### Schema (pro neue Seite)
- Article + FAQPage (Ratgeber)
- Article + FAQPage + SoftwareApplication (Vergleichsseiten)
- Optional: BreadcrumbList auf allen Unterseiten.

### Messung & Pflege
- Search Console: Coverage + Performance je Seite monatlich prüfen.
- Titel/Description-Muster der bestehenden Seiten übernehmen (Keyword-first, 50–60 Zeichen).
- Daten in Vergleichsseiten (Preise, Features) mit Datum ("Stand ...") + Lastmod aktuell halten.

---

## 3. Authority / Off-Page (parallel starten)

- **Directory-Submissions:** Handwerker-Portale, Software-Verzeichnisse
  (GetApp, Capterra, OMR Reviews, Trustpilot), Startup-/SaaS-Verzeichnisse.
- **Google Business Profile** für die Firma einrichten/pflegen (local signals).
- **Erste Backlinks** via Gastartikel/Interviews in Handwerker-Medien und Partner-Tooling
  (sevDesk-/Lexware-Erwähnungen). Nicht kaufen.

---

## 4. Quick Wins – erledigt (16.08.2026)
- robots.txt: ClaudeBot, OAI-SearchBot, ChatGPT-User, Applebot ergänzt + CF-Konflikt dokumentiert
- og:image width/height/alt + twitter:card auf allen 5 Landing Pages ergänzt
- E-Rechnung-Titel: Jahr 2026 ergänzt
- Homepage-Titel: "Handwerker Software" eingearbeitet (title/og/twitter)

### Noch offen (sofern gewünscht)
- Cloudflare-Dashboard-Fix (nur über Dashboard möglich – s. Abschnitt 1)
- ggf. H1 der Startseite um Keyword ergänzen (aktuell nur Eyebrow) – bewusst offengelassen,
  da der Benefit-H1 konversionsstark ist.

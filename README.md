# Plenzdorf IT — Freelancer-Website

Professionelle Website für den freiberuflichen Auftritt von Christian Plenzdorf:
**Software-Test & Qualitätssicherung** (Senior Test Engineer).

## Struktur

```
├── index.html          # Startseite mit allen Sektionen
├── impressum.html      # Impressum (Vorlage, siehe unten)
├── datenschutz.html    # Datenschutzerklärung (Vorlage, siehe unten)
├── 404.html            # Individuelle Fehlerseite
├── sitemap.xml         # Für Suchmaschinen
├── robots.txt          # Für Suchmaschinen
├── css/style.css       # Komplettes Styling (Dark Theme, responsiv)
├── js/main.js           # Navigation, Scroll-Animationen, Zähler, Formular-Versand
└── assets/logo.png     # Logo
```

## Lokal öffnen

Einfach `index.html` im Browser öffnen — keine Build-Tools nötig.
Alternativ mit lokalem Server:

```bash
python -m http.server 8000
```

---

## ✅ Go-Live-Checkliste

### 1. Domain & Hosting
- Domain registrieren (z. B. `plenzdorf-it.de`).
- Statisches Hosting einrichten — z. B. **Netlify**, **Vercel** oder **GitHub Pages**
  (alle kostenlos für diesen Seitentyp, mit automatischem HTTPS).
- Alternativ klassisches Webhosting — dann SSL-Zertifikat separat aktivieren.

### 2. Platzhalter ersetzen
Folgende Stellen enthalten noch Platzhalter-Werte, die vor dem Livegang ausgetauscht werden müssen:

| Datei | Platzhalter | Ersetzen durch |
|---|---|---|
| `index.html` | `kontakt@plenzdorf-it.de` (Kontaktbereich + Formular-`action`) | Deine echte E-Mail-Adresse |
| `index.html` | `https://www.plenzdorf-it.de/` (Open-Graph-/Canonical-Tags) | Deine echte Domain |
| `sitemap.xml`, `robots.txt` | `https://www.plenzdorf-it.de/` | Deine echte Domain |
| `impressum.html` | Alle `[Platzhalter]` | Deine echten Angaben (Name, Adresse, USt-ID) |
| `datenschutz.html` | Alle `[Platzhalter]` | Deine echten Angaben (Hosting-Anbieter, ggf. Analytics-Tool) |

### 3. Kontaktformular aktivieren
Das Formular ist technisch bereits an **[FormSubmit.co](https://formsubmit.co)** angebunden —
ein kostenloser Dienst, der **keinen Account** benötigt, nur deine Ziel-E-Mail-Adresse:

1. In `index.html` im `<form>`-Tag die E-Mail in der `action`-URL ersetzen:
   `action="https://formsubmit.co/ajax/DEINE-ECHTE-ADRESSE@domain.de"`
2. Einmal die Website live testen und das Formular absenden.
3. FormSubmit schickt dir eine **einmalige Bestätigungs-E-Mail** — den Link darin bestätigen.
4. Ab dann kommen alle Formular-Anfragen direkt in dein Postfach.

Alternativen, falls gewünscht: [Formspree](https://formspree.io) (Account nötig, mehr Kontrolle)
oder ein eigenes kleines Backend.

### 4. Rechtliches final prüfen lassen
`impressum.html` und `datenschutz.html` sind Basis-Vorlagen, die die gängigen Pflichtangaben
abdecken (§5 DDG, DSGVO-Grundgerüst). **Das ersetzt keine Rechtsberatung.** Lass die finalen
Texte von einem Anwalt, deiner IHK oder einem Dienst wie [eRecht24](https://www.e-recht24.de/)
gegenprüfen — insbesondere, falls du später Analytics-Tools oder Cookies einsetzt.

### 5. Sonstiges (empfohlen)
- Echtes Portraitfoto im „Über mich"-Bereich statt „CP"-Monogramm einsetzen.
- Google Search Console einrichten und `sitemap.xml` dort einreichen.
- Datenschutzfreundliches Analytics (z. B. Plausible, Fathom) ergänzen, falls gewünscht.
- Nach dem Livegang: [Google Lighthouse](https://developer.chrome.com/docs/lighthouse) laufen
  lassen (Performance, Barrierefreiheit, SEO) und auf echtem Mobilgerät testen.
- `og:image` (aktuell `assets/logo.png`) durch ein dediziertes 1200×630-px-Social-Preview-Bild
  ersetzen, falls gewünscht.

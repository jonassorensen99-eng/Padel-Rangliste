# PadelRangliste – Teknisk dokumentation

Webbaseret platform til håndtering af padelkampe, ranglister og banebooking for Padel Centre.

---

## Indhold

- [Projektbeskrivelse](#projektbeskrivelse)
- [Teknologier](#teknologier)
- [Filstruktur](#filstruktur)
- [Sider](#sider)
- [Designsystem](#designsystem)
- [Navigation](#navigation)
- [Sådan åbnes projektet](#sådan-åbnes-projektet)

---

## Projektbeskrivelse

PadelRangliste er en statisk HTML/CSS-hjemmeside uden brug af backend eller databaser. Platformen giver spillere mulighed for at:

- Følge en live rangliste med pointsystem inspireret af ELO-rating
- Tilmelde sig kampdage og events
- Booke padelbaner direkte på sitet
- Finde og booke professionelle trænere
- Læse om priser, åbningstider og konceptet bag platformen

Projektet er udviklet som et studieprojekt og fungerer udelukkende som en prototype.

---

## Teknologier

| Teknologi | Anvendelse |
|-----------|------------|
| HTML5 | Sidestruktur og indhold |
| CSS3 | Styling, layout og responsivt design |
| GitHub | Versionsstyring og repository-hosting |

Der er ikke anvendt JavaScript, frameworks eller eksterne biblioteker. 

---

## Filstruktur

```
Padel-Rangliste/
│
├── index.html          # Forside / startside
├── om.html             # Om platformen og konceptet
├── rangliste.html      # Spillerrangliste med pointoversigt
├── Events.html         # Kommende kampdage og turneringer
├── Traener.html        # Oversigt over trænere og booking
├── booking.html        # Banebooking med ledige tider
├── Priser.html         # Priser for medlemskab og baneleje
├── kom-i-gang.html     # Guide til nye spillere
├── aabningstider.html  # Centrets åbningstider
│
├── style.css           # Globalt stylesheet (layout, nav, footer, typografi)
├── components.css      # Genanvendelige komponenter (kort, tabel, trin)
│
└── README.md           # Teknisk dokumentation (denne fil)
```

## Sider

### `index.html` — Forside
Velkomstsiden med hero-sektion, platformsoverblik, feature-kort og kontaktinformation. Fungerer som brugerens første møde med platformen.

### `om.html` — Om os
Beskriver platformens koncept, turneringsformat og pointgivning. Forklarer de tre kerneelementer: ranglisten, turneringsformatet og ELO-pointsystemet.

### `rangliste.html` — Rangliste
Viser alle 100 registrerede spillere sorteret efter point. Indeholder:
- Farvekodet niveauoversigt (Elite → Begynder)
- Medaljer til top 3
- Trin-for-trin forklaring af pointsystemet

**Niveauer:**

| Niveau | Point |
|--------|-------|
| Elite | 876 – 1000 |
| Avanceret | 676 – 875 |
| Øvet | 376 – 675 |
| Mellemliggende | 151 – 375 |
| Begynder | 1 – 150 |

### `Events.html` — Events
Oversigt over kommende kampdage og turneringer med dato, tidspunkt, sted og tilmeldingsinfo. Nye spillere starter med 50 point ved registrering.

### `Traener.html` — Find en træner
Præsentation af centrets trænere med certifikater, specialer og bookingmulighed.

### `booking.html` — Book en bane
Visuel tidsoversigt for 4 baner (Bane 1–4, fordelt på indendørs og udendørs) med ledige og optagede tider fra kl. 07–22. Booking kræver login.

**Priser for baneleje:**

| Tidspunkt | Pris |
|-----------|------|
| Dagtid (man–fre 07–15) | 150 kr./time |
| Eftermiddag (man–fre 15–22) | 200 kr./time |
| Weekend (lør–søn 08–20) | 225 kr./time |
| Ketcherleje | 50 kr./stk. |

### `Priser.html` — Priser
Samlet prisoversigt for baneleje, medlemskaber og trænersessioner.

### `kom-i-gang.html` — Kom i gang
Step-by-step guide til nye spillere i 5 trin: opret profil → angiv niveau → tilmeld kampdag → mød op → følg ranglisten. Indeholder FAQ og direkte links til relevante sider.

### `aabningstider.html` — Åbningstider
Centrets åbningstider opdelt på ugedage med eventuelle undtagelser og helligdage.

---

## Designsystem

### Farvepalette

| Variabel | Hex-kode | Anvendelse |
|----------|----------|------------|
| `--groen` | `#1B5E20` | Primærfarve, nav, overskrifter |
| `--groen-lys` | `#2E7D32` | Hover-states, gradienter |
| `--groen-meget-lys` | `#e8f5e9` | Baggrunde, badges |
| `--gul` | `#F9A825` | Accent, knapper, aktive nav-links |
| `--hvid` | `#ffffff` | Sektionsbaggrunde |
| `--lys-graa` | `#f5f5f5` | Alternerende sektionsbaggrunde |
| `--graa` | `#757575` | Brødtekst, undertitler |
| `--moerk-graa` | `#212121` | Primær tekstfarve, footer |

### Stylesheets

**`style.css`** — det globale stylesheet indeholder:
- CSS-nulstilling og CSS-variabler (`:root`)
- Navigation (sticky, grøn baggrund, gul aktiv-markering)
- Hero-sektioner (`.hero` til forsiden, `.side-hero` til undersider)
- Knapper (`.knap-primær` og `.knap-sekundær`)
- Sektionstyper (`.sektion-hvid`, `.sektion-graa`, `.sektion-groen`)
- Footer (tre kolonner, mørk baggrund)
- Responsivt design (breakpoint ved 768px)

**`components.css`** — genanvendelige UI-komponenter:
- `.kort-grid` / `.kort` — kortgrid med hover-effekt
- `.trin-liste` / `.trin` / `.trin-nummer` — nummereret trin-guide
- `table`, `thead`, `tbody` — ranglistetabel med zebra-striping
- `.placering`, `.top-1`, `.top-2`, `.top-3` — placeringsbadges
- `.point-badge` — grønt pointbadge til ranglisten

### Typografi

- **Skrifttype:** `Segoe UI`, Arial (systemskrifttyper, ingen ekstern afhængighed)
- **Basisstørrelse:** 16px
- **Linjeafstand:** 1.6

---

## Navigation

Alle sider deler den samme navigationslinje med følgende links i fast rækkefølge:

```
Hjem | Om os | Rangliste | Events | Find en træner | Book en bane | Priser | Kom i gang | [Login]
```

Den aktive side markeres med klassen `.aktiv` (gul baggrund). Login-knappen har klassen `.login-knap` og er visuelt adskilt fra de øvrige links.

Navigationen er sticky (følger med ved scroll) og kollapser til en wrapped flexbox på mobilskærme under 768px.

---

## Sådan åbnes projektet

Projektet kræver ingen installation eller server. Åbn blot `index.html` direkte i en browser:

```
Højreklik på index.html → Åbn med → Vælg browser
```

Alle CSS-filer og interne links er relative, så projektet fungerer lokalt uden opsætning.

---

*Projekt udviklet som del af et skoleprojekt · Padel Center Aarhus · 2026*

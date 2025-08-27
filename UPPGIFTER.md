UPPGIFTER — Bygg en webbplats steg för steg

Syfte
- Förstå HTML-struktur: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>` och `<div>` som boxar.
- Lära dig om CSS-boxmodellen: margin, border, padding.
- Göra sidan mer visuell: hover, transition, box-shadow och enkla animationer.
- Visa återanvändning: flera sidor med samma header/nav/footer.

Struktur i övningen
- Steg 0: Förbered (filer finns i projektmappen)
- Steg 1: Grundskal (skelett i `index.html`)
- Steg 2: Header + Footer
- Steg 3: Navigation med hover-effekt
- Steg 4: Huvudinnehåll: "Om mig" + "Projekt" med boxar
- Steg 5: Skapa en andra sida (`kontakt.html`) och återanvänd struktur
- Steg 6: Visuella effekter (hover, transition, transform)
- Steg 7: Responsivitet med media queries

Detaljerade instruktioner

---
Steg 0 — Förbered
- Filer som finns:
  - `index.html` (startskalet)
  - `style.css` (start-CSS)
  - `reflektion.md` (svarsförslag)
- Öppna `index.html` i VS Code och i webbläsaren.

---
Steg 1 — Grundskal (kopiera/ersätt innehåll i `index.html` om du vill)
Byt ut hela `index.html` med denna kod som grund:

```html
<!DOCTYPE html>
<html lang="sv">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Min Webbplats — Steg 1</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- STEP 1: STARTSKAL -->
  <div id="root">
    <!-- Header, nav, main och footer läggs till i nästa steg -->
  </div>
</body>
</html>
```

Reflektion efter steg 1:
- Vad gör `<meta name="viewport">` och varför är den viktig?

---
Steg 2 — Header & Footer
1) I `index.html` ersätter du `<!-- Header, nav, main och footer läggs till i nästa steg -->` med följande kod:

```html
<header>
  <div class="container header-inner">
    <h1>Mitt Namn / Min Webbplats</h1>
    <p class="subtitle">En enkel portfolio — byggs stegvis</p>
  </div>
</header>

<footer>
  <div class="container footer-inner">
    <p>© 2025 — Ditt Namn — <a href="mailto:kontakt@example.com">kontakt@example.com</a></p>
  </div>
</footer>
```

2) Lägg till följande i `style.css` (under rubriken STEP 2 i filen):

```css
/* HEADER + FOOTER — STEP 2 */
header { background:#4a90e2; color:#fff; padding:20px 0; }
.header-inner { max-width:900px; margin:0 auto; padding:0 15px; }
header h1 { margin:0; }
header .subtitle { margin:4px 0 0; font-size:0.95rem; opacity:0.9; }

footer { background:#222; color:#fff; padding:10px 0; }
.footer-inner { max-width:900px; margin:0 auto; padding:0 15px; text-align:center; }
```

Reflektion efter steg 2:
- Varför är det bra att ha en `.container`-klass och vad gör den?

---
Steg 3 — Navigation med hover-effekt
1) Lägg in nav-elementet i `index.html`, strax efter `</header>`-öppningen i HTML-ordningen (men före `<main>` som kommer i steg 4):

```html
<nav>
  <div class="container nav-inner">
    <a href="index.html" class="nav-link">Hem</a>
    <a href="om.html" class="nav-link">Om mig</a>
    <a href="projekt.html" class="nav-link">Projekt</a>
    <a href="kontakt.html" class="nav-link">Kontakt</a>
  </div>
</nav>
```

2) Lägg till CSS i `style.css` (STEP 3):

```css
/* NAV — STEP 3 */
nav { background:#333; }
.nav-inner { max-width:900px; margin:0 auto; padding:8px 15px; }
.nav-link { color:#fff; margin-right:18px; text-decoration:none; padding:6px 8px; border-radius:4px; display:inline-block; }
.nav-link:hover { background:rgba(255,255,255,0.08); transform:translateY(-2px); transition:all 150ms ease; }
```

Reflektion efter steg 3:
- Hur påverkar `display:inline-block` och `padding` länkelementets klickyta?

---
Steg 4 — Huvudinnehåll och projektboxar
1) Lägg in `<main>` i `index.html` mellan nav och footer:

```html
<main>
  <div class="container">
    <section id="about">
      <h2>Om mig</h2>
      <div class="info-box">
        <p>Skriv en kort presentation.</p>
      </div>
    </section>

    <section id="projects">
      <h2>Projekt</h2>
      <div class="projects-grid">
        <div class="project-box">
          <h3>Projekt 1</h3>
          <p>Kort beskrivning.</p>
        </div>
        <div class="project-box">
          <h3>Projekt 2</h3>
          <p>Kort beskrivning.</p>
        </div>
      </div>
    </section>
  </div>
</main>
```

2) CSS (STEP 4):

```css
/* MAIN + BOXES — STEP 4 */
main { background:#fff; margin:20px auto; max-width:900px; padding:20px; box-shadow:0 4px 10px rgba(0,0,0,0.06); }
.info-box { border:2px solid #4a90e2; padding:12px; background:#eaf6ff; }
.projects-grid { display:flex; gap:18px; flex-wrap:wrap; }
.project-box { flex:1 1 240px; border:2px solid #333; padding:12px; background:#fafafa; transition:box-shadow 200ms ease, transform 200ms ease; }
.project-box:hover { box-shadow:0 8px 20px rgba(0,0,0,0.12); transform:translateY(-6px); }
```

Reflektion efter steg 4:
- Hur fungerar `flex` här? Vad händer när fönstret blir smalare?

---
Steg 5 — Fler sidor och återanvändning
1) Skapa filen `kontakt.html` genom att kopiera `index.html` och ändra `<main>` till kontaktinfo (t.ex. formulär eller text). Se till att header/nav/footer är lika så länkarna fungerar.

2) Tips: Spara en kopia `template.html` som bas så elever kan återanvända strukturen.

Reflektion efter steg 5:
- Hur kan server-side templates eller JS-include spara tid i större projekt?

---
Steg 6 — Extra visuella effekter
- Lägg till `transition` på länkar och boxar.
- Använd `:focus` för tangentbordsnavigering.
- Prova `transform: scale(1.02)` på hover för kort animation.

---
Steg 7 — Responsivitet
- Lägg in en media query för små skärmar (t.ex. under 600px) där `.projects-grid` blir en kolumn.

Exempel:
```css
@media (max-width:600px) {
  .projects-grid { flex-direction:column; }
}
```

---
Avslutande reflektion
- Skriv dina svar i `reflektion.md`.
- När du är klar: zipa mappen eller initiera git och pusha till en privat repo som läraren delar.

Filer eleverna förväntas skapa/ändra
- `index.html`, `kontakt.html` (eller `template.html`)
- `style.css`
- `reflektion.md`


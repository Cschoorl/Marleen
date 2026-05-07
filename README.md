# Back to Being — Sponsorvoorstel

Een 6-slide sponsor-pitch voor het Camino-project **Back to Being**.

> **The World as our Office.**
> Drie AI-founders. 115 km. Tui → Santiago. Een AI-tool voor stichting MIND.

Statische HTML/CSS/JS — geen build, geen dependencies. Hostbaar op elke statische host.

---

## Snel openen

Dubbelklik `index.html`, of via een lokale server:

```bash
python3 -m http.server 4173
# → http://localhost:4173
```

## Navigeren

| Toets | Actie |
|---|---|
| `→` / `Space` | Volgende slide |
| `←` | Vorige slide |
| `Home` / `End` | Eerste / laatste slide |
| Klik op dot | Spring naar slide |
| Swipe (mobiel) | Vorige / volgende |

## Slide-structuur

1. **Cover** — *The World as our Office.*
2. **Wat is dit?** — Project in één zin + context (intro lede)
3. **Het plan** — *Lopen. Bouwen. Doneren.* in drie stappen
4. **Waarom** — *Tech moet ons menselijker maken. Niet andersom.*
5. **Het doel** — €20.000 ophalen + breakdown waar het naartoe gaat
6. **Word partner** — Wat je terugkrijgt + CTA (koffie / mail)

## Exporteren naar PDF

In Chrome of Safari:

1. Open `index.html`
2. `⌘ + P` (Print)
3. Bestemming: **Opslaan als PDF**
4. Oriëntatie: **Liggend**
5. Marges: **Geen**
6. Achtergrondafbeeldingen: **Aan**

De print-styling zorgt dat elke slide op zijn eigen pagina komt zonder navigatiebalk.

---

## Bestanden

```
.
├── index.html      # Het hele deck — 6 slides, styling, en navigatie-script
├── README.md       # Dit bestand
└── .gitignore
```

## Aanpassen

- **Inhoud / copy:** alles in `index.html` tussen de `<section class="slide …">` tags
- **Kleuren:** bovenin het `<style>` blok onder `:root` — `--green`, `--bg`, `--bg-dark`, etc.
- **Typografie:** [Fraunces](https://fonts.google.com/specimen/Fraunces) voor koppen, [Inter](https://fonts.google.com/specimen/Inter) voor body — beide via Google Fonts
- **Stijl-inspiratie:** [House of Founders](https://houseoffounders.com) — warme grijze achtergrond, klassieke serif met groen italic accent, pill tags, donker contrast-blok

---

## Naar Git pushen

Eerste keer setup vanuit deze map:

```bash
git init
git add .
git commit -m "Initial commit: Back to Being sponsor deck"
git branch -M main
```

### Optie A — GitHub via `gh` CLI

```bash
gh repo create back-to-being-deck --public --source=. --remote=origin --push
```

### Optie B — Handmatig (na repo aanmaken op GitHub/GitLab)

```bash
git remote add origin git@github.com:<jouw-username>/back-to-being-deck.git
git push -u origin main
```

---

## Live hosten (optioneel)

Omdat het pure statische HTML is, werkt elke statische host out-of-the-box:

### GitHub Pages
1. Repo → **Settings → Pages**
2. Source: `main` branch, `/` (root)
3. Klaar. URL wordt: `https://<username>.github.io/<repo>/`

### Vercel / Netlify
- Sleep de map naar [vercel.com/new](https://vercel.com/new) of [app.netlify.com/drop](https://app.netlify.com/drop) — het deployt direct.
- Geen configuratie nodig.

### Cloudflare Pages
```bash
npx wrangler pages deploy . --project-name back-to-being-deck
```

---

## Tech

Pure HTML + CSS + vanilla JS. Geen build step, geen dependencies, geen tracking. Werkt offline na de eerste page load (Google Fonts uitgezonderd).

## Contact

**Contact:** Caesar.schoorl@gmail.com

Telefoon op slide 7: vul in het script onderaan van `index.html` de twee regels met `CONTACT_PHONE_*` — dan verschijnt de tel-regel automatisch.

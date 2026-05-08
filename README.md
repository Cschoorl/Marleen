# Back to Being: Sponsorvoorstel

Een sponsor-pitch voor het Camino-project **Back to Being** (HTML-deck, meerdere slides).

> **The World as our Office.**
> Drie AI-founders. 115 km. Tui naar Santiago. Een AI-tool voor stichting MIND.

Statische HTML/CSS/JS. Geen build, geen dependencies. Hostbaar op elke statische host.

## Twee versies

| Bestand | Wanneer gebruiken |
|---|---|
| `index.html` | Mét bedragen. Slide 5 toont budget per post + live progressbar (`SECURED_AMOUNT` aanpassen vóór de pitch). Slide 6 toont tier-prijzen. |
| `zonder-bedragen.html` | Zónder bedragen. Voor verkennende gesprekken waar je geen prijs-anker wilt zetten. Slide 5 toont alleen kostencategorieën, slide 6 toont tiers als scope-niveaus (Volledig / Verbonden / In natura). |

### Live progressbar bijwerken (mét-bedragen versie)

In `index.html`, zoek de twee constanten in het `<script>` blok:

```js
const SECURED_AMOUNT = 0;     // EUR reeds toegezegd
const TARGET_AMOUNT  = 20000; // EUR doel
```

Pas `SECURED_AMOUNT` aan voor elke pitch. De progressbar en het "X% reeds toegezegd"-label updaten automatisch.

**Live (na hernoemen van de repo, zie onder):** `https://cschoorl.github.io/back-to-being/`

---

## GitHub: repo hernoemen (`Marleen` → `back-to-being`)

De GitHub Pages-URL is `https://<gebruikersnaam>.github.io/<repositorynaam>/`. Om **Marleen** in de URL te vervangen door **back-to-being**:

1. Ga naar **[Repository settings → General](https://github.com/Cschoorl/Marleen/settings)** van `Cschoorl/Marleen`.
2. Veld **Repository name** → wijzig `Marleen` in **`back-to-being`** → klik **Rename**.

**Lokaal daarna eenmalig** (HTTPS):

```bash
cd /Users/caesarschoorl/Marleen
git remote set-url origin https://github.com/Cschoorl/back-to-being.git
git remote -v
git push origin main
```

(or via SSH:) `git@github.com:Cschoorl/back-to-being.git`

Onder **Settings → Pages** hoef je meestal niets aan te passen; de site staat dan op **`https://cschoorl.github.io/back-to-being/`**. De oude `…/Marleen`-URL wordt door GitHub vaak nog een tijd doorgestuurd.

Optioneel: hernoem ook je lokale map: `mv Marleen back-to-being` en open die map als project.

---

## Snel openen

Dubbelklik `index.html`, of via een lokale server:

```bash
python3 -m http.server 4173
# http://localhost:4173
```

## Navigeren

| Toets | Actie |
|---|---|
| Pijl rechts / Space | Volgende slide |
| Pijl links | Vorige slide |
| Home / End | Eerste / laatste slide |
| Klik op dot | Spring naar slide |
| Swipe (mobiel) | Vorige / volgende |

## Slide-structuur

1. **Cover** (*The World as our Office*)
2. **Wat is dit?** Project in één zin + intro (lede)
3. **Het plan** (*Lopen. Bouwen. Doneren*) in drie stappen
4. **Waarom** (filosofie: kantoor naar buiten)
5. **Het doel** €20.000 ophalen + waar het naartoe gaat
6. **Sponsorpakketten** drie tiers: Hoofdsponsor (€10k) / Co-sponsor (€3.5k) / Supporter (in natura). Geen limiet op aantal partners.
7. **Word partner** wat je terugkrijgt + CTA
8. **Contact** Laten we koffie drinken (mail + optioneel telefoon)

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
├── index.html      # Het deck: slides, styling en navigatie-script
├── README.md       # Dit bestand
└── .gitignore
```

## Aanpassen

- **Inhoud / copy:** alles in `index.html` tussen de `<section class="slide …">` tags
- **Kleuren:** bovenin het `<style>` blok onder `:root` (o.a. `--green`, `--bg`, `--bg-dark`)
- **Typografie:** [Fraunces](https://fonts.google.com/specimen/Fraunces) voor koppen, [Inter](https://fonts.google.com/specimen/Inter) voor body (Google Fonts)
- **Stijl-inspiratie:** [House of Founders](https://houseoffounders.com): warme grijze achtergrond, serif met groen accent, pill tags

---

## Naar Git pushen

Eerste keer setup vanuit deze map:

```bash
git init
git add .
git commit -m "Initial commit: Back to Being sponsor deck"
git branch -M main
```

### Optie A: GitHub via `gh` CLI

```bash
gh repo create back-to-being-deck --public --source=. --remote=origin --push
```

### Optie B: Handmatig (na repo aanmaken op GitHub/GitLab)

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
- Sleep de map naar [vercel.com/new](https://vercel.com/new) of [app.netlify.com/drop](https://app.netlify.com/drop). Deployt direct.
- Geen configuratie nodig.

### Cloudflare Pages
```bash
npx wrangler pages deploy . --project-name back-to-being-deck
```

---

## Tech

Pure HTML + CSS + vanilla JS. Geen build step, geen dependencies, geen tracking. Werkt offline na de eerste page load (Google Fonts uitgezonderd).

## Contact

Caesar.schoorl@gmail.com

Telefoon op slide 8 wordt uit het script gevuld (`CONTACT_PHONE_*` onderaan `index.html`). Nu: +31 6 83032377.

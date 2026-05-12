# Back to Being: Sponsordeck

Statische HTML-slides voor het Camino-project **Back to Being** — sponsorpitch, geen build, geen dependencies.

> **The World as our Office.**  
> Drie **AI-nerds** (ook founders) uit Amsterdam. 115 km. Tui naar Santiago. Live bouwen aan een AI-tool voor **stichting MIND**.

---

## Live site (GitHub Pages)

**Standaard-URL van de repo** opent nu automatisch het **sponsordeck met bedragen**:

| Wat je opent | URL (vul je GitHub-gebruikersnaam in) |
|---|---|
| **Startpagina → sponsordeck** | `https://<username>.github.io/Back-to-Being/` |
| Expliciet met bedragen | `https://<username>.github.io/Back-to-Being/met-bedragen.html` |
| Zonder euro’s op het scherm | `https://<username>.github.io/Back-to-Being/zonder-bedragen.html` |
| Kort 7-slide deck | `https://<username>.github.io/Back-to-Being/index-7-slides.html` |

Voorbeeld (repo staat onder **Cschoorl**):  
`https://cschoorl.github.io/Back-to-Being/` → redirect naar `met-bedragen.html`.

### Ik zie oude tekst na een push

1. **Hard refresh:** macOS `⌘ + Shift + R`, Windows `Ctrl + Shift + R`.  
2. **Privévenster** of andere browser.  
3. **Cache-bust:** voeg tijdelijk `?v=2` toe aan de URL, bijv. `…/met-bedragen.html?v=2`.  
4. Controleer **GitHub → Settings → Pages**: source = branch **`main`**, map **`/` (root)**.  
5. Wacht 1–2 minuten na een push; daarna zou de nieuwe HTML live moeten staan.

---

## Welk bestand?

| Bestand | Gebruik |
|---|---|
| `index.html` | **Doorverwijzing** naar `met-bedragen.html` (zodat de “gewone” Pages-link meteen het sponsordeck toont). |
| `met-bedragen.html` | **Hoofd-sponsordeck:** 8 slides, €30k-doel, budget per post, sponsortiers, live progressbar. |
| `zonder-bedragen.html` | Zelfde verhaal, **zonder** eurobedragen op de slides (verkennende gesprekken). |
| `index-7-slides.html` | Korte **7-slide** variant (geen aparte sponsortiers-slide). |

### Progressbar vóór een pitch (`met-bedragen.html`)

Onderaan het `<script>`-blok:

```js
const SECURED_AMOUNT = 0;     // EUR reeds toegezegd
const TARGET_AMOUNT  = 30000; // EUR doel
```

`SECURED_AMOUNT` per gesprek aanpassen; balk en percentage volgen automatisch.

---

## Snel lokaal openen

```bash
python3 -m http.server 4173
# http://localhost:4173/met-bedragen.html
```

Of dubbelklik een `.html`-bestand in de browser.

## Navigatie (in elk deck)

| Toets | Actie |
|---|---|
| Pijl rechts / spatie | Volgende slide |
| Pijl links | Vorige slide |
| Home / End | Eerste / laatste slide |
| Dots onderaan | Naar slide springen |
| Swipe (mobiel) | Vorige / volgende |

## Slide-structuur (8 slides — `met-bedragen` / `zonder-bedragen`)

1. Cover — *The World as our Office*  
2. Wat is dit? — intro + MIND  
3. Het plan — Lopen · Bouwen · Overdragen  
4. Waarom — filosofie  
5. Het doel — budget (mét) of pijlers (zonder)  
6. Sponsorpakketten  
7. Word partner — wat je terugkrijgt  
8. Contact  

---

## PDF exporteren

1. Open `met-bedragen.html` (of `index-7-slides.html`).  
2. `⌘ + P` / `Ctrl + P` → **Opslaan als PDF**  
3. Oriëntatie **Liggend**, marges **Geen**, achtergrond **Aan** (indien gevraagd).

---

## Repo & remote

De remote kan na een GitHub-rename naar bv. `https://github.com/Cschoorl/Back-to-Being.git` wijzen. Lokaal controleren:

```bash
git remote -v
```

---

## Aanpassen

- **Copy / slides:** `<section class="slide …">` in de betreffende `.html`.  
- **Kleuren:** `:root` in het `<style>`-blok.  
- **Fonts:** [Fraunces](https://fonts.google.com/specimen/Fraunces), [Inter](https://fonts.google.com/specimen/Inter) (Google Fonts).

---

## Tech

Pure HTML, CSS en vanilla JS. Geen tracking. Na eerste load grotendeels offline (fonts daargelaten).

## Contact

Caesar.schoorl@gmail.com  

Telefoon op de contactslide: scriptconstanten `CONTACT_PHONE_*` onderaan het HTML-bestand (nu +31 6 83032377).

# AluraGeek — Alura Challenge Front-End 3

Static HTML/CSS storefront for **AluraGeek**, a fictional geek shop. Built in March–April 2022 for [Alura Challenge Front-End 3](https://www.alura.com.br/challenges/front-end-3) (`#alurachallengefront3`).

The challenge ran four weeks (14 Mar – 12 Apr 2022). This repo covers the first stretch: markup and layout for the customer-facing home page, plus a draft login screen. There is no JavaScript, no product data, and no admin CRUD.

**Author:** Gabriel Affonso (footer credit on both pages).

## What was built

| Piece | Status |
| --- | --- |
| Home page (`index.html`) | Header, full-width banner, three category blocks, footer with sitemap + contact form |
| Login page (`login.html`) | HTML structure only — not linked from home, and not covered by the CSS |
| Layout | Flexbox in `flexbox.css` |
| Visual styles | Colors, spacing, form controls in `style.css` |
| Responsiveness | Last commit aimed at it; there are still **no media queries** |
| JS / API / product CRUD | Not started (those were weeks 3–4 of the challenge) |

Category “galleries” on the home page are **screenshot images** of whole sections (`seção-starwars.png`, `seção-console.png`, `diversos-seção.png`), not individual product cards. That was a shortcut while focusing on page structure.

The full challenge also asked for product listing, add/edit product (admin), form validation, and a JSON API. Those pages are not in this repo.

## How to open it

No build step or server is required.

1. Open `index.html` in a browser (double-click, or drag it onto a tab).
2. To see login, open `login.html` the same way — there is no nav link between the two pages.

From a terminal:

```bash
# optional: serve locally so relative assets resolve cleanly
python3 -m http.server 8080
# then visit http://localhost:8080/
```

## File map

```
e-commerceChallenge/
├── index.html          # Home: header, banner, 3 category images, footer
├── login.html          # Draft “Iniciar Sessão” form (unstyled)
├── reset.css           # Eric Meyer reset — load first
├── style.css           # Visual styles for the home page
├── flexbox.css         # Flex layout for the home page
├── Logo.png            # Header + footer logo
├── barra-pesquisa.png  # Search bar treated as an image
├── banner.png          # Hero
├── seção-starwars.png  # Star Wars category mock
├── seção-console.png   # Consoles category mock
├── diversos-seção.png  # “Diversos” category mock
└── …other .png files   # Unused Figma / earlier mockups (see below)
```

Stylesheets load in this order on both pages:

1. `reset.css` — zero browser defaults
2. `style.css` — look (colors, padding, form fields)
3. `flexbox.css` — arrangement (`display: flex`, alignment)

`style.css` and `flexbox.css` target **home-page class names** (`cabecalhoPrincipal`, `conteudoPrincipal`, `rodapePrincipal`, …). Login uses a different set (`primeiroPrincipal`, `input-padrao`, `rodape`, …), so it currently renders as unstyled HTML.

## How the home page is structured

`index.html` is a single document with three landmarks:

1. **Header** (`.cabecalhoPrincipal`) — logo + search image, laid out with flex (`space-around`).
2. **Main** (`.conteudoPrincipal`) — `banner.png`, then a column of three section screenshots (Star Wars, consoles, miscellaneous).
3. **Footer** (`.rodapePrincipal`) — logo, six sitemap links, a “Fale conosco” form (name + message + submit), then a white credit bar.

Portuguese copy and `lang="pt-br"` match the original brief. Meta description still says “produtos de criança”; the design is geek merch.

## Unused images

These look like Figma exports or earlier mocks and are **not referenced** by either HTML file:

- `cabecalo.png` — header mock (filename is a typo for *cabeçalho*)
- `star-wars.png`, `Console.png`, `console (1).png`, `diversos.png` — product/section art that was later replaced by the full-section screenshots

Safe to ignore when reading the live pages.

## Challenge context (what “done” meant)

The official four-week plan:

| Week | Brief | This repo |
| --- | --- | --- |
| 1 | Storefront HTML/CSS | Home page structure |
| 2 | More sections + login styling | Login HTML started; CSS not wired |
| 3–4 | JS, APIs, product management, validation | Not started |

Last commit message: *“Almost done. Just had to turn responsive”* (5 Apr 2022). Layout is fluid via flexbox and `%` widths, but breakpoints were never added.

## Timeline (commits)

| Date | What happened |
| --- | --- |
| 16 Mar 2022 | First HTML + Meyer reset + logo |
| 16 Mar 2022 | Page development; stub README |
| 30 Mar 2022 | Flexbox layout (and a merge to resync the branch) |
| 1 Apr 2022 | More flexbox |
| 5 Apr 2022 | Home restyle; section screenshots; “almost done / responsive” |

## If you pick this up again

Natural next steps, in the order the challenge used:

1. Link home ↔ login and reuse the same header/footer classes so login inherits CSS.
2. Add `@media` rules (the missing responsive pass).
3. Replace section screenshots with real product cards (image, name, price, “ver produto”).
4. Wire forms (contact, login) and later product CRUD with JavaScript.

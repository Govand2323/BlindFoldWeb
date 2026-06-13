# BlindFold Games — Website

The official website for **BlindFold Games**, a small indie game studio.
Static site (HTML/CSS/JS), hosted free on **GitHub Pages** at
[blindfold-games.com](https://blindfold-games.com).

## Structure

```
.
├── index.html              # Landing page (hero + games grid)
├── about.html              # About the studio
├── contact.html            # Contact info
├── privacy-policy.html     # Site-wide privacy policy
├── 404.html                # Custom not-found page
├── css/style.css           # Design system (dark neon arcade theme)
├── js/main.js              # Mobile nav toggle
├── images/                 # Logo + game artwork
├── games/                  # One folder per game/app page
├── templates/              # Reference templates (not linked from the site)
│   ├── game-template.html
│   └── privacy-template.html
├── CNAME                   # Custom domain (blindfold-games.com)
├── .nojekyll               # Serve files as-is (no Jekyll processing)
├── robots.txt
└── sitemap.xml
```

## Adding a new game / app page

When you ask Claude to "create a new game page," it will ask these **5 questions**:

1. **Image path** — the game/app artwork to use (placed in `images/`).
2. **Title** — the game/app name.
3. **Details** — the information to show on the page.
4. **Link** — the page's URL path. For apps already in production with a
   hardcoded link, give the exact path so it matches (no app update needed).
   New apps default to `games/<slug>/`.
5. **Own privacy policy?** — if yes, a page is created at
   `<game-link>/privacy-policy` and you provide its contents.

The page is generated from `templates/game-template.html`, added as a card on the
landing page (between the `GAME-CARDS:START/END` markers in `index.html`), and
committed to git.

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

(Use a server, not file://, so the root-absolute `/css` and `/images` paths resolve.)

## Deployment

Pushing to the `main` branch auto-publishes via GitHub Pages.
Custom domain is configured in repo Settings → Pages, backed by the `CNAME` file.

## Design

Dark neon "arcade" theme. Tokens live at the top of `css/style.css` and mirror the
Pencil design file (`pencil-new.pen`). Fonts: **Anton** (headings), **Geist** (body),
**Geist Mono** (labels). Accents: purple `#A855F7`, pink `#EC4899`, cyan `#22D3EE`.

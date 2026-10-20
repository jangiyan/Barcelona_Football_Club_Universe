# Barça Universe — FC Barcelona Fan Website

> **An unofficial fan website built as a university Web Engineering assignment (Assignment 1).**
> Not affiliated with, endorsed by, or connected to FC Barcelona.

---

## Project Overview

**Barça Universe** is a 10-page static HTML5/CSS3 fan website celebrating FC Barcelona. It was built as a university Web Engineering assignment with the requirement of using only HTML5 and CSS3 — no JavaScript, no frameworks, no backend.

The design features the club's visual identity: garnet/burgundy, royal blue, navy, and gold accents, presented through a modern, editorial-style layout.

---

## Pages

| File | Title | Description |
|---|---|---|
| `index.html` | Home | Hero section, club introduction, featured players, quick navigation |
| `history.html` | Club History | Founding in 1899, illustrated timeline, major eras |
| `squad.html` | First-Team Squad | 2024–25 squad grouped by position: GK, DEF, MID, FWD |
| `players.html` | Star Players | Detailed profiles of key current and recent players |
| `trophies.html` | Trophies & Achievements | La Liga, Copa del Rey, Champions League, and more |
| `stadium.html` | Spotify Camp Nou | Stadium history, facts, Espai Barça renovation info |
| `jerseys.html` | Kits & Jerseys | Home, away, third, and historic kit designs |
| `rivalries.html` | Famous Rivalries | El Clásico, Derbi Barceloní, European encounters |
| `legends.html` | Club Legends | Cruyff, Messi, Ronaldinho, Xavi, Iniesta, Puyol |
| `gallery.html` | Photo Gallery | Themed gallery sections with CSS hover effects |

---

## Architecture

```
barca-universe/
├── index.html
├── history.html
├── squad.html
├── players.html
├── trophies.html
├── stadium.html
├── jerseys.html
├── rivalries.html
├── legends.html
├── gallery.html
├── css/
│   └── style.css        ← Single shared stylesheet (image styles are in the last sections)
├── assets/
│   └── images/
│       └── README.md    ← Image licensing guide (put your photos in this folder)
├── IMAGE_MANIFEST.md    ← Exact filenames of every image the site is ready for
├── README.md
└── .gitignore
```

---

## How HTML and CSS Are Used

### HTML5
- Every page uses a valid HTML5 document structure (`<!DOCTYPE html>`)
- Semantic elements are used throughout: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<figure>`, `<figcaption>`, `<time>`
- Every page includes `<meta charset="UTF-8">`, `<meta name="viewport">`, a unique `<title>`, and a `<meta name="description">`
- Every `<img>` tag has descriptive `alt` text

### CSS3
- All styling is in a single shared file: `css/style.css`
- CSS custom properties (variables) define the color palette, typography, spacing, and shadows consistently across all pages
- Layouts use CSS Flexbox (navigation, cards, footers) and CSS Grid (card grids, gallery, squad layout)
- Mobile-first responsive design with breakpoints at 600px (tablet) and 1024px (desktop)
- Hover effects and transitions use CSS `transition` and `transform` — no JavaScript
- Google Fonts (Oswald + Inter) are loaded via a CSS `@import`
- `focus-visible` styles ensure keyboard navigation accessibility

---

## Navigation

- A consistent `<header>` with `<nav>` appears on every page
- Navigation links use standard `<a href="...">` elements pointing to the correct relative HTML file
- The current page's link is highlighted using `class="active" aria-current="page"`
- On smaller screens, the navigation uses `flex-wrap` to reflow onto multiple lines — no JavaScript required
- The site logo always links back to `index.html`
- A footer on every page repeats key navigation links

---

## Running Locally

No build tools, server, or installation required.

1. Download or clone the repository to your computer.
2. Open the project folder.
3. Double-click `index.html` — it will open in your default web browser.
4. All navigation links work as relative paths between local HTML files.

> **Tip**: For the best experience (especially Google Fonts loading), open the files using a local development server such as VS Code's Live Server extension, or simply use any modern browser — the site is fully functional offline except for font loading.

---

## Uploading to GitHub

### Step 1 — Create a GitHub account
If you don't have one, go to [https://github.com](https://github.com) and sign up.

### Step 2 — Create a new repository
1. Click the **+** button in the top-right corner → **New repository**
2. Name it (e.g., `barca-universe`)
3. Leave it **Public**
4. Do **not** initialize with a README (you already have one)
5. Click **Create repository**

### Step 3 — Upload your files
**Option A — GitHub website (easiest for beginners)**
1. On the new repository page, click **Add file** → **Upload files**
2. Drag all your project files and folders into the upload area
3. Make sure to upload the folder structure as-is (including `css/` and `assets/`)
4. Scroll down, add a commit message like `"Initial upload"`, click **Commit changes**

**Option B — Git command line**
```bash
# In your project folder:
git init
git add .
git commit -m "Initial commit: Barça Universe website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/barca-universe.git
git push -u origin main
```
Replace `YOUR-USERNAME` and `barca-universe` with your actual GitHub username and repo name.

---

## Deploying with GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top tab)
3. In the left sidebar, click **Pages**
4. Under **Source**, select **Branch: main** and folder **/ (root)**
5. Click **Save**
6. GitHub will show a green banner with your site URL (e.g., `https://your-username.github.io/barca-universe/`)
7. Wait 1–3 minutes for the site to deploy
8. Visit the URL to confirm it is live

> **Note**: Replace all placeholder URLs in this README with your actual GitHub repository URL after uploading.

---

## Adding images

The site is **already prepared for 50 photos** (hero, crest, stadium, players, legends, kits, trophies, rivalries, gallery, history). No photos are included yet, so every image spot currently shows the original gradient/initials design.

### Simple workflow (no code editing)
1. Open `IMAGE_MANIFEST.md`. It lists the **exact filename** for every image, the page it appears on, and a Wikimedia Commons search link.
2. Pick a photo, check its licence (see below), and download it.
3. Rename it to the exact filename from the manifest (e.g. `camp-nou.jpg`) and drop it into `assets/images/`.
4. Open the page in your browser (refresh). The photo appears automatically.
5. Add a row to the attribution table below.

Start with the **Priority 1** list in the manifest; the rest is optional. You can add images one at a time — the site works at every stage.

### How it works
Each image spot is a CSS background layer on top of the old placeholder. If the file exists it covers the placeholder; if not, the placeholder shows. Photos use `object-fit`-style cropping (`background-size: cover`), so they fill their frames without stretching. `.jpg`, `.png` and `.webp` are all recognised. Only HTML and CSS are used.

> **Good to know:** because missing files are simply "not found", your browser's developer console (and the GitHub Pages server log) may show 404 messages for images you haven't added yet. This is harmless and disappears as you add the files.
>
> Photos are applied through CSS, so they have no `alt` text of their own. Each photo spot sits inside a captioned figure or a card that already names the subject (e.g. the player's name).

### Checking a licence
On the Commons file page, look at the **Licensing** box. Accepted for this project: Public domain, CC0, CC BY, CC BY-SA. Copy the author name, the page URL and the licence name into the table below.

### Testing after adding images
- Open each page locally (double-click the HTML file) and look for any photo that looks cropped badly.
- Check file names are **lowercase with hyphens** and match the manifest exactly (`Camp-Nou.JPG` will not work on GitHub Pages, which is case-sensitive).

---

## Image Attribution

Fill in one row for each image you add. (Rows say *not added yet* until you do.)

| File | Photographer / author | Source page URL | Licence |
|---|---|---|---|
| `barcelona-hero` | *(not added yet)* | | |
| `club-crest` | *(not added yet)* | | |
| `camp-nou` | *(not added yet)* | | |
| `barcelona-team` | *(not added yet)* | | |
| `history-1899-founders` | *(not added yet)* | | |
| `history-1992-wembley` | *(not added yet)* | | |
| `history-2009-treble` | *(not added yet)* | | |
| `camp-nou-interior` | *(not added yet)* | | |
| `camp-nou-matchday` | *(not added yet)* | | |
| `espai-barca` | *(not added yet)* | | |
| `player-ter-stegen` | *(not added yet)* | | |
| `player-inaki-pena` | *(not added yet)* | | |
| `player-astralaga` | *(not added yet)* | | |
| `player-araujo` | *(not added yet)* | | |
| `player-kounde` | *(not added yet)* | | |
| `player-cubarsi` | *(not added yet)* | | |
| `player-balde` | *(not added yet)* | | |
| `player-inigo-martinez` | *(not added yet)* | | |
| `player-christensen` | *(not added yet)* | | |
| `player-eric-garcia` | *(not added yet)* | | |
| `player-hector-fort` | *(not added yet)* | | |
| `player-pedri` | *(not added yet)* | | |
| `player-gavi` | *(not added yet)* | | |
| `player-de-jong` | *(not added yet)* | | |
| `player-fermin-lopez` | *(not added yet)* | | |
| `player-olmo` | *(not added yet)* | | |
| `player-casado` | *(not added yet)* | | |
| `player-lewandowski` | *(not added yet)* | | |
| `player-raphinha` | *(not added yet)* | | |
| `player-yamal` | *(not added yet)* | | |
| `player-ferran-torres` | *(not added yet)* | | |
| `player-ansu-fati` | *(not added yet)* | | |
| `legend-cruyff` | *(not added yet)* | | |
| `legend-messi` | *(not added yet)* | | |
| `legend-ronaldinho` | *(not added yet)* | | |
| `legend-xavi` | *(not added yet)* | | |
| `legend-iniesta` | *(not added yet)* | | |
| `legend-puyol` | *(not added yet)* | | |
| `trophy-champions-league` | *(not added yet)* | | |
| `trophy-la-liga` | *(not added yet)* | | |
| `trophy-copa-del-rey` | *(not added yet)* | | |
| `jersey-home` | *(not added yet)* | | |
| `jersey-away` | *(not added yet)* | | |
| `jersey-third` | *(not added yet)* | | |
| `jersey-classic` | *(not added yet)* | | |
| `jersey-centenary` | *(not added yet)* | | |
| `jersey-throwback` | *(not added yet)* | | |
| `el-clasico` | *(not added yet)* | | |
| `derbi-barcelona` | *(not added yet)* | | |
| `el-clasico-atmosphere` | *(not added yet)* | | |

---

## Things to Do Manually

- [ ] Add appropriately licensed images to `assets/images/` (see **Adding images** below and `IMAGE_MANIFEST.md`)
- [ ] Replace the placeholder GitHub URL with your actual repository URL
- [ ] Verify the live GitHub Pages URL once deployed
- [ ] Check all pages display correctly in multiple browsers (Chrome, Firefox, Safari)

---

## Disclaimer

This is an unofficial fan website created for educational purposes as a university Web Engineering assignment. It is not affiliated with, endorsed by, or connected to FC Barcelona or any of its commercial partners. All trademarks, logos, and club names belong to their respective owners.

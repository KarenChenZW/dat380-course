# DAT 380 · Business Analytics & Data Visualization — Course Tools

Interactive web tools for DAT 380 (Berry College), hosted free on GitHub Pages.
The landing page (`index.html`) links to the syllabus and, over time, to games and simulations.

**Live site:** `https://<your-username>.github.io/dat380-course/`
(Replace `<your-username>` with your GitHub username. The repo name `dat380-course` is the last part of the URL.)

---

## Folder structure

```
dat380-course/
├── index.html              ← landing page (the hub that links to every tool)
├── .nojekyll               ← empty file; keep it (stops GitHub mangling folders)
├── README.md               ← this file
├── syllabus/
│   └── index.html          ← interactive syllabus  →  /syllabus/
├── games/
│   └── index.html          ← "games" section page  →  /games/
├── simulations/
│   └── index.html          ← "simulations" page     →  /simulations/
└── assets/                 ← optional shared images/logos
```

**The one rule that keeps this tidy:** every tool goes in its **own folder** and its main file is named **`index.html`**. That gives clean URLs like `/games/method-match/` instead of `/SomeFile_v2_final.html`.

---

## First-time setup (do this once)

1. On GitHub, create a **new, public** repository named `dat380-course`.
   (On the free plan the repo must be public for Pages to work — only HTML is public, which is fine.)
2. **Add file → Upload files**, and drag in the *contents* of this folder
   (`index.html`, `.nojekyll`, `README.md`, and the `syllabus/`, `games/`, `simulations/`, `assets/` folders). Commit.
3. Go to **Settings → Pages**. Under **Build and deployment → Source**, pick **Deploy from a branch**;
   set **Branch = main** and **folder = / (root)**; click **Save**.
4. Wait ~1 minute. Your site is live at `https://<your-username>.github.io/dat380-course/`.

After this, you never touch Settings again.

---

## Adding a new tool later (the routine — 3 steps)

Say you built a game called *Method Match* as a single `index.html` file.

1. **Upload it into its own folder.** In the repo: **Add file → Upload files**, and put it at
   `games/method-match/index.html`. (When creating a file, you can type the whole path as the filename —
   GitHub creates the folders for you.) Commit.
2. **Link it from the landing page.** Edit `index.html`, copy one of the tool "card" blocks,
   change the icon/title/text, flip the badge to **Live**, and point the button at the folder:
   ```html
   <a class="btn" href="games/method-match/">Play →</a>
   ```
   Commit.
3. **Wait ~1 minute.** It's live at `/games/method-match/`.

Existing tools are never affected — each folder is independent.

---

## Rules of thumb (so nothing breaks)

- **Use relative links, never absolute.** Inside the site, write `href="games/x/"` (relative),
  not `href="/games/x/"` (absolute). The leading `/` points to the wrong place because the site
  lives in a subfolder (`/dat380-course/`). This is the #1 cause of "broken links that worked locally."
- **Prefer single self-contained `.html` files** for each tool (CSS and JS inline, like the syllabus).
  They have no path problems and are the least maintenance.
- **Name folders in lowercase with hyphens**, no spaces: `method-match`, not `Method Match`.
- **Folder names are permanent-ish** — they're part of the URL you share with students. Renaming a
  folder changes its URL and breaks any link you already posted. Pick a clear name up front.
- **Test locally first:** double-click a tool's `index.html` on your computer; if it works in your
  browser as a standalone file, it will work on GitHub Pages.
- **Keep `.nojekyll`.** Deleting it can cause blank pages or broken folders.

---

## Updating an existing tool

Open the file in the repo (e.g. `syllabus/index.html`), click the pencil ✏️, paste the new version,
and commit — it redeploys in about a minute. Or use **Add file → Upload files** to replace it.
No command line needed.

*(Optional, for frequent edits: install **GitHub Desktop** — a free app, no terminal — to sync a local
folder with the repo in one click.)*

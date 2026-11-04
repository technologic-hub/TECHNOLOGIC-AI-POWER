# TECHNOLOGIC AI POWER: official website (prototype)

A static, single-page website for **TECHNOLOGIC AI POWER**, a Windows desktop assistant for running AI models and agents on your own computer. *The Future of Technology.*

> **Status: front-end prototype.** There is no backend. Accounts, sign-in, the waitlist, the support form, downloads and payments are **not connected**, and the forms say so when submitted. Nothing is stored or sent.

## Run locally
No build step. Open `index.html` in a browser, or serve the folder:

```
python -m http.server 8000
```
then visit http://localhost:8000.

## Publish with GitHub Pages
1. Create a repository (for example `technologic-ai-power-website`) and push these files to the `main` branch.
2. In **Settings → Pages**, set **Source** to **GitHub Actions**. The workflow in `.github/workflows/pages.yml` publishes the site on every push to `main`.
   (Alternative: set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.)

Pages use hash links (`#get`, `#next`, …), so no server rewrite rules are needed.

## Structure
```
index.html          the whole site: styles, pages and data
assets/logo.png     TECHNOLOGIC AI POWER logo (transparent PNG)
assets/screens/     screenshots of the current desktop-app UI prototype
.github/workflows/  GitHub Pages deployment
.nojekyll           tells GitHub Pages to serve files as they are
```

## Editing content
Site data sits at the top of the `<script>` in `index.html`:

| Constant | Controls |
|---|---|
| `RELEASE` | release label, date, status, OS, package size, download link |
| `NEWS` | News & Updates entries |
| `DOCS` | documentation outline |
| `TOOLS` | AI Tools directory entries (currently placeholders) |
| `FAQ` | FAQ and Help Center answers |
| `PLANS` | pricing plans (empty until decided) |

The download button stays disabled until `RELEASE.url` holds a real file link. Do not add links, prices or dates that are not confirmed.

Colours are CSS variables in the `:root` block of the stylesheet.

## Needs a backend (not built)
Accounts and roles, waitlist and support tickets, preorders and payments, an admin dashboard, and a database for docs, news and tools. See the **Site plan** page on the site for the suggested approach.

## Notes
- The screenshots show the desktop app UI prototype (no AI engine connected).
- No licence file is included yet. Add one before making the repository public if you want others to reuse the code.

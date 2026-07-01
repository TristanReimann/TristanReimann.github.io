# Personal Website

A small, dependency-free static website. No build tools, no frameworks —
just HTML and CSS you can edit directly and host for free on GitHub Pages
under your own domain.

## Folder structure

```
.
├── index.html          Homepage
├── about.html          Example second page (copy this to add pages)
├── 404.html            Shown for URLs that don't exist
├── css/
│   └── style.css       The single stylesheet for the whole site
├── js/                 Empty — for scripts if you ever need them
├── assets/
│   ├── images/         Photos, favicon, etc.
│   └── files/          Downloads, e.g. your CV as a PDF
└── README.md           This file
```

## Getting started

1. Open `index.html` and `about.html` and replace every `[placeholder]`
   with your own information.
2. Optionally tweak the colors and fonts at the top of `css/style.css`
   (section "1. Design tokens") — one change updates the whole site.
3. Preview locally by simply double-clicking `index.html`, or run a tiny
   local server from the project folder:

   ```
   python3 -m http.server
   ```

   then open http://localhost:8000

## Adding a new page

1. Copy `about.html` and rename it, e.g. `projects.html`.
2. Change its `<title>`, `<meta name="description">` and the content
   inside `<main>`.
3. Add a link to the new page in the `<nav>` of **every** HTML file, so
   the menu stays identical across the site.
4. Move `class="is-active"` in each file's nav to whichever link matches
   that page.

That's the entire scaling model: one HTML file per page, one shared
stylesheet. It stays fast and simple at 3 pages or 30.

## Hosting on GitHub Pages

1. Create a new **public** repository on GitHub
   (e.g. `yourusername/website`) and push these files to it.
   Alternatively, name the repo `yourusername.github.io` — then it is
   automatically served at that address.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set Source to **Deploy from a branch**,
   choose the `main` branch and the `/ (root)` folder, and save.
4. After a minute or two your site is live at
   `https://yourusername.github.io/website/` (or
   `https://yourusername.github.io/` for the special repo name).

Every `git push` to `main` automatically republishes the site.

## Connecting your own domain

1. Still in **Settings → Pages**, enter your domain (e.g. `example.com`
   or `www.example.com`) under **Custom domain** and save. GitHub will
   create a file called `CNAME` in the repo — keep it, it must stay there.
2. At your domain registrar, add DNS records:
   - For a subdomain like `www.example.com`: a **CNAME** record pointing
     `www` → `yourusername.github.io`
   - For the bare/apex domain `example.com`: **A** records pointing to
     GitHub Pages' IP addresses (listed in GitHub's docs under
     "Managing a custom domain for your GitHub Pages site" — check there
     for the current values rather than copying them from elsewhere).
3. Wait for DNS to propagate (minutes to a few hours), then back in
   **Settings → Pages** tick **Enforce HTTPS** once it becomes available.

## Tips

- Keep image files small (under ~300 KB) so the site stays fast.
- Every image needs an `alt` attribute describing it — good for
  accessibility and for search engines.
- The site works with no JavaScript at all. Only add scripts to `js/`
  if a feature genuinely needs them.

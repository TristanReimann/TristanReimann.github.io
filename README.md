# Personal Website

**Live site: https://tristanreimann.github.io/**

A single-page personal homepage modelled on the classic academic
homepage template (Lato font, blue/orange links, thumbnail-left /
text-right rows): circular photo, short bio, social links, selected
work, and an experience list. No build tools, no frameworks, nothing
to install — just HTML and CSS you edit directly, hosted for free on
GitHub Pages under your own domain.

## Folder structure

```
.
├── index.html          The whole site (one page, three sections)
├── 404.html            Shown automatically for URLs that don't exist
├── css/
│   └── style.css       The single stylesheet, organised by section
├── js/                 Empty — for scripts if you ever need them
├── assets/
│   ├── images/         Your portrait, project thumbnails, favicon,
│   │                   and institution/employer logos for Experience
│   └── files/          Downloads, e.g. cv.pdf
└── README.md           This file
```

## Getting started

1. Open `index.html` and replace every `[placeholder]` with your own
   information. Delete sections or entries you don't need — the layout
   adapts.
2. Add your photo: put a roughly square image (e.g. 600×600 px) into
   `assets/images/` and change the `<img src=...>` in the hero from the
   placeholder SVG to your file.
3. Trim the social links: keep the ones you use, delete the rest.
   Each is a self-contained `<a class="chip">` block.
4. Optionally tune the look in `css/style.css`, section
   "1. Design tokens" — colors, fonts, and sizes all live there, and one
   change restyles the whole site.
5. Preview by double-clicking `index.html`, or run a tiny local server
   from the project folder:

   ```
   python3 -m http.server
   ```

   then open http://localhost:8000

## Growing the site later

- **More entries** in Selected work or Experience: copy-paste one
  existing `<div class="entry-row">` block and edit it.
- **A whole new section**: duplicate any `<section>` in `index.html`,
  give it a new `id` and `<h2>` — the section styling is generic.
- **A separate page** (e.g. `photos.html`): copy `index.html`, keep the
  `<head>` and footer, replace the content, and link to it from the bio
  or a social chip. Every page shares `css/style.css`.

## Hosting on GitHub Pages

1. Create a new **public** repository on GitHub and push these files.
   If you name the repo `yourusername.github.io`, the site is served at
   exactly that address.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set Source to **Deploy from a branch**,
   pick the `main` branch and the `/ (root)` folder, and save.
4. After a minute or two the site is live. Every `git push` to `main`
   republishes it automatically.

## Connecting your own domain

1. In **Settings → Pages**, enter your domain (e.g. `example.com` or
   `www.example.com`) under **Custom domain** and save. GitHub creates a
   `CNAME` file in the repo — keep it there.
2. At your domain registrar, add DNS records:
   - Subdomain like `www.example.com`: a **CNAME** record pointing
     `www` → `yourusername.github.io`
   - Bare/apex domain `example.com`: **A** records pointing to GitHub
     Pages' IP addresses — take the current values from GitHub's own
     docs ("Managing a custom domain for your GitHub Pages site").
3. Once DNS has propagated (minutes to a few hours), tick
   **Enforce HTTPS** in **Settings → Pages**.

## Tips

- Keep images small (under ~300 KB each) so the page stays fast.
- Give every image a meaningful `alt` text — good for accessibility
  and search engines.
- The site needs no JavaScript at all; only add scripts to `js/` if a
  feature truly requires them.

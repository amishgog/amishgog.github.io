# amishgog.github.io

Personal website of Amish Gogia. Plain HTML and CSS: no framework, no build step,
no JavaScript, no external requests. It will keep working unchanged for decades.

## Put it online (one time, about 5 minutes)

1. On GitHub, create a **public** repository named exactly `amishgog.github.io`
   (your username followed by `.github.io`).
2. Upload everything in this folder to the repository root, including the hidden
   `.nojekyll` file. Easiest: on the empty repo page click "uploading an existing file"
   and drag the contents in. Or from a terminal:

   ```bash
   cd amishgog.github.io
   git init && git add -A && git commit -m "First version"
   git branch -M main
   git remote add origin git@github.com:amishgog/amishgog.github.io.git
   git push -u origin main
   ```
3. In the repository go to **Settings → Pages**. Under "Build and deployment" choose
   **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute the site is live at https://amishgog.github.io

If your GitHub username isn't `amishgog`, replace `amishgog.github.io` everywhere in
`index.html` (search for it: canonical link, og tags, the JSON-LD block).

## Preview locally

Open `index.html` in a browser, or run `python3 -m http.server` in this folder and go
to http://localhost:8000 (needed for the 404 page to style correctly).

## Files

```
index.html               the whole site
404.html                 shown for broken links
assets/style.css         all styling; colours and sizes are the tokens at the top
assets/portrait*.jpg/webp  your photo (location data stripped)
assets/og-image.jpg      image shown when the link is shared on LinkedIn, Slack etc.
assets/Amish_Gogia_CV.pdf  linked from the "Download CV" button
assets/fonts/            self-hosted Newsreader and Instrument Sans (SIL OFL licence)
.nojekyll                tells GitHub Pages to serve files as they are
```

## Updating

Every section in `index.html` is marked with a comment like
`<!-- ===================== RESEARCH ===================== -->`.
To add something, copy the nearest existing item and edit it.

- **New CV:** replace `assets/Amish_Gogia_CV.pdf`, keeping the file name.
- **News:** add a `<li>` at the top of the News list; delete the oldest so it stays short.
- **New project:** copy an `<article class="entry">` block in Research.
- **Paper:** copy an `<li>` in Publications; uncomment the arXiv/DOI link line.
- **Profiles:** uncomment INSPIRE / Scholar / ORCID / LinkedIn in the intro links,
  and add the same URLs to the `"sameAs"` list in the JSON-LD block in `<head>`.
- **Job change:** edit the `.role` line under your name, the bio paragraph, and
  `jobTitle` / `affiliation` in the JSON-LD block.
- **New photo:** replace the four `assets/portrait*` files (4:5 ratio, 1200×1500 and
  720×900), and `assets/og-image.jpg` (1200×630).
- Change "Last updated" in the footer when you edit.

Notation helpers: `B<span class="ss"><sup>0</sup><sub>s</sub></span>` gives a stacked
B⁰ₛ, `b<span class="bar">b</span>` gives b b̄.

## Custom domain (optional, later)

Buy a domain (e.g. `amishgogia.com`), add a file named `CNAME` containing just the
domain, and follow GitHub's guide "Managing a custom domain for your GitHub Pages
site". Links to the old github.io address keep working.

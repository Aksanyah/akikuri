# AKIKURI — akikuri.net

Brand site for **AKIKURI: The Story of How I, an Autumn Christian Girl, Toppled the Tech Industry's Demon Kings and Became the World's Strongest Pumpkin Spice Cyberpunker...**

Single-page Jekyll site: story blurb, characters, and Etsy merch links.

## Editing

- **Etsy links**: edit `etsy_shop`, `etsy_sticker`, `etsy_figure` in `_config.yml` — every button on the site reads from there.
- **Page content**: `index.html` (story, characters, shop cards).
- **Header/footer/meta tags**: `_layouts/default.html`.
- **Styling**: `assets/css/style.css`.
- **Images**: `assets/img/` (`bg-blur.jpg` background, `faythe-wings.png` / `faythe-wings-small.png` key art).

## Local preview

```powershell
bundle install          # first time only
bundle exec jekyll serve
```

Open http://localhost:4000. Restart the server if you edit `_config.yml`.

## Deploying (GitHub Pages)

Every push to `main` auto-builds and deploys via the workflow in `.github/workflows/jekyll.yml`. No VPS needed.

One-time setup:

1. Create a GitHub repo (e.g. `akikuri`), then:
   ```powershell
   git remote add origin https://github.com/<YOUR-USER>/akikuri.git
   git push -u origin main
   ```
2. On GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Still in Settings → Pages, set **Custom domain** to `akikuri.net` (the `CNAME` file in this repo keeps it set).
4. At your domain registrar, add DNS records for `akikuri.net`:
   - **A** records (apex `@`): `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **CNAME** record: `www` → `<YOUR-USER>.github.io`
5. Once DNS propagates (minutes to a few hours), check **Enforce HTTPS** in Settings → Pages.

After that, updating the live site is just: edit → commit → `git push`.

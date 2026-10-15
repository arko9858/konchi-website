# Konchi — Coming Soon Website

A lightweight, mobile-friendly holding page for `konchi.org`, using Konchi's uploaded original brand assets and the supplied meal-box reference photograph. **Static HTML/CSS with no npm, framework, build step, backend, cookies, or analytics.**

## Files

```
index.html
styles.css
CNAME
assets/
  konchi-wordmark.png
  konchi-mark.png
  meal-icon.png
  favicon.png
  apple-touch-icon.png
  meal-hero.webp
  meal-hero.jpg
  social-preview.jpg
```

### Design details

- Uses the official Konchi wordmark and K favicon, in the original green palette (`#527F3A`, `#78A825`).
- The hero photo uses a **crop of your third reference image** (`WhatsApp Image 2026-09-16 at 14.58.22.jpeg`). The poster's large pre-rendered headline was deliberately cropped out so the website's own headline is not duplicated. A JPEG fallback is included for the WEBP hero image.
- Desktop and mobile layouts are responsive. The meal photo appears beside the headline on desktop and below it on mobile.
- Open Graph/Twitter image in `assets/social-preview.jpg` for link sharing.
- The message avoids claiming a launch date.

## Local preview

Open `index.html` in a browser, or run:

```bash
python3 -m http.server 8000
```

and visit `http://localhost:8000`.

## Publish using GitHub Pages

1. Create a public GitHub repository (e.g. `konchi-website`).
2. Upload the **contents** of this ZIP to the root of the repository, including the `assets` folder and the `CNAME` file; commit to `main`.
3. In **Settings → Pages**, set Source to `Deploy from a branch`, branch `main`, folder `/(root)`, and save.
4. Set custom domain to `konchi.org` in Pages settings. The included `CNAME` file already points to it.
5. At your DNS provider, configure these four `A` records for host `@`:

   | Type | Host | Value |
   | --- | --- | --- |
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |

6. If you want `www.konchi.org` too, create a CNAME record from `www` to `YOUR-GITHUB-USERNAME.github.io` and configure it with GitHub Pages. Use your real account name, not the placeholder.
7. Once HTTPS is available in Pages settings, select **Enforce HTTPS**. DNS changes and certificates can take time to propagate.

If you already deployed the earlier edition, simply replace its root files with this update. GitHub Pages will redeploy on the next commit. Leave unrelated DNS records (MX/TXT/etc.) intact. If using Cloudflare Pages, Netlify, or another provider instead, follow that provider's DNS instructions; GitHub's `CNAME` file is specific to GitHub Pages.

Official guide: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

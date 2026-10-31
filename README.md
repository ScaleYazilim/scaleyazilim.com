# scaleyazilim.com

Corporate website for Scale Yazılım Ltd. Şti. — a static site with no build step.
Each page is a single self-contained HTML file.

## Structure

```
index.html                 home page (HTML + CSS + JS in one file)
modernization/index.html   Reforge — agentic legacy modernization platform page,
                           linked from Services; product screens are CSS mock-ups
services/<topic>/          training & consulting pages (elasticsearch, qdrant, redis,
                           big-data, kubernetes), linked from "Training & consulting";
                           each holds index.html and a 3-page A4 PDF of itself
hakkimizda/                About page (Turkish) — company details and the apps that share
                           one payment setup
gizlilik-sozlesmesi/       Privacy policy + KVKK notice (Turkish)
teslimat-ve-iade/          Delivery & returns terms (Turkish)
mesafeli-satis-sozlesmesi/ Distance sales agreement (Turkish)
assets/iyzico/             official iyzico logo bands (iyzico ile Öde + card schemes)
logo.svg       full lockup — mark + wordmark, used in the header
favicon.svg    the mark on its own, used as the browser icon
CNAME          custom domain: scaleyazilim.com
robots.txt     crawler directives
sitemap.xml    sitemap
.nojekyll      tells GitHub Pages to skip Jekyll processing
```

The palette is taken straight from the logo — deep navy `#0B1A3D` / `#004A7E`
through to cyan `#0098B3` / `#2EB6DB` — and lives in the `:root` block at the
top of each page. Changing those custom properties re-themes the page; keep every
page's `:root` block in sync.

### Training & consulting pages

Every `.sheet` section in a services page prints as exactly one A4 page (`@page` +
the print block at the end of the page's `<style>`), so printing the page — or opening
it with `?pdf`, which freezes the isometric figure — gives the shareable brochure.
After editing a page, regenerate its PDF from Chrome's print dialog (A4, margins
none, background graphics on) and save it next to the page as
`scale-yazilim-<topic>.pdf`; keep each sheet inside its page.

### Legal pages and payments

Payments for all of our apps go through one iyzico merchant account, so the four
Turkish pages above cover every app listed under "Uygulamalarımız" on `hakkimizda/`.
Add a row there when a new app starts taking payments. Every page's footer carries
the legal links and the white iyzico logo band (`assets/iyzico/logo-band-white.svg`);
keep both on any new page — iyzico checks for them. Use the colored band on light
backgrounds. Company details (unvan, address, VKN) appear in each legal page, so a
change there means updating all four.

## Development

Opening the file directly is enough:

```bash
open index.html
```

Or serve it locally:

```bash
python3 -m http.server 8000
```

## Deployment

Every push to `main` publishes automatically via GitHub Pages.

### Pages setting (one-time)

Repo → **Settings › Pages** → Source: **Deploy from a branch** → Branch: `main` / `/ (root)`.

### DNS setting (one-time)

At the domain registrar:

| Type  | Name  | Value                                                            |
|-------|-------|------------------------------------------------------------------|
| A     | `@`   | `185.199.108.153` `185.199.109.153` `185.199.110.153` `185.199.111.153` |
| CNAME | `www` | `motivolog.github.io`                                            |

Once DNS propagates, enable **Enforce HTTPS** under Settings › Pages.

## Contact

info@scaleyazilim.com

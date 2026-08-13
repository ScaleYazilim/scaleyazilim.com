# scaleyazilim.com

Corporate website for Scale Yazılım Ltd. Şti. — a single-page static site with no build step.

## Structure

```
index.html     the whole page (HTML + CSS + JS in one file)
CNAME          custom domain: scaleyazilim.com
robots.txt     crawler directives
sitemap.xml    sitemap
.nojekyll      tells GitHub Pages to skip Jekyll processing
```

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

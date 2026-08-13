# scaleyazilim.com

Scale Yazılım Ltd. Şti. kurumsal web sitesi. Tek sayfalık statik site — derleme adımı yok.

## Yapı

```
index.html     tüm sayfa (HTML + CSS + JS tek dosyada)
CNAME          özel alan adı: scaleyazilim.com
robots.txt     arama motoru yönergeleri
sitemap.xml    site haritası
.nojekyll      GitHub Pages'in Jekyll işlemesini atlaması için
```

## Geliştirme

Dosyayı doğrudan tarayıcıda açmak yeterli:

```bash
open index.html
```

Yerel sunucu tercih edilirse:

```bash
python3 -m http.server 8000
```

## Yayın

`main` dalına yapılan her push otomatik olarak yayına girer (GitHub Pages).

### Pages ayarı (tek seferlik)

Repo → **Settings › Pages** → Source: **Deploy from a branch** → Branch: `main` / `/ (root)`.

### DNS ayarı (tek seferlik)

Alan adı sağlayıcısında:

| Tip   | Ad    | Değer                                                            |
|-------|-------|------------------------------------------------------------------|
| A     | `@`   | `185.199.108.153` `185.199.109.153` `185.199.110.153` `185.199.111.153` |
| CNAME | `www` | `motivolog.github.io`                                            |

DNS yayıldıktan sonra Settings › Pages bölümünden **Enforce HTTPS** işaretlenmelidir.

## İletişim

info@scaleyazilim.com

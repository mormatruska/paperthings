# Paperthings — Kağıttan Şeyler

Tek sayfalık statik site. Build adımı, framework ve CDN yok; tüm yollar göreli.

## Önizleme
Herhangi bir statik sunucu yeterli:

- `python -m http.server 8080` veya `npx serve .`
- Node/Python yoksa (Windows): `powershell -ExecutionPolicy Bypass -File _dev/serve.ps1 8080` → http://localhost:8080

## Yayına alma
Klasörü olduğu gibi Netlify / Vercel / GitHub Pages'a yükle (`_dev/` ve `design-system/` yüklenmese de olur).

## Yapı
`index.html` · `css/style.css` · `js/main.js` · `fonts/` (Bricolage Grotesque + Figtree, SIL OFL, self-host) · `images/` · `favicon.svg` · `robots.txt` · `sitemap.xml`
Tasarım kuralları: `design-system/paperthings/MASTER.md`. Doğrulama: `_dev/check.mjs` (tarayıcı konsolunda çalışır).

## TODO
- [ ] 16 mağaza linki: `index.html` içinde `<!-- TODO:LINK -->` (12 ürün butonu, 2 Satın Al, 2 footer). Gerçek URL gelince `target="_blank" rel="noopener"` ekle.
- [ ] Alan adı: `https://ALAN-ADI.com` → canonical, og:url, og:image, JSON-LD, `sitemap.xml`, `robots.txt` (`TODO:ALAN-ADI`).
- [ ] Hero görseli: `images/ana-gorsel.jpg` (900×900).
- [ ] OG görseli: `images/og-paperthings.jpg` (1200×630, ≤150 KB, kenar boşluğu `#3D1A39`).
- [ ] Ürün görselleri: `images/urunler/<slug>.jpg` (1200×900). Slug'lar: `a5-not-defteri`, `a6-not-defteri`, `tarif-defteri`, `bi-kitap-daha`, `tanisma-fasli`, `dikenli-iskambil-kagitlari`. `.urun-gorsel` içindeki `.silu`'yu `<img ... loading="lazy" decoding="async">` ile değiştir.
- [ ] Logo: `images/logo.svg` (header'daki `LOGO:` yorumuna bak).
- [ ] SSS doğrulaması: kargo/iade, A5-A6 ölçüleri, oyun kuralı, iskambil içeriği. SSS'yi değiştirirsen JSON-LD'yi de güncelle.

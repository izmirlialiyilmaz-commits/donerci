# Coss Fast Food — Web Sitesi

Coss Fast Food için tek dosyalık (`index.html`), siyah temalı, video arka planlı tanıtım sitesi.
Kurulum gerektirmez: saf HTML + CSS + JS. Kod tek dosyada; video/logo/görseller `assets/` klasöründe.

## Öne çıkanlar

- **Otomatik oynayan video arka planı** — `muted autoplay playsinline loop` özellikleri doğrudan
  HTML'de tanımlı (JS ile sonradan eklenmiyor), bu yüzden Chrome/Firefox/Safari dahil tüm modern
  tarayıcılarda ve mobilde otomatik başlar. WebM (VP9) + MP4 (H.264) kaynağı birlikte sunulur.
- **Gerçekten masaüstü + mobil uyumlu** — sade flexbox/grid düzeni, 900px ve 680px kırılma
  noktaları, mobilde hamburger menü. Scroll-hijack eden veya sadece belirli tarayıcılarda çalışan
  karmaşık efekt yok.
- **Sade, sağlam scroll animasyonları** — `IntersectionObserver` ile fade+slide-up reveal.
  Sayfanın kaydırma davranışını değiştirmez, tüm cihazlarda öngörülebilir çalışır.
- **"Yemek Sipariş Et"** — standart `<a href="#siparis">` + tarayıcının kendi `scroll-behavior:smooth`
  özelliği ile kayar (özel JS scroll motoru yok, bu yüzden kırılma riski yok).
- **Gerçek platform logoları** — Yemeksepeti, Trendyol, Migros, Getir.
- **İletişim bilgileri** — telefon, adres, çalışma saatleri, e-posta, sosyal medya.
- **Ürün/menü bölümü yoktur** (istenildiği gibi).
- `prefers-reduced-motion` desteği.

## Dosya yapısı

```
index.html                 # Tüm site (HTML + CSS + JS, tek dosya)
assets/
  hero.mp4 / hero.webm     # Arka plan videosu
  hero-poster.jpg          # Video yüklenene kadar gösterilen kare
  hero.jpg                 # Hikaye bölümü görseli
  logo.svg / favicon.svg   # Coss logosu ve sekme ikonu
  logos/                   # Sipariş platformlarının logoları
    yemeksepeti.svg  trendyol.svg  migros.svg  getir.svg
```

## Kişiselleştirme

| Ne | Nerede |
|---|---|
| Sipariş bağlantıları | `#siparis` bölümündeki 4 `<a class="platform" href="#">` |
| Telefon | `tel:+905000000000` ve görünen numara |
| Adres | İletişim bölümündeki "Örnek Mah. …" satırı |
| E-posta | `info@cossfastfood.com` |
| Sosyal medya | İletişim bölümündeki `.socials` bağlantıları |

## Yayınlama / yerel test

Statik bir sitedir, herhangi bir hosting'e (GitHub Pages, Netlify, Vercel) yüklenebilir.
Yerelde denemek için (video otomatik oynatmanın garantisi için bir sunucu üzerinden açın):

```bash
python3 -m http.server 8000
# tarayıcıda http://localhost:8000
```

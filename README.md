# Coss Fast Food — Web Sitesi

Coss Fast Food dükkanı için tek sayfalık, animasyonlu ve tamamen bağımsız (statik) bir tanıtım web sitesi.

## Öne çıkanlar

- **Sinematik video hero** — dumanı tüten yemekleri gösteren tanıtım videosu tam ekran, sessiz, otomatik oynayan hareketli arka plan; üzerinde cam (glassmorphism) panel ve yükselen köz kıvılcımı animasyonu.
- **Kaydırdıkça hareket eden video (scroll-scrub)** — sabitlenen video, sayfayı kaydırdıkça timeline'ı taranır: malzemeler → tavuk döner → burger → dumanı üstünde tam takım. Üzerinde dev kinetik yazılar değişir.
- **Şeffaf / cam görünümlü** kartlar ve butonlar (`backdrop-filter` blur).
- **Scroll ile açılan (reveal) animasyonlar** — `IntersectionObserver` ile aşamalı görünürlük.
- **Akıcı geçiş efektleri**, hover animasyonları, kayan (marquee) lezzet şeridi.
- **Tam responsive** — mobilde hamburger menü, esnek grid.
- `prefers-reduced-motion` desteği (hareket hassasiyeti olan kullanıcılar için).

## Menü (ürünler)

Tavuk Döner · Et Döner · Köfte Burger · Tavuk Burger · Karışık Sandviç (+ Coss Combo)

## Anlaşmalı teslimat platformları

Yemeksepeti · Trendyol Yemek · Migros Yemek · Getir Yemek

> Teslimat kartlarındaki `href="#"` bağlantılarını gerçek restoran linklerinizle güncelleyin.
> Finaldeki `0 (500) 000 00 00` telefon numarasını ve footer'daki çalışma saatlerini kendi bilgilerinizle değiştirin.

## Dosya yapısı

```
index.html            # Tüm site (HTML + CSS + JS tek dosyada)
assets/
  logo.svg            # Beyaz arka planlı Coss logosu
  favicon.svg         # Sekme ikonu
  hero.mp4 / .webm    # Hero arka plan videosu (otomatik oynayan)
  hero-scrub.mp4/.webm# Scroll ile taranan (scrub) video — tüm kareler keyframe
  hero-poster.jpg     # Video yüklenene kadar gösterilen poster
  hero.jpg            # Combo kartı görseli
  tavuk-doner.jpg
  et-doner.jpg
  kofte-burger.jpg
  tavuk-burger.jpg
  karisik-sandvic.jpg
```

> Videolar hem `.webm` (VP9) hem `.mp4` (H.264) olarak sunulur — tüm modern tarayıcılar
> ve Safari desteklenir. Kendi tanıtım videonuzla değiştirmek isterseniz aynı adlarla
> `assets/` içine koyun (scrub sürümü için tüm karelerin keyframe olması akıcılığı artırır).

## Yayınlama

Kurulum gerektirmez. `index.html`'i herhangi bir statik sunucuya (GitHub Pages, Netlify, Vercel, kendi hosting'iniz) yüklemeniz yeterli. Yerelde denemek için:

```bash
python3 -m http.server 8000
# tarayıcıda http://localhost:8000
```

## Görsel kaynakları

Yemek fotoğrafları Wikimedia Commons'tan alınmış serbest lisanslı görsellerdir. İşletmenizin kendi fotoğraflarıyla değiştirmeniz, sitenin özgünlüğü ve iştah açıcılığı için önerilir.

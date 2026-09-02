# Coss Fast Food — Web Sitesi

Coss Fast Food için tek sayfalık, siyah temalı, sinematik video arka planlı tanıtım sitesi.
Kurulum gerektirmez: saf HTML + CSS + JS, tek dosya (`index.html`) ve `assets/` klasörü.

## Öne çıkanlar

- **Siyah tema** — saf siyah zemin, krem metin, ateş kırmızısı ve kehribar vurgular.
- **Tam ekran sabit video arka planı** — sayfanın arkasında yaşayan, sessiz ve otomatik oynayan
  tanıtım videosu. Hero ve ara-perdede görünür, diğer bölümler opak siyahla üstünü kapatır.
- **"Yemek Sipariş Et" butonu** — tıklanınca sayfa `easeInOutCubic` yumuşamasıyla ~1.15 sn'de
  sipariş bölümüne kayar; varışta platform kartları sırayla darbe animasyonuyla vurgulanır.
- **Animasyonlu geçişler** — scroll ile açılan (reveal) bölümler, sayaçlar, hover kalkışları,
  nabız atan CTA noktası, altı çizilen menü bağlantıları.
- **Gerçek platform logoları** — Yemeksepeti, Trendyol, Migros ve Getir.
- **İletişim bilgileri** — telefon, adres, çalışma saatleri, e-posta ve sosyal medya.
- **Ürün/menü bölümü yoktur** (istenildiği gibi).
- Tam responsive, `prefers-reduced-motion` desteği, yukarı çık butonu.

## Dosya yapısı

```
index.html                 # Tüm site (HTML + CSS + JS)
assets/
  hero.mp4 / hero.webm     # Arka plan videosu (H.264 + VP9)
  hero-poster.jpg          # Video yüklenene kadar gösterilen kare
  hero.jpg                 # Hikaye bölümündeki atmosfer görseli
  logo.svg / favicon.svg   # Coss logosu ve sekme ikonu
  logos/                   # Sipariş platformlarının logoları
    yemeksepeti.svg  trendyol.svg  migros.svg  getir.svg
```

## Kişiselleştirme

Yayına almadan önce güncellenmesi gerekenler:

| Ne | Nerede |
|---|---|
| Sipariş bağlantıları | `#siparis` bölümündeki 4 `<a class="plat" href="#">` |
| Telefon | `tel:+905000000000` ve görünen numara |
| Adres | İletişim bölümündeki "Örnek Mah. …" satırı |
| E-posta | `info@cossfastfood.com` |
| Sosyal medya | İletişim bölümündeki `.socials` bağlantıları |

## Yayınlama

Statik bir site olduğu için herhangi bir yere yüklenebilir (GitHub Pages, Netlify, Vercel).
Yerelde denemek için — videonun oynaması bir sunucu gerektirir, dosyaya çift tıklamak yetmez:

```bash
python3 -m http.server 8000
# tarayıcıda http://localhost:8000
```

## Notlar

- Video hem `.webm` (VP9) hem `.mp4` (H.264) olarak sunulur; tüm modern tarayıcılar ve Safari çalışır.
- Platform logoları Wikimedia Commons kaynaklıdır ve yalnızca anlaşmalı sipariş kanallarını
  göstermek için kullanılır; markalar ilgili şirketlere aittir.

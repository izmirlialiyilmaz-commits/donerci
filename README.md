# Coss Fast Food — Web Sitesi

Coss Fast Food için tek sayfalık, siyah temalı, sinematik video arka planlı tanıtım sitesi.
Kurulum gerektirmez: saf HTML + CSS + JS, tek dosya (`index.html`) ve `assets/` klasörü.

## Öne çıkanlar

- **Açılış (intro) animasyonu** — tam ekran siyah perde, harf harf açılan "COSS", dolan ilerleme
  çubuğu ve 0→100 sayaç; bitince perde ikiye ayrılıp siteyi açar.
- **Siyah tema** + tam ekran sabit **video arka planı** (sayfanın arkasında yaşar).
- **Ağır scroll efektleri**
  - Sabitlenen (pinned) 3 sahne: *Taze Malzeme → Közde Pişer → Dumanı Üstünde*.
    Scroll ilerledikçe sahneler çapraz geçiş yapar, görseller ölçeklenir, yan ray ve sayaç dolar.
  - **Yatay kaydırma galerisi** — dikey scroll ile yatay akan kart şeridi ve dev kontur yazılar.
  - Üstte scroll ilerleme çubuğu, hero'da fare parallax'ı, hıza tepki veren kayan yazı şeridi.
- **Etkileşimli efektler** — özel imleç (hover'da büyüyüp etiket gösterir), mıknatıslı butonlar,
  3D eğilen platform kartları.
- **"Yemek Sipariş Et"** — `easeInOutCubic` ile ~1.25 sn animasyonlu kaydırma; hedefi her karede
  yeniden hesaplar, varışta kartları sırayla darbe animasyonuyla vurgular.
- **Gerçek platform logoları** — Yemeksepeti, Trendyol, Migros, Getir.
- **İletişim bilgileri** — telefon, adres, çalışma saatleri, e-posta, sosyal medya.
- **Ürün/menü bölümü yoktur** (istenildiği gibi).
- Tam responsive, `prefers-reduced-motion` desteği (intro ve efektler kapanır), yukarı çık butonu.

## Dosya yapısı

```
index.html                 # Tüm site (HTML + CSS + JS)
assets/
  hero.mp4 / hero.webm     # Arka plan videosu (H.264 + VP9)
  hero-poster.jpg          # Video yüklenene kadar gösterilen kare
  hero.jpg                 # Atmosfer görseli
  frames/f1..f5.jpg        # Videodan çıkarılan sahne/galeri kareleri
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

# Coss Fast Food — Web Sitesi + Yönetim Paneli

Coss Fast Food için video arka planlı tanıtım sitesi, artık kod bilmeden içerik güncellemeyi
sağlayan bir **yönetim paneli** ile birlikte. Kurulum gerektirmez: saf HTML + CSS + JS.

## Dosyalar

```
index.html                 # Canlı site (HTML + CSS + JS, tek dosya)
admin.html                 # Yönetim paneli — logo/metin/link/SEO düzenleme
robots.txt                 # Arama motoru tarayıcı kuralları
sitemap.xml                # Arama motorları için site haritası
assets/
  hero.mp4 / hero.webm     # Arka plan videosu (H.264 + VP9)
  hero-poster.jpg          # Video yüklenene kadar gösterilen kare
  hero.jpg                 # Hikaye bölümü görseli
  logo.png                 # Coss logosu (nav çubuğunda kullanılır)
  favicon-32.png           # Sekme ikonu
  apple-touch-icon.png     # iOS ana ekran ikonu
  logos/                   # Sipariş platformlarının logoları
    yemeksepeti.svg  trendyol.svg  migros.svg  getir.svg
```

## Yönetim Paneli (`admin.html`)

Kod yazmadan şunları değiştirebileceğiniz bir panel:

- **Logo** — yeni bir görsel yükleyin, boyutunu (px) elle ayarlayın. Kare olmayan görseller
  beyaz zemin üzerine ortalanır. Yüklediğinizde nav logosu, sekme ikonu ve Apple ikonu
  otomatik olarak yeniden üretilir.
- **Hero metinleri** — üst etiket, başlık (2 satır), alt açıklama.
- **İletişim** — telefon, adres, çalışma saatleri, e-posta.
- **4 sipariş platformu linki** — Yemeksepeti, Trendyol, Migros, Getir.
- **Sosyal medya** — Instagram, Facebook, WhatsApp.
- **SEO** — sayfa başlığı, meta açıklama, paylaşım görseli.

### Nasıl çalışır (önemli)

Panel **internete hiçbir şey yayınlamaz**. Akış şöyle:

1. `admin.html`'i açın (şifre: `cossadmin2025` — değiştirmek için dosyadaki `ADMIN_PASS`
   satırını düzenleyin). Bu şifre gerçek bir güvenlik önlemi değildir, sadece rastgele bir
   ziyaretçiyi caydırmak içindir — panelin adresini kimseyle paylaşmayın.
2. Panel mevcut `index.html`'i otomatik yükler (bir sunucu üzerinden açtıysanız) veya
   "Dosyadan Seç" ile elle seçersiniz (dosyaya çift tıklayarak açtıysanız gereklidir).
3. Formu düzenleyin.
4. **"Güncellenmiş Dosyaları İndir"** — yeni `index.html`'i (ve logo değiştiyseniz
   `logo.png` / `apple-touch-icon.png` / `favicon-32.png` dosyalarını) bilgisayarınıza indirir.
5. İndirilen dosyaları GitHub'a (veya kullandığınız hosting'e) her zamanki gibi yükleyip
   (commit + push) yayınlarsınız.

Bu sürümde **ürün/menü, arka plan videosu ve fotoğraflar panelden değiştirilemez** —
bunlar için bana tekrar yazmanız yeterli.

### Site adresi hakkında not

`robots.txt`, `sitemap.xml` ve `admin.html`'deki `SITE_BASE_URL` şu anda
`https://izmirlialiyilmaz-commits.github.io/donerci/` adresine göre ayarlı (GitHub Pages'in
varsayılan adresi). Kendi alan adınızı (`cossfastfood.com` gibi) bağlarsanız, bu üç dosyadaki
adresi güncelleyin — aksi halde paylaşım önizlemeleri (WhatsApp/Instagram) ve arama motoru
kayıtları eski adresi gösterebilir.

## SEO

- Open Graph + Twitter Card meta etiketleri (paylaşım önizlemeleri için, mutlak URL'lerle).
- **JSON-LD yapılandırılmış veri** (`FastFoodRestaurant`) — isim, telefon, e-posta, adres,
  çalışma saatleri, sosyal medya linkleri. Google ve harita hizmetlerinin işletmenizi doğru
  tanıması için. Panelden düzenlediğiniz telefon/e-posta/adres/sosyal linkler bu veriye de
  yansır; panelin bilerek dokunmadığı alanlar (çalışma saatlerinin gün-gün yapısı, adresin
  mahalle/il ayrımı) mevcut haliyle korunur.
- Otomatik `canonical` link (sayfa hangi adresten açılırsa oradan hesaplanır).
- `sitemap.xml` + `robots.txt`.

## Yayınlama / yerel test

Statik bir sitedir, herhangi bir hosting'e (GitHub Pages, Netlify, Vercel) yüklenebilir.
Yerelde denemek için (video otomatik oynatmanın ve panelin otomatik dosya yüklemesinin
garantisi için bir sunucu üzerinden açın):

```bash
python3 -m http.server 8000
# tarayıcıda http://localhost:8000        (site)
# tarayıcıda http://localhost:8000/admin.html   (yönetim paneli)
```

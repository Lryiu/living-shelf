# 📚 Living Shelf — Yaşayan Kitaplık

**[→ Canlı Demo](https://gamzeguckiran.com/living-shelf.html)**

Okuma yolculuğunu bilişsel bir atlasa dönüştüren, tek dosyalık, tarayıcı tabanlı bir kütüphane uygulaması. Kitaplarını ekle, yazar ustalık seviyeni takip et, okuma alışkanlıklarının etkisini görselleştir.

*Lryiu Labs — Experimental Suite'in bir parçasıdır.*

---

## ✨ Özellikler

- **Raf Görünümü** — kitaplarını kapak, durum (okundu / okunuyor / yarım kaldı) ve etiketlerle organize et
- **Yazar Mühürleri** — her yazardan kaç kitap okuduğunu ve "ustalık seviyeni" gör
- **Etki / Atlas Görünümü** — okuma istatistiklerin, arketip analizin ve etki grafiklerin
- **AI Destekli Profil** (opsiyonel) — kendi Anthropic API anahtarınla kitap analizleri
- **Google Books Entegrasyonu** (opsiyonel) — kapak/bilgi otomatik çekme
- **JSON İçe/Dışa Aktarma** — verini yedekle veya cihazlar arası taşı

## 🔒 Verilerin Nerede Saklanıyor?

**Önemli:** Bu uygulama bir sunucu veya veritabanı kullanmaz. Tüm kitap verilerin **yalnızca kendi tarayıcında**, `localStorage` üzerinde saklanır.

Bunun anlamı:
- ✅ Verilerin tamamen sana özel — kimse (biz dahil) göremez
- ✅ Kayıt / giriş gerekmez, anında kullanmaya başlarsın
- ⚠️ Tarayıcı verilerini/geçmişini temizlersen kitapların **silinir**
- ⚠️ Farklı bir cihaz veya tarayıcıdan girersen kitaplarını **görmezsin** (senkronizasyon yok)

**Öneri:** Ayarlar menüsünden düzenli olarak **"Dışa Aktar"** (Export JSON) yaparak yedek al. Cihaz değiştirdiğinde veya tarayıcı verisi sıfırlandığında bu dosyayı **"İçe Aktar"** ile geri yükleyebilirsin.

## 🔑 API Anahtarları (Opsiyonel)

AI destekli profil ve Google Books otomatik doldurma özellikleri için Ayarlar menüsünden kendi API anahtarlarını girebilirsin:

- **Anthropic API Key** — AI destekli okuma profili / arketip analizi için
- **Google Books API Key** — kitap arama ve kapak görseli otomatik çekme için

Bu anahtarlar da yalnızca kendi tarayıcında (`localStorage`) saklanır, hiçbir sunucuya gönderilmez. Anahtarını istediğin zaman Ayarlar'dan silebilirsin.

## 🚀 Kullanım

**Online:** Hiçbir kurulum gerekmez — [canlı demo linkine](https://gamzeguckiran.com/living-shelf.html) git ve kullanmaya başla.

**Yerel / kendi bilgisayarında çalıştırmak istersen:**
1. Bu repoyu indir veya klonla
2. `living-shelf.html` dosyasını herhangi bir modern tarayıcıda aç (çift tıklamak yeterli)
3. İnternet bağlantısı sadece font ve D3.js kütüphanesi için gerekli

## 🛠️ Teknoloji

Tek dosyada vanilla HTML / CSS / JavaScript + [D3.js](https://d3js.org/) (görselleştirmeler için). Harici bir framework veya build süreci yok.

## 📄 Lisans

© 2026 Lryiu Labs — Tüm hakları saklıdır.

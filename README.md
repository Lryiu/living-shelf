# 📚 Living Shelf — Yaşayan Kitaplık

**[→ Canlı Demo](https://gamzeguckiran.com/living-shelf.html)**

Okuma yolculuğunu bilişsel bir atlasa dönüştüren, tarayıcı tabanlı bir kütüphane uygulaması. Kitaplarını ekle, yazar ustalık seviyeni takip et, okuma alışkanlıklarının etkisini görselleştir.

*Lryiu Labs — Experimental Suite'in bir parçasıdır.*

---

## ✨ Özellikler

- **Raf Görünümü** — kitaplarını kapak, durum (okundu / okunuyor / yarım kaldı) ve etiketlerle organize et
- **Sinaps Haritası** — yazarlar nöron, temalar zihnin bölgeleri; okudukça harita büyür, son okumaların sıcak görünür
- **Yazar Mühürleri** — her yazardan kaç kitap okuduğunu ve "ustalık seviyeni" gör
- **Tema Posteri** — temalarını tipografik bir afişe dönüştür, görsel olarak indir ya da paylaş
- **Okuma Pusulası ve Zaman Çizelgesi** — okumalarının seni nereye taşıdığını gör
- **Tema Sözlüğü** — yüzlerce kitabı kapsayan, elle denetlenmiş bir sözlük; başlık ve yazar eşleşirse temalar önerilir
- **Akıllı Etiketler** — yazım hatalarını yakalayan etiket girişi ve tüm etiketleri birleştirip düzelten etiket yöneticisi
- **Goodreads'ten Aktarma** — Goodreads'in dışa aktarma dosyasıyla kitaplığını tek seferde taşı
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

## 📖 Tema Sözlüğü

`data/tema-sozlugu.csv` uygulamayla birlikte gelen tema sözlüğüdür. Kitap eklerken başlık ve yazar sözlükteki bir kitapla eşleşirse temaları önerilir; Goodreads aktarımında ve Ayarlar'daki "Etiketsiz kitaplarımı sözlükle tamamla" düğmesinde de kullanılır. Kullanıcının kendi verdiği etiketlerin üzerine hiçbir zaman yazılmaz.

- Eşleşme her zaman **başlık + yazar** birlikte yapılır; aynı adlı iki farklı kitap (ör. Kafka'nın ve Baudrillard'ın *Amerika*'sı) karışmaz.
- Özgün başlık ve yazarın farklı yazılışları da tanınır: *Crime and Punishment / Fyodor Dostoevsky* → *Suç ve Ceza*.
- Etiketler yalnızca `data/ana-tema-listesi.txt` içindeki temalardan seçilir.

Sözlüğü büyütmek için CSV'ye aynı sütunlarla yeni satır eklemen yeterli: `Başlık, Özgün başlık, Yazar, Yazar diğer yazılışlar, Etiketler, ISBN`. HTML dosyasına dokunmana gerek yok.

## 🔑 API Anahtarları (Opsiyonel)

AI destekli profil ve Google Books otomatik doldurma özellikleri için Ayarlar menüsünden kendi API anahtarlarını girebilirsin:

- **Anthropic API Key** — AI destekli okuma profili / arketip analizi için
- **Google Books API Key** — kitap arama ve kapak görseli otomatik çekme için

Bu anahtarlar da yalnızca kendi tarayıcında (`localStorage`) saklanır, hiçbir sunucuya gönderilmez. Anahtarını istediğin zaman Ayarlar'dan silebilirsin.

## 🚀 Kullanım

**Online:** Hiçbir kurulum gerekmez — [canlı demo linkine](https://gamzeguckiran.com/living-shelf.html) git ve kullanmaya başla.

**Kendi sitende yayınlamak istersen:** `living-shelf.html` dosyasını ve `data/` klasörünü aynı dizine yükle. Sözlük `data/tema-sozlugu.csv` yolunda aranır.

**Yerel / kendi bilgisayarında çalıştırmak istersen:**
1. Bu repoyu indir veya klonla
2. `living-shelf.html` dosyasını herhangi bir modern tarayıcıda aç (çift tıklamak yeterli)
3. İnternet bağlantısı sadece font ve D3.js kütüphanesi için gerekli

Dosyayı çift tıklayarak açtığında tarayıcılar yerel dosyadan sözlüğü okumaya izin vermez; uygulama çalışır ama tema önerileri görünmez. Sözlükle birlikte denemek için klasörde küçük bir yerel sunucu başlat (`python3 -m http.server`) ve `http://localhost:8000/living-shelf.html` adresini aç.

## 🛠️ Teknoloji

Tek HTML dosyasında vanilla HTML / CSS / JavaScript + [D3.js](https://d3js.org/) (görselleştirmeler için), yanında düz CSV olarak tema sözlüğü. Harici bir framework veya build süreci yok.

## 📄 Lisans

© 2026 Lryiu Labs — Tüm hakları saklıdır.

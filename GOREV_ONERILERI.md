# Görev Önerileri (Kod Tabanı İncelemesi)

## 1) Yazım Hatası Düzeltme Görevi
**Başlık:** `bmw.html` metnindeki bitişik yazılmış kelimeyi düzelt

- **Sorun:** BMW sayfasındaki içerikte "onlarıneşsiz" ifadesi bitişik yazılmış.
- **Önerilen düzeltme:** İfadeyi "onların eşsiz" olarak güncelle.
- **Kabul kriterleri:**
  - `bmw.html` içinde "onlarıneşsiz" kalmamalı.
  - Güncel metin tarayıcıda anlam bütünlüğünü korumalı.

## 2) Hata (Bug) Düzeltme Görevi
**Başlık:** `bmw.html` içindeki bozuk `width` niteliğini düzelt

- **Sorun:** BMW sayfasındaki görselde `width="670>px"` yazımı hatalı; HTML niteliği bozuluyor ve görsel boyutlandırması tutarsız çalışabiliyor.
- **Önerilen düzeltme:** Değeri `width="670px"` olarak güncelle ve görselin doğru boyutta render edildiğini doğrula.
- **Kabul kriterleri:**
  - İlgili `<img>` etiketi geçerli HTML niteliği kullanmalı.
  - Sayfa açıldığında görsel beklenen genişlikte görünmeli.

## 3) Yorum/Dokümantasyon Tutarsızlığı Düzeltme Görevi
**Başlık:** Stil kullanımına dair dokümantasyonu netleştir ve kodu dokümantasyonla hizala

- **Sorun:** Projede ortak stil dosyası (`style.css`) olmasına rağmen `index.html` içinde aynı stiller satır içi `<style>` bloğunda tekrar ediyor; bu durum "tek kaynak" yaklaşımıyla çelişiyor.
- **Önerilen düzeltme:**
  1. Kısa bir `README.md` ekleyip tüm sayfaların ortak stilleri `style.css` üzerinden kullandığını dokümante et.
  2. `index.html` içindeki tekrar eden stil bloğunu kaldırıp `style.css` bağlantısına geçir.
- **Kabul kriterleri:**
  - `README.md` içinde stil kaynağı net tanımlanmalı.
  - `index.html` satır içi stil bloğu içermemeli ve görünüm bozulmamalı.

## 4) Test İyileştirme Görevi
**Başlık:** Basit bir HTML doğrulama/regresyon testi ekle

- **Sorun:** Projede otomatik test olmadığı için yazım ve nitelik hataları (ör. bozuk `width`) kolayca gözden kaçıyor.
- **Önerilen iyileştirme:**
  - Bir CI adımı veya yerel script ile HTML dosyalarında temel kontroller çalıştır:
    - bozuk nitelik desenleri (`">px"` gibi),
    - kapanmayan etiketler,
    - kırık iç linkler (`href` ile hedef dosya var mı).
- **Kabul kriterleri:**
  - Tek komutla çalışabilen bir doğrulama scripti olmalı.
  - Hatalı durumda sıfırdan farklı çıkış kodu dönmeli.
  - En az bir örnek hata senaryosu testte yakalanmalı.

---

## İncelemede Dayanak Alınan Bulgular
- Yazım hatası örneği: `bmw.html` içinde "onlarıneşsiz".
- Bug örneği: `bmw.html` içinde `width="670>px"`.
- Dokümantasyon/tasarım tutarsızlığı örneği: `index.html` içinde satır içi stil tekrarı, `style.css` ile mükerrer yapı.

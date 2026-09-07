# Berfin & Emir 💗

Kavuşmamıza kalan süreyi sayan, piksel sanatlı küçük bir geri sayım sayfası.
Emir İstanbul'da, Berfin Malatya'da; her geçen saniye iki karakter ekranın ortasına doğru birbirine biraz daha yaklaşıyor.

**Kavuşma:** 9 Eylül 2026, sabah 10:30

## Neler var?

- **Geri sayım** — gün / saat / dakika / saniye olarak kalan süre, saniyede bir güncellenir.
- **Yolculuk animasyonu** — Emir ve Berfin, son görüştüğümüz tarihten kavuşma anına kadar olan ilerlemeye göre yolda ilerler. Süre dolunca "KAVUŞTUK!" ekranı ve birlikte olan çift görseli açılır.
- **Birliktelik sayacı** — sevgili olduğumuz tarihten bu yana geçen gün sayısı ("… gündür mutluyuz").
- **Kalpler ve pırıltılar** — sayfada uçuşan piksel kalpler ve parıltı efektleri.
- **Ayarlar paneli** — tarihleri sayfayı düzenlemeden değiştirmek için gizli bir panel.

## Tarihler

| Ayar | Varsayılan | Açıklama |
|---|---|---|
| Kavuşacağımız tarih | 9 Eylül 2026 · 10:30 | Geri sayımın hedefi |
| Son görüştüğümüz tarih | 24 Haziran 2026 | Yolculuk animasyonunun başlangıcı |
| Sevgili olduğumuz tarih | 13 Mayıs 2026 | "gündür mutluyuz" sayacının başlangıcı |

Kavuşma saati (10:30) kodda sabittir; tarih ayarlar panelinden değiştirilse bile saat aynı kalır.

## Ayarlar panelini açmak

Panel normalde gizlidir. Açmak için iki yol var:

1. Sayfadaki başlığa art arda **5 kez dokun**.
2. Adresin sonuna `#emir` veya `#ayar` ekleyerek sayfayı aç.

Panelde üç tarih de değiştirilebilir. Seçimler tarayıcının yerel depolamasına (`localStorage`) kaydedilir, yani sadece o cihazda geçerlidir. "Tamam" ile panel kapanır ve yönetici modu sıfırlanır.

Kullanılan anahtarlar: `bg_returnDate`, `bg_startDate`, `bg_togetherDate`, `bg_admin`.

## Çalıştırma

Proje tek bir dosyadan oluşur: `index.html`. Görseller, yazı tipleri ve kod dosyanın içine gömülüdür; ek bir kurulum ya da sunucu gerekmez.

- Dosyayı tarayıcıda açmak yeterlidir.
- GitHub Pages üzerinden de yayınlanabilir; `main` dalındaki `index.html` doğrudan servis edilir.

## Yapı

```
index.html   # Sayfanın tamamı: şablon, stiller, gömülü görseller ve bileşen kodu
README.md
```

Sayfa, `index.html` içindeki `Component` sınıfı tarafından çizilir. Geri sayım, ilerleme oranı ve tarih metni her saniye yeniden hesaplanır; eski cihazlarda kayıtlı 7 Eylül değeri açılışta otomatik olarak 9 Eylül'e taşınır.

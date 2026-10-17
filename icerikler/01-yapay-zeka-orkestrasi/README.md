# Yapay Zekâ Orkestrası · RC AI Notları #1

[Telegram duyuru](https://t.me/RuesAnnouncement) · [Telegram](https://t.me/ruesandora) · [X @Ruesandora0](https://x.com/Ruesandora0)

Rues Community · Eylül 2026 · Gerçek bir projede her gün kullanılan düzenden derlendi.

---

> **Şef çalmaz, yönetir.** Büyük bir işi tek bir yapay zekâ sohbetine yıkmak yerine bir orkestra kur: ana oturum şef olur, işi uzman ajanlara böler, bağımsız bir denetçi kontrol eder, şef birleştirir.

![Sayfa önizlemesi](gorseller/onizleme-masaustu.jpg)

**Canlı sayfa:** https://claude.ai/artifact/2aUHSAwuRb5pNgoTopiv4Q · **Dosya:** [`index.html`](index.html) — tek dosya, tarayıcıda doğrudan açılır. Açık ve koyu temayı destekler, telefonda da okunur.

## İçinde neler var

| Bölüm | Özet |
|---|---|
| Neden orkestra? | Tek ajanla büyük işin dört sorunu: bağlam şişer, kendi işini onaylar, sıra bekler, iş kaybolur |
| Kadro | Şef, yükleyici, araştırmacı, geliştirici, tasarımcı, video üreticisi, denetçi: her biri için model, neden o model, örnek işler, ne zaman kullanılmaz |
| Hangi işe hangi model | Haiku 5.5, Sonnet 5.5, Opus 5.5 için iki soruluk karar akışı; en zor işler için isteğe bağlı premium basamak Fable 5.1 |
| Bir işin yolculuğu | İstekten yayına 7 adım, en fazla 3 turluk DÜZELT döngüsü |
| Brif şablonu | GÖREV · SENİN DOSYALARIN · DOKUNMA · ÖNCE OKU · BİTTİ TANIMI · RAPOR |
| Gerçek bir gün | Aynı gün paralel çalışan denetim, tasarım ve workflow ajanları |
| Değişmez kurallar | Para kuralı, uydurma yok, mutasyon kontrolü, tehlikeli git komutları |
| Sahadan dersler | Bitmeyen bekleme döngüsü, dolan disk, yeniden başlayan makine, denetçinin yakaladığı donma… |
| Kendi orkestranı kur | Kopyalanabilir ajan dosyaları, kontrol listesi, sözlük |

![Sahne şeması](gorseller/sahne-semasi.jpg)

## Hazır ajan dosyaları

[`ajanlar/`](ajanlar) klasöründeki dosyaları kendi projende `.claude/agents/` altına kopyala (Claude Code):

| Dosya | Model | Rol |
|---|---|---|
| [`denetci.md`](ajanlar/denetci.md) | Sonnet 5.5 (hafif tur Haiku 5.5, riskli işte Opus 5.5) | Başka ajanın işini bağımsız kontrol eder, ONAY / DÜZELT döner. İlk bunu kur. |
| [`gelistirici.md`](ajanlar/gelistirici.md) | Sonnet 5.5 | Tarif edilmiş kod değişiklikleri ve testler |
| [`arastirmaci.md`](ajanlar/arastirmaci.md) | Sonnet 5.5 | Kaynaklı araştırma; kod yazmaz |
| [`yukleyici.md`](ajanlar/yukleyici.md) | Haiku 5.5 | Mekanik toplu işler ve hafif denetim turları |
| [`tasarimci.md`](ajanlar/tasarimci.md) | Opus 5.5 | Görsel yargı gerektiren işler |
| [`video-ureticisi.md`](ajanlar/video-ureticisi.md) | Opus 5.5 | Video ve ses; ölçerek doğrular |

**Model basamakları:** Haiku 5.5 (en ucuz; mekanik iş + hafif denetim) · Sonnet 5.5 (orta; günlük iş gücü) · Opus 5.5 (yetenekli; şef, tasarım, riskli denetim) · Fable 5.1 (premium; en zor akıl yürütme, en pahalı). Fable 5.1 isteğe bağlıdır: en zor işler için ya da bütçe elverince orkestranın tamamını veya en zorlu rollerini ona çıkarmak için. Hafif denetim turları artık Haiku 5.5'e verilebilir; güvenlik, para ya da veri kaybı riski olan denetim Opus 5.5'te kalır.

Şefin kuralı için [`CLAUDE-orkestra-kurali.md`](ajanlar/CLAUDE-orkestra-kurali.md) içeriğini projendeki `CLAUDE.md` dosyasına ekle.

---


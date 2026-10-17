# Kırmızı Ajanlar · Rues Community Yapay Zekâ Notları #2

> **Kapıyı önce sen bul.** Zaten *yapan* yapay zekâ ajanların var. Birkaçını ters çevir ve kendi uygulamana saldırgan gibi bak: biri kimliğe bürünür, biri arayüzün güvendiği sınırları zorlar, biri dışarıdan bir yabancı gibi gelir. Bir orkestrator kanıtı toplar, sıralar; sonra **ayrı** bir tur düzeltir ve düzeltmenin tuttuğunu kanıtlar.

![Banner](gorseller/banner.svg)

> ⚠️ **Önce angajman kurallarını oku.** Bu yöntem ajanlara saldırgan gibi davranmalarını söyler. Bu yalnızca **sahibi olduğun ya da test etmeye açıkça (yazılı) yetkili olduğun** bir hedefte ve korumalar içinde yasal ve güvenlidir. İstisna yok.

**Dosya:** [`index.html`](index.html) — tek dosya, tarayıcıda doğrudan açılır. Açık ve koyu temayı destekler, telefonda da okunur.

## İçinde neler var

| Bölüm | Özet |
|---|---|
| Angajman kuralları | Ön uçuş kapısı, altı değişmez kural ve "hemen dur" koşulları; her şeye üstündür |
| Neden sürü, tek ajan değil? | Tek ajan bağlamı taşır, içeriden bilir, nazik dener; sürüde saldıran ajan düzelten ajan değildir |
| Kadro | Şef, Saldırgan A/B/C, Düzeltici: her biri için model, çaba, ne test eder, ne zaman durur |
| Hangi role hangi model | İki kadran — yetenek katmanı ve akıl yürütme çabası — ve role göre tablo |
| 9 grup, 38 sınıf | Bir saldırganın düşündüğü gibi gruplanmış zayıflık sınıfları, taranabilir rozetlerle |
| Bir tatbikatın yolculuğu | Yetki kapısından sorumlu açıklamaya 7 adım, ayrı düzeltici turuyla |
| Disiplin | Maskeli kanıt, kanıt defteri satırı ve düzelt → doğrula biçimi |
| Kendi tatbikatını kur | Kopyalanabilir ajan dosyaları, CLAUDE kuralı, ön uçuş kontrol listesi, sözlük |

![Hat](gorseller/flow.svg)

![9 grup, 38 sınıf](gorseller/groups.svg)

## Hazır ajan dosyaları

[`ajanlar/`](ajanlar) klasöründeki dosyaları kendi projende `.claude/agents/` altına kopyala (Claude Code). Orkestrator ana oturumdur (şef); diğerleri alt ajan olarak başlatılır.

| Dosya | Model · çaba | Rol |
|---|---|---|
| [`orkestrator.md`](ajanlar/orkestrator.md) | Şef (en güçlü) | Yetki kapısını tutar, işi dağıtır, bulguları toplar, triyaj yapar. Saldırmaz, düzeltmez. |
| [`kimlige-burun.md`](ajanlar/kimlige-burun.md) | Opus · yüksek | Ajan A — Grup 1: kimliğe bürünme ve yetki yükseltme (IDOR/BOLA, BFLA, oturum, MFA) |
| [`ui-sinirlari.md`](ajanlar/ui-sinirlari.md) | Opus · yüksek | Ajan B — Grup 2: UI'nin güvendiği sınırlar (kütle atama, iş mantığı, yarış koşulları) |
| [`disaridan.md`](ajanlar/disaridan.md) | Sonnet · orta | Ajan C — Grup 3–7: dışarıdan tarama (XSS, SSRF, CSRF, SSTI, güvenlik başlıkları…) |
| [`duzeltici.md`](ajanlar/duzeltici.md) | Opus | Grup 9: rapordan sonra koşan ayrı tur; kök nedeni düzeltir, düzeltmenin tuttuğunu kanıtlar |

Şefin kuralı için [`CLAUDE-tatbikat-kurali.md`](ajanlar/CLAUDE-tatbikat-kurali.md) içeriğini projendeki `CLAUDE.md` dosyasına ekle.

Saldırı sınıflarının teknik kısaltmaları (IDOR, BOLA, SSRF, XSS, CSRF, SSTI…) özgün hâliyle bırakıldı. Bu dosyalar, insanların **kendi** uygulamalarını test etmek için ajanlarına yapıştırdığı prompt'lardır.

---
[Telegram duyuru](https://t.me/RuesAnnouncement) · [Telegram](https://t.me/ruesandora) · [X @Ruesandora0](https://x.com/Ruesandora0)

Rues Community · Ekim 2026 · Yalnızca sahibi olduğun ya da test etmeye açıkça yetkili olduğun sistemler için.

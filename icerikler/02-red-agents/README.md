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
| 10 grup, 45 sınıf | Bir saldırganın düşündüğü gibi gruplanmış zayıflık sınıfları; yeni Grup 10: kendi LLM/yapay zekâ uygulaman |
| Sır, bağımlılık, oran sınırı, izleme | Git geçmişinde sır, tedarik zinciri, CI izinleri; giriş/OTP/pahalı uçlarda sınır; loglama eksikleri |
| Yapmayacaklarımız | Bu yöntemin asla yapmadığı şeyler: üçüncü taraf hedef, hazır istismar kodu, bulunan sırrı kullanma… |
| Bulgu raporu şablonu | Sabit alanlar ve bul → raporla → düzelt → yeniden test döngüsü |
| Alt ajan ve model dağılımı | Ajan alt ajan açar, alt ajan açamaz; iş başına en çok 4; keşif Haiku/Sonnet, doğrulama Sonnet, kritik son kontrol Opus |
| Bir tatbikatın yolculuğu | Yetki kapısından sorumlu açıklamaya 7 adım, ayrı düzeltici turuyla |
| Disiplin | Maskeli kanıt, kanıt defteri satırı ve düzelt → doğrula biçimi |
| Kendi tatbikatını kur | Kopyalanabilir ajan dosyaları, CLAUDE kuralı, ön uçuş kontrol listesi, sözlük |

![Hat](gorseller/flow.svg)

![İlk 9 grup, 38 sınıf (Grup 10 sayfada metinle anlatılır)](gorseller/groups.svg)

## Hazır ajan dosyaları

[`ajanlar/`](ajanlar) klasöründeki dosyaları kendi projende `.claude/agents/` altına kopyala (Claude Code). Orkestrator ana oturumdur (şef); diğerleri alt ajan olarak başlatılır.

| Dosya | Model · çaba | Rol |
|---|---|---|
| [`orkestrator.md`](ajanlar/orkestrator.md) | Şef (en güçlü) | Yetki kapısını tutar, işi dağıtır, bulguları toplar, triyaj yapar. Saldırmaz, düzeltmez. |
| [`kimlige-burun.md`](ajanlar/kimlige-burun.md) | Opus · yüksek | Ajan A — Grup 1: kimliğe bürünme ve yetki yükseltme (IDOR/BOLA, BFLA, oturum, MFA) |
| [`ui-sinirlari.md`](ajanlar/ui-sinirlari.md) | Opus · yüksek | Ajan B — Grup 2: UI'nin güvendiği sınırlar (kütle atama, iş mantığı, yarış koşulları) |
| [`disaridan.md`](ajanlar/disaridan.md) | Sonnet · orta | Ajan C — Grup 3–7: dışarıdan tarama (XSS, SSRF, CSRF, SSTI, güvenlik başlıkları…) |
| [`llm-uygulamalari.md`](ajanlar/llm-uygulamalari.md) | Sonnet · orta | Ajan D — Grup 10: prompt injection (doğrudan/dolaylı), araç yetkisi, sır sızıntısı, güvensiz çıktı, RAG zehirlenmesi, maliyet |
| [`sir-ve-bagimlilik.md`](ajanlar/sir-ve-bagimlilik.md) | Haiku · düşük | Git geçmişinde sır, `.env`, bağımlılık açıkları, kilit dosyası, CI/GitHub Actions izinleri (salt okunur) |
| [`oran-ve-izleme.md`](ajanlar/oran-ve-izleme.md) | Sonnet · orta | Giriş, şifre sıfırlama, OTP, pahalı uçlarda oran sınırı; loglama/izleme eksikleri |
| [`duzeltici.md`](ajanlar/duzeltici.md) | Opus | Grup 9: rapordan sonra koşan ayrı tur; kök nedeni düzeltir, düzeltmenin tuttuğunu kanıtlar |

Şefin kuralı için [`CLAUDE-tatbikat-kurali.md`](ajanlar/CLAUDE-tatbikat-kurali.md) içeriğini projendeki `CLAUDE.md` dosyasına ekle.

## Yapmayacaklarımız

- Sahibi olmadığın hedef yok; yazılı izin yoksa tek istek yok.
- Üretimde yıkıcı test, DoS, veri silme yok.
- Gerçek kullanıcı verisine dokunma yok; yalnız test hesabı.
- Bulunan sırrı kullanma yok: konumunu bildir, iptal ettir.
- Hazır saldırı yükü, istismar kodu, atlatma tarifi paylaşma yok.
- Üçüncü taraf servislere (model sağlayıcı, e-posta/SMS, ödeme, bulut) tarama yok.

## Bulgu raporu ve döngü

Her bulgu: başlık · etki · kanıt (sırlar `REDACTED`) · tekrar adımları (yalnız kendi ortamın) · önerilen düzeltme · düzeltme doğrulaması · önem (Kritik / Yüksek / Orta / Düşük). Döngü: **bul → raporla → ayrı tur düzelt → yeniden test**; düzeltme geri alınınca bulgu geri gelmeli. Şablon: [`orkestrator.md`](ajanlar/orkestrator.md).

## Alt ajan ve model

Ajan alt ajan açabilir, alt ajan açamaz (derinlik 1); iş başına en çok 4; `model:` her seferinde açık yazılır; yetki kapısı alt ajana aynen geçer. Keşif/tarama Haiku 5.5 ya da Sonnet 5.5, bulgu doğrulama Sonnet 5.5, kritik bulgunun son kontrolü Opus 5.5.

Saldırı sınıflarının teknik kısaltmaları (IDOR, BOLA, SSRF, XSS, CSRF, SSTI…) özgün hâliyle bırakıldı. Bu dosyalar, insanların **kendi** uygulamalarını test etmek için ajanlarına yapıştırdığı prompt'lardır.

---
[Telegram duyuru](https://t.me/RuesAnnouncement) · [Telegram](https://t.me/ruesandora) · [X @Ruesandora0](https://x.com/Ruesandora0)

Rues Community · Ekim 2026 · Yalnızca sahibi olduğun ya da test etmeye açıkça yetkili olduğun sistemler için.

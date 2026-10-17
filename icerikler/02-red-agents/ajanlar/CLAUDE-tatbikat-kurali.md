## Kırmızı-takım tatbikat kuralı
- Bu, **yalnızca sahibi olduğun ya da test etmeye açıkça
  yetkili olduğun** bir sistemin kendi-testidir. Yetki
  kapısı geçilmeden hiçbir istek gönderilmez.
- Sen orkestratörsün: işi rol ajanlarına dağıt, bulguları
  tek maskeli rapora topla, triyaj yap, sade dille raporla.
  **Kendin saldırmazsın ve kendin düzeltmezsin.**
- Saldıran ajan, düzelten ajan değildir; düzeltici ayrı bir
  turdur ve rapor oluştuktan sonra koşar.
- Model: mekanik toplama haiku; dışarıdan tarama (Grup 3–7)
  sonnet; kimliğe bürünme ve iş-mantığı zincirleri (Grup 1–2)
  en güçlü model + yüksek çaba. Kredin varsa en üst katmanı
  premium modelde (Fable) tut.
- Yalnızca `yerel` ya da `staging-tek-kullanımlık-db`. Canlı
  yalnızca imzalı onay + değişiklik penceresiyle, okuma ağırlıklı.
- Yalnızca test hesabı ve test verisi; gerçek kullanıcı
  verisine dokunulmaz.
- Her sır (token, çerez, anahtar, kart, PII) göründüğü an
  REDACTED; canlı sır asla yapıştırılmaz, commit'lenmez.
- Kanıtla, istismar etme: asgari kanıt, sonra dur. DoS yok;
  hız/brute testi onlarca istekle kanıtlanır ve durur.
- Bir korumayı yalnızca yerel kopyada, geçici kapat; asla
  commit'leme, paylaşılan/canlı ortamı asla zayıflatma.
- Bir istek kapsamdan çıkacaksa dur ve sor.

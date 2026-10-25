## Orkestra kuralı
- Sen şefsin: işi böl, brif yaz, ajan ve model
  seç, denetçiye kontrol ettir, birleştir, sade
  dille raporla.
- Kod, tasarım ya da metni kendin üretme; kendi
  işini kendin onaylama.
- Model (varsayılan sonnet): haiku mekanik iş ve
  basit okuma, özet, sınıflama, format; sonnet kod,
  araştırma, normal denetim, metin; opus görsel
  tasarım yönü ve güvenlik, para, veri kaybı riski
  olan denetim; fable (pahalı, nadir) çok adımlı
  belirsiz karar, çelişkili bulguların sentezi, zor
  hata ayıklama: derin-akil ajanı. Genel amaçlı
  ajana modeli açıkça ver. Haiku bir işe yeter mi,
  kendi işinde ölçerek gör. Bedrock/Vertex'te
  "sonnet" takma adı başka (eski) sürüme çözülebilir;
  tam model kimliği yaz.
- Alt ajan: ajan kendi alt ajanını açabilir (tools
  listesinde Agent), alt ajan açamaz. İş başına en
  çok 4; her birine model açıkça verilir. Ajan alt
  ajan sonuçlarını kendisi birleştirir, bana tek
  rapor verir. Belgedeki sınır: ana oturumun altında
  en çok 3 katman; CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH
  ortam değişkeni derinliği ayarlar (1 = kapalı).
- Ajan dosyasında effort: low, medium, high, xhigh
  ya da max yazılabilir (modele göre değişir).
- Dosya değiştiren her ajan ayrı çalışma
  kopyasında (worktree) ve kendi dalında
  çalışır, sık kaydeder.
- Ana dala yalnızca sen, testler geçtikten sonra,
  merge --no-ff ile birleştirirsin.
- DÜZELT en fazla 3 tur; sonra bana sor.
- Her brif ve raporda dört komşu: kim kullanıyor,
  ikizi nerede, karşı parça (yaz/oku, aç/kapa)
  güncellendi mi, sessiz hata başarı gibi görünüyor
  mu? Düzeltilmeyen komşu raporda "bakiye" olur.
- Ajanın "testler yeşil" sözü kanıt sayılmaz;
  birleştirmeden önce testleri sen yeniden koşarsın.
- Çalışamıyorsan söyle: depo, erişim ya da veri
  yoksa iş "başarılı" diye bitmez. Zamanlanmış görev
  her çalıştırmada yeni oturum açar, kendini kurar.
- Küçük iş: denetçi yok, diff'e sen bak.
  Orta: 1 ajan + denetçi. Büyük: paralel ajanlar.
- Workflow yalnızca ben "workflow kullan" dersem.

## Orkestra kuralı
- Sen şefsin: işi böl, brif yaz, ajan ve model
  seç, denetçiye kontrol ettir, birleştir, sade
  dille raporla.
- Bana cevap en çok 5 satır: ne oldu, ne yapacaksın,
  benden ne lazım. Ayrıntı dosyaya. Ayar tarifinde
  menü anlatma; doğrudan sayfa linki + son adım.
  Karar sorusu: "A: …, B: …, Önerim A."
- Konuştuğumuz iş, ben "boşver" demedikçe
  bırakılmaz; bekleyenleri devir dosyasındaki
  "Açık işler" listesinde tut, oturum bitmeden
  güncelle.
- Kod, tasarım ya da metni kendin üretme; kendi
  işini kendin onaylama.
- Model (varsayılan sonnet): haiku mekanik iş ve
  basit okuma, özet, sınıflama, format; sonnet kod,
  araştırma, normal denetim, metin; opus yalnız
  görsel tasarım yönü ve güvenlik, para, veri kaybı
  riski olan denetim; fable (pahalı, nadir) çok
  adımlı belirsiz karar, çelişkili bulguların
  sentezi, zor hata ayıklama: derin-akil ajanı.
  Ajan dosyasındaki modeli üstüne yazma. Genel
  amaçlı ajana modeli açıkça ver. Kredi tasarrufu
  yalnız ben söylersem. Bedrock/Vertex'te "sonnet"
  takma adı başka (eski) sürüme çözülebilir; tam
  model kimliği yaz.
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
- Ana dala yalnızca sen, testler ve denetim
  geçtikten sonra, merge --no-ff ile birleştirirsin
  (önce fetch + merge). ONAY gelmeden birleştirme yok.
- Denetçi bir kez bakar. DÜZELT en fazla 3 tur;
  sonra bana sor. Yeşil test kanıt değil: düzeltme
  geri alınınca test kırılmalı.
- Düşen tarayıcı testini tek başına yeniden koş;
  tek başına da düşüyorsa hata gerçektir.
- Ücretsiz katmanı olan her kaynakta kodla zorlanan
  sert sınır: ücretsiz limitin en çok %99'u. Sınıra
  gelince dur, bana bildir; ücretliye taşma.
- Yasak komutlar (force push, reset --hard, rebase,
  clean -fd, stash, rm -rf /, pkill -f, killall, .env
  okuma) araç izin ayarında da engelli olsun.
- Küçük iş: denetçi yok, diff'e sen bak.
  Orta: 1 ajan + denetçi. Büyük: paralel ajanlar.
- Workflow yalnızca ben "workflow kullan" dersem.

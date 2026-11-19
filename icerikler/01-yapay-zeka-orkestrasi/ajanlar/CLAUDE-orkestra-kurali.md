## Orkestra kuralı
- Sen şefsin: işi böl, brif yaz, ajan ve model
  seç, gerektiğinde denetçiye kontrol ettir, birleştir,
  sade dille raporla.
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
  riski olan denetim. En güçlü model iş yürütmez,
  yalnız danışmandır (aşağıdaki Danışman maddesi).
  Ajan dosyasındaki modeli üstüne yazma. Genel
  amaçlı ajana modeli açıkça ver. Kredi tasarrufu
  yalnız ben söylersem. Bedrock/Vertex'te "sonnet"
  takma adı başka (eski) sürüme çözülebilir; tam
  model kimliği yaz.
- Danışman: en güçlü model yalnız danışır, dosya
  yazmaz. Danışman, işi yürüten modelden zayıf olamaz;
  şefi en güçlü modelde çalıştırırsan danışacak kimse
  kalmaz, o yüzden şef bir alt modelde olur. En az
  biri varsa sorulur: belirsiz mimari ya da strateji
  kararı kilitlenmeden önce (iş büyük ya da riskliyse);
  aynı hata ya da komut 3 kez tekrarlandı; ajan
  bulguları çelişiyor; riskli işte "bitti" demeden
  önce, tek sefer. Sorulmaz: küçük ve orta rutin iş,
  taslak, mekanik iş, denetçi görevi, "emin olmak
  için". Soru en çok 8 satır (karar, A/B ve bedeli,
  bildiklerin, denediğin); cevap en çok 120 kelime.
  İş başına en çok 2, oturum başına en çok 6 soru;
  ikinci soru ilkine aykırı yeni bir bulguyla gelir.
- Alt ajan: ajan kendi alt ajanını açabilir (tools
  listesinde Agent), alt ajan açamaz. İş başına en
  çok 4; her birine model açıkça verilir. Küçük işte
  alt ajan açma: her biri soğuk başlar. Ajan alt
  ajan sonuçlarını kendisi birleştirir, bana tek
  rapor verir. Belgedeki sınır: ana oturumun altında
  en çok 3 katman; CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH
  ortam değişkeni derinliği ayarlar (1 = kapalı).
- Ajan dosyasında effort: low, medium, high, xhigh
  ya da max yazılabilir (modele göre değişir).
- Dosya değiştiren her ajan ayrı çalışma
  kopyasında (worktree) ve kendi dalında
  çalışır, sık kaydeder.
- Doğrulama ortam × risk ile ölçülür; hücrenin
  istediği yapılır, fazlası yapılmaz. Ortam: E1 taslak
  ya da test (canlıya etkisi yok), E2 canlıya gidecek,
  E3 canlı. Risk: R1 görünür taslak ya da içerik, R2
  sıradan kod, R3 para, sır, veri kaybı, yetki.
  - E1: ilgili test 1 kez. R1 ve R2'de denetçi yok,
    diff'e sen bak. R3'te Sonnet denetçi, 1 tam + kısmi tur.
  - E2: ilgili test + tam takım 1 kez (sen, birleşik
    kodda). R2'de Sonnet denetçi; R3'te Opus denetçi,
    en çok 3 tur, canlıya açmak benim onayımla.
  - E3: yalnız canlı doğrulama (sayfayı çek, ilgili
    satıra bak); test yeniden koşulmaz.
  Ben "tam test" ya da "tam denetim" dersem tam tur.
- Ana dala yalnızca sen, bu hücre tamamlanınca,
  merge --no-ff ile birleştirirsin (önce fetch +
  merge). Denetçi istenen işte ONAY gelmeden
  birleştirme yok.
- Aynı test aynı kodda iki kez koşulmaz. Ajan
  raporuna komut + kodun ağaç kısa kodunu (git
  rev-parse --short HEAD^{tree}) + sonucu yazar.
  Aynı ağaç kodunu görürsen yeniden koşma; farklıysa
  yalnız ilgili testi bir kez koş. Birleştirmede yalnız
  iki dalın ortak değiştirdiği dosyanın testi koşulur.
- Denetçi bir kez bakar. DÜZELT'ten sonra 2. tur
  yalnız önceki engellerin kapandığına bakar. En çok
  2 tur (E2-R3'te 3); sonra bana sor.
- Mutasyon kontrolü (düzeltme geri alınınca yeni test
  kırılmalı) yalnız hata düzeltmesinde ve R3'te;
  taslakta ve sıradan yeni özellikte aranmaz.
- Düşen testi tek başına bir kez koş. Tek başına da
  düşüyorsa hata gerçektir; geçiyorsa kararsız testtir,
  listeye yaz, tekrar tekrar koşma.
- Ücretsiz katmanı olan her kaynakta kodla zorlanan
  sert sınır: ücretsiz limitin en çok %99'u. Sınıra
  gelince dur, bana bildir; ücretliye taşma.
- Yasak komutlar (force push, reset --hard, rebase,
  clean -fd, stash, rm -rf /, pkill -f, killall, .env
  okuma) araç izin ayarında da engelli olsun.
- Her brif ve raporda dört komşu: kim kullanıyor,
  ikizi nerede, karşı parça (yaz/oku, aç/kapa)
  güncellendi mi, sessiz hata başarı gibi görünüyor
  mu? Düzeltilmeyen komşu raporda "bakiye" olur.
- Çalışamıyorsan söyle: depo, erişim ya da veri
  yoksa iş "başarılı" diye bitmez. Zamanlanmış görev
  her çalıştırmada yeni oturum açar, kendini kurar.
- Maliyet: oturumun modelini başta seç, iş ortasında
  değiştirme (önbellek bozulur). Test çıktısını
  kısalt (| tail -n 100). Bu dosyayı kısa tut.
- Küçük iş (tek dosya, ~30 satırdan az): denetçi yok,
  diff'e sen bak. Orta, E1 ya da R1/R2: 1 ajan,
  denetçi yok. Orta, E2 ya da R3: 1 ajan + denetçi.
  Büyük: paralel ajanlar.
- Workflow yalnızca ben "workflow kullan" dersem.

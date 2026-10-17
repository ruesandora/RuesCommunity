# Herhangi bir yapay zekâya yapıştır

Aşağıdaki bloğu kullandığın aracın sohbetine (ya da ajan
modunda) yapıştır. Araç kendi modellerine göre eşleme
çıkarır; bilmediğini uydurmaz.

```text
Sana bir "yapay zekâ orkestrası" düzeni vereceğim. Bunu benim
kullandığım araca uyarla.

1. Kullandığın araç ve sürümün nedir? Hangi modellere erişimin
   var? Model adlarını yalnızca bildiğin ya da araçtan okuyabildiğin
   gibi yaz; bilmediğin adı uydurma, "bilmiyorum" de.
2. Modelleri üç katmana ayır: UCUZ, ORTA, GÜÇLÜ (varsa dördüncü:
   EN GÜÇLÜ, pahalı ve nadir). Bir tablo yap: katman, bu araçtaki
   model adı, düşünme/çaba ayarı (varsa), hangi iş.
3. İş dağılımı:
   - UCUZ: mekanik iş, basit okuma, özet, sınıflama, format.
   - ORTA (varsayılan): kod, araştırma, normal denetim, metin.
   - GÜÇLÜ: görsel tasarım yönü, güvenlik/para/veri kaybı riski olan denetim.
   - EN GÜÇLÜ: çok adımlı belirsiz karar, çelişkili bulguların sentezi, zor hata ayıklama.
4. Roller: şef (işi böler, birleştirir, kendi işini onaylamaz),
   geliştirici, araştırmacı, bağımsız denetçi (dosya değiştirmez,
   ONAY ya da DUZELT döner). Aracın ajan/alt ajan dosya biçimini
   ve konumunu söyle; emin değilsen resmi belgesine bak de.
5. Alt ajan kuralı: ajan kendi alt ajanını açabilir, alt ajan
   açamaz; iş başına en çok 4; her alt ajana model açıkça verilir;
   ajan sonuçları birleştirip şefe tek rapor verir. Aracın bunu
   destekleyip desteklemediğini ve derinlik sınırını söyle.
6. Ortak kurallar: dosya değiştiren ajan ayrı dalda çalışır;
   ana dala yalnız şef, testler geçince birleştirir; DUZELT en
   fazla 3 tur; stash, reset --hard, rebase, push --force yok;
   sır dosyaya yazılmaz.
7. Çıktı: (a) eşleme tablosu, (b) araca konacak dosyalar ve
   yolları, (c) bu araçta yapamadıkların ve doğrulayamadıkların.
   Yapamadığın şeyi yapmış gibi gösterme.
```

Sonra çıkan tabloyu kendi işinde ölçerek dene: ucuz katman bir
işe yetiyor mu, test geçiyor mu?

# Bilgi Paneli

### [⬇️ İndir (BilgiPaneli.zip)](https://github.com/Abrahamexe/bilgi-paneli-raporlar/raw/main/BilgiPaneli.zip) · [Kurulum](#kurulum) · [Kullanım](#kullanım) · [Rapor gönder](#rapor-nasıl-gönderilir) · [Gönderilen raporlar](../../issues)

Sürüm: **v0.2.0** (test sürümü)

Bilgi Paneli, Windows görev çubuğunun sağında (sistem tepsisinde) duran küçük bir uygulama. İkona tıklayınca bağlı fare, klavye ve kulaklıkların **adını, pil yüzdesini, şarj durumunu ve kaç Hz'de çalıştığını** tek pencerede gösterir. Her cihazın kendi yazılımını açmaya gerek kalmaz.

- Arka planda neredeyse hiç kaynak kullanmaz: boştayken ~2 MB RAM, %0 CPU.
- Cihazlara sadece **okuma** komutları gönderir. Hiçbir cihaz ayarını değiştirmez.

Her markanın pil ve Hz bilgisi farklı bir protokolle okunuyor. Desteği büyütmek için **sizin raporlarınıza** ihtiyacımız var. Bu repo, uygulamanın indirme yeri ve cihaz raporlarının toplandığı yer.

---

## Kurulum

Kurulum programı yok. Uygulama tek bir dosya.

1. Bu sayfanın en üstündeki **⬇️ İndir** linkine tıklayın. `BilgiPaneli.zip` iner.
2. İnen zip dosyasına **sağ tıklayın → Tümünü ayıkla → Ayıkla**.
3. Açılan klasörde **`bilgi-paneli.exe`**'ye çift tıklayın.
4. Mavi bir **"Windows kişisel bilgisayarınızı korudu"** uyarısı çıkarsa:
   1. **Ek bilgi**'ye tıklayın.
   2. **Yine de çalıştır**'a tıklayın.

   Uygulama imzasız olduğu için bu uyarı normal. Bir kez sorulur.
5. Görev çubuğunun sağında, saatin yanında **Bilgi Paneli ikonu** belirir. İkon görünmüyorsa saatin yanındaki **˄** okuna tıklayın; ikonu görev çubuğuna sürükleyerek sabitleyebilirsiniz.

Uygulama bundan sonra **bilgisayar her açıldığında kendiliğinden başlar**. İstemezseniz ikona sağ tıklayıp **Windows ile başlat** işaretini kaldırın.

Klasörü daha sonra taşırsanız `bilgi-paneli.exe`'yi yeni yerinden bir kez çalıştırın.

### Güncelleme

Yeni sürüm çıkınca:

1. İkona sağ tıklayıp **Çıkış**'ı seçin.
2. Yeni `BilgiPaneli.zip`'i indirip eski klasörün üzerine ayıklayın (dosyaların değiştirilmesini onaylayın).
3. `bilgi-paneli.exe`'yi çalıştırın.

Ayarlarınız ve GitHub girişiniz korunur.

### Kaldırma

1. İkona sağ tıklayıp **Windows ile başlat** işaretini kaldırın.
2. **Çıkış**'ı seçin.
3. Klasörü silin.

---

## Kullanım

### Paneli açma

Görev çubuğundaki ikona **sol tıklayın**. Panel açılır:

| Ne görürsünüz | Anlamı |
|---|---|
| Ad | Cihazın adı. Dongle'lı cihazlarda mümkünse gerçek model adı. |
| Alt satır | Bağlantı: **Dongle**, **Kablolu** veya **Bluetooth**. Şarjdaysa **şarj oluyor**. |
| Pil çubuğu ve % | Pil yüzdesi. Yeşil: %40 üstü, sarı: %16–40, kırmızı: %15 ve altı. **⚡** şarj oluyor demek. |
| Hz | Cihazın çalıştığı polling rate. |
| — | Bu bilgi bu cihazdan okunamıyor (henüz desteklenmiyor veya cihazda yok). |
| uykuda (12 dk önce) | Cihaz şu an cevap vermiyor; son okunan değer gösteriliyor. |

Panel dışına tıklayınca veya **Esc**'ye basınca kapanır. Panel açılınca değerler hemen yenilenir. Panel kapalıyken uygulama 10 dakikada bir okur.

### Sağ tık menüsü

| Menü | Ne yapar |
|---|---|
| Yenile | Cihazları hemen yeniden okur. |
| **Rapor → Rapor gönder** | Cihaz raporunu hazırlar ve doğrudan bu repoya gönderir. |
| Rapor → Raporu sadece kaydet | Raporu masaüstüne kaydeder (GitHub hesabı olmayanlar için). |
| Rapor → Rapor nasıl gönderilir? | Bu sayfayı açar. |
| Rapor → Çıkış yap (GitHub) | Kayıtlı GitHub girişini siler. |
| Test bildirimleri | Test listesindeki bir cihaz takılınca bildirim gösterir. |
| Ayarlar | Ayar dosyasını açar (aşağıda). |
| Windows ile başlat | Açılışta otomatik başlatmayı açar/kapatır. |
| Çıkış | Uygulamayı kapatır. |

### Ayarlar

**Ayarlar** menüsü `config.toml` dosyasını Not Defteri'nde açar. Burada:

- Cihaza kendi isminizi verebilirsiniz.
- Görmek istemediğiniz cihazları gizleyebilirsiniz.
- Cihazların sırasını değiştirebilirsiniz.
- Arka plandaki okuma sıklığını değiştirebilirsiniz (`refresh_minutes`; `0` = sadece panel açılınca oku).

Dosyanın içinde açıklamalar ve bağlı cihazlarınızın kimlikleri yazılı. Kaydedip kapatın; değişiklik bir sonraki yenilemede uygulanır.

---

## Rapor nasıl gönderilir?

Raporunuz, cihazınızın desteğini eklemek veya düzeltmek için kullanılır. Rapor göndermek için ücretsiz bir **GitHub hesabı** gerekir ([buradan açılır](https://github.com/signup)). Hesabınız yoksa bkz. [Hesabım yok](#hesabım-yok).

1. **Raporu başlatın.** İki yol var:
   - Test listesindeki bir cihazı taktığınızda **"Test listesindeki cihaz bulundu"** bildirimi çıkar. Bildirime tıklayın.
   - Ya da ikona sağ tıklayıp **Rapor → Rapor gönder**'i seçin.
2. **Cihazı seçin.** Açılan pencerede raporlamak istediğiniz cihazı seçin. Cihazı açık tutun ve biraz kullanın (fareyi oynatın); rapor 10 saniye kadar hazırlanır.
3. **Üretici yazılımındaki değerleri yazın.** Cihazın kendi programında (G Hub, Synapse, web sürücüsü vb.) görünen:
   - Pil yüzdesi
   - Şarj oluyor mu?
   - Hz (polling rate)

   **Bu değerler en önemli kısım.** Uygulamanın doğru okuyup okumadığını bunlarla karşılaştırıyoruz.
4. **Gönder**'e basın.
5. **Sadece ilk gönderimde** GitHub'a bağlanmanız gerekir:
   1. Pencerede `ABCD-1234` gibi 8 haneli bir kod çıkar. Kod panoya da kopyalanır.
   2. Tarayıcıda `github.com/login/device` sayfası açılır. GitHub hesabınızla giriş yapın.
   3. Kodu yapıştırın (Ctrl+V) ve **Continue**'ya, sonra **Authorize bilgi-paneli-rapor**'a basın.
   4. Uygulamaya dönün; gönderim kendiliğinden devam eder.
6. **"Gönderildi! Teşekkürler."** yazısını görünce bitti. **Raporu aç** ile gönderdiğiniz raporu görebilirsiniz.

Sonraki raporlarda kod sorulmaz; **Gönder**'e basmanız yeterli.

**İpucu:** Gönder'den önce **Raporu göster** ile raporun içeriğini görebilirsiniz.

Uygulamanın GitHub yetkisi **sadece bu repoda rapor açmakla** sınırlıdır. Diğer repolarınıza veya hesabınıza erişemez. Yetkiyi istediğiniz zaman kaldırabilirsiniz: GitHub → Settings → Applications → Authorized GitHub Apps → bilgi-paneli-rapor → Revoke.

### Aynı cihazdan birden fazla rapor

Aynı cihazdan **iki farklı pil seviyesinde** (örn. %80 ve %60) ve **iki farklı Hz'de** rapor göndermek protokolü çözmeyi çok hızlandırır. Hz'i sadece üretici yazılımında değiştirin.

### Hesabım yok

1. İkona sağ tıklayıp **Rapor → Raporu sadece kaydet**'i seçin.
2. Rapor masaüstüne `BilgiPaneli-rapor-....md` olarak kaydedilir.
3. Dosyayı Discord'daki rapor kanalına atın. Üretici yazılımındaki pil yüzdesini, şarj durumunu ve Hz'i mesaja yazın.

### Bir sorun mu var?

| Sorun | Çözüm |
|---|---|
| İkon görünmüyor | Saatin yanındaki **˄** okuna tıklayın. Yoksa `bilgi-paneli.exe`'yi tekrar çalıştırın. |
| Cihazım listede yok | Cihazı çıkarıp takın, sonra **Yenile**. Hâlâ yoksa rapor gönderin. |
| Pil veya Hz "—" | Bu cihaz henüz desteklenmiyor. Rapor gönderin. |
| Değer üretici yazılımından farklı | Rapor gönderin; pencereye doğru değerleri yazın. |
| "GitHub uygulaması bu repoya kurulmamış" | Bizim tarafta bir sorun var. Raporu kaydedip Discord'a atın. |
| Antivirüs uyarısı | Uygulama imzasız olduğu için bazı antivirüsler yanlış alarm verebilir. |

---

## Raporda neler var? (gizlilik)

Göndermeden önce **Raporu göster** ile içeriğini görebilirsiniz. Raporda şunlar bulunur:

- Cihazın üretici ve ürün kimlikleri (VID/PID), ürün adı.
- Cihazın HID ve USB tanımlayıcıları.
- Uygulamanın cihazla alıp verdiği komutların bayt dökümü.
- Cihazın kendiliğinden gönderdiği verilerin 5 saniyelik kaydı (sadece üreticiye özel kanallar).
- Windows sürüm numarası ve uygulama sürümü.

Raporda **bulunmayanlar**:

- Seri numaraları, Bluetooth MAC adresleri: anonimleştirilir (geri çevrilemez kısa bir koda dönüştürülür).
- Bluetooth cihaz adları ("Ahmet'in AirPods'u" gibi): ürün adıyla değiştirilir.
- Kullanıcı adınız, bilgisayar adınız, dosya yolları.
- Klavyede yazdıklarınız. Normal tuş ve fare verileri kaydedilmez.

---

## Aradığımız cihazlar

### Grup 1 — Protokolü hiç bilinmeyenler

Bu cihazların raporu çok değerli. Mümkünse [USB kaydı](#usb-kaydı-ileri-seviye) da ekleyin.

| Tür | Cihazlar |
|---|---|
| Fare | WLMouse Beast X 4K, Endgame Gear OP1 8K, Darmoshark (kablosuz), Roccat / Turtle Beach Kone Air, Burst Pro Air, Incott |
| Klavye | Luminkey (kablosuz), Razer BlackWidow V4 Pro, Razer DeathStalker V2 Pro, SteelSeries Apex Pro wireless, HyperX Alloy Rise 75, Feker, Lofree, Ducky, Varmilo (kablosuz), Keychron 2.4 GHz dongle'lı modeller |
| Kulaklık | Razer BlackShark V2 Pro, Razer Barracuda / Kaira / Nari, Turtle Beach Stealth, ASUS ROG Delta, JBL Quantum, Cooler Master kablosuz, Logitech G PRO X 3 / G522 |

### Grup 2 — Doğrulanması gerekenler

Bu cihazlar için normal rapor yeterli.

| Tür | Cihazlar | Özellikle kontrol edilecek |
|---|---|---|
| Fare | Lamzu Atlantis | 2K / 4K / 8K Hz doğru mu? |
| Fare | Pulsar Pro serisi, X3, Xlite v4 | Pil ve Hz |
| Fare | WLMouse Beast X, Beast Miao, Strider | Pil, Hz, model adı |
| Fare | VXE, ATK, VGN, Scyrox, Attack Shark | Pil ve Hz |
| Fare | Vaxee, Finalmouse ULX / SLX, Rapoo VT9 | Pil ve Hz |
| Fare | Logitech (Lightspeed / Bolt) | Ad, pil, Hz |
| Fare | HyperX Haste 2 Wireless, ASUS ROG Harpe / Keris, Glorious Model O / D Wireless | Pil, şarj, Hz |
| Klavye | Akko, MonsGeek, Epomaker, Womier (dongle ile) | Pil ve 8K Hz |
| Klavye | NuPhy, AULA F87 Pro, PMO Wave 75, MCHOSE, Keychron 8K | Pil ve Hz |
| Kulaklık | Logitech G PRO X 2, SteelSeries Arctis Nova 7, HyperX Cloud Alpha Wireless | Pil ve şarj |

Listede olmayan cihazların raporu da işe yarar. Uygulama tanımadığı her cihaz için de bildirim gösterir.

**İpucu:** Aynı cihazdan **iki farklı pil seviyesinde** (örn. %80 ve %60) ve **iki farklı Hz'de** rapor göndermek protokolü çözmeyi çok hızlandırır.

---

## USB kaydı (ileri seviye)

Sadece Grup 1 cihazlar için gerekir.

### Cihaz web sürücüsü kullanıyorsa

Bazı markalar ayarları tarayıcıdan yapıyor (örn. hub.atk.store). Bu durumda Wireshark gerekmez. Raporun notlar kısmına web sürücüsünün tam adresini yazın. Protokolü sayfanın kodundan çıkarırız.

### Cihaz masaüstü yazılımı kullanıyorsa

1. [Wireshark](https://www.wireshark.org/download.html)'ı kurun. Kurulumda **USBPcap** seçeneğini işaretleyin. Ardından bilgisayarı yeniden başlatın.
2. Wireshark'ta `USBPcap1`, `USBPcap2`... arasından cihazın bağlı olduğunu seçin. Emin değilseniz fareyi oynatın: paket sayısı artan doğrudur.
3. Kaydı başlatın.
4. Üretici yazılımını açın, pil ekranına gidin. **Saati ve pil yüzdesini not edin.**
5. Hz'i sırayla değiştirin: **1000 → 500 → 1000**. Her değişikliğin saatini not edin.
6. Kaydı durdurun ve **File → Save As** ile `.pcapng` olarak kaydedin.
7. Dosyayı zip'leyin ve gönderdiğiniz rapor issue'suna yorum olarak ekleyin (en fazla 25 MB). Notlarınızı da yazın.

Kayıt sırasında klavyede bir şey yazmayın. Tuş vuruşları da USB trafiğine girer.

---

## Önemli uyarılar

- Hz ve diğer ayarları **sadece üretici yazılımında** değiştirin.
- `probe.exe send` komutunu **kullanmayın**. Cihaza doğrudan komut gönderir; yanlış bayt cihaz ayarlarını bozabilir.
- `probe.exe list`, `probe.exe dump` ve `probe.exe report` sadece bilgi okur, güvenlidir.

# Modül 16: Application Layer Services — Uygulama Katmanı Servisleri

## 📌 Modül Genel Bakış

Bu modülde internet üzerindeki temel iletişimi mümkün kılan **uygulama katmanı servislerini** ve protokollerini ele alıyoruz. Temel mantık: bilgisayarınızda olmayan bir şeyi almak istediğinizde siz **client**, karşı taraf **server** olur ve protokoller devreye girer.

**Modül Hedefi:** Yaygın uygulama katmanı servislerinin işlevini açıklayabilmek.

---

## 🏥 Giriş Senaryosu — Neden Önemli?

Bir hastanede çalışan Kishori, hasta dosyasına erişmek istiyor. Bunu defalarca yaptı ama hiç düşünmedi:

- Bu elektronik belge **nereden geliyor?**
- Hastane intranet'ine **nasıl bağlanıyor?**
- İnternete **nasıl erişiyor?**

Tüm bunları mümkün kılan şey **uygulama katmanı servisleridir**.

---

## 📚 Modülde Öğrenilen Konular

1. Client ve server'ın nasıl etkileşime girdiği
2. Yaygın network uygulamalarının nasıl çalıştığı
3. DNS'in ne işe yaradığı
4. HTTP ve HTML'in web'i nasıl çalıştırdığı
5. FTP ile dosya transferi
6. Telnet ve SSH ile sanal terminal bağlantıları
7. E-posta protokolleri: SMTP, POP ve IMAP

---

## 1️⃣ Client–Server Etkileşimi

**Server:** Ağa bağlı diğer cihazlara bilgi veya servis sağlayan yazılımı çalıştıran host'tur. Milyonlarca server internete bağlı: web siteleri, e-posta, finansal işlemler, müzik indirme...

**Client:** Chrome, Firefox gibi web tarayıcıları. Tek bir bilgisayar aynı anda birden fazla client yazılımı çalıştırabilir — e-postanızı açarken web'e bakabilir, mesajlaşabilir, müzik dinleyebilirsiniz.

> Tüm bunların çalışabilmesi için ortak bir dil konuşmaları gerekir: **üzerinde anlaşılmış standartlar ve protokoller.**

### Temel Server Türleri

| Server Türü | Açıklama |
|-------------|----------|
| **Email Server** | Outlook gibi mail client'lar bu sunucular üzerinden e-postaya erişir |
| **Web Server** | Chrome veya Firefox gibi tarayıcılar web sayfalarına bu sunuculardan erişir |
| **File Server** | Şirket dosyaları merkezi tutulur; Windows File Explorer gibi araçlarla erişilir |

---

## 2️⃣ Web Client–Server IP Etkileşimi

Bir web sayfası açıldığında arka planda şu adımlar gerçekleşir:

```
URL → DNS Lookup → IP Adresi Öğren → TCP Bağlantısı Kur → HTTP İsteği → Sayfa Gelir
```

### Adım Adım Senaryo (`www.learnip.com` örneği)

1. **DNS Lookup:** Sistem DNS sunucusuna `www.learnip.com`'un IP adresini sorar → `172.16.10.50` döner
2. **TCP Bağlantısı:** Client (`192.168.10.15:5507`) ile Server (`172.16.10.50:80`) arasında bağlantı kurulur
3. **Socket Oluşur:** Kaynak IP:port + Hedef IP:port kombinasyonu o konuşmayı benzersiz tanımlar; router'lar ve firewall'lar bu bilgiyi okur
4. **İstek & Yanıt:** Server gelen paketi port 80'den alır, web sayfasını hazırlar ve geri gönderir

---

## 3️⃣ URI, URN ve URL

**URI (Uniform Resource Identifier):** Bir ağ kaynağını tanımlayan karakter dizisi. İki alt türü vardır:

| Kavram | Açıklama | Soru |
|--------|----------|------|
| **URN** (Uniform Resource Name) | Kaynağın adını tanımlar, protokol referansı içermez | "Bu kaynak nedir?" |
| **URL** (Uniform Resource Locator) | Kaynağın ağdaki konumunu tanımlar | "Bu kaynağa nasıl ulaşırım?" |

### URL Anatomisi

```
https://www.example.com/author/book.html#page155
│       │               │                │
│       │               │                └── Fragment: sayfa içi konum
│       │               └─────────────────── Path & File: dosya yolu
│       └─────────────────────────────────── Hostname: sunucu adresi
└─────────────────────────────────────────── Protocol/Scheme: kullanılan protokol
```

---

## 4️⃣ Yaygın Network Uygulama Servisleri

| Protokol | Port | İşlev |
|----------|------|-------|
| **DNS** | 53 | Alan adlarını IP adreslerine çevirir |
| **DHCP** | 67/68 | Cihazlara otomatik IP adresi ve ağ yapılandırması atar |
| **HTTP** | 80 | Web sayfalarını istemek ve iletmek için kullanılır |
| **HTTPS** | 443 | Şifrelenmiş güvenli web iletişimi |
| **FTP** | 20/21 | Sistemler arasında dosya transferi |
| **SSH** | 22 | Sunuculara güvenli uzaktan erişim |
| **SMTP** | 25 | E-posta gönderme |
| **POP3** | 110 | E-posta indirme (sunucudan siler) |
| **IMAP4** | 143 | E-postaya sunucu üzerinden erişim (sunucuda kalır) |

---

## 5️⃣ DNS (Domain Name System)

DNS'in görevi çok basit ama kritik: **bir domain adını IP adresiyle eşleştirmek.**

> DNS olmadan her web sitesini sadece IP adresiyle hatırlamak zorunda kalırdık.

### DNS Çalışma Süreci

```
1. Kullanıcı → browser'a "www.cisco.com" yazar
2. Sistem    → DNS sunucusuna IP adresini sorar
3. DNS       → "www.cisco.com = 104.x.x.x" döner
4. Host      → bu IP adresini kullanarak web sunucusuna bağlanır
5. Web sayfası indirilir
```

### Test Komutu

```bash
nslookup www.cisco.com   # Windows ve Linux'ta çalışır
```

---

## 6️⃣ HTTP ve HTML

- **HTTP (Hypertext Transfer Protocol):** Bilginin client ile web server arasında nasıl iletileceğini yöneten kurallar bütünü
- **HTML (Hypertext Markup Language):** Web sayfasının içeriğini oluşturan kod

### Web Sayfası Yükleme Süreci

```
1. DNS lookup → domain adı IP'ye çevrilir
2. HTTP isteği → web server'a gönderilir
3. Server → HTML kodunu HTTP ile geri gönderir
4. Browser → HTML'i yorumlar ve sayfayı ekranda gösterir
```

> ⚠️ **Güvenlik Uyarısı:** HTTP şifreleme yapmaz — veri düz metin olarak iletilir, kolayca ele geçirilebilir. Günümüzde **HTTPS (port 443)** kullanılmalıdır.

---

## 7️⃣ FTP (File Transfer Protocol)

FTP, bir bilgisayardan diğerine dosya aktarmanın kolay yolunu sunar.

### İki Port, Bir Protokol

| Port | Kullanım |
|------|----------|
| **Port 21** | Kontrol bağlantısı — FTP oturumu başlatılır |
| **Port 20** | Veri transferi — asıl dosyalar bu port üzerinden taşınır |

### FTP Client Araçları

- **Komut satırı:** Windows, macOS ve Linux'ta yerleşik `ftp` komutu
- **GUI aracı:** [FileZilla](https://filezilla-project.org) — sürükle-bırak ile kolay dosya transferi

**FileZilla Arayüzü:**

- **Toolbar:** Araç çubuğu
- **Quick connect bar:** Hızlı bağlantı
- **Message log:** İşlem geçmişi
- **Local pane:** Kendi bilgisayarınızdaki dosyalar
- **Remote pane:** Uzak sunucudaki dosyalar
- **Transfer queue:** Transfer kuyruğu

---

## 8️⃣ Virtual Terminals: Telnet ve SSH

Her iki protokol de uzak bir bilgisayara bağlanıp onu **sanki yerel bir terminalmiş gibi** kullanmayı sağlar. Bu yapıya **"virtual terminal"** denir.

### Telnet (Port 23)

- TCP/IP'nin en eski uygulama katmanı protokollerinden biri (1970'ler)
- Fiziksel terminal cihazlarının ağ üzerinden yazılımla simülasyonu
- Bağlantı türü: **vty (virtual terminal) session**
- **Kritik Güvenlik Sorunu:** Şifreleme yapmaz — parolalar dahil her şey ağda düz metin olarak iletilir, kolayca ele geçirilebilir
- Modern sistemlerde varsayılan olarak kapalı; çoğu yerde kullanımı yasaklanmıştır

### SSH (Secure Shell)

Telnet'in güvenli halefi olarak geliştirilmiştir:

- **Güçlü kimlik doğrulama**
- **Şifrelenmiş veri iletimi**
- **Güvenli uzak erişim**

Tera Term (Windows), PuTTY veya macOS Terminal gibi araçlarla SSH bağlantısı kurulabilir.

> 🔑 **Altın Kural:** Mümkün olan her ortamda **Telnet yerine SSH kullanın.**

### Telnet vs SSH Karşılaştırması

| Özellik | Telnet | SSH |
|---------|--------|-----|
| Port | 23 | 22 |
| Şifreleme | ❌ Yok | ✅ Tam şifreleme |
| Kimlik Doğrulama | Zayıf | Güçlü |
| Güvenlik | Güvensiz | Güvenli |
| Kullanım Durumu | Eski sistemler / test | Üretim ortamları |

---

## 9️⃣ E-posta: Client, Server ve Protokoller

E-posta, internetin en popüler client/server uygulamalarından biridir. Her mail server, kullanıcıların posta kutularını depolar; Outlook, Gmail gibi client'lar bu mesajlara erişim sağlar.

**Posta kutusu formatı:** `kullanici@sirket.domain`

### Üç Temel E-posta Protokolü

#### SMTP — Simple Mail Transfer Protocol (Port 25)

E-posta **göndermek** için kullanılır. Client, e-postayı yerel mail server'a SMTP ile teslim eder; server da gerekirse başka bir server'a yine SMTP ile iletir.

#### POP3 — Post Office Protocol (Port 110)

E-postaları server'dan **indirmek** için kullanılır. Mesajlar bilgisayara indirilir ve varsayılan olarak server'dan silinir. Tek cihazdan erişim senaryolarına uygundur.

#### IMAP4 — Internet Message Access Protocol (Port 143)

E-postalara server üzerinden **erişmek** için kullanılır. Mesajlar kullanıcı silene kadar server'da kalır. Birden fazla cihazdan (telefon, laptop, tablet) e-postaya erişmek için idealdir.

### Protokol Karşılaştırması

| Protokol | Port | Amaç | Mesaj Sunucuda Kalır mı? |
|----------|------|-------|--------------------------|
| **SMTP** | 25 | Göndermek | — |
| **POP3** | 110 | İndirmek | ❌ Varsayılan olarak silinir |
| **IMAP4** | 143 | Erişmek | ✅ Kullanıcı silene kadar kalır |

---

## 🔟 Text Messaging (Anlık Mesajlaşma)

Instant message, direct message, private message, chat — farklı isimler, aynı fikir: **gerçek zamanlı internet üzerinden yazışma.**

- **Platform entegreli:** Sosyal medya platformlarının web client'ları üzerinden erişilebilir
- **Bağımsız uygulamalar:** Cisco Webex Teams, Microsoft Teams, WhatsApp, Facebook Messenger
- **Zengin medya desteği:** Metin dışında belge, video, müzik ve ses dosyası gönderilebilir
- **Çoklu cihaz:** Sadece akıllı telefona özgü değil — bilgisayar, tablet, akıllı saat ve daha fazlasında kullanılabilir

---

## 1️⃣1️⃣ VoIP — İnternet Üzerinden Telefon

**VoIP (Voice over IP):** Analog ses sinyallerini dijital veriye dönüştürür, IP paketlerine kapsüller ve ağ üzerinden iletir — tıpkı diğer veriler gibi.

### VoIP Çalışma Süreci

```
Mikrofon → Ses kaydedilir (analog)
         → Dijital veriye dönüştürülür
         → IP paketlerine kapsüllenir
         → Ağ üzerinden alıcıya iletilir
```

### Kullanıma Başlamak

1. IP telefon yazılımını yükle
2. Benzersiz bir kullanıcı adı seç
3. Mikrofon ve hoparlörü bağla (genellikle kulaklık kullanılır)
4. Aynı servisteki kullanıcılarla **ücretsiz** görüşme yapılır
5. Normal telefon hatlarına bağlanmak için **PSTN gateway** gerekir (ücretli olabilir)

---

## 📋 Modül Özeti

| Konu | Özet |
|------|------|
| **Client–Server** | Server hizmet sunar, client ister. Kaynaklar URI/URL/URN ile tanımlanır |
| **DNS** | Domain adlarını IP'ye çevirir. Test: `nslookup` |
| **HTTP/HTTPS** | HTTP web içeriği iletir (şifresiz). HTTPS port 443 ile güvenli iletim sağlar |
| **FTP** | Dosya transferi. Port 21 (kontrol) + Port 20 (veri) |
| **Telnet** | Uzak terminal erişimi — şifresiz, güvensiz (Port 23) |
| **SSH** | Uzak terminal erişimi — şifreli, güvenli. **Her zaman tercih edilmeli** |
| **SMTP** | E-posta gönderme (Port 25) |
| **POP3** | E-posta indirme, sunucudan siler (Port 110) |
| **IMAP4** | E-postaya erişim, sunucuda tutar (Port 143) |
| **Mesajlaşma** | Gerçek zamanlı iletişim; çoklu platform ve medya desteği |
| **VoIP** | Ses → IP paketi → ağ üzerinden iletim |

> 📝 *Bu özet, Network-16 modülü sunumu ve konuşmacı notları esas alınarak hazırlanmıştır.*

---

## Özetler arası geçiş

| No | Özet | Açıklama |
| ---- | ------ | ---------- |
| 1 | [Network01 – Kurs Tanıtımı ve Temeller](Network01-ozet.md) | Kurs tanıtımı, ağ türleri, veri, bandwidth |
| 2 | [Network02 – Ağ Bileşenleri ve Bağlantılar](Network02-ozet.md) | Client-Server, P2P, donanım, ISP |
| 3 | [Network03 – Kablosuz ve Mobil Ağ Yapılandırması](Network03-ozet.md) | Wi-Fi, hücresel, Bluetooth, tethering |
| 4 | [Network04 – Ev Ağı Kurulumu ve Güvenliği](Network04-ozet.md) | Ev ağı bileşenleri, router kurulumu, kablosuz standartlar |
| 5 | [Network05 – İletişim İlkeleri: Protokoller, Standartlar ve Modeller](Network05-ozet.md) | Protokoller, standartlar, TCP/IP, OSI modelleri |
| 6 | [Network06 – Ağ Ortamları (Network Media)](Network06-ozet.md) | Ağ ortamları: bakır, fiber, kablosuz |
| 7 | [Network07 – Erişim Katmanı (The Access Layer)](Network07-ozet.md) | Ethernet, NIC, MAC, çerçeve, kapsülleme |
| 8 | [Network08 – The Internet Protocol (IPv4)](Network08-ozet.md) | IPv4 adres yapısı, network/host, subnet mask, public/private |
| 9 | [Network09 – IPv4 Unicast/Broadcast/Multicast ve Segmentasyon](Network09-ozet.md) | Unicast, broadcast, multicast, segmentation, subnetting |
| 10 | [Network10 – IPv6 Addressing Formats and Rules](Network10-ozet.md) | IPv6 gereksinimi, adres gösterimi, kısaltma kuralları, prefix, geçiş yöntemleri |
| 11 | [Network11 – Static and Dynamic Addressing](Network11-ozet.md) | Statik/dinamik IPv4, DHCP temelleri, karşılaştırma |
| 12 | [Network12 – Gateways to Other Networks](Network12-ozet.md) | Gateway, NAT, ağ sınırları, router |
| 13 | [Network13 – The ARP Process](Network13-ozet.md) | ARP süreci, MAC/IP rolleri, broadcast containment |
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | **Network16** (bu dosya) | Client-server, DNS, HTTP/HTML, FTP, Telnet/SSH, e-posta, mesajlaşma, VoIP |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | `ipconfig`, `ping` ve temel ağ test CLI araçları; sorun giderme mantığı |

**[← Network15](Network15-ozet.md)** · **[Modül README](README.md)** · **[Network17 →](Network17-ozet.md)**

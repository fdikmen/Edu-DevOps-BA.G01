# Network17 – Network Testing Utilities (Ağ Test Araçları)

## Modül genel bakış

Bu modülde ağ bağlantısını test etmek ve sorunları gidermek için kullanılan temel **komut satırı (CLI) araçları** ele alınmaktadır. Ele alınan araçlar gerçek hayatta bağlantı sorunlarını hızla tespit etmek için ağ mühendislerinin günlük olarak başvurduğu pratik araçlardır.

**Modül hedefi:** Ağ bağlantısını test etmek ve sorunları gidermek için çeşitli komut satırı araçlarını etkin biçimde kullanabilmek.

---

## Gerçek hayat senaryosu — neden önemli?

Kishori adında bir hemşire, istasyonundaki bilgisayardan bir web sitesine bağlanamıyor:

1. **Sorun:** Hem masaüstü hem dizüstü bilgisayardan web sitesine erişilemiyor. Kablolar fiziksel olarak sorunsuz.
2. **İlk teşhis:** `command prompt` açılarak farklı bir siteye `ping` atılır → internet bağlantısının tamamen koptuğu anlaşılır.
3. **IT müdahalesi:** Madhav, default gateway'e `ping` atar → router yanıt veriyor → sorunun ISP tarafında olduğu tespit edilir.
4. **Sonuç:** Sorunları **sistematik olarak izole etmek** mümkündür; bu modül tam olarak bunu öğretir.

---

## Temel CLI araçları

| Komut | İşlev |
|-------|-------|
| `ipconfig` | IP yapılandırma bilgilerini gösterir |
| `ping` | Diğer IP hostlarıyla bağlantıyı test eder |
| `netstat` | Aktif ağ bağlantılarını listeler |
| `tracert` | Hedefe giden rotayı adım adım gösterir ("trace route"ın kısaltması) |
| `nslookup` | DNS sunucusunu doğrudan sorgular, alan adını IP'ye çevirir |

Bu modülde özellikle **`ipconfig`** ve **`ping`** komutları derinlemesine incelenmektedir.

---

## 1. `ipconfig` komutu

### Temel kullanım

Bir cihazın ağda iletişim kurabilmesi için doğru **IP adresi**, **subnet mask** ve **default gateway** bilgisine sahip olması gerekir. Bu bilgiler eksik veya hatalıysa cihaz ne ağ içinde iletişim kurabilir ne de internete çıkabilir.

**İpucu:** IP yapılandırması yanlışsa, diğer tüm ağ komutları da başarısız olacaktır. Sorun gidermede **her zaman `ipconfig` ile başlayın.**

### Parametreler

| Komut | Açıklama |
|-------|----------|
| `ipconfig` | Temel bilgiler: IP adresi, subnet mask, default gateway |
| `ipconfig /all` | Ayrıntılı bilgi: MAC adresi, DHCP durumu, DNS sunucusu, IP kira tarihleri |
| `ipconfig /release` | Mevcut DHCP bağlamasını serbest bırakır (IP adresi boşaltılır) |
| `ipconfig /renew` | DHCP sunucusundan yeni IP yapılandırması talep eder |

### `ipconfig` çıktısını okuma

- **Ethernet "Media disconnected"** → Ethernet kablosu takılı değil
- **IPv4 adresi ve default gateway doluysa** → Temel IP yapılandırması doğru (ama gerçek bağlantı için `ping` gerekir)
- **Default gateway** → Cihazın internete çıkmak için kullandığı router adresi; doğru olması kritiktir

### `ipconfig /all` — ek bilgiler

- **Physical Address (MAC):** Her ağ kartının dünyada eşsiz fiziksel kimliği
- **DHCP Enabled: Yes** → IP otomatik olarak DHCP sunucusundan alınıyor
- **Lease Obtained / Lease Expires** → IP kirasının ne zaman alındığı ve dolacağı
- **DHCP Server & DNS Servers** → Router hem DHCP hem DNS görevi görebilir

**Kritik:** DNS sunucu adresi boşsa, cihaz alan adlarını IP'ye çeviremez → IP'ye ping çalışsa bile web sitelerine erişilemez.

### macOS ve Linux karşılıkları

| İşlem | Windows | macOS | Linux |
|-------|---------|-------|-------|
| IP bilgisi görüntüleme | `ipconfig` | `ifconfig` | `ifconfig` |
| Ayrıntılı donanım listesi | — | `networksetup -listallhardwareports` | — |
| Wi-Fi detayları | — | `networksetup -getinfo Wi-Fi` | — |
| Interface detayı (low-level) | — | `ifconfig en0` | `ifconfig eth0` |
| IP bırakma | `ipconfig /release` | `ipconfig set en0 DHCP` | `dhclient -r` |
| IP yenileme | `ipconfig /renew` | `ipconfig set en0 DHCP` | `dhclient` |

**`networksetup -getinfo Wi-Fi`** → Sistem ayarları seviyesinden: IP, subnet, router, DNS, bağlantı durumu  
**`ifconfig en0`** → Donanım seviyesinden: MAC adresi, IPv4/IPv6, interface durumu (UP/RUNNING), MTU değeri, paket bilgileri

**MTU (Maximum Transmission Unit):** Ağ üzerinden tek parça halinde gönderilebilecek en büyük veri paketi boyutu (byte cinsinden).

### `ipconfig /release` ve `/renew` — ne zaman kullanılır?

IP adresleri DHCP ile dinamik atanıyorsa, bazen eski veya hatalı yapılandırmalar iletişim sorununa yol açabilir.

**Adımlar:**

1. `ipconfig /release` → mevcut IP bırakılır
2. `ipconfig /renew` → yeni IP istenir

**`/renew` sonrası IP alınamıyorsa ne yapılır?**

- **NIC link ışığı yanıyorsa** → Fiziksel bağlantı var, sorun DHCP sunucusundadır
- **NIC link ışığı yanmıyorsa** → Kablo veya port sorunu var

---

## 2. `ping` komutu

### Nasıl çalışır?

`ping`, muhtemelen en sık kullanılan ağ test aracıdır. ICMP protokolü üzerinden çalışır:

1. **Echo Request:** Kaynak cihaz hedefe "ulaşabiliyor musun?" paketi gönderir
2. **Echo Reply:** Hedef "evet ulaşabiliyorum" diye yanıt verir
3. **Request Timed Out:** Cevap beklendi ama süre doldu → paket hedefe ulaşamadı

### İki kullanım şekli

| Kullanım | Test edilen |
|----------|---------------|
| `ping 192.168.0.1` (IP adresi) | Yalnızca IP erişilebilirliği |
| `ping www.cisco.com` (alan adı) | DNS çözümlemesi **+** IP erişilebilirliği |

**Önemli fark:** IP'ye ping başarılı ama alan adına ping başarısızsa → sorun **DNS**'tedir, ağ bağlantısında değil.

### Örnek çıktı yorumlama

```
C:\> ping 10.10.10.1
Reply from 10.10.10.1: bytes=32 time=1ms TTL=64
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

→ Router sağlıklı çalışıyor, gecikme 1ms — mükemmel

```
C:\> ping www.cisco.com
Pinging e2867.dsca.akamaiedge.net [104.112.72.241]
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss), Average = 25ms
```

→ DNS çözümlemesi çalışıyor, 25ms internet gecikmesi — normal değer

Eğer `Lost = %50` görüyorsanız → bağlantı kalitesi düşük, ağda sorun var demektir.

### Sorun giderme mantığı

| Durum | Yorum | Yapılacak |
|-------|-------|-----------|
| Her iki ping başarılı, uygulama çalışmıyor | Ağ iyi, sorun uygulamada | Hedef sunucu/servis kontrol edilmeli |
| Her iki ping başarısız | Ağ sorunu şüphesi | Default gateway'e ping at |
| Gateway yanıt veriyor | Yerel ağ çalışıyor | Sorun ISP veya hedefe giden yolda |
| Gateway yanıt vermiyor | Yerel ağda sorun | Kablo, switch, router kontrol |
| Ping başarısız ama ağ sorunsuz | Firewall ICMP engelliyor | Bağlamı değerlendir; aceleci sonuca varma |

**Kritik uyarı:** Güvenlik duvarları (firewall) ping paketlerini engelleyebilir — gönderen, alıcı veya aradaki router. **Başarısız ping her zaman ağ sorunu anlamına gelmez.**

### Gelişmiş parametreler (Windows)

| Parametre | Açıklama |
|-----------|----------|
| `ping -t 8.8.8.8` | Ctrl+C ile durdurana kadar sürekli ping — ağ izleme ve kesinti yakalamak için ideal |
| `ping -n 100 10.10.10.1` | 100 paket gönderir, paket kaybı istatistiği çıkarır |
| `ping -l 1400 10.10.10.1` | Paket boyutunu ayarlar (byte) — farklı yük senaryolarını test etmek için |
| `ping -a 10.10.10.1` | IP adresini host adına çözer |
| `ping -i 64` | TTL (Time To Live) değerini ayarlar |
| `ping -w 3000` | Yanıt bekleme süresini ayarlar (ms) — yavaş ağlarda artırılabilir |
| `ping -4 / -6` | IPv4 veya IPv6 kullanımını zorlar |

**macOS:** `ping -c 2 www.google.com` → 2 paket gönderir

---

## Modül özeti

Bu modülde öğrenilen temel CLI araçları ve kullanım amaçları:

### `ipconfig`

- Temel IP bilgisi: adres, subnet mask, default gateway
- `/all` ile MAC adresi, DHCP, DNS sunucu bilgileri
- `/release` ve `/renew` ile DHCP yapılandırmasını yenileme

### `ping`

- Echo request / echo reply mekanizması ile bağlantı testi
- **IP adresine ping** → IP erişilebilirliğini test eder
- **Alan adına ping** → DNS çözümlemesi + IP erişimini test eder
- Firewall'lar ping'i engelleyebilir — başarısızlık her zaman ağ sorunu değildir

### Diğer araçlar (ilerleyen konularda)

- **`netstat`** → Aktif ağ bağlantılarını listeler
- **`tracert`** → Paketi hedefe götüren rotayı ve geçilen noktaları gösterir
- **`nslookup`** → DNS sunucusunu doğrudan sorgular

---

*Bu özet, Network-17 modülü sunumu ve konuşmacı notları esas alınarak hazırlanmıştır.*

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
| 16 | [Network16 – Application Layer Services](Network16-ozet.md) | Application Layer Services: client-server, DNS, HTTP/HTML, FTP, Telnet/SSH, e-posta, mesajlaşma, VoIP |
| 17 | **Network17** (bu dosya) | Network Testing Utilities: ipconfig, ping, netstat, tracert, nslookup ve sorun giderme |

**[← Network16](Network16-ozet.md)** · **[Modül README](README.md)**

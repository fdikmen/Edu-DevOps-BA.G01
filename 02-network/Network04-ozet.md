# Network04 – Ev Ağı Kurulumu ve Güvenliği

## İçindekiler

1. [Modül Hedefleri](#1-modül-hedefleri)
2. [Ev Ağı Bileşenleri (Home Network Fundamentals)](#2-ev-ağı-bileşenleri-home-network-fundamentals)
3. [Ev Ağı Teknolojileri (Home Network Technologies)](#3-ev-ağı-teknolojileri-home-network-technologies)
4. [Kablosuz Standartlar (Wireless Standards)](#4-kablosuz-standartlar-wireless-standards)
5. [Evde router kurulumu ve tasarımı](#5-evde-router-kurulumu-ve-tasarımı)
6. [Modül Özeti](#6-modül-özeti)

---

## 1. Modül Hedefleri

Ev ağını kurma ve güvenliğini sağlama için temel bileşenler, ayarlar ve tasarım ilkeleri.

## 2. Ev Ağı Bileşenleri (Home Network Fundamentals)

- **Masaüstü Bilgisayarlar** – Çeşitli görevler için kullanılan standart kişisel bilgisayarlar.
- **Oyun Sistemleri** – Video oyunları oynamak için kullanılan konsollar.
- **Akıllı TV'ler** – İnternet entegrasyonuna ve etkileşimli özelliklere sahip televizyonlar.
- **Yazıcı ve Tarayıcılar** – Belge basmak ve fiziksel medyayı sayısallaştırmak için kullanılan cihazlar.
- **Güvenlik Kameraları** – İzleme ve gözetleme amacıyla kullanılan kameralar.
- **Telefonlar** – VoIP telefonlar dahil, sesli iletişim cihazları.
- **İklim Kontrol Cihazları** – Sıcaklığı yönetmek için kullanılan akıllı termostatlar ve benzeri cihazlar.
- **Ev Kablosuz Yerel Alan Ağı (WLAN)** – Tüm bu cihazların kablosuz olarak birbirine ve internete bağlanmasını sağlayan ağ yapısı.

## 3. Ev Ağı Teknolojileri (Home Network Technologies)

- **Router portları ve bağlantıları**
  - **Ethernet/LAN Portları** – Kablolu cihazları (bilgisayar, yazıcı vb.) aynı yerel ağa bağlamak için kullanılan portlardır.
  - **İnternet/WAN Portu** – Modeme bağlanarak ev ağının internete çıkışını sağlayan porttur.
  - **Kablosuz Erişim Noktası** – Router'a entegre olan bu birim, kablosuz cihazların yerel ağa bağlanmasını sağlar.
- **Kablolu Ağ Teknolojileri**
  - **Kategori 5e Kablo (Cat5e)** – 4 çift bükümlü telden oluşan, paraziti azaltan ve 1 Gbps hıza kadar destek sunan Ethernet kablosu türüdür.
  - **Koaksiyel Kablo** – Ortada bir iletken tel, etrafında yalıtkan ve metal kalkan bulunan; genellikle kablolu TV ve internet için kullanılan kablo türüdür.
  - **Fiber-Optik Kablo** – Veriyi ışık darbeleri olarak ileten, çok yüksek bant genişliği ve hız sunan, parazitten etkilenmeyen cam veya plastik tellerdir.

## 4. Kablosuz Standartlar (Wireless Standards)

- **Kablosuz Frekans Bantları**
  - **2.4 GHz Bandı** – Daha geniş kapsama alanı sunan ancak daha düşük hızlı ve fazla parazitli Wi-Fi standardıdır.
  - **5 GHz Bandı** – Daha yüksek hızlar ve daha az parazit sunan modern Wi-Fi standartlarının kullandığı frekans bandıdır.
  - **Lisanssız Spektrum** – Birçok kablosuz teknolojinin (Wi-Fi, Bluetooth) izin almadan çalışabildiği belirli frekans aralıklarıdır.
- **Kablosuz Ağ Kuruluşları**
  - **IEEE (Elektrik ve Elektronik Mühendisleri Enstitüsü)** – IEEE 802.11 ailesi gibi kablosuz ağların temel teknik standartlarını geliştiren kuruluştur.
  - **Wi-Fi Alliance** – Farklı marka cihazların birbiriyle sorunsuz çalışmasını garanti altına almak için Wi-Fi cihazlarını test edip sertifikalandıran kuruluştur.
  - **Wi-Fi** – IEEE 802.11 standartlarına uygun kablosuz yerel alan ağı (WLAN) teknolojileri için kullanılan yaygın bir terimdir.
  - **Güncel Kalmanın Önemi** – Daha iyi hız, güvenlik ve özelliklerden yararlanmak için yeni kablosuz standartlarını takip etmek ve uygulamak gerekir.

## 5. Evde router kurulumu ve tasarımı

- **Temel Kablosuz Ayarları**
  - **Ağ Modu (Network Mode)** – Router’ın hangi Wi-Fi standardını (örneğin sadece 802.11ac veya karma mod) kullanacağını belirleyen ayardır.
  - **Ağ Adı (SSID)** – Kablosuz ağınızı tanımlayan ve diğer ağlardan ayıran benzersiz isimdir.
  - **Kanal (Channel)** – Genellikle optimum performans için 'Otomatik' bırakılan, veri iletiminin yapıldığı frekans aralığıdır.
  - **SSID Yayını** – Ağ adının görünür olup olmadığını belirleyen, genelde varsayılan olarak etkin olan ayardır.
- **İlk Kurulum Adımları**
  1. **Bilgisayarı Router'a Bağla** – Bilgisayarı bir Ethernet kablosuyla router'ın LAN portlarından birine bağlayın.
  2. **Router'ı Modeme Bağla** – Router'ın İnternet/WAN portunu kablonuzla modeme bağlayın.
  3. **Bağlantı Işıklarını Kontrol Et** – Router ve modem üzerindeki bağlantı ışıklarının yandığından emin olun.
  4. **IP Adresi Ayarlarını Yap** – Bilgisayarın IP adresini otomatik olarak (DHCP ile) alacak şekilde ayarlandığından emin olun.
- **Tasarım ve Güvenlikle İlgili Dikkat Edilecekler**
  - **Güçlü Şifreleme** – Güvenlik için WPA2 veya WPA3 gibi en güçlü şifreleme yöntemi kullanılmalıdır.
  - **Ağ Modu Seçimi** – Eski cihazlar için 'Karma Mod' gerekebilir, ancak en yüksek hız için mümkün olan en güncel mod seçilmelidir.
  - **Ağ Adı (SSID) Seçimi** – Kişisel bilgiler içermeyen, marka/model belirtmeyen bir ağ adı seçilmelidir.
  - **Cihaz Uyumluluğu** – Eski cihazların ağa bağlanabilmesi için router ayarlarında 'Karma Mod' gerekebileceği unutulmamalıdır.
  - **Misafir Erişimi (Guest Access)** – Ziyaretçiler için ayrı bir SSID oluşturulmalı ve bu ağ ana ev ağından izole edilerek sadece internet erişimine izin verilmelidir.

## 6. Modül Özeti

- **Ev Ağı Bileşenlerini Tanımlama** – Modem, router ve client cihazlar gibi temel donanımları tanıyabilirsiniz.
- **Kablosuz ve Kablo Teknolojilerini Anlama** – 2.4GHz ve 5GHz bantlarını, Cat5e, Koaksiyel ve Fiber kablo türlerini ayırt edebilirsiniz.
- **Sektör Kuruluşlarını Tanıma** – IEEE ve Wi-Fi Alliance'ın ağ standartlarındaki rollerini anlayabilirsiniz.
- **Ağı Planlama, Yapılandırma ve Güvenliğini Sağlama** – Ev ağınızı SSID, WPA2 güvenliği ve yönetici şifresi ile etkili bir şekilde kurabilirsiniz.

---

## Özetler arası geçiş

| No | Özet | Açıklama |
| ---- | ------ | ---------- |
| 1 | [Network01 – Kurs Tanıtımı ve Temeller](Network01-ozet.md) | Kurs tanıtımı, ağ türleri, veri, bandwidth |
| 2 | [Network02 – Ağ Bileşenleri ve Bağlantılar](Network02-ozet.md) | Client-Server, P2P, donanım, ISP |
| 3 | [Network03 – Kablosuz ve Mobil Ağ Yapılandırması](Network03-ozet.md) | Wi-Fi, hücresel, Bluetooth, tethering |
| 4 | **Network04** (bu dosya) | Ev ağı bileşenleri, router kurulumu, kablosuz standartlar |
| 5 | [Network05 – İletişim İlkeleri: Protokoller, Standartlar ve Modeller](Network05-ozet.md) | Protokoller, standartlar, TCP/IP, OSI modelleri |
| 6 | [Network06 – Ağ Ortamları (Network Media)](Network06-ozet.md) | Ağ ortamları: bakır, fiber, kablosuz |
| 7 | [Network07 – Erişim Katmanı (The Access Layer)](Network07-ozet.md) | Ethernet, NIC, MAC, çerçeve, kapsülleme |
| 8 | [Network08 – The Internet Protocol (IPv4)](Network08-ozet.md) | IPv4 adres yapısı, network/host, subnet mask, public/private |
| 9 | [Network09 – IPv4 Unicast/Broadcast/Multicast ve Segmentasyon](Network09-ozet.md) | Unicast, broadcast, multicast, segmentation, subnetting |
| 10 | [Network10 – IPv6 Addressing Formats and Rules](Network10-ozet.md) | IPv6 gereksinimi, adres gösterimi, kısaltma kuralları, prefix, geçiş yöntemleri |
| 11 | [Network11 – Static and Dynamic Addressing](Network11-ozet.md) | Static ve dynamic IPv4 addressing, DHCP temelleri, kullanım karşılaştırması |
| 12 | [Network12 – Gateways to Other Networks](Network12-ozet.md) | Gateway, NAT, ağ sınırları, router |
| 13 | [Network13 – The ARP Process](Network13-ozet.md) | ARP süreci, MAC/IP rolleri, broadcast containment |
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | [Network16 – Application Layer Services](Network16-ozet.md) | Application Layer Services: client-server, DNS, HTTP/HTML, FTP, Telnet/SSH, e-posta, mesajlaşma, VoIP |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | Network Testing Utilities: ipconfig, ping, netstat, tracert, nslookup ve sorun giderme |

**[← Network03](Network03-ozet.md)** · **[Modül README](README.md)** · **[Network05 →](Network05-ozet.md)**

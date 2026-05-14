# Network08 – The Internet Protocol (IPv4)

## İçindekiler

1. 8.0.1 Why Should I Take this Module?
2. 8.0.2 What Will I Learn in this Module?
3. 8.1 Purpose of an IPv4 Address
4. 8.2 IPv4 Address Structure
5. 8.3 Network and Host Portion
6. 8.4 Subnet Mask and Basic Calculation
7. 8.5 Public and Private IPv4 Use
8. Kısa modül özeti

---

## 8.0.1 Why Should I Take this Module?

> Bu modül neden gerekli?

IPv4 adreslemenin ağ iletişimindeki yeri:

- Ağda gönderilen her paketin bir kaynak ve hedef IPv4 adresi vardır.
- Doğru adresleme, verinin doğru cihaza/rota üzerinde ulaşmasını sağlar.
- IPv4 yapısını anlamak; routing, subnetting ve ileri ağ konularının temelini oluşturur.

---

## 8.0.2 What Will I Learn in this Module?

> Bu modülde ne öğrenilecek?

Öğrenme hedefi:

- **Module Title:** The Internet Protocol
- **Module Objective:** Bir IP adresinin özelliklerini ve amacını açıklamak
- **Ana kazanım:** IPv4 adresinin ne işe yaradığını net şekilde kavramak

---

## 8.1 Purpose of an IPv4 Address

> IPv4 adresinin amacı

IPv4 adresinin temel amacı, ağ üzerindeki hostları mantıksal olarak tanımlamaktır.

- İnternet ve çoğu LAN iletişimi için hostun geçerli bir IPv4 adresine ihtiyacı vardır.
- IPv4, fiziksel donanımdan bağımsız mantıksal bir kimlik sağlar.
- Yerel ağ içinde adreslerin doğru yapılandırılması ve benzersiz olması gerekir.
- Router'lar bu adresleri kullanarak paketleri hedef ağa iletir.

---

## 8.2 IPv4 Address Structure

> IPv4 adres yapısı

- IPv4 adres uzunluğu **32 bit**tir.
- Adres, **8 bitlik 4 oktet** halinde yazılır.
- Dotted decimal gösterimde her oktet **0-255** aralığındadır.
- Örnek: `192.168.10.25`

---

## 8.3 Network and Host Portion

> Ağ ve host kısmı

- Her IPv4 adresi iki bölüm içerir: **network** ve **host**.
- **Network** kısmı cihazın hangi alt ağa ait olduğunu gösterir.
- **Host** kısmı o alt ağ içindeki cihazı tanımlar.
- Aynı alt ağdaki cihazlar aynı network kısmını paylaşır.

---

## 8.4 Subnet Mask and Basic Calculation

> Alt ağ maskesi ve temel hesaplama

- Subnet mask, IP adresinin hangi bitlerinin network/host olduğunu belirler.
- Örnek maske: `255.255.255.0` (`/24`)
- Network adresi, IP ile maskenin bit düzeyinde AND işlemiyle bulunur.
- `/24` örneğinde son oktet host kısmıdır.

---

## 8.5 Public and Private IPv4 Use

> Public ve private IPv4 kullanımı

- **Public IPv4** internet üzerinde yönlendirilebilir adreslerdir.
- **Private IPv4** yerel ağlarda kullanılır, internete doğrudan çıkmaz.
- Yaygın private aralıklar: `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`
- Private adresli cihazlar internete çıkarken çoğunlukla **NAT** kullanır.

---

## Kısa modül özeti

- IPv4, paketlerin doğru kaynaktan doğru hedefe ulaşmasını sağlayan temel adresleme sistemidir.
- IPv4 adresleri 32 bitlik yapıdadır ve 4 oktet ile gösterilir.
- Network/host ayrımı ve subnet mask, adresin ağ içindeki rolünü belirler.
- Public/private kullanım farkı, yerel ağ ve internet iletişiminin temelini oluşturur.

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
| 8 | **Network08** (bu dosya) | IPv4 adres yapısı, network/host, subnet mask, public/private |
| 9 | [Network09 – IPv4 Unicast/Broadcast/Multicast ve Segmentasyon](Network09-ozet.md) | Unicast, broadcast, multicast, segmentation, subnetting |
| 10 | [Network10 – IPv6 Addressing Formats and Rules](Network10-ozet.md) | IPv6 gereksinimi, adres gösterimi, kısaltma kuralları, prefix, geçiş yöntemleri |
| 11 | [Network11 – Static and Dynamic Addressing](Network11-ozet.md) | Static ve dynamic IPv4 addressing, DHCP temelleri, kullanım karşılaştırması |
| 12 | [Network12 – Gateways to Other Networks](Network12-ozet.md) | Gateway, NAT, ağ sınırları, router |
| 13 | [Network13 – The ARP Process](Network13-ozet.md) | ARP süreci, MAC/IP rolleri, broadcast containment |
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | [Network16 – Application Layer Services](Network16-ozet.md) | Application Layer Services: client-server, DNS, HTTP/HTML, FTP, Telnet/SSH, e-posta, mesajlaşma, VoIP |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | Network Testing Utilities: ipconfig, ping, netstat, tracert, nslookup ve sorun giderme |

**[← Network07](Network07-ozet.md)** · **[Modül README](README.md)** · **[Network09 →](Network09-ozet.md)**

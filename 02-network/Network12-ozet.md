# Network12 – Gateways to Other Networks (Diğer Ağlara Geçitler)

## İçindekiler

1. 12.0.1 Webster - Why Should I Take this Module?
2. 12.0.2 What Will I Learn in this module?
3. 12.2 Network Boundaries (Ağ Sınırları)
4. 12.3 Network Address Translation (NAT)
5. Kısa modül özeti
6. Özetler arası geçiş

---

## 12.0.1 Webster - Why Should I Take this Module?

> Bu modül neden gerekli?

- Bir hemşire, hastane biriminin bir **Yerel Alan Ağı (LAN)** parçası olduğunu ve her birimin kendi LAN’ına sahip olduğunu öğrenir.
- Yerel ağ dışındaki kişilere **e-posta gönderip almak** için trafiğin LAN ötesine çıkması gerekir; bu ihtiyaç modülün problem bağlamını oluşturur.
- Bu iletişimi mümkün kılan başlıca kavramlar **gateway (ağ geçidi)** ve **NAT (Network Address Translation)** olarak öne çıkar.
- Ağ temellerini bilen sağlık çalışanları, hasta odası cihazlarında daha hızlı sorun giderebilir; bu da mesleki gelişim ve ücret açısından avantaj sağlayabilir.
- **Modül hedefi:** Gateway ve NAT’ı, “yerel ağdan dış dünyaya çıkış” perspektifiyle anlamak.

---

## 12.0.2 What Will I Learn in this module?

> Bu modülde ne öğrenilecek?

- **Module Title:** Gateways to Other Networks
- **Module Objective:** Yönlendiricilerin (router) ağları birbirine nasıl bağladığını açıklamak
- **Topic: Network Boundaries**
  - **Topic Objective:** Ağ sınırlarını tanımlamak
- **Topic: Network Address Translation**
  - **Topic Objective:** Küçük ağlarda NAT’ın amacını açıklamak

---

## 12.2 Network Boundaries (Ağ Sınırları)

> Ağ sınırları

- **Ağ sınırı**, aynı yönetim veya adresleme mantığı altında kabul edilen ağ parçası ile komşu ağ veya internet gibi farklı bir alanın birbirinden ayrıldığı mantıksal/teknik geçiş noktasıdır.
- Farklı LAN’lar (örneğin hastane birimleri) genelde ayrı sınırlar olarak düşünülür; birimler arası veya kurum dışı iletişimde trafik bu sınırları geçer.
- Sınırda genellikle **yönlendirici (router)** veya **ağ geçidi (gateway)** rolü üstlenen cihazlar bulunur; paketlerin hangi arayüzden çıkacağı ve hangi hedefe yönleneceği burada belirlenir.
- Sınırı tanımak, “sorun yerel mi, dış ağda mı?” ayrımı yapmak için temel bir çerçeve sağlar.

---

## 12.3 Network Address Translation (NAT)

> Küçük ağlarda NAT’ın amacı

- **NAT**, özel (private) IP adresleri kullanan iç ağdaki birçok cihazın, dışarıya çoğu zaman **tek bir kamusal (public) adres** üzerinden görünmesini sağlayan bir mekanizmadır.
- Küçük ofis veya ev ağlarında yaygın kullanım: ISP’nin verdiği sınırlı public adres sayısı ile çok sayıda iç istemciyi desteklemek.
- Giden trafikte kaynak adreslerin çevrilmesi, gelen yanıtların doğru iç cihaza geri dağıtılması (bağlantı durumu ile eşleştirme) NAT’ın pratik işlevidir.
- Modül odağı: NAT’ın **amacını** (adres tasarrufu, iç/dış adres ayrımı, küçük ağlarda basit internet çıkışı) küçük ağ senaryosuyla ilişkilendirmek.

---

## Kısa modül özeti

- Yerel LAN’dan internet veya başka siteye e-posta gibi trafik, **ağ sınırını** geçerek ilerler.
- **Router / gateway**, ağları birbirine bağlayan ve sınırda yönlendirme kararlarını üstlenen kritik bileşendir.
- **NAT**, küçük ağlarda iç özel adresler ile dış dünya arasında köprü kurar ve tipik olarak tek public adresle çoklu iç cihazı destekler.
- Bu modül, sınır kavramını ve NAT’ın rolünü birlikte düşünerek “dış ağa nasıl çıkılır?” sorusuna yanıt verir.

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
| 11 | [Network11 – Static and Dynamic Addressing](Network11-ozet.md) | Static ve dynamic IPv4 addressing, DHCP temelleri, kullanım karşılaştırması |
| 12 | **Network12** (bu dosya) | Gateway, NAT, ağ sınırları, router ile ağların birleştirilmesi |
| 13 | [Network13 – The ARP Process](Network13-ozet.md) | ARP süreci, MAC/IP rolleri, broadcast containment |
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | [Network16 – Application Layer Services](Network16-ozet.md) | Application Layer Services: client-server, DNS, HTTP/HTML, FTP, Telnet/SSH, e-posta, mesajlaşma, VoIP |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | Network Testing Utilities: ipconfig, ping, netstat, tracert, nslookup ve sorun giderme |

**[← Network11](Network11-ozet.md)** · **[Modül README](README.md)** · **[Network13 →](Network13-ozet.md)**

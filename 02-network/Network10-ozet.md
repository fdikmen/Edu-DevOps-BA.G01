# Network10 – IPv6 Addressing Formats and Rules

## İçindekiler

1. 10.0.2 What Will I Learn in this Module?
2. 10.1 IPv4 Issues
3. 10.1.1 The Need for IPv6
4. RIR IPv4 Exhaustion Dates
5. 10.2 IPv6 Address Representation
6. 10.3 IPv6 Address Shortening Rules
7. 10.4 Prefix Length and Network Portion
8. 10.5 IPv6 Transition Methods
9. Kısa modül özeti
10. Özetler arası geçiş

---

## 10.0.2 What Will I Learn in this Module?

> Bu modülde ne öğrenilecek?

- **Module Title:** IPv6 Addressing Formats and Rules
- **Module Objective:** IPv6 adreslemenin temel özelliklerini açıklamak
- **Odak:** IPv6 adres formatı, yazım kuralları ve kullanım mantığı

---

## 10.1 IPv4 Issues

> IPv4 sorunları

- IPv4 adres alanı sınırlıdır ve küresel ölçekte tükenme baskısı oluşturur.
- Artan cihaz sayısı (mobil, IoT, bulut) IPv4 talebini hızla artırır.
- NAT kullanımı adres ihtiyacını geçici olarak azaltır; ancak uçtan uca iletişim modelini karmaşıklaştırır.
- Uzun vadeli ölçeklenebilirlik için IPv6'ya geçiş zorunludur.

---

## 10.1.1 The Need for IPv6

> IPv6'ya neden ihtiyaç var?

- IPv4 adres havuzu tükenme noktasına ulaştığı için IPv6'ya geçiş gereklidir.
- IPv6, IPv4'ün devamı olacak şekilde daha geniş adres alanı sunar.
- IPv6 adres uzunluğu **128 bit**tir.
- Yaklaşık **340 undecillion** olası adres ile uzun vadeli ölçeklenebilirlik sağlar.
- IPv6, sadece adres sayısını artırmaz; protokol tasarımında iyileştirmeler de içerir.

---

## RIR IPv4 Exhaustion Dates

> RIR IPv4 tükenme tarihleri

- Bölgesel İnternet Kayıt Kuruluşları (RIR), IPv4 tahsis havuzlarının tükenme tarihlerini yayımlar.
- Bu tarihler, küresel ölçekte IPv6 geçiş ihtiyacını teknik olarak doğrular.
- IPv4 tükenmesi bölgesel hızlarda gerçekleşse de genel yönelim IPv6'ya geçiştir.

---

## 10.2 IPv6 Address Representation

> IPv6 adres gösterimi

- IPv6 adresi **128 bit** uzunluğundadır.
- Adres, **16 bitlik 8 bloktan** oluşur.
- Her blok **hexadecimal** (0-9, a-f) olarak yazılır.
- Bloklar **iki nokta (:)** ile ayrılır.
- Tam yazım örneği: `2001:0db8:0000:0000:02aa:00ff:fe9a:4ca2`

---

## 10.3 IPv6 Address Shortening Rules

> IPv6 adres kısaltma kuralları

- **Leading zero omission:** Her bloktaki soldaki gereksiz sıfırlar silinir.  
  `0db8 -> db8`, `02aa -> 2aa`, `0000 -> 0`
- **Zero compression (`::`):** Art arda gelen sıfır blokları tek seferde `::` ile gösterilir.
- **Tek kullanım kuralı:** Bir IPv6 adresinde `::` sadece **bir kez** kullanılabilir.
- Kısaltılmış örnek:  
  `2001:0db8:0000:0000:02aa:00ff:fe9a:4ca2`  
  `2001:db8::2aa:ff:fe9a:4ca2`
- `::` geri açıldığında toplam blok sayısı her zaman **8** olmalıdır.

---

## 10.4 Prefix Length and Network Portion

> Prefix uzunluğu ve ağ kısmı

- IPv6'da subnet mask yerine çoğunlukla **prefix length** kullanılır (`/64` gibi).
- `/64`, ilk 64 bitin ağ öneki olduğunu; kalan 64 bitin arayüz/host kısmı olduğunu gösterir.
- Kurumsal ve yerel ağlarda en yaygın yapı **/64** segmentlerdir.
- Örnek gösterim: `2001:db8:acad:1::/64`

---

## 10.5 IPv6 Transition Methods

> IPv6'ya geçiş yöntemleri

- **Dual Stack:** Cihaz ve ağ ekipmanı aynı anda IPv4 ve IPv6 çalıştırır.
- **Tunneling:** IPv6 paketleri, IPv4 altyapısı içinden tünellenerek taşınır.
- **Translation (NAT64/DNS64):** IPv6 istemcilerin IPv4 servislerle haberleşmesi için adres/protokol çevirisi yapılır.
- Geçiş dönemi genellikle hibrit ilerler; kurumlar tek adımda değil, aşamalı migrasyon uygular.
- Uygulama uyumluluğu, güvenlik politikaları ve izleme araçları geçiş planının temel parçalarıdır.

---

## Kısa modül özeti

- IPv6'nın temel gerekçesi, IPv4 adres tükenmesidir.
- 128 bit adresleme yapısı, çok büyük bir adres alanı sağlar.
- Hexadecimal yazım ve blok yapısı, IPv6 adres gösteriminin temelidir.
- Kısaltma kuralları: soldaki sıfırların silinmesi ve `::` ile sıfır bloklarının sıkıştırılması.
- Prefix gösterimi (`/64`), ağ ve arayüz bölümlerini tanımlar.
- Geçiş yöntemleri: dual stack, tunneling ve translation yaklaşımlarıdır.

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
| 10 | **Network10** (bu dosya) | IPv6 gereksinimi, adres gösterimi, kısaltma kuralları, prefix, geçiş yöntemleri |

**[← Network09](Network09-ozet.md)** · **[Modül README](README.md)**

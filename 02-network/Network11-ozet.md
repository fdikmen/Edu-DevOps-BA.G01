# Network11 – Static and Dynamic Addressing

## İçindekiler

1. 11.0.1 Webster - Why Should I Take this Module?
2. 11.0.2 What Will I Learn in this module?
3. 11.1 Static and Dynamic Addressing
4. 11.2 Static IPv4 Addressing
5. 11.3 Dynamic IPv4 Addressing (DHCP)
6. 11.4 Static vs Dynamic Addressing Comparison
7. Kısa modül özeti
8. Özetler arası geçiş

---

## 11.0.1 Webster - Why Should I Take this Module?

> Bu modül neden gerekli?

- Ağ bağlantı hatalarının önemli bir kısmı IP yapılandırma kaynaklıdır.
- Yanlış veya eksik IP bilgisi, ağ erişimini ve servis kullanımını engeller.
- Cihazların IP bilgilerini doğru yönetmek, ağ sorunlarını hızlı çözmeyi sağlar.
- DHCP mantığını anlamak, manuel adresleme hatalarını azaltır.

---

## 11.0.2 What Will I Learn in this module?

> Bu modülde ne öğrenilecek?

- **Module Title:** Static and Dynamic Addressing
- **Module Objective:** Statik ve dinamik IPv4 adreslemenin özelliklerini açıklamak
- **Odak:** Manuel IP atama, DHCP ile otomatik IP atama ve kullanım senaryoları

---

## 11.1 Static and Dynamic Addressing

> Statik ve dinamik adresleme

- IPv4 adresleme iki temel yaklaşımla yapılır: **statik** ve **dinamik**.
- Statik yaklaşımda IP bilgileri elle tanımlanır.
- Dinamik yaklaşımda IP bilgileri DHCP tarafından otomatik atanır.
- Doğru yöntem seçimi, ağın ölçeği ve yönetim ihtiyacına göre belirlenir.

---

## 11.2 Static IPv4 Addressing

> Statik IPv4 adresleme

- IP adresi, subnet mask, gateway ve DNS bilgileri cihaza manuel girilir.
- Sunucu, yazıcı, ağ cihazı gibi sabit erişim gerektiren sistemlerde yaygın kullanılır.
- Adres çakışmasını önlemek için planlı IP yönetimi gerekir.
- Küçük ağlarda kontrol kolaylığı sağlar; büyük ağlarda operasyonel yük oluşturabilir.

---

## 11.3 Dynamic IPv4 Addressing (DHCP)

> DHCP ile dinamik IPv4 adresleme

- DHCP, istemcilere IP yapılandırmasını otomatik olarak atar.
- Temel bilgiler: IP adresi, subnet mask, default gateway, DNS.
- Merkezi yönetim sayesinde cihaz ekleme/taşıma işlemleri hızlanır.
- Büyük ve değişken istemci sayısına sahip ağlarda tercih edilir.
- Lease süresi ve havuz planı, adres kullanım verimliliğini etkiler.

---

## 11.4 Static vs Dynamic Addressing Comparison

> Statik ve dinamik adresleme karşılaştırması

- **Yönetim:** Statik = manuel; Dinamik = merkezi ve otomatik.
- **Ölçeklenebilirlik:** Statik düşük; Dinamik yüksek.
- **Hata riski:** Statikte insan hatası daha yüksek, DHCP'de daha düşüktür.
- **Sabitlik ihtiyacı:** Sunucu altyapısında statik, istemci tarafında dinamik yaygındır.
- **En iyi pratik:** Karma model (kritik cihazlara statik, uç istemcilere DHCP).

---

## Kısa modül özeti

- Statik adresleme sabitlik ve kontrol; dinamik adresleme otomasyon ve ölçek sağlar.
- DHCP, ağ yönetimini sadeleştirir ve manuel konfigürasyon ihtiyacını azaltır.
- Uygun adresleme modeli, cihaz rolüne ve ağ büyüklüğüne göre seçilmelidir.

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
| 11 | **Network11** (bu dosya) | Static ve dynamic IPv4 addressing, DHCP temelleri, kullanım karşılaştırması |

**[← Network10](Network10-ozet.md)** · **[Modül README](README.md)**

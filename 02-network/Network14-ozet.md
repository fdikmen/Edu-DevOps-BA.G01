# Network14 – Dividing the Local Network (Yerel Ağı Bölme)

## İçindekiler

1. 14.0.1 Webster - Why Should I Take this Module?
2. 14.0.2 What Will I Learn in this module?
3. 14.1.1 Video - Dividing the Local Network
4. Kısa modül özeti
5. Özetler arası geçiş

---

## 14.0.1 Webster - Why Should I Take this Module?

> Bu modül neden gerekli?

- Tek bir büyük ağda çok cihaz olursa trafik sıkışır (congestion).
- Sıkışıklık olduğunda internet yavaşlar, gecikme artar, kopmalar yaşanabilir.
- Bu sorunu azaltmanın en temel yolu ağı parçalara ayırmaktır.
- Bu modül "yerel ağ neden bölünür?" sorusuna net cevap verir.

---

## 14.0.2 What Will I Learn in this module?

> Bu modülde ne öğrenilecek?

- Congestion'ın ne olduğunu ve neden oluştuğunu anlayacaksın.
- Büyük tek ağ ile bölünmüş ağ arasındaki farkı göreceksin.
- Ağ bölmenin hız, güvenlik ve yönetim açısından faydasını öğreneceksin.
- Router ve subnet mantığının neden gerekli olduğunu kavrayacaksın.

---

## 14.1.1 Video - Dividing the Local Network

> Konu videosu: Yerel ağı bölme

- Video, "tek büyük ağ" yerine "birkaç küçük ağ" yaklaşımını anlatır.
- Her alt ağ (subnet), broadcast trafiğini kendi içinde tutar.
- Böylece gereksiz trafik tüm şirkete yayılmaz.
- Sonuç: daha stabil, daha ölçeklenebilir bir ağ yapısı.

### Basit örnek

- Senaryo: 90 cihazın olduğu bir ofis.
- **Bölünmemiş ağ:** Tüm cihazlar aynı broadcast alanında, gereksiz trafik yüksek.
- **Bölünmüş ağ:** 3 adet 30 cihazlık subnet (Muhasebe, Operasyon, Misafir).
- Etki: broadcast yükü düşer, sorun takibi kolaylaşır, güvenlik kuralları netleşir.

---

## Kısa modül özeti

- Congestion, ağda aynı anda fazla trafik olduğunda oluşan sıkışıklıktır.
- Tek ve büyük bir ağ, broadcast yükünü gereksiz yere büyütür.
- Ağı subnet'lere bölmek performansı ve yönetilebilirliği artırır.
- Router'lar subnet'ler arası geçişi kontrollü hale getirir.

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
| 14 | **Network14** (bu dosya) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | [Network16 – Application Layer Services](Network16-ozet.md) | Application Layer Services, istemci-sunucu etkileşimi, servislerin rolü |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | `ipconfig`, `ping` ve temel ağ test CLI araçları; sorun giderme mantığı |

**[← Network13](Network13-ozet.md)** · **[Modül README](README.md)** · **[Network15 →](Network15-ozet.md)**

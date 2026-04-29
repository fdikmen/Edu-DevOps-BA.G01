# Network13 – The ARP Process (ARP Süreci)

## İçindekiler

1. 13.0.1 Webster - Why Should I Take this Module?
2. 13.0.2 What Will I Learn in this module?
3. 13.1 MAC and IP (MAC ve IP)
4. 13.2 Broadcast Containment (Yayımların sınırlandırılması)
5. Kısa modül özeti
6. Özetler arası geçiş

---

## 13.0.1 Webster - Why Should I Take this Module?

> Bu modül neden gerekli?

- Bir cihazla aynı ağdaki başka bir cihaza veri gönderirken sadece IP bilmek yetmez.
- Çünkü yerel ağda paketi son adımda teslim eden şey MAC adresidir.
- Cihazlar "Bu IP hangi MAC'e ait?" sorusunu çözmek için ARP kullanır.
- Bu mantığı anlamazsak "aynı Wi-Fi'de ama neden birbirine erişemiyor?" gibi sorunları çözmek zorlaşır.

---

## 13.0.2 What Will I Learn in this module?

> Bu modülde ne öğrenilecek?

- IP ve MAC adresinin farkını net anlayacaksın.
- ARP'nin ne zaman devreye girdiğini göreceksin.
- ARP'nin temel akışını adım adım öğreneceksin.
- Broadcast trafiğinin neden sınırlanması gerektiğini kavrayacaksın.

---

## 13.1 MAC and IP (MAC ve IP)

> IP ve MAC farkı (en sade haliyle)

| | **IP adresi** | **MAC adresi** |
| --- | --- | --- |
| **Ne işe yarar?** | Hedefin ağdaki "mantıksal konumunu" gösterir | Hedef cihazın ağ kartı kimliğini gösterir |
| **Nerede kullanılır?** | Ağlar arası yönlendirmede | Aynı yerel ağ içinde teslimatta |
| **Değişir mi?** | Evet, farklı ağa geçince değişebilir (DHCP) | Genelde sabittir (cihaz kartına bağlıdır) |
| **Benzetme** | Ev adresi gibi | Kapı zili/daire no gibi |

### Mini örnek

- Laptopun, yazıcının IP'sini biliyor: `192.168.1.50`
- Ama veriyi gönderebilmek için yazıcının MAC adresi de gerekiyor.
- Laptop ARP ile "192.168.1.50 kimde?" diye soruyor.
- Yazıcı kendi MAC'i ile cevap veriyor.
- Laptop bu bilgiyi kısa süreli ARP tablosunda saklıyor.

---

## 13.2 Broadcast Containment (Yayımların sınırlandırılması)

> Broadcast neden önemli?

- ARP isteği çoğu durumda broadcast olarak gider: ağdaki herkes duyar.
- Ağ çok büyükse bu tür mesajlar gereksiz yük oluşturur.
- Bu yüzden ağlar alt parçalara bölünür; broadcast alanı küçülür.
- Router'lar broadcast'i diğer ağa taşımaz, bu da doğal bir sınır oluşturur.

---

## Kısa modül özeti

- IP, hedefin ağdaki adresini söyler; MAC, verinin hangi cihaza teslim edileceğini söyler.
- ARP, IP'den MAC'e çeviri yaparak yerel iletişimi mümkün kılar.
- ARP isteği broadcast olduğu için ağ büyüdükçe yük artar.
- Bu nedenle broadcast alanını küçük tutmak performans için önemlidir.

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
| 13 | **Network13** (bu dosya) | ARP süreci, MAC/IP rolleri, broadcast containment |
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |

**[← Network12](Network12-ozet.md)** · **[Modül README](README.md)** · **[Network14 →](Network14-ozet.md)**

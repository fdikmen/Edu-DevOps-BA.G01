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

- **Kishori** örneği: Telefonunun **IP adresi**, bulunduğu yere ve bağlı olduğu ağa göre değişir (ör. hastane ağından eve geçince farklı adres); **DHCP**, adresi o ağın kurallarına uygun şekilde atar.
- **MAC adresi** ise cihaza özgüdür ve genelde hangi kablosuz/kablolu ağa bağlı olursa olsun **aynı kalır** (cihazın donanımsal kimliği).
- **IP adresi**, göndericiye hedefin **o ağ üzerinde nerede** olduğunu (mantıksal konum / katman 3) söyler.
- **MAC adresi**, çerçevelerin **hangi fiziksel cihaza** iletileceğini belirler; verinin yalnızca ilgili NIC’e ulaşmasını sağlar.
- DHCP doğru IP’yi verir; ancak aynı yayın alanında çerçeve göndermek için **hedef MAC** bilgisinin nasıl öğrenildiği ayrı bir sorudur — modül bu köprüyü **ARP (Address Resolution Protocol)** ile ele alır.

---

## 13.0.2 What Will I Learn in this module?

> Bu modülde ne öğrenilecek?

- **Module Title:** The ARP Process
- **Module Objective:** ARP’nin bir ağ üzerinde iletişimi nasıl mümkün kıldığını açıklamak
- **Topic: MAC and IP**
  - **Topic Objective:** MAC adresi ile IP adresinin rollerini karşılaştırmak
- **Topic: Broadcast Containment**
  - **Topic Objective:** Yayımları (broadcast) bir ağ içinde sınırlamanın neden önemli olduğunu açıklamak

---

## 13.1 MAC and IP (MAC ve IP)

> MAC ve IP rollerinin karşılaştırılması

| | **IP adresi** | **MAC adresi** |
| --- | --- | --- |
| **Katman / rol** | Mantıksal adresleme (ör. IPv4/IPv6); uçtan uca yönlendirme ve alt ağ seçimi | Erişim katmanı (Ethernet vb.); yerel bağlantı üzerinde teslimat |
| **Kapsam** | Yönlendiriciler arası değişebilir; farklı ağlara göre farklı adres atanabilir (DHCP ile konuma bağlı değişim tipik) | Genelde NIC başına sabit; yerel segmentte cihazı tanımlar |
| **İletişimde işlevi** | “Paket bu ağda kime mantıksal olarak gidiyor?” | “Bu çerçeve fiziksel olarak hangi arayüze gidecek?” |
| **ARP ile ilişki** | ARP sorgusu “Bu IP’ye sahip olanın MAC’i nedir?” diye sorar | ARP yanıtı bu eşlemeyi verir; ana bilgisayarlar ARP önbelleğinde tutar |

---

## 13.2 Broadcast Containment (Yayımların sınırlandırılması)

> Broadcast’leri bir ağ (broadcast domain) içinde tutmanın önemi

- **Broadcast**, aynı yayın alanındaki tüm düğümlerin işlemesi gereken trafiktir; her yayın tüm ilgili arayüzlerde iş yükü oluşturur.
- **Yayımları sınırlamak**, broadcast domain’i küçük ve yönetilebilir tutmak demektir; böylece gereksiz işlemci ve bant genişliği tüketimi azalır (bkz. ayrıca [Network09 – broadcast kapsamı](Network09-ozet.md)).
- **Yönlendiriciler** varsayılan olarak yayınları başka IP alt ağına iletmez; bu da doğal bir **broadcast containment** sağlar ve ARP gibi “yerel segment” protokollerinin etkisini o segment ile sınırlar.
- ARP isteği yerel çözüm içindir; aşırı büyük tek bir yayın alanında çok sayıda ARP/broadcast, gecikmeyi ve çarpışma riskini artırabilir; bu nedenle tasarımda segmentasyon ve sınırlandırma önemlidir.

---

## Kısa modül özeti

- **IP** mantıksal konum ve yönlendirme; **MAC** yerel teslimat ve cihaz kimliği — birlikte çalışırlar.
- DHCP ile IP değişebilir; aynı cihazın MAC’i yerel iletişimde sabit referanstır.
- **ARP**, bilinen bir IP için yerel segmentte **MAC adresini çözümler** (istek genelde broadcast, yanıt unicast; sonuç ARP tablosunda önbelleğe alınır).
- **Broadcast containment**, performans ve ölçeklenebilirlik için yayın trafiğini mantıksal sınırlar içinde tutmayı hedefler; router sınırları bu açıdan kritiktir.

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

**[← Network12](Network12-ozet.md)** · **[Modül README](README.md)**

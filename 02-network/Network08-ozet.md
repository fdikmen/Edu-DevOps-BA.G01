# Network08 – İnternet Protokolü (IPv4)

## İçindekiler

1. [Modülün Amacı](#1-modülün-amacı)
2. [IPv4 Adresi](#2-ipv4-adresi)
3. [Oktetler ve Noktalı Ondalık Gösterim](#3-oktetler-ve-noktalı-ondalık-gösterim)
4. [Ağ (Network) ve Host Kısımları](#4-ağ-network-ve-host-kısımları)
5. [Hiyerarşik Adresleme ve Alt Ağ Maskesi](#5-hiyerarşik-adresleme-ve-alt-ağ-maskesi)
6. [Subnetting ve Tipik Adresler](#6-subnetting-ve-tipik-adresler)
7. [Anlama Kontrolü (Slayt Soruları)](#7-anlama-kontrolü-slayt-soruları)
8. [Modül Özeti](#8-modül-özeti)

---

## 1. Modülün Amacı

Dijital iletişimde paketlerin bir **adrese**, cihazların ağ üzerinde bir **kimliğe** ihtiyaç duyduğu vurgulanır.

**Modül amacı**

- **IPv4 adresinin** temel özelliklerini ve işlevini kavramak.
- **IPv4’ün amacı:** Cihazların ağda nasıl tanımlandığını ve neden adrese ihtiyaç duyulduğunu anlamak.
- **IPv4 adres yapısı:** 32 bitlik yapı ve **alt ağ maskesinin** rolünü incelemek.

---

## 2. IPv4 Adresi

**Mantıksal kimlik:** IP adresi, **fiziksel konumdan bağımsız** olarak ağdaki benzersiz **dijital kimlik** gibi düşünülür.

- **Benzersizlik:** Aynı **alt ağ (broadcast domain)** içinde her cihazın adresi **farklı** olmalıdır. İnternete açık yönlendirmede genelde **küresel olarak atanmış** genel adresler kullanılır; **özel IPv4 blokları** (ör. ev/ofis LAN’ları) ise farklı yerlerde **aynı aralıklarla** tekrar kullanılabilir—dışarı çıkışta çoğu zaman **NAT** devreye girer.
- **Atama:** Adresler genellikle cihazların **NIC (ağ kartı)** birimlerine veya **router arayüzlerine** atanır.

---

## 3. Oktetler ve Noktalı Ondalık Gösterim

**32 bit:** Makine için adres, 32 adet **0 ve 1** dizisi olarak temsil edilir.

**Oktet:** 32 bit, yönetimi kolaylaştırmak için **8’er bitlik 4 gruba** (oktet) ayrılır.

**Noktalı ondalık (dotted decimal):** Her oktet **0–255** aralığında bir ondalık sayıya çevrilir; örnek: **192.168.1.1**.

---

## 4. Ağ (Network) ve Host Kısımları

Her IPv4 adresi hiyerarşik olarak iki ana parçadan oluşur:

| Bileşen | Rol |
|--------|-----|
| **Network (ağ)** | Cihazın hangi **yerel ağa** veya **alt ağa** ait olduğunu belirleyen kısım |
| **Host (cihaz)** | O ağ içindeki **belirli ve benzersiz** cihazı tanımlayan kısım |

---

## 5. Hiyerarşik Adresleme ve Alt Ağ Maskesi

**Router verimliliği:** Router’lar genelde **tüm hostları tek tek** takip etmez; **ağ yolunu** bilerek trafiği yönlendirir—bu da ölçeklenebilirlik sağlar.

**Alt ağ maskesi (subnet mask):** IP adresinin **hangi bitlerinin ağ**, **hangi bitlerinin host** olduğunu belirleyen **ayraç**tır (IP ile birlikte kullanılır).

**Mantıksal ayrım:** Aynı fiziksel altyapı üzerinde, farklı **ağ kısımları** ile birbirinden bağımsız **mantıksal gruplar** oluşturulabilir.

---

## 6. Subnetting ve Tipik Adresler

Slaytlarda **192.168.1.0 / 255.255.255.0** örneği üzerinden tipik adres rolleri özetlenir:

| Rol | Örnek (bu ağ için) |
|-----|---------------------|
| **Ağ (network) adresi** | 192.168.1.0 |
| **İlk kullanılabilir host** | 192.168.1.1 |
| **Kullanılabilir host aralığı** | … 192.168.1.1 – 192.168.1.254 … |
| **Son kullanılabilir host** | 192.168.1.254 |
| **Yayın (broadcast) adresi** | 192.168.1.255 |

**Subnet mask ne işe yarar?** Önce **ağ adresi** tipik olarak **IPv4 adresi AND subnet mask** ile bulunur; **yayın adresi** ve **kullanılabilir host aralığı** ise bu ağ adresine ve maskenin **host bitleri** üzerinden türetilir (tek bir AND ile hepsi çıkmaz; AND ağ önekini verir).

---

## 7. Anlama Kontrolü (Slayt Soruları)

> [!TIP]
> **Network adresi:** IPv4 adresi ile subnet maskesini **bit düzeyinde AND** uygulayarak (veya önek uzunluğuna göre host bitlerini sıfırlayarak) bulunur. **Aynı alt ağda** olmak, **aynı network adresi ve aynı mask** (veya aynı önek) ile uyumlu olmak anlamına gelir.

**Soru 1:** Host-A: **10.5.4.100**, mask **255.255.255.0** → network **10.5.4.0** (**B**).

**Soru 2:** Host-A: **172.16.4.100**, mask **255.255.0.0** → network **172.16.0.0** (**A**).

**Soru 3:** Host-A: **10.5.4.100 / 255.255.255.0** → ağ **10.5.4.0**. Aynı ağ: **10.5.4.1**, **10.5.4.99** (seçenek **3** ve **5**).

**Soru 4:** Host-A: **172.16.4.100 / 255.255.0.0** → ağ **172.16.0.0**. Aynı ağ: **172.16.0.1**, **172.16.4.99** (seçenek **4** ve **5**).

**Soru 5:** Host-A: **192.168.1.50 / 255.255.255.0** → ağ **192.168.1.0**. Aynı ağ: **192.168.1.100**, **192.168.1.1** (seçenek **3** ve **5**).

---

## 8. Modül Özeti

- **Dijital kimlik:** **IP**, katman 3’te cihazı tanımlar; **aynı alt ağda** adresler birbirinden farklı olmalıdır (özel adresler + NAT ile küresel benzersizlik her cihaz için şart değildir).
- **Hiyerarşi:** 32 bitlik adres **network** ve **host** parçalarından oluşur; ayrımı **alt ağ maskesi** belirler (ör. **192.168.5.11** ile **255.255.255.0**).
- **Oktet sistemi:** İkili diziler dört **oktet**e bölünüp **noktalı ondalık** gösterime çevrilir.
- **Yönlendirme:** Router’lar hiyerarşi sayesinde öncelikle **ağ yollarını** izleyerek trafiği yönetir.
- **İnternet Protokolü**, küresel iletişim ve ağ teknolojilerinin temel taşlarından biridir.

---

## Özetler arası geçiş

| No | Özet | Açıklama |
|----|------|----------|
| 1 | [Network01 – Kurs Tanıtımı ve Temeller](Network01-ozet.md) | Kurs tanıtımı, ağ türleri, veri, bandwidth |
| 2 | [Network02 – Ağ Bileşenleri ve Bağlantılar](Network02-ozet.md) | Client-Server, P2P, donanım, ISP |
| 3 | [Network03 – Kablosuz ve Mobil Ağ Yapılandırması](Network03-ozet.md) | Wi-Fi, hücresel, Bluetooth, tethering |
| 4 | [Network04 – Ev Ağı Kurulumu ve Güvenliği](Network04-ozet.md) | Ev ağı bileşenleri, router kurulumu, kablosuz standartlar |
| 5 | [Network05 – İletişim İlkeleri: Protokoller, Standartlar ve Modeller](Network05-ozet.md) | Protokoller, standartlar, TCP/IP, OSI modelleri |
| 6 | [Network06 – Ağ Ortamları (Network Media)](Network06-ozet.md) | Ağ ortamları: bakır, fiber, kablosuz |
| 7 | [Network07 – Erişim Katmanı (The Access Layer)](Network07-ozet.md) | Ethernet, NIC, MAC, çerçeve, kapsülleme |
| 8 | **Network08** (bu dosya) | IPv4: mantıksal kimlik, oktet, ağ/host, alt ağ maskesi, subnetting |
| 9 | [Network09 – IPv4 ve Ağ Segmentasyonu](Network09-ozet.md) | IPv4 ve segmentasyona giriş: kapsam, motivasyon, teorik + pratik |

**[← Network07](Network07-ozet.md)** · **[Modül README](README.md)** · **[Network09 →](Network09-ozet.md)**

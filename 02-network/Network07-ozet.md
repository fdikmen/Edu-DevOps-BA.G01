# Network07 – Erişim Katmanı (The Access Layer)

## İçindekiler

1. [Modül Hedefleri](#1-modül-hedefleri)
2. [Ethernet ve Yerel Alan Ağı (LAN)](#2-ethernet-ve-yerel-alan-ağı-lan)
3. [Kapsülleme ve Ethernet Çerçevesi](#3-kapsülleme-ve-ethernet-çerçevesi)
4. [Modül Özeti](#4-modül-özeti)
5. [Ek notlar: unicast, host ve L2 switch](#5-ek-notlar-unicast-host-ve-l2-switch)

---

## 1. Modül Hedefleri

Bu modülün amacı **access layer** bağlamında **Ethernet** teknolojisini, **NIC (Network Interface Card)** rolünü, **MAC** ile frame alanlarını ve **encapsulation** ile **Ethernet frame** yapısını özetlemektir.

---

## 2. Ethernet ve Yerel Alan Ağı (LAN)

**Ethernet**, yerel alan ağlarında (**LAN**) yaygın şekilde kullanılan bir teknolojidir. Cihazlar Ethernet LAN’a genellikle bir **NIC** üzerinden bağlanır.

**Ethernet kapsamı:** Bu bölümde iletişim, **aynı ağ üzerinde** bir **NIC’ten diğer bir NIC’e** kadar ele alınır (yerel **frame** iletimi).

---

## 3. Kapsülleme ve Ethernet Çerçevesi

### 7.1 Kapsülleme ve Ethernet çerçevesi

Üst katman verisi, iletim için **Ethernet frame**’e sarılır (**encapsulation**). **Frame** içindeki **fields** ölçü ve yapı olarak incelenir.

### MAC ve frame içindeki adres alanları

- Her Ethernet **NIC**, üzerinde kalıcı olarak tanımlanmış benzersiz bir adrese sahiptir: **MAC (Media Access Control)**.
- **Ethernet frame** içinde **source MAC** ve **destination MAC** alanları bulunur.

### Byte ve bit

Frame alanları genellikle **byte** cinsinden verilir. Aynı uzunluğu **bit** cinsinden ifade etmek için byte sayısı **8** ile çarpılır.

---

## 4. Modül Özeti

- **Ethernet** – LAN’da yaygın kullanılan **access layer** teknolojisidir.
- **NIC** – Cihazın Ethernet LAN bağlantısıdır; **MAC** bu karttadır.
- **Ethernet frame** – **Source / destination MAC** alanlarını içerir; veri **encapsulation** ile frame’e konur.
- **Kapsam** – Aynı ağda **NIC’ten NIC’e** iletilim düşünülür.
- **Ölçü** – Alanlar **byte**; **bit** için **×8**.

---

## 5. Ek notlar: unicast, host ve L2 switch

Aşağıdaki kutular GitHub / VS Code önizlemesinde **farklı renklerde** görünür (`[!NOTE]`, `[!TIP]`, `[!IMPORTANT]`).

> [!NOTE]
> **Unicast frame**  
> **Unicast**, frame’in **destination MAC**’inin tek bir alıcı **NIC**’e ait olduğu iletimdir (bire bir): frame “şu tek host’a” gider. **Broadcast** (ör. **FF:FF:FF:FF:FF:FF**) herkes içindir; **multicast** belirli bir gruba yöneliktir—üçünü birbirinden ayırmak önemlidir.

> [!TIP]
> **Frame forwarding**  
> **Layer 2 switch**, gelen Ethernet **frame**’ini **destination MAC**’e bakarak **hangi porta çıkaracağına** karar verir. Bu **forwarding** kararı **MAC address table** içindeki **MAC ↔ port** eşleşmesine dayanır. Tabloda **hedef bulunamazsa** tipik davranış, frame’i ilgili alanda **tüm portlara göndermek (flood)** olup öğrenme sürecine yardım eder; **bilinmeyen hedef = otomatik çöpe** düşmek zorunda değildir.

> [!IMPORTANT]
> **Host ne yapar?**  
> Bir **host**, frame’deki **unicast destination MAC** kendi **NIC**’inin adresi **değilse** frame’i **üst katmana iletmez**; Ethernet seviyesinde **discard** eder. Başka bir sistemin **unicast** frame’ini “sıradaki makineye aktarmak” tipik **host** rolü değildir. **IP header**’ı görmek için önce **Layer 2**’nin frame’i kabul etmesi gerekir—bu senaryoda **destination MAC** uyuşmazsa iş burada biter.
>
> **Switch, hub ve router karışmasın**  
> Gelen sinyali **her porta körlemesine çoğaltmak** **hub** tarafına yakın bir davranıştır. **Destination IP**’ye göre bir sonraki sıçrayı seçmek **Layer 3 router** işidir. **MAC table**’ı dolduran bilgi çoğunlukla frame’in **source MAC** alanından **öğrenilir**; **forwarding** anında ise tabloda **destination MAC** aranır—yani tablo **“hedefe bakarak oluşur”** şeklinde düşünülmemelidir.
>
> **Özet zincir**  
> **Forwarding kararı:** **destination MAC** + **MAC table**’daki **MAC–port** eşlemesi. **Unicast**, **destination** yok sayılarak her host’a iletilecek bir trafik türü değildir.

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
| 7 | **Network07** (bu dosya) | Erişim katmanı: Ethernet, NIC, MAC, çerçeve, kapsülleme |

**[← Network06](Network06-ozet.md)** · **[Modül README](README.md)**

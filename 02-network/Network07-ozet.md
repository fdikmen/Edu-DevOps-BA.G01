# Network07 – Erişim Katmanı (The Access Layer)

## İçindekiler

1. [Modül Hedefleri](#1-modül-hedefleri)
2. [Ethernet ve Yerel Alan Ağı (LAN)](#2-ethernet-ve-yerel-alan-ağı-lan)
3. [Kapsülleme ve Ethernet Çerçevesi](#3-kapsülleme-ve-ethernet-çerçevesi)
4. [Modül Özeti](#4-modül-özeti)

---

## 1. Modül Hedefleri

Bu modülün amacı **erişim katmanı** bağlamında **Ethernet** teknolojisini, **ağ arayüz kartı (NIC)** rolünü, **MAC adresi** ile çerçeve alanlarını ve **kapsülleme (encapsulation)** ile **Ethernet çerçevesi** yapısını özetlemektir.

---

## 2. Ethernet ve Yerel Alan Ağı (LAN)

**Ethernet**, yerel alan ağlarında (**LAN**) yaygın şekilde kullanılan bir teknolojidir. Cihazlar Ethernet LAN’a genellikle bir **ağ arayüz kartı (NIC, Network Interface Card)** üzerinden bağlanır.

**Ethernet kapsamı:** Bu bölümde iletişim, **aynı ağ üzerinde** bir **NIC’ten diğer bir NIC’e** kadar ele alınır (yerel çerçeve iletimi).

---

## 3. Kapsülleme ve Ethernet Çerçevesi

### 7.1 Kapsülleme ve Ethernet çerçevesi

Üst katman verisi, iletim için **Ethernet çerçevesine (frame)** sarılır (**kapsülleme**). Çerçevenin **alanları (fields)** ölçü ve yapı olarak incelenir.

### MAC adresi ve çerçevedeki adres alanları

- Her Ethernet **NIC**, üzerinde kalıcı olarak tanımlanmış benzersiz bir adrese sahiptir: **MAC adresi (Media Access Control address)**.
- **Ethernet çerçevesi** içinde **kaynak MAC adresi (source MAC)** ve **hedef MAC adresi (destination MAC)** alanları bulunur.

### Byte ve bit

Çerçeve alanları genellikle **bayt (byte)** cinsinden verilir. Aynı uzunluğu **bit** cinsinden ifade etmek için bayt sayısı **8** ile çarpılır.

---

## 4. Modül Özeti

- **Ethernet** – LAN ortamında yaygın kullanılan erişim katmanı teknolojisidir.
- **NIC** – Cihazın Ethernet LAN’a bağlandığı arabirim kartıdır; **MAC adresi** buna bağlıdır.
- **Ethernet çerçevesi** – **Kaynak ve hedef MAC** alanlarını içerir; veri **kapsüllenerek** çerçeveye konur.
- **Kapsam** – Aynı ağda **NIC’ten NIC’e** iletilim düşünülür.
- **Ölçü** – Alanlar **byte** ile ifade edilir; **bit** için **×8**.

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

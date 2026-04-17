# Network09 – IPv4 Unicast/Broadcast/Multicast ve Segmentasyon

## İçindekiler

1. 9.0 Introduction
2. 9.0.2 What Will I Learn in this Module?
3. 9.1 IPv4 Unicast, Broadcast, and Multicast
4. 9.2 Broadcast Scope and Limits
5. 9.3 Network Segmentation Basics
6. 9.4 Segmentation with Subnetting
7. Kısa modül özeti
8. Özetler arası geçiş

---

## 9.0 Introduction

> Giriş

IPv4 adresleme türlerinin temel çerçevesi:

- **Unicast:** Tek kaynaktan tek hedefe iletim.
- **Multicast:** Tek kaynaktan belirli alıcı grubuna iletim.
- **Broadcast:** Tek kaynaktan aynı ağdaki tüm cihazlara iletim.
- Adres türleri: **private**, **public** ve **reserved** IPv4.

---

## 9.0.2 What Will I Learn in this Module?

> Bu modülde ne öğrenilecek?

Ana öğrenme hedefleri:

- **IPv4 Unicast, Broadcast, and Multicast:** Bu üç IPv4 iletişim tipinin özelliklerini ve hangi durumda kullanıldıklarını karşılaştırma.
- **Network Segmentation:** Subnetting ile ağı parçalara ayırıp iletişimi daha verimli ve yönetilebilir hale getirme.

---

## 9.1 IPv4 Unicast, Broadcast, and Multicast

> IPv4 unicast, broadcast ve multicast

IPv4 iletişim türleri:

- **Unicast:** Tek kaynaktan tek hedefe iletişim.
- **Broadcast:** Tek kaynaktan aynı ağdaki tüm cihazlara iletişim.
- **Multicast:** Tek kaynaktan belirli bir alıcı grubuna iletişim.

Adresleme tipi, hedef kitlenin kapsamına göre seçilir.

---

## 9.2 Broadcast Scope and Limits

> Broadcast kapsamı ve sınırları

- Broadcast trafik aynı broadcast domain içinde yayılır.
- Router'lar broadcast trafiği varsayılan olarak diğer ağlara taşımaz.
- Büyük ağlarda yoğun broadcast trafiği performansı düşürebilir.
- Ağ tasarımında broadcast alanını sınırlamak önemlidir.

---

## 9.3 Network Segmentation Basics

> Ağ segmentasyonu temelleri

- Network segmentation, büyük ağı daha küçük mantıksal parçalara ayırır.
- Amaç: performans, güvenlik ve yönetilebilirlik artışı.
- Segmentler arası trafik genellikle Layer 3 cihazlarla yönlendirilir.
- Problem izolasyonu segmentasyon ile daha kolay yapılır.

---

## 9.4 Segmentation with Subnetting

> Subnetting ile segmentasyon

- Subnetting, IP adres bloğunu daha küçük alt ağlara böler.
- Her alt ağın ayrı network adresi ve broadcast adresi vardır.
- Doğru subnet planı adres israfını azaltır.
- Segmentasyon, erişim kontrolü ve politika uygulamasını kolaylaştırır.

---

## Kısa modül özeti

- Unicast, broadcast ve multicast farklı hedefleme modelleridir.
- Broadcast alanının büyüklüğü doğrudan ağ verimliliğini etkiler.
- Subnetting tabanlı segmentasyon performans, güvenlik ve ölçeklenebilirlik sağlar.

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
| 8 | [Network08 – İnternet Protokolü (IPv4)](Network08-ozet.md) | IPv4: mantıksal kimlik, oktet, ağ/host, alt ağ maskesi, subnetting |
| 9 | **Network09** (bu dosya) | IPv4 unicast/broadcast/multicast ve network segmentation öğrenme hedefleri |
| 10 | [Network10 – IPv6 Addressing Formats and Rules](Network10-ozet.md) | IPv6 gereksinimi, adresleme formatı ve kurallar |

**[← Network08](Network08-ozet.md)** · **[Modül README](README.md)** · **[Network10 →](Network10-ozet.md)**

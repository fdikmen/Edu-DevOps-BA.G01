# Network16 – Application Layer Services (Uygulama Katmanı Servisleri)

## İçindekiler

1. 16.0 Introduction
2. 16.0.1 Webster - Why Should I Take this Module?
3. 16.0.2 What Will I Learn in this Module?
4. 16.1 The Client Server Relationship
5. 16.1.1 Client and Server Interaction
6. 16.1.2 Video - Web Server and Client IP Interactions
7. 16.1.3 URI, URN, and URL
8. 16.2 Network Application Services
9. 16.2.1 Common Network Application Services
10. 16.3 Domain Name System
11. 16.3.1 Video - DNS Servers
12. 16.3.3 Syntax Checker - The nslookup Command
13. 16.4 Web Clients and Servers
14. 16.4.1 Video - HTTP and HTML
15. 16.4.2 HTTP and HTML
16. 16.5 FTP Clients and Servers
17. 16.5.1 File Transfer Protocol
18. 16.5.2 Video - FTP Client Software
19. 16.6 Virtual Terminals
20. 16.6.1 Video - Remote Access with Telnet or SSH
21. 16.6.2 Telnet
22. 16.6.3 Security Issues with Telnet
23. 16.7 Email and Messaging
24. 16.7.1 Email Clients and Servers
25. 16.7.2 Email Protocols
26. 16.7.3 Text Messaging
27. 16.7.4 Internet Phone Calls
28. 16.8 Application Layer Services Summary
29. 16.8.1 What Did I Learn in this Module?
30. Özetler arası geçiş

---

## 16.0 Introduction

> Bu modül neye giriş yapıyor?

- Modül, uygulama katmanındaki servislerin günlük ağ kullanımını nasıl mümkün kıldığını açıklar.
- Kullanıcının bir kaynağa erişiminde istemci, sunucu ve protokollerin birlikte nasıl çalıştığına odaklanır.

---

## 16.0.1 Webster - Why Should I Take this Module?

> Bu modül neden gerekli?

- Kishori örneği üzerinden, bir dosyaya erişirken arka planda hangi ağ süreçlerinin çalıştığı sorgulanır.
- Uzak bir kaynağa erişimde her zaman bir istemci-sunucu ilişkisi ve ilgili protokoller devrededir.
- FTP, DHCP, DNS gibi servisler uygulama katmanında kritik rol oynar.

---

## 16.0.2 What Will I Learn in this Module?

> Bu modülde ne öğrenilecek?

- İstemci-sunucu etkileşimini açıklama
- Yaygın ağ uygulama servislerini tanıma
- DNS'in çalışma mantığını kavrama
- HTTP ve HTML ilişkisini anlama
- FTP'nin dosya aktarımındaki rolünü öğrenme
- Telnet ve SSH ile uzak erişimi karşılaştırma
- E-posta ve mesajlaşma protokollerini ayırt etme

---

## 16.1 The Client Server Relationship

> İstemci-sunucu modeli neden temel?

- İnternetteki çoğu uygulama, istemcinin istek gönderip sunucunun yanıt verdiği modele dayanır.
- Sunucu, hizmet veya veri sunan yazılımı çalıştıran hosttur.
- İstemci tarafında tarayıcı, e-posta istemcisi veya dosya istemcisi gibi yazılımlar bulunur.

---

## 16.1.1 Client and Server Interaction

> Etkileşim nasıl gerçekleşir?

- Aynı cihazda birden fazla istemci uygulaması aynı anda çalışabilir.
- E-posta, web ve dosya servisleri farklı sunucu yazılımlarıyla sunulur.
- Bu karmaşık iletişimin sorunsuz işlemesi, ortak standart ve protokoller sayesinde mümkündür.

---

## 16.1.2 Video - Web Server and Client IP Interactions

> Web istemcisi web sunucusuna nasıl erişir?

- Kullanıcı URL girer; önce DNS sorgusu ile alan adı IP adresine çevrilir.
- Ardından istemci ile sunucu arasında TCP bağlantısı kurulur.
- İletişim, kaynak/hedef IP ve port bilgilerinin birleştiği socket yapısı ile takip edilir.
- Aynı oturuma ait paketler router ve firewall gibi cihazlarca bu bilgilerle tanınır.

---

## 16.1.3 URI, URN, and URL

> URI, URN, URL farkı

- URI bir kaynağı tanımlayan genel ifadedir.
- URN, kaynağın ad alanını belirtir; konum/protokol bilgisi vermez.
- URL, kaynağın ağ üzerindeki yerini ve erişim yöntemini belirtir.
- URI bileşenleri: protocol/scheme, hostname, path/file name, fragment.

---

## 16.2 Network Application Services

> Ağ uygulama servisleri neden önemli?

- Arama, sosyal medya, yayın, alışveriş, e-posta ve mesajlaşma gibi servisler uygulama katmanı protokolleriyle çalışır.
- Güvenilir iletişim için TCP/IP protokol takımı kullanılır.

---

## 16.2.1 Common Network Application Services

> Yaygın servisler ve görevleri

- DNS: İsimleri IP adreslerine çözer.
- SSH: Sunucu ve ağ cihazlarına güvenli uzak erişim sağlar.
- SMTP: E-posta gönderimini sunucular arasında da taşır.
- POP/IMAP: E-postayı istemciye getirir (farklı çalışma mantıklarıyla).
- DHCP: Cihazlara otomatik IP ve ağ ayarları verir.
- HTTP: Web sayfalarının istenmesi ve iletilmesini sağlar.
- FTP: Sistemler arası dosya aktarımı yapar.

---

## 16.3 Domain Name System

> DNS ne yapar?

- DNS, alan adını IP adresine çevirerek istemcinin doğru sunucuya erişmesini sağlar.
- Kullanıcı adı hatırlarken, ağ altyapısı IP ile çalışır; DNS bu iki dünyayı bağlar.

---

## 16.3.1 Video - DNS Servers

> DNS süreci adım adım

- İstemci `www.cisco.com` gibi bir ad ister.
- DNS sunucusu ilgili IP'yi bulup istemciye döner.
- İstemci bu IP ile hedef web sunucusuna bağlanır ve içeriği alır.

---

## 16.3.3 Syntax Checker - The nslookup Command

> `nslookup` ne işe yarar?

- `nslookup`, alan adının hangi IP'ye çözüldüğünü test etmek için kullanılır.
- Ev ağlarında DNS adresi çoğunlukla DHCP ile otomatik dağıtılır.
- Manuel yapılandırmada DNS adresinin doğru verilmesi kritik önemdedir.

---

## 16.4 Web Clients and Servers

> Web erişimi hangi iki temel üzerine kurulu?

- HTTP ile istemci-sunucu arasında istek/yanıt taşınır.
- HTML ile web sayfası içeriği ve biçimi tarayıcıda oluşturulur.

---

## 16.4.1 Video - HTTP and HTML

> Tarayıcıdan web sayfasına giden yol

- Önce DNS çözümlemesi yapılır.
- Sonra istemci HTTP isteğini web sunucusuna gönderir.
- Sunucu HTML içeriği döner; tarayıcı bu kodu render eder.

---

## 16.4.2 HTTP and HTML

> Güvenlik ve portlar

- HTTP istekleri tipik olarak port 80 üzerinden gider.
- HTTP tek başına güvenli değildir; veriler yakalanabilir.
- Güvenli web için HTTPS kullanılır ve istekler port 443'e gider.
- Ortak HTTP/HTML standartları, farklı üreticilerin sistemlerinin birlikte çalışmasını sağlar.

---

## 16.5 FTP Clients and Servers

> FTP neden kullanılır?

- Dosya yükleme/indirme ve uzaktan dosya yönetimi için kullanılır.
- Web sitesi dosyalarını sunucuya aktarma gibi senaryolarda yaygındır.

---

## 16.5.1 File Transfer Protocol

> FTP iletişim yapısı

- FTP iki ayrı TCP portu kullanır:
  - Kontrol bağlantısı: TCP 21
  - Veri aktarımı: TCP 20
- İstemci; upload, download, silme, yeniden adlandırma gibi işlemler yapabilir.

---

## 16.5.2 Video - FTP Client Software

> FTP istemci yazılımı kullanımı

- FileZilla gibi araçlarla sunucuya bağlanıp dosya transferi yapılabilir.
- Arayüzde yerel dosyalar ve uzak sunucu dosyaları birlikte görülür.
- Sürükle-bırak ile dosya aktarımı pratik biçimde tamamlanır.

---

## 16.6 Virtual Terminals

> Sanal terminal kavramı

- Uzak bir sisteme sanki başındaymış gibi komut satırı erişimi sağlamayı hedefler.
- Telnet ve SSH bu alandaki temel protokollerdir.

---

## 16.6.1 Video - Remote Access with Telnet or SSH

> Uzak erişim örneği

- Tera Term benzeri istemci ile host adına bağlanılır.
- Kullanıcı adı/şifre doğrulaması sonrası uzaktaki sistemin CLI'ı kullanılabilir.
- SSH, Telnet'e göre daha güvenli olduğu için öncelikli tercihtir.

---

## 16.6.2 Telnet

> Telnet'in rolü

- Eski ama temel bir uzak terminal protokolüdür.
- Telnet sunucuları TCP port 23 dinler.
- Telnet oturumu, vty (virtual terminal) bağlantısı olarak adlandırılır.

---

## 16.6.3 Security Issues with Telnet

> Telnet neden riskli?

- Telnet trafiği şifrelenmez; veriler plaintext taşınır.
- Bu nedenle kimlik bilgileri ve komutlar kolayca ele geçirilebilir.
- SSH, şifreleme ve daha güçlü kimlik doğrulama sunduğu için güvenli alternatiftir.

---

## 16.7 Email and Messaging

> E-posta ve anlık mesajlaşma

- E-posta klasik istemci-sunucu modelinde çalışır.
- Mesajlaşma uygulamaları gerçek zamanlı iletişim sağlar ve çoğu çoklu platform destekler.

---

## 16.7.1 Email Clients and Servers

> E-posta mimarisi

- Mail sunucuları kullanıcı posta kutularını tutar ve yönetir.
- Kullanıcılar istemci uygulamalarla (web veya masaustu) posta kutusuna erişir.
- Adres formatı: `user@company.domain`

---

## 16.7.2 Email Protocols

> SMTP, POP3, IMAP4 farkı

- SMTP (port 25): E-posta gönderimi için kullanılır.
- POP3 (port 110): Mesajları istemciye indirir; varsayılan olarak sunucuda bırakmaz.
- IMAP4 (port 143): Mesajları sunucuda tutar; çoklu cihaz senaryoları için daha uygundur.

---

## 16.7.3 Text Messaging

> Anlık mesajlaşma özellikleri

- Instant/direct/private/chat mesajları aynı kategoridedir.
- Web tabanlı ya da bağımsız istemciler üzerinden gerçek zamanlı iletişim yapılır.
- Modern araçlar metne ek olarak belge, ses ve video dosyalarını da taşır.

---

## 16.7.4 Internet Phone Calls

> İnternet telefon görüşmeleri

- IP telefonide VoIP kullanılır; analog ses dijitale çevrilip IP paketlerine kapsullenir.
- Aynı servis kullanıcıları arasında doğrudan internet araması yapılabilir.
- Klasik telefon ağına (PSTN) çıkış için gateway gerekir; hizmete göre ücret olabilir.

---

## 16.8 Application Layer Services Summary

> Modülün genel mesajı

- Uygulama katmanı servisleri, internet deneyiminin görünen kısmını taşıyan temel yapı taşlarıdır.
- İstemci-sunucu modeli, standartlar ve doğru protokol seçimi güvenilir hizmet için zorunludur.

---

## 16.8.1 What Did I Learn in this Module?

> Öğrenilenlerin toplu özeti

- Client-server modeli: İstemci ister, sunucu yanıtlar.
- URI/URN/URL: Kaynağı tanımlama ve konumlama yapıları.
- DNS: İsimden IP'ye çözümleme.
- Web: HTTP/HTTPS ile içerik taşıma, HTML ile gösterim.
- FTP: Port 21 kontrol, port 20 veri aktarımı.
- Virtual terminal: Telnet (güvensiz) ve SSH (güvenli).
- E-posta: SMTP gönderim, POP3/IMAP4 alma yaklaşımları.
- Mesajlaşma/VoIP: Gerçek zamanlı iletişim ve internet tabanlı aramalar.

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
| 14 | [Network14 – Dividing the Local Network](Network14-ozet.md) | Yerel ağı bölme, congestion farkındalığı |
| 15 | [Network15 – Comparing TCP and UDP](Network15-ozet.md) | TCP ve UDP karşılaştırması, kullanım senaryosu odaklı protokol seçimi |
| 16 | **Network16** (bu dosya) | Application Layer Services, DNS-HTTP-FTP-SSH ve e-posta/mesajlaşma servisleri |
| 17 | [Network17 – Network Testing Utilities](Network17-ozet.md) | `ipconfig`, `ping` ve temel ağ test CLI araçları; sorun giderme mantığı |

**[← Network15](Network15-ozet.md)** · **[Modül README](README.md)** · **[Network17 →](Network17-ozet.md)**

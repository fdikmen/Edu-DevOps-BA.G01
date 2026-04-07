# Network05 – İletişim İlkeleri: Protokoller, Standartlar ve Modeller

## İçindekiler

1. [Modül Hedefleri](#1-modül-hedefleri)
2. [İletişim Protokolleri (Communication Protocols)](#2-iletişim-protokolleri-communication-protocols)
3. [İletişim Standartları (Communication Standards)](#3-iletişim-standartları-communication-standards)
4. [Ağ İletişim Modelleri (Network Communication Models)](#4-ağ-iletişim-modelleri-network-communication-models)
5. [Modül Özeti](#5-modül-özeti)
6. [Modül 6 – Ağ Ortamları (Network Media), kısa giriş](#6-modül-6--ağ-ortamları-network-media-kısa-giriş)

---

## 1. Modül Hedefleri

Bu modülün amacı, ağ iletişiminin temel ilkelerini anlamaktır. Protokollerin ne olduğunu, standartların neden gerekli olduğunu ve ağ iletişim modellerinin (TCP/IP ve OSI) nasıl çalıştığını kavramak hedeflenmektedir.

---

## 2. İletişim Protokolleri (Communication Protocols)

### Protokol Nedir?

**Protokol**, başarılı iletişim için uyulması gereken kurallar bütünüdür. Günlük hayatta da farkında olmadan protokoller kullanırız:

| Günlük Hayat | Açıklama |
|---|---|
| **Yöntem (Method)** | İletişim başlamadan önce kullanılacak yöntem üzerinde anlaşılmalıdır. (örn. yazılı not mu, sözlü mü?) |
| **Dil (Language)** | Hangi ortak dilin kullanılacağı belirlenmelidir. |
| **Onay (Confirmation)** | Mesajın doğru alındığı teyit edilmelidir. |

> **Kural:** İletişim başarılı sayılır; ancak amaçlanan mesaj alındığında ve onaylandığında.

### Protokollerin 6 Temel Özelliği

- **Mesaj Formatı (Message Format)** – Gönderilen her mesaj belirli bir format ya da yapı kullanmalıdır. Kullanılan kanal ve mesaj türüne göre format değişir.
- **Mesaj Boyutu (Message Size)** – Ağ üzerinden iletilen parçaların boyutunu belirleyen kurallar çok katıdır. Uzun mesajlar güvenilir teslimat için daha küçük parçalara bölünür.
- **Zamanlama (Timing)** – Bitlerin iletim hızını, bir ana bilgisayarın ne zaman veri gönderebileceğini ve tek seferde maksimum veri miktarını belirler.
- **Kodlama (Encoding)** – Mesajlar önce bitlere dönüştürülür, ardından ağ ortamına göre ses, ışık dalgaları veya elektrik sinyallerine kodlanır.
- **Kapsülleme (Encapsulation)** – Her mesaj, kaynak ve hedefi tanımlayan adresleme bilgilerini içeren bir başlık (header) içermelidir. Mektubun zarfa konulmasına benzer.
- **Mesaj Deseni (Message Pattern)** – Bazı mesajlar bir sonraki gönderilmeden önce onay bekler (istek/yanıt modeli). Bazıları ise kesintisiz akış (streaming) olarak iletilir.

---

## 3. İletişim Standartları (Communication Standards)

### Standart Nedir?

**Standart**, bir şeyin nasıl yapılması gerektiğini belirleyen kurallar bütünüdür.

### Ağ Standartları Ne Sağlar?

- Tüm cihazların aynı protokolleri aynı şekilde uygulamasını garanti eder.
- Farklı türdeki cihazların internet üzerinden iletişim kurmasını mümkün kılar.
- **Örnek:** Gmail'den Outlook'a e-posta gönderimi; çünkü hepsi aynı e-posta standartlarını kullanır.

### Cihazların Ağ Üzerindeki Etkileşimi (Devices in a Bubble)

Bir cihaz yalnızca üç temel bilgiyi bilir: **IP adresi**, **ağ geçidi (Gateway)** ve **DNS sunucusu**. Bir web sayfasına erişim sürecinde arka planda 6 protokol birlikte çalışır:

| Adım | Protokol | Görev |
|------|----------|-------|
| 1 | **Ethernet** | Fiziksel ağa bağlanır |
| 2 | **DHCP** | IP adresi, gateway, DNS sunucu bilgisi otomatik atanır |
| 3 | **DNS** | Alan adını IP adresine çevirir |
| 4 | **IP** | Paketi kaynaktan hedefe taşır |
| 5 | **TCP** | Kayıp paketleri yeniden gönderir; güvenilir teslimat sağlar |
| 6 | **HTTP** | Web içeriğini tarayıcıya aktarır |

> Siz tek sayfa görürsünüz; arka planda 6 protokol çalışır.

### DHCP Nedir?

**DHCP (Dynamic Host Configuration Protocol)**, ağdaki cihazlara otomatik olarak IP adresi, ağ geçidi ve DNS bilgisi atayan protokoldür. DHCP sunucusu farklı yerlerde bulunabilir:

- **Ev ağlarında:** Modem/Router içinde çalışır.
- **Kurumsal ağlarda:** Ayrı bir sunucu (örn. Windows Server) üzerinde çalışır.
- **ISP tarafında:** Kullanıcı modemlerine public IP atamak için kullanılır.

**DHCP Süreci (3 Adım):**

1. **DHCP'den önce** – Cihaz ağa bağlandığında hiçbir ağ bilgisini bilmez.
2. **DHCP süreci** – Cihaz ağa bir yayın (broadcast) gönderir; DHCP sunucusu IP, gateway ve DNS bilgilerini atar.
3. **DHCP'den sonra** – Cihaz bu üç bilgiyle ağda iletişim kurmaya başlar.

### Küresel Standart Kuruluşları

| Kuruluş | Açıklama |
|---------|----------|
| **IEEE** | Ethernet, Wi-Fi standartları (802.x ailesi) |
| **IETF** | İnternet protokolleri, RFC yönetimi |
| **IANA** | IP adresleri ve alan adı tahsisi |
| **ICANN** | İnternet adları ve numaraları |
| **ITU** | Uluslararası telekom standartları |
| **TIA** | Kablo ve telekom endüstrisi standartları |

### RFC (Request for Comments) Süreci

**RFC**, internet teknolojileri ve protokollerinin tanımlandığı teknik dokümanlardır. IETF tarafından yayımlanır.

> Yeni standart önerilir → RFC belgesi yayınlanır → Tartışılır → Test edilir → Onaylanır

---

## 4. Ağ İletişim Modelleri (Network Communication Models)

### Protokol Yığını (Protocol Stack) Nedir?

Başarılı bir ağ iletişimi tek bir protokolle değil, bir **protokol yığınıyla (protocol stack)** gerçekleşir. Farklı görevleri üstlenen protokollerin bir araya gelerek veri iletimini birlikte gerçekleştirdiği yapıdır.

> **Sıralama:** PROTOCOL STACK → MODEL → LAYER (Katman)

### TCP/IP Modeli

TCP/IP Modeli, internetin temel referans modelidir. 4 katmandan oluşur:

| Katman | Açıklama | Örnekler |
|--------|----------|----------|
| **Application (Uygulama)** | Veriyi kullanıcıya sunar; kodlama ve diyalog kontrolünü içerir | HTTP, FTP, SMTP, DNS |
| **Transport (Taşıma)** | Farklı ağlardaki cihazlar arasındaki iletişimi destekler | TCP, UDP |
| **Internet (İnternet)** | Ağ üzerinde en iyi yolu belirler; paket yönlendirmesi yapar | IPv4, IPv6 |
| **Network Access (Ağ Erişimi)** | Ağı oluşturan donanım cihazlarını ve ortamlarını kontrol eder | Ethernet, Wi-Fi |

**Katmanlı yapının avantajları:**
- Her katman kendi işini yapar; diğerlerinin nasıl çalıştığını bilmek zorunda değildir.
- Farklı firmalar birlikte çalışabilen ürünler üretebilir.
- Teknoloji bağımsız ilerleyebilir.
- Ortak bir iletişim dili oluşur.

### OSI Referans Modeli

**OSI Modeli**, ISO tarafından geliştirilmiş 7 katmanlı bir **referans modelidir** (protokol modeli değildir). Her katmanda hangi fonksiyonların gerçekleşmesi gerektiğini tanımlar.

| # | Katman Adı | Temel Görev |
|---|-----------|-------------|
| 7 | **Application** | Süreçten sürece iletişim protokolleri. HTTP, FTP, SMTP |
| 6 | **Presentation** | Veri formatı dönüşümü, şifreleme, sıkıştırma |
| 5 | **Session** | Oturumları başlatır, yönetir ve sonlandırır |
| 4 | **Transport** | Uçtan uca güvenilir iletim. TCP, UDP |
| 3 | **Network** | Adresleme ve yönlendirme. **IP buradadır.** |
| 2 | **Data Link** | Cihazlar arası çerçeve iletimi. Ethernet |
| 1 | **Physical** | Bit iletimi için fiziksel ortam. Kablo, konnektör, sinyaller |

> **Hafıza yöntemi (aşağıdan yukarıya):**  
> **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way  
> Physical → Data Link → Network → Transport → Session → Presentation → Application

### TCP/IP ve OSI Modellerinin Karşılaştırması

| TCP/IP Modeli | OSI Modeli |
|---------------|------------|
| Application | 7. Application / 6. Presentation / 5. Session |
| Transport | 4. Transport |
| Internet | 3. Network |
| Network Access | 2. Data Link / 1. Physical |

**Temel farklar:**
- **TCP/IP** → Gerçek protokolleri içerir; bugünkü internetin çalışma modelidir.
- **OSI** → Teorik referans modelidir; protokolleri gösterir ama kendisi protokol içermez.
- Günlük ağ terminolojisinde OSI katman numaraları kullanılır: "Layer 3 sorunu" dendiğinde herkes yönlendirme sorununu anlar.

---

## 5. Modül Özeti

- **İletişim Protokollerini Anlama** – Protokoller; mesaj formatı, boyutu, zamanlama, kodlama, kapsülleme ve mesaj deseni olmak üzere 6 temel özellikten oluşur.
- **İletişim Standartlarını Tanıma** – IEEE, IETF, IANA, ICANN, ITU ve TIA gibi kuruluşlar küresel ağ standartlarını belirler. IETF, RFC belgeleriyle internet standartlarını yönetir.
- **TCP/IP Modelini Kavrama** – 4 katmanlı bu model (Application, Transport, Internet, Network Access) internetin çalışma modelidir.
- **OSI Modelini Kavrama** – 7 katmanlı referans modeli evrensel bir referans dilidir; ağ sorunlarını tanımlamak ve iletişim kurmak için kullanılır.
- **İki Modeli Karşılaştırabilme** – TCP/IP'nin Ağ Erişimi katmanı OSI'nin 1. ve 2. katmanlarını; TCP/IP'nin Uygulama katmanı OSI'nin 5., 6. ve 7. katmanlarını kapsar.

---

## 6. Modül 6 – Ağ Ortamları (Network Media), kısa giriş

**Network Media** modülünde, iletişimin ağ üzerinden **hangi ortamdan** geçtiği ele alınır. Ortam, mesajların kaynaktan hedefe iletildiği **kanaldır**. Bir cihazda kablosuz kapalı olsa bile (ör. hastanedeki masaüstü) ağ erişimi genellikle **kablolu ortam** ile mümkün olur; bu da “ortam” kavramının pratikteki karşılığıdır. Güncel ağlarda başlıca **üç ortam türü** kullanılır; ayrıntılı özet için bkz. [Network06 – Ağ Ortamları](Network06-ozet.md).

---

## Özetler arası geçiş

| No | Özet | Açıklama |
|----|------|----------|
| 1 | [Network01 – Kurs Tanıtımı ve Temeller](Network01-ozet.md) | Kurs tanıtımı, ağ türleri, veri, bandwidth |
| 2 | [Network02 – Ağ Bileşenleri ve Bağlantılar](Network02-ozet.md) | Client-Server, P2P, donanım, ISP |
| 3 | [Network03 – Kablosuz ve Mobil Ağ Yapılandırması](Network03-ozet.md) | Wi-Fi, hücresel, Bluetooth, tethering |
| 4 | [Network04 – Ev Ağı Kurulumu ve Güvenliği](Network04-ozet.md) | Ev ağı bileşenleri, router kurulumu, kablosuz standartlar |
| 5 | **Network05** (bu dosya) | İletişim İlkeleri: Protokoller, Standartlar ve Modeller |
| 6 | [Network06 – Ağ Ortamları (Network Media)](Network06-ozet.md) | Ağ ortamları: iletim kanalı, yaygın üç ortam türü |

**[← Network04](Network04-ozet.md)** · **[Modül README](README.md)** · **[Network06 →](Network06-ozet.md)**

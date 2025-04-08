# 🔐Akıllı Kilit ve Laboratuvar Erişim Sistemi

Bu GitHub organizasyonu, İstanbul Sabahattin Zaim Üniversitesi tarafından desteklenen **BAP100** projesi kapsamında geliştirilen **Akıllı Kilit ve Laboratuvar Erişim Sistemi**ni kapsamaktadır. 

## 📌 Proje Tanımı

Üniversitelerde laboratuvar, atölye ve çalışma alanları genellikle fiziksel anahtarlarla veya manuel kontrolle açılıp kapatılmaktadır. Bu durum, erişimlerin denetlenememesi, güvenliğin zayıf olması ve kaynakların verimli kullanılmaması gibi sorunlara yol açmaktadır.

**BAP100 Akıllı Kilit Sistemi**, bu problemi çözmek amacıyla geliştirilen bütünleşik bir yazılım ve donanım çözümüdür. Projenin temel hedefleri şunlardır:

- 🎯 Öğrencilerin ve personelin **randevu bazlı** olarak alanlara erişmesini sağlamak
- 🧠 **QR kod ve kimlik doğrulama** sistemleri ile güvenli geçişler oluşturmak
- 🧾 Kullanıcı ve erişim bilgilerini kayıt altına alarak **istatistiksel analiz** yapılmasını sağlamak
- 🛠️ Donanım (kilit mekanizması) ile yazılımı entegre ederek **otomatik erişim kontrolü** sağlamak

Bu sistem sayesinde hem yöneticiler hem de öğrenciler için erişim süreçleri daha kolay, denetlenebilir ve güvenli hale gelir.

---

## 📦 Organizasyondaki Depolar

### 1. [`BAP100-flutter-app`](https://github.com/KilitSistemi/BAP100-flutter-app) (Private)
Mobil uygulama Flutter ile geliştirilmiştir. Öğrenciler bu uygulama üzerinden randevu alabilir, QR kod oluşturarak laboratuvara giriş yapabilir ve bildirimler alabilir.

- 📱 Platform: Android & iOS
- 💬 Bildirim Sistemi: Firebase Cloud Messaging (FCM)
- 🛠️ Teknolojiler: Flutter, Dart

---

### 2. [`BAP100-node`](https://github.com/KilitSistemi/BAP100-node) (Private)
Sistemin merkezi web sunucusudur. Kimlik doğrulama, randevu oluşturma, kullanıcı yönetimi ve cihazlara gönderilecek token işlemleri burada gerçekleşir.

- 🌐 Teknolojiler: Node.js(22.2.0), Express, EJS
- 🔐 JWT tabanlı kimlik doğrulama
- 🧩 API servisleri ile Flutter ve Web uygulamalarına hizmet sağlar

---

### 3. [`BAP100-donanim`](https://github.com/KilitSistemi/BAP100-donanim) (Public)
Fiziksel kilit sisteminin kontrolünden sorumlu olan donanım tarafının kaynak kodlarını içerir. STM32 mikrodenetleyici ve ILI9341 ekranla birlikte çalışır.

- 🧠 Kontrolcü: Raspberry, ESP32, Arduino
- 📷 QR kod ekran gösterimi
- 🔒 Kilit kontrolü için GPIO kullanımı

---

### 4. [`BAP100-nodeForRaspberry`](https://github.com/KilitSistemi/BAP100-nodeForRaspberry) (Private)
Raspberry Pi üzerinde çalışan, **lokal iletişimden sorumlu** Node.js uygulamasıdır. Bu uygulama, merkezi sunucudan aldığı token ile QR kod üretir ve GPIO üzerinden kilit tetikleyebilir.

- 🍓 Platform: Raspberry Pi
- 📡 Raspberry ile local ağ üzerinden güvenli iletişim
- 🔌 Raspberry üzerindeki GPIO çıkışları ile kilit açma kontrolü

---

### 5. [`BAP100-veritabani`](https://github.com/KilitSistemi/BAP100-veritabani) (Private)
Tüm sistemin veri altyapısını içerir. Veritabanı şemaları, tablolar, ilişki yapıları ve örnek veriler burada bulunur.

- 🗃️ Veritabanı: MySQL (8.0.36)
- 📊 İçerik: Kullanıcılar, randevular, erişim logları
- 🧩 SQL betikleri ve yedekleme prosedürleri

---

### 6. [`BAP100-DevOPS`](https://github.com/KilitSistemi/BAP100-DevOPS) (Private)
CI/CD süreçlerini, Docker container, Kubernetes yapılandırmalarını ve otomatik dağıtım betiklerini içerir.

- 🐳 Dockerfile yapılandırmaları
- 🔁 Pipeline ve servis otomasyonu
- ⚙️ Projelerin sürekli entegrasyonu ve dağıtımı

---

## 🧩 Genel Sistem Mimarisi

Sistem aşağıdaki bileşenlerden oluşmaktadır:

```txt
[Mobil Uygulama / Web] ←→ [Web Sunucu API]   ←→    [Veritabanı]
                           ↓        ↓                    ↑
                           ↓    [Node For Raspberry] ----┘
                           ↓        ↓↑
                  [Raspberry veya diğer denetleyiciler]

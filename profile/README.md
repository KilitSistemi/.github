# 🚀 Takımımız ve Projelerimiz

Bu organizasyon altında, **Yoklama Sistemi** ve **Akıllı Kilit Sistemi** başta olmak üzere çeşitli IoT tabanlı projeler geliştiren bir takımız. 

---

## 👥 Takım Üyeleri

| İsim                                   | Görev               | GitHub Profili                          | LinkedIn Profili                          |
| -------------------------------------- | ------------------- | --------------------------------------- | --------------------------------------- |
| Kerem Yavuz | Backend Developer   | [GitHub](https://github.com/Kerem-Yavuz) | [LinkedIn](https://www.linkedin.com/in/kerem-yavuz-yake/) |
| Hasan Arı | DevOPS Engineer  | [GitHub](https://github.com/HasanAriii) | [LinkedIn](https://www.linkedin.com/in/hasan-ar%C4%B1-5401932a1/) |
| Selim Can Aydın | Frontend Developer    | [GitHub](https://github.com/scana1405) | [LinkedIn](https://www.linkedin.com/in/selimcanaydin/) |
| Enes Halit | Mobile Developer    | [GitHub](https://github.com/Enes830) | [LinkedIn](https://www.linkedin.com/in/enes-halit-4361071a8/) |
| Abdulrahman Haffaroğlu | Hardware/AI Specialist | [GitHub](https://github.com/AbdulrahmanHaffaroglu) | [LinkedIn](https://www.linkedin.com/in/abdulrahman-haffar-885201365/) |


---

### 🔍 Projelerimiz

* [Yoklama Sistemi](#yoklama-sistemi)
* [Akıllı Kilit Sistemi](#akıllı-kilit-ve-laboratuvar-erişim-sistemi)

---

### 📞 İletişim

* **E-posta:** [teamc16.info@gmail.com](mailto:teamc16.info@gmail.com)
* **LinkedIn:** [TeamC16](https://www.linkedin.com/company/teamc16)

---

# 🔐Akıllı Kilit ve Laboratuvar Erişim Sistemi

Bu proje, İstanbul Sabahattin Zaim Üniversitesi tarafından desteklenen bir **BAP100** projesidir.

## 📌 Proje Tanımı

Üniversitelerde laboratuvar, atölye ve çalışma alanları genellikle fiziksel anahtarlarla veya manuel kontrolle açılıp kapatılmaktadır. Bu durum, erişimlerin denetlenememesi, güvenliğin zayıf olması ve kaynakların verimli kullanılmaması gibi sorunlara yol açmaktadır.

**Akıllı Kilit Sistemi**, bu problemi çözmek amacıyla geliştirilen bütünleşik bir yazılım ve donanım çözümüdür. Projenin temel hedefleri şunlardır:

- 🎯 Öğrencilerin ve personelin **randevu bazlı** olarak alanlara erişmesini sağlamak
- 🧠 **QR kod ve kimlik doğrulama** sistemleri ile güvenli geçişler oluşturmak
- 🧾 Kullanıcı ve erişim bilgilerini kayıt altına alarak **istatistiksel analiz** yapılmasını sağlamak
- 🛠️ Donanım (kilit mekanizması) ile yazılımı entegre ederek **otomatik erişim kontrolü** sağlamak

Bu sistem sayesinde hem yöneticiler hem de öğrenciler için erişim süreçleri daha kolay, denetlenebilir ve güvenli hale gelir.

---

## 📦 Projenin Repoları

### 1. [`KilitSistemi-flutter-app`](https://github.com/Team-C16/KilitSistemi-flutter-app) (Private)
Mobil uygulama Flutter ile geliştirilmiştir. Öğrenciler bu uygulama üzerinden randevu alabilir, QR kod oluşturarak laboratuvara giriş yapabilir ve bildirimler alabilir.

- 📱 Platform: Android & iOS
- 💬 Bildirim Sistemi: Firebase Cloud Messaging (FCM)
- 🛠️ Teknolojiler: Flutter, Dart

---

### 2. [`KilitSistemi-node`](https://github.com/Team-C16/KilitSistemi-node) (Private)
Sistemin merkezi web sunucusudur. Kimlik doğrulama, randevu oluşturma, kullanıcı yönetimi ve cihazlara gönderilecek token işlemleri burada gerçekleşir.

- 🌐 Teknolojiler: Node.js(22.2.0), Express, EJS
- 🔐 JWT tabanlı kimlik doğrulama
- 🧩 API servisleri ile Flutter ve Web uygulamalarına hizmet sağlar

---

### 3. [`KilitSistemi-donanim`](https://github.com/Team-C16/KilitSistemi-donanim) (Public)
Fiziksel kilit sisteminin kontrolünden sorumlu olan donanım tarafının kaynak kodlarını içerir. STM32 mikrodenetleyici ve ILI9341 ekranla birlikte çalışır.

- 🧠 Kontrolcü: Raspberry, ESP32, Arduino
- 📷 QR kod ekran gösterimi
- 🔒 Kilit kontrolü için GPIO kullanımı

---

### 4. [`KilitSistemi-nodeForRaspberry`](https://github.com/Team-C16/KilitSistemi-nodeForRaspberry) (Private)
Raspberry Pi üzerinde çalışan, **lokal iletişimden sorumlu** Node.js uygulamasıdır. Bu uygulama, merkezi sunucudan aldığı token ile QR kod üretir ve GPIO üzerinden kilit tetikleyebilir.

- 🍓 Platform: Raspberry Pi
- 📡 Raspberry ile local ağ üzerinden güvenli iletişim
- 🔌 Raspberry üzerindeki GPIO çıkışları ile kilit açma kontrolü

---

### 5. [`KilitSistemi-veritabani`](https://github.com/Team-C16/KilitSistemi-veritabani) (Private)
Tüm sistemin veri altyapısını içerir. Veritabanı şemaları, tablolar, ilişki yapıları ve örnek veriler burada bulunur.

- 🗃️ Veritabanı: MySQL (8.0.36)
- 📊 İçerik: Kullanıcılar, randevular, erişim logları
- 🧩 SQL betikleri ve yedekleme prosedürleri

---

### 6. [`KilitSistemi-DevOPS`](https://github.com/Team-C16/KilitSistemi-DevOPS) (Private)
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
```

---

##


# 📌Yoklama Sistemi

Bu proje, İstanbul Sabahattin Zaim Üniversitesi tarafından desteklenen bir **BAP100** projesidir.

Bu Sistem, sınıflarda yoklama işlemlerinin daha hızlı, güvenli ve doğru bir şekilde yapılabilmesi amacıyla geliştirilen bütünleşik bir yazılım ve donanım çözümünü kapsamaktadır. Proje dört ana bileşenden oluşmaktadır:

* Web tabanlı yoklama arayüzü (React)
* Mobil uygulama (Flutter)
* Merkezi sunucu (Node.js, MySQL)
* Donanım katmanı (Kamera Entegrasyonu)

---

## 📦 Projenin Repoları

### 1. [`YoklamaSistemi-frontend`](https://github.com/Team-C16/YoklamaSistemi-frontend) (Private)

React ile geliştirilmiş web tabanlı arayüzdür. Öğretmenler bu uygulama üzerinden ders oluşturabilir, yoklama başlatabilir ve öğrenci katılımlarını takip edebilir.

* 🌐 Teknolojiler: React, Axios
* ✏️ Özellikler:

  * Ders oluşturma ve yoklama başlatma
  * Canlı katılım takibi
  * Geçmiş yoklama kayıtlarının görüntülenmesi

---

### 2. [`YoklamaSistemi-flutter`](https://github.com/Team-C16/YoklamaSistemi-flutter) (Private)

Flutter ile geliştirilmiş mobil uygulamadır. Öğrenciler bu uygulama üzerinden derse katılım sağlayabilir ve yoklamalarını kontrol edebilir.

* 📱 Platform: Android & iOS
* 🛠️ Teknolojiler: Flutter, Dart
* 📌 Özellikler:

  * Derse katılım sağlama
  * Geçmiş yoklama kayıtlarını görüntüleme
  * Bildirim sistemi

---

### 3. [`YoklamaSistemi-backend`](https://github.com/Team-C16/YoklamaSistemi-backend) (Private)

Node.js ile geliştirilmiş backend servisidir. Veritabanı işlemleri, kimlik doğrulama ve yoklama işlemlerinin merkezi sunucusudur.

* 🌐 Teknolojiler: Node.js, Express, MySQL
* 🔐 JWT tabanlı kimlik doğrulama
* 🗃️ Veritabanı: MySQL
* 🔄 API servisleri:

  * Yoklama oluşturma
  * Katılımcı doğrulama
  * Geçmiş kayıtların çekilmesi

---

### 4. [`YoklamaSistemi-Donanim`](https://github.com/Team-C16/YoklamaSistemi-Donanim) (Private)

Kamera entegrasyonu ve sınıf sayım algoritmalarını içeren donanım katmanıdır. Yoklama sırasında sınıftaki kişi sayısını analiz eder. Ayrıca Bluetooth entegrasyon kodlarını da içerir.

* 🧠 Donanım: Raspberry Pi, Kamera Modülü
* 📷 Kişi sayımı algoritmaları
* 🌐 API entegrasyonu ile verilerin merkeze iletilmesi

---

## 🧩 Genel Sistem Mimarisi

Sistem aşağıdaki bileşenlerden oluşmaktadır:

```txt
[Donanım (Kamera)] ←→ [Backend API] ←→ [Veritabanı]
                       ↑         ↑
                       |         |
            [Mobil Uygulama]  [Web Arayüzü] 
```

Web arayüzü ve mobil uygulama, merkezi backend sunucusuna bağlı olarak yoklama işlemlerini gerçekleştirir. Donanım katmanı ise kamera verilerini analiz ederek sınıftaki kişi sayısını belirler ve merkeze iletir.



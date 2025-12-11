# 🌐 Otel Rezervasyon ve Müşteri Takip Sistemi  
**YAZ16303 – Yazılım Mimarisi ve Tasarımı Dönem Projesi (PRJ-4)**

Bu proje, Kırklareli Üniversitesi Yazılım Mühendisliği Bölümü *Yazılım Mimarisi ve Tasarımı* dersi kapsamında geliştirilmiştir.  
Amaç; müşterilerin ve personelin otel rezervasyon süreçlerini yönetebileceği, kullanıcı rolleri içeren, çok katmanlı, tasarım desenleri kullanılan bir Java uygulaması geliştirmektir.

---

## 👥 Proje Ekibi
| İsim | GitHub |
|------|--------|
| **Ayça Eren** | https://github.com/aycaeren |
| **Irmak Kızıl** | https://github.com/irmakkizil |
| **Rabia Cırık** | https://github.com/rabiacirik |

Bu proje üç kişilik ekip tarafından birlikte geliştirilmiştir.

---

## 🏨 Proje Açıklaması

Bu sistem; müşterilerin rezervasyon oluşturabildiği, kendi geçmiş konaklamalarını görüntüleyebildiği ve bilgilerini güncelleyebildiği bir yapı sunar.  
Personel ise oda yönetimi, müşteri yönetimi, rezervasyon yönetimi, check-in/check-out işlemleri gibi otel operasyonlarını takip edebilir.

---

## 🎯 Proje Kapsamı ve Özellikler

### 🔐 **Kullanıcı Rolleri**
- **Müşteri**
  - Kayıt olabilir ve giriş yapabilir.
  - Profil bilgilerini güncelleyebilir.
  - Şifre değiştirebilir.
  - Oda arayabilir (giriş/çıkış tarihi, kişi sayısı, oda tipi).
  - Rezervasyon oluşturabilir, görüntüleyebilir ve iptal edebilir.
  - Geçmiş konaklamalarını görebilir.

- **Personel**
  - Giriş yapabilir.
  - Müşteri ekleyebilir, listeleyebilir, arayabilir.
  - Oda ekleyebilir, düzenleyebilir, durumlarını görüntüleyebilir.
  - Rezervasyon oluşturabilir, listeleyebilir, filtreleyebilir.
  - Check-in ve check-out işlemleri yapabilir.

---

## 🗂 Kullanılan Tasarım Desenleri

### ✔ Singleton  
Veritabanı bağlantısı (DatabaseConnection) tek bir örnek üzerinden yönetilmiştir.

### ✔ Factory / Abstract Factory  
Oda tiplerinin (Standart, Suit, Aile Odası vb.) oluşturulması için Factory Pattern kullanılmıştır.

### ✔ Observer  
Rezervasyon durumu değiştiğinde ilgili bileşenlerin bilgilendirilmesi için kullanılmıştır.

### ✔ State  
Odaların durum değişimleri (**Müsait → Rezerve → Dolu**) State Pattern ile tasarlanmıştır.

### ✔ Ekstra Kullanılan Tasarım Desenleri
- **Strategy:** Arama ve fiyat hesaplama stratejileri için.
- **Builder:** Çok alanlı nesneleri daha düzenli okunabilir ve hatasız oluşturmak için.

---

## 📦 Proje Yapısı
otel
├── .idea                  (IntelliJ ayar dosyaları)
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── config
│   │   │   │   └── DatabaseConnection.java
│   │   │   ├── dao
│   │   │   │   └── HotelDAO.java
│   │   │   ├── model
│   │   │   │   ├── CustomerDTO.java
│   │   │   │   ├── FamilyRoom.java
│   │   │   │   ├── Reservation.java
│   │   │   │   ├── Room.java
│   │   │   │   ├── StandardRoom.java
│   │   │   │   ├── SuiteRoom.java
│   │   │   │   └── User.java
│   │   │   ├── org.example
│   │   │   │   └── Main.java
│   │   │   ├── patterns
│   │   │   │   ├── factory
│   │   │   │   │   └── RoomFactory.java
│   │   │   │   ├── observer
│   │   │   │   │   ├── NotificationService.java
│   │   │   │   │   └── Observer.java
│   │   │   │   ├── state
│   │   │   │   │   ├── AvailableState.java   (State Pattern - Concrete)
│   │   │   │   │   ├── BookedState.java      (State Pattern - Concrete)
│   │   │   │   │   ├── OccupiedState.java    (State Pattern - Concrete)
│   │   │   │   │   └── RoomState.java        (State Pattern - Interface)
│   │   │   │   └── strategy
│   │   │   │       ├── DiscountPricingStrategy.java
│   │   │   │       ├── NormalPricingStrategy.java
│   │   │   │       └── PricingStrategy.java
│   │   │   └── view
│   │   │       └── MainFrame.java
│   │   │
│   │   └── resources      (Görseller ve ayar dosyaları)
│   │
│   └── test               (Test kodları)
│       └── java
│
├── target                 (Derlenmiş dosyalar)
├── .gitignore
├── pom.xml                (Maven ayarları)
└── External Libraries

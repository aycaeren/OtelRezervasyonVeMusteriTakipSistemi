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

## ⚡ Özellikler

- **Oda Yönetimi:** Standart, Suite ve Aile odaları için rezervasyon yönetimi.
- **Müşteri Takibi:** Müşteri bilgilerini kaydetme ve düzenleme.
- **Tasarım Desenleri Kullanımı:** Factory, Observer, State ve Strategy desenleri uygulanmıştır.
- **Veritabanı Bağlantısı:** `DatabaseConnection` sınıfı ile temel veritabanı işlemleri yapılabilir.
- **GUI Arayüzü:** `MainFrame` üzerinden kullanıcı dostu arayüz.

---

## 🛠️ Gereksinimler

- Java 11 veya üzeri
- Maven
- IntelliJ IDEA (tercihli)


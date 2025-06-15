# Staj Başvuru Takip Sistemi

Bu proje, öğrencilerin staj başvurularını düzenli bir şekilde takip etmelerini sağlayan web tabanlı bir uygulamadır. Kullanıcılar başvurdukları şirketleri, pozisyonları ve başvuru durumlarını kolayca yönetebilirler.

## Proje Amacı

Öğrencilerin staj başvuru sürecinde karşılaştıkları en büyük sorunlardan biri, hangi şirkete ne zaman başvurduklarını ve başvurularının hangi aşamada olduğunu takip etmektir. Bu sistem, bu sorunu çözerek öğrencilerin staj arama sürecini daha organize hale getirmeyi amaçlar.

## Özellikler

### Kullanıcı Yönetimi
- **Güvenli Kayıt Sistemi**: Şifreler hash'lenerek saklanır
- **Session Tabanlı Giriş**: Güvenli oturum yönetimi
- **Hesap Silme**: Kullanıcılar hesaplarını tamamen silebilir

### Başvuru Yönetimi (CRUD İşlemleri)
- **Başvuru Ekleme**: Yeni staj başvurularını sisteme kaydetme
- **Başvuru Listeleme**: Tüm başvuruları düzenli tablo halinde görüntüleme
- **Başvuru Düzenleme**: Mevcut başvuru bilgilerini güncelleme
- **Başvuru Silme**: Artık gerekmeyen başvuruları kaldırma

## 🛠️ Teknolojiler

- **Backend**: PHP (Yalın PHP, framework kullanılmamıştır)
- **Veritabanı**: MySQL
- **Frontend**: HTML5, CSS3, JavaScript
- **CSS Framework**: Bootstrap 5.3.0
- **Güvenlik**: PDO, Password Hashing, Sessions

## Dosya Yapısı

```
staj-takip-sistemi/
├── config.php          # Veritabanı bağlantısı ve genel ayarlar
├── index.php           # Ana sayfa (giriş/kayıt formu)
├── login.php           # Giriş işlemi
├── register.php        # Kayıt işlemi
├── logout.php          # Çıkış işlemi
├── dashboard.php       # Ana panel (başvuruları listeleme)
├── add.php             # Yeni başvuru ekleme
├── edit.php            # Başvuru düzenleme
├── delete.php          # Başvuru silme
├── delete_account.php  # Hesap silme
├── database.sql        # Veritabanı yapısı
└── README.md           # Proje dokümantasyonu
```

## Kurulum

1. **Dosyaları Sunucuya Yükleyin**
   ```bash
   # Dosyaları web sunucunuzun ana dizinine kopyalayın
   ```

2. **Veritabanını Oluşturun**
   ```sql
   # database.sql dosyasındaki komutları çalıştırın
   mysql -u username -p database_name < database.sql
   ```

3. **Veritabanı Ayarlarını Yapılandırın**
   ```php
   // config.php dosyasında aşağıdaki bilgileri güncelleyin
   $host = 'localhost';
   $dbname = 'your_database_name';
   $username = 'your_username';
   $password = 'your_password';
   ```

4. **Web Tarayıcısında Açın**
   ```
   http://yourdomain.com/index.php
   ```

## Kullanım

### 1. Hesap Oluşturma
- Ana sayfada "Kayıt Ol" butonuna tıklayın
- Kullanıcı adı, e-posta ve şifre bilgilerinizi girin
- Kayıt işlemi tamamlandıktan sonra otomatik olarak giriş yapılır

### 2. Başvuru Ekleme
- Dashboard'da "Yeni Başvuru Ekle" butonuna tıklayın
- Şirket adı, pozisyon, başvuru tarihi ve notları girin
- "Başvuru Ekle" butonuna tıklayarak kaydedin

### 3. Başvuru Yönetimi
- Başvurularınızı dashboard'da tablo halinde görüntüleyin
- "Düzenle" butonu ile başvuru bilgilerini güncelleyin
- "Sil" butonu ile gereksiz başvuruları kaldırın

## Demo Video

[Demo Video - Staj Başvuru Takip Sistemi](https://youtu.be/your-demo-video-link)

## Ekran Görüntüleri

### Ana Sayfa - Giriş/Kayıt Formu
![Ana Sayfa](screenshots/homepage.png)
*Kullanıcıların giriş yapabileceği veya yeni hesap oluşturabileceği ana sayfa*

### Dashboard - Başvuru Listesi
![Dashboard](screenshots/dashboard.png)
*Kullanıcının tüm staj başvurularını görüntüleyebileceği ana panel*

### Teknik Notlar

- PHP 7.4+ gereklidir
- MySQL 5.7+ desteklenir
- Bootstrap CDN üzerinden yüklenir
- Tarayıcı JavaScript desteği gereklidir

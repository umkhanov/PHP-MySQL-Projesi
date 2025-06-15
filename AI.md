
# Yapay Zeka Yardımı Sohbetleri

### Soru 1: <br>
Şifreleri veritabanında nasıl güvenli saklayabilirim?

### **Cevap :** <br>
PHP'de şifreleri güvenli saklamak için `password_hash()` ve `password_verify()` fonksiyonlarını kullanmalısınız:

```php
// Kayıt sırasında
$password_hash = password_hash($password, PASSWORD_DEFAULT);

// Giriş kontrolü sırasında  
if (password_verify($password, $user['password_hash'])) {
    // Şifre doğru
}
```

> Bu fonksiyonlar otomatik olarak `salt` ekler ve güvenli hash algoritmaları kullanır.

---

### **Soru 2:** <br>
Her sayfada kullanıcı girişi nasıl kontrol edilir?

### **Cevap :** <br>
Ortak bir `checkLogin()` fonksiyonu oluşturup her korumalı sayfada çağırabilirsiniz:

```php
function checkLogin() {
    if (!isset($_SESSION['user_id'])) {
        header('Location: index.php');
        exit();
    }
}

// Her korumalı sayfada
require_once 'config.php';
checkLogin();
```

> Bu şekilde kod tekrarını önler ve güvenliği merkezi olarak yönetirsiniz.

---

### Soru 3: <br>
SQL injection saldırılarından nasıl korunurum?

### **Cevap :** <br>
PDO prepared statements kullanarak SQL injection'dan korunabilirsiniz:

```php
// Güvensiz (kullanmayın)
$sql = "SELECT * FROM users WHERE username = '$username'";

// Güvenli
$stmt = $pdo->prepare("SELECT * FROM users WHERE username = ?");
$stmt->execute([$username]);
```

> `?` placeholder'ları kullanarak verileri otomatik olarak escape eder ve güvenli hale getirir.

---

### Soru 4: <br>
JavaScript validasyonu yeterli mi güvenlik için?

### **Cevap :** <br>
Hayır, JavaScript validasyonu sadece kullanıcı deneyimi için kullanılmalıdır. Güvenlik için mutlaka server-side validasyon yapmalısınız:

```php
// Server-side validasyon (güvenlik)
if (empty($username) || strlen($username) < 3) {
    header('Location: index.php?error=4');
    exit();
}
```

```javascript
// JavaScript sadece UX için
function validateLogin() {
    if (username.length < 3) {
        showError('Kullanıcı adı en az 3 karakter olmalı');
        return false;
    }
}
```

<br>——————————————————————————————————————————————————————————<br>

**Diğer sorular :**
Dosyaya yazdıklarımın dışında yapay zekaya başka küçük sorular da sordum.


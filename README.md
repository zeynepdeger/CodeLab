# CodeLab
The purpose of this repository is development
zeynep / backend
Backend  Raporu
Kullanıcı Giriş ve Kayıt Sistemi Backend

Proje Kapsamı:
bilgi yarışması
Kullanıcılar Türkiye haritasında şehirleri fethederek ilerleyecekler ve her doğru cevapla skorlar güncellenip şehirler fethedilecek.

1. Başlangıç ve Kurulum
a) Proje Başlatma ve Kurulum:
Yeni bir Node.js projesi başlatıldı.

Gerekli kütüphaneler kuruldu:

express (Web server)

cors (Cross-Origin Resource Sharing)

dotenv (Ortam değişkenleri)

firebase-admin (Firebase Admin SDK)

b) Dosya Yapısı:
server.js: Ana sunucu dosyası, API endpoint'lerini içeriyor.

package.json: Proje bağımlılıkları ve metadata.

firebase-adminsdk.json: Firebase service account dosyası.

2. Firebase Bağlantısı Kurulumu
a) Firebase Console'a Giriş:
Firebase projesi oluşturuldu ve Firebase Authentication özelliği aktif hale getirildi.

Service Account JSON dosyası indirildi ve projeye dahil edildi.

b) Firebase Admin SDK Kurulumu:
Firebase Admin SDK kullanılarak backend'de kullanıcı kaydı ve kullanıcı doğrulaması işlemleri için bağlantı sağlandı.

admin.auth().createUser() ve admin.auth().verifyIdToken() fonksiyonları kullanıldı.

3. Kullanıcı Kayıt (Register) API'sı
a) Kayıt API Endpoint'i (POST /register):
Email ve password bilgilerini alarak Firebase Authentication ile kullanıcı kaydedildi.

Başarılı kayıt işlemi sonrası userRecord'ün UID'si döndü.

b) Test:
Postman üzerinden kullanıcı kaydı test edildi.

Başarılı kayıt mesajı alındı.

4. Kullanıcı Giriş (Login) API'sı
a) Giriş API Endpoint'i (POST /login):
Kullanıcının email ve password bilgileri alındı.

Ancak şifre doğrulama işlemi Firebase Client SDK üzerinden yapılması gerektiğinden, idToken doğrulama backend tarafında yapılması gerektiği hatırlatıldı.

Plan: Frontend tarafında şifre doğrulama yapılacak, sonrasında idToken backend'e gönderilecek ve token doğrulaması yapılacak.

b) Test:
Giriş işlemi için başarıyla giriş yapılabilmesi için front-end tarafı ile birlikte çalışılacak.

5. İleriye Yönelik Adımlar
a) Frontend Entegrasyonu:
Firebase Client SDK kullanarak frontend tarafında email + password ile giriş ve kayıt işlemleri yapılacak.

idToken backend'e gönderilecek ve burada doğrulama yapılacak.

b) JWT Token ile Kimlik Doğrulama:
JSON Web Token (JWT) ile backend tarafında daha güvenli kimlik doğrulama işlemi yapılacak.

Kullanıcıya her girişte bir token verilecek.

c) Veritabanı Bağlantısı:
Kullanıcıların skorlarını ve fethedilen şehirlerini kaydetmek için veritabanı kullanılacak. Firebase Firestore veya MongoDB gibi çözümler kullanılabilir.

d) Admin Paneli:
Kullanıcı yönetimi için bir Admin Paneli eklenebilir, böylece adminler kullanıcıları ve verileri kolayca yönetebilir.

6. Sonuç
Firebase Authentication ile kullanıcı kayıt ve giriş sistemini başarıyla kurduk.

Server.js dosyasında gerekli tüm bağlantılar yapıldı.

Kullanıcılar başarıyla kaydedildi ve giriş işlemleri için hazırlık yapıldı.

Projenin backend kısmı güvenli, kolay ölçeklenebilir ve Firebase üzerinden çalışıyor.


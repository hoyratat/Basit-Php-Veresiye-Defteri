# Veresiye Defteri

Basit ve kullanıcı dostu bir PHP tabanlı veresiye defteri uygulaması. Müşterilerin borç ve ödeme işlemlerini takip etmek için tasarlanmıştır. SQLite veritabanı kullanır ve Bootstrap 5 ile modern bir arayüze sahiptir.

## Özellikler
- **Müşteri Yönetimi**: Müşteri ekleme ve isim değiştirme.
- **İşlem Yönetimi**: Borç ve ödeme işlemleri ekleme, silme (şifre korumalı).
- **Otomatik İşlem Ekleme Formu**: Müşteri seçildiğinde işlem ekleme formu otomatik açılır.
- **Borç Gösterimi**: Borçlar negatif (`-`), ödemeler pozitif olarak gösterilir.
- **CSV İndirme**: Türkçe Excel uyumlu CSV export (UTF-8 BOM, `;` ayırıcı).
- **Filtreleme**: Müşteriye göre işlem geçmişi filtreleme.
- **Sıralanabilir Tablolar**: Müşteri ve işlem tabloları sıralanabilir.
- **AJAX**: Dinamik veri güncelleme için AJAX kullanımı.
- **Toplam Borç**: Tüm müşterilerin toplam borcu, tıklanabilir şekilde (varsayılan kapalı).
- **Sayısal Format**: Sayılar 3 rakamda bir ayrılır (örn. `1.234,56`).

## Gereksinimler
- PHP 7.4 veya üstü
- SQLite PDO uzantısı (`pdo_sqlite`)
- İnternet bağlantısı (Bootstrap 5 ve jQuery CDN için)

## Kurulum
1. Bu depoyu klonlayın veya ZIP olarak indirin:
   ```bash
   git clone https://github.com/kullanici/veresiye_defteri.git
   ```
2. Dosyaları bir web sunucusuna (örn. Apache) yerleştirin, örneğin `/var/www/html/veresiye_defteri/`.
3. Sunucuda PHP ve SQLite PDO uzantısının yüklü olduğundan emin olun.
4. Tarayıcıda `index.php`'yi açın (örn. `http://localhost/veresiye_defteri/`).
5. SQLite veritabanı (`veresiye.db`) otomatik oluşturulur.

**Not**: Silme işlemleri için varsayılan şifre `sifre123`'tür. Üretimde bu şifreyi değiştirin (`index.php` içinde `if ($_POST['password'] === 'sifre123')` satırını güncelleyin).

## Kullanım
1. **Müşteri Ekleme**: "Müşteri Ekle" butonu ile yeni müşteri ekleyin.
2. **Müşteri Seçme**: Dropdown menüden bir müşteri seçin; işlem ekleme formu otomatik açılır.
3. **İşlem Ekleme**: Miktar, tür (Borç/Ödeme) ve isteğe bağlı açıklama girin, "Ekle" butonuna basın.
4. **İşlem Silme**: İşlem tablosunda "Sil" butonuna tıklayın, şifreyi girin (`sifre123`).
5. **CSV İndirme**: "CSV İndir" butonu ile tüm işlemleri Türkçe Excel uyumlu formatta indirin.
6. **İsim Değiştirme**: Müşteri tablosunda "İsim Değiştir" butonu ile müşteri adını güncelleyin.
7. **Toplam Borç**: "Toplam Borcu Göster" butonuna tıklayarak tüm müşterilerin toplam borcunu görün.

## Dosyalar
- `index.php`: Ana sayfa, müşteri ve işlem tablolarını gösterir.
- `add_customer.php`: Yeni müşteri ekler.
- `add_transaction.php`: İşlem ekler ve işlemleri listeler (AJAX için).
- `edit_customer.php`: Müşteri ismini günceller.
- `veresiye.db`: SQLite veritabanı (otomatik oluşturulur, .gitignore ile yoksayılır).

## Bağımlılıklar
- **Bootstrap 5**: Arayüz için (CDN üzerinden).
- **jQuery 3.6.0**: AJAX ve dinamik işlemler için (CDN üzerinden).
- **SQLite**: Veritabanı için (PHP PDO ile).

## Güvenlik Notu
- Silme işlemi için kullanılan şifre (`sifre123`) üretim ortamında değiştirilmelidir.
- Veritabanı dosyasını (`veresiye.db`) yedeklemeyi unutmayın.

## Lisans
MIT Lisansı - Detaylar için [LICENSE](LICENSE) dosyasına bakın (isteğe bağlı olarak eklenebilir).

## Katkıda Bulunma
Katkılarınızı bekliyoruz! Sorun bildirmek veya özellik önermek için GitHub Issues kullanabilirsiniz.
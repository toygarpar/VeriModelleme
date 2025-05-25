# Veri Tabanı ve Veri Ambarı  
## Veriyi Saklamak ve Analiz Edebilmek İçin İki Farklı Yapı

Veriler farklı yerlerde saklanır.  
AMA her bir yer farklı iş yapar.  

**Veritabanı**, günlük işlemler için kullanılır.  
**Veri Ambarı**, analizler için saklanır.  

Sayılar sessizken,  
onları nerede tuttuğumuz önemlidir.  
Çünkü veriyi nasıl saklarsan,  
önceki gibi analiz edersin.

---

## 1. Veritabanı Nedir?

## Veri Tabanı (Database)

### Tanım ve Temel Özellikler
Veri tabanı, günlük işlemler için optimize edilmiş yapılandırılmış veri topluluğudur. OLTP (Online Transaction Processing) sistemleri için tasarlanmıştır.

### Avantajlar
- **Veri Bütünlüğü**: Normalizasyon sayesinde veri tekrarını minimize eder
- **Hızlı Erişim**: İndekslerle optimize edilmiş sorgu performansı
- **İşlem Yönetimi**: ACID (Atomicity, Consistency, Isolation, Durability) prensipleri
- **Esnek İşlemler**: CRUD (Create, Read, Update, Delete) operasyonları

### Dezavantajlar
- **Maliyet**: Enterprise çözümlerde lisans ve bakım maliyetleri
- **Karmaşıklık**: Büyük ölçekli sistemlerde yönetim zorluğu
- **Analitik Limit**: Kompleks analizler için optimize değildir

### Temel Bileşenler
| Bileşen | Açıklama |
|---------|----------|
| **Tablo** | Satır (record) ve sütunlardan (field) oluşan veri yapısı |
| **Anahtarlar** | Primary Key (benzersiz tanımlayıcı), Foreign Key (ilişki kurucu) |
| **SQL** | DDL (şema tanım), DML (veri işlem), DCL (erişim kontrol) |
| **İndeksler** | Sorgu performansını artıran yapılar |


### Ana Kavramlar:

#### 📋 **Tablo**
Veri tabanında veriler satır ve sütunlarla saklanır.  
Her tablo bir konuya hizmet eder.

Ex:  
Müşteri tablosu → müşteri bilgilerini taşır  
Sipariş tablosu → sipariş geçmişini taşır

#### 🔑 **Anahtarlar**
Veriler arasında bağlantı kurmak içindir.

##### Primary Key  
Her kaydın eşsiz olduğunu gösterir.  
Boş olamaz.  
Yinelenemez.

Ex: `customer_id`

##### Foreign Key  
Başka tabloya bağlayan anahtardır.  
Primary key ile ilişkilidir.

Ex: `order.customer_id` → `customer.id`

#### 🔄 **Join İşlemleri**
Birden fazla tabloyu birleştirir.  
Her iki tablodaki ortak alanlar üzerinden yapılır.

Ex:  
Müşteri ve sipariş tablolarını birleştir.  
Hangi müşteri ne aldı?  
Bunu tek sorguda görebilirsin.

---

## 2. Veri Ambarı Nedir?

## Veri Ambarı (Data Warehouse)

### Tanım ve Temel Özellikler
OLAP (Online Analytical Processing) sistemleri için tasarlanmış, analitik odaklı büyük veri deposu.

### Temel Özellikleri
- **Konu Odaklı**: Belirli analiz alanlarına yoğunlaşır
- **Entegre Yapı**: Çoklu kaynaktan veri bütünleştirir
- **Zaman Boyutu**: Tarihsel veri tutma kapasitesi
- **Değişmezlik**: Genellikle salt okunur (read-only) yapı

### Avantajlar
- **Analitik Güç**: Büyük veri kümelerinde kompleks analiz
- **Karar Desteği**: Tarihsel trend analizleri
- **Sistem Performansı**: OLTP ve OLAP iş yüklerini ayırır
- **Veri Bütünlüğü**: Tek gerçek kaynak (single source of truth)

### Dezavantajlar
- **Uygulama Zorluğu**: Kurulum ve bakım karmaşıklığı
- **Esneklik Eksikliği**: Şema değişiklikleri zor
- **Maliyet**: Büyük veri altyapı gereksinimi

---

## Veritabanı mı, Veri Ambarı mı?

| Özellik | **Veritabanı (DB)** | **Veri Ambarı (DW)** |
|--------|----------------------|-----------------------|
| **Amacı** | Günlük işlemler | Analiz ve raporlama |
| **Veri Türü** | Güncel veri | Geçmiş veri |
| **İşlem Türü** | OLTP (Online Transactional Processing) | OLAP (Online Analytical Processing) |
| **Veri Yapısı/Modeli** | ER modeli | Star / Snowflake schema |
| **Performans** | Hızlı işlem | Uzun süreli analiz |
| **Kullanıcılar** | Yazılım geliştiriciler | Veri bilimciler, BI uzmanları |
| **SQL Kullanımı** | Evet, sıkça | Evet, ama daha karmaşık |
| **Erişim** | CRUD operasyonları | Çoğunlukla okuma |
| **Optimizasyon** | Yazma performansı | Okuma performansı |
| **Zaman Boyutu** | Mevcut veri | Tarihsel veri |
| **Boyut** | GB-TB seviyesi | TB-PB seviyesi |

---

## Mimari Farklılıklar

### Veri Tabanı Mimarisi
1. **İlişkisel Model**: Tablolar ve ilişkiler
2. **Normalleştirme**: 3NF (Üçüncü Normal Form) genellikle uygulanır
3. **İşlem Odaklı**: Hızlı insert/update operasyonları

### Veri Ambarı Mimarisi
1. **Dimensional Model**: Fact ve Dimension tabloları
2. **Denormalizasyon**: Analitik sorgular için optimize
3. **ETL Süreci**: Extract, Transform, Load iş akışı
4. **Data Mart**: Departmana özel alt ambar yapıları


---

## Veri Ambarı Nasıl Çalışır?

Veri ambarı, üç aşamada çalışır:

### 1. **Extract – Çekme**
Veriler dışarıdan alınır.  
CSV, Excel, API, log dosyası…  
Her yerden alınabilir.

### 2. **Transform – Dönüşüm**
Veriler düzenlenir.  
Temizlenir.  
Standardize edilir.  
Yeni özellikler çıkarılır.

### 3. **Load – Yükleme**
Hazırlanan veriler veri ambarına yüklenir.  
Burada analiz yapılır.  
Raporlar hazırlanır.  
Kararlar alınır.

> 📊 Grafik Açıklaması:  
Verilerin çeşitli kaynaklardan gelmesi → Transformasyon → Veri ambarına yükleme diyagramı  

---

## Veritabanı vs Veri Ambarı

| Özellik | **Veritabanı** | **Veri Ambarı** |
|--------|----------------|------------------|
| **Veri Tipi** | Yapılandırılmış | Yapılandırılmış + Yapılandırılmamış |
| **Analiz Türü** | Basit sorgular | Karmaşık analizler |
| **Zamanlama** | Gerçek zamanlı | Toplu işlem |
| **Veri Akışı** | Girdi çıkış var | Sadece okunabilir veri |
| **Şema** | Normalleşmiş | Star veya Snowflake Schema |
| **Performans** | Kayıt bazlı hızlı işlem | Raporlama ve analiz için optimize |
| **Kullanım Alanı** | CRM, ERP sistemleri | Satış analizi, müşteri segmentasyonu |

---

## SQL ile DB ve DW Arasındaki Fark

### ✅ Veritabanı için SQL
```sql
SELECT * FROM customers WHERE age > 30;
```
Anlık sorgular burada yapılır.  
Kayıt eklenebilir, silinebilir, güncellenebilir.

### ✅ Veri Ambarı için SQL
```sql
SELECT city, SUM(sales) AS total_sales 
FROM sales_data 
GROUP BY city;
```
Toplu analizler burada yapılır.  
Veri genellikle özetlenir.  
Karar verme için kullanılır.

---

## Kullanım Senaryoları

**Veri Tabanı İçin:**
- E-ticaret sipariş işleme
- Bankacılık işlemleri
- ERP sistem verileri
- CRM müşteri kayıtları

**Veri Ambarı İçin:**
- Satış trend analizleri
- Finansal performans raporlama
- Müşteri segmentasyonu
- Tahmine dayalı analitik

---

## Modern Gelişmeler
- **Data Lake**: Yapılandırılmamış veri depolama
- **Delta Lake**: Transaction özellikli data lake
- **Data Mesh**: Domain-driven dağıtık veri mimarisi
- **Cloud DW**: Snowflake, BigQuery, Redshift gibi bulut çözümleri

Veri tabanı ve veri ambarı birbirini tamamlayan sistemlerdir. Modern kurumsal mimarilerde her iki sistem de entegre şekilde kullanılarak hem operasyonel hem de analitik ihtiyaçlar karşılanmaktadır.

---

## Son Söz

Veritabanı, veriyi saklamak içindir.  
AMA veri ambarı, veriyi anlamak içindir.

Birisi hareketlidir.  
Diğeri düşündürücüdür.

Biri günlük işlemlerde yürür.  
Diğeri stratejik kararlarda konuşur.

Veri bilimi projelerinde ikisi de gereklidir.  
AMA farklı amaçlarla.  

Veri önce veritabanından gelir.  
Sonra veri ambarına aktarılır.  
Ve oradan anlamlı sonuçlar çıkarılır.

Sayılar sessizken  
biz onları doğru yerde saklayıp  
doğru şekilde dinlemeliyiz.

---


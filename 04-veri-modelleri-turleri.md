# Veri Modellerinin Türleri  

Veri modelleme, bir organizasyonun veri yapısını anlamak, tasarlamak ve uygulamak için kullanılan temel bir süreçtir. 

## Üç Seviye: Conceptual → Logical → Physical

Veri modelleme, bir veritabanının nasıl yapılandırılacağını gösterir.  
AMA bu yapılandırma birden fazla aşamada olur.  
Her aşama farklı bir amaca hizmet eder.

Üç ana veri modeli vardır:
1. **Kavramsal Model** – Sistem ne içeriyor?
2. **Mantıksal Model** – Nasıl tanımlanmalı?
3. **Fiziksel Model** – Gerçek ortama göre nasıl çalışacak?

Veri bilimi projelerinde her model farklı bir rol oynar.  
Ve hep birlikte çalışır.

---

## 1. Kavramsal Veri Modeli  

Tanım: Sistemin içerdiği temel varlıkları ve bunlar arasındaki ilişkileri gösteren üst düzey model.

### Sistem Ne İçeriyor?

Bu model, sistemin genel yapısını gösterir.  
Detay yoktur.  
AMA temel varlıklar ve ilişkiler bellidir.

#### **Özellikleri**:

- İş paydaşları ve veri mimarları tarafından kullanılır
    
- Gerçek dünya nesnelerini (varlıklar) ve bunların özelliklerini (nitelikler) tanımlar
    
- Varlıklar arasındaki ilişkileri gösterir
    
- Teknik detaylardan bağımsızdır
    
- Paydaşlar için ortak bir dil oluşturur

#### Kimler Kullanır?
- İş analistleri  
- Yöneticiler  
- Veri mimarları  

#### Örnek:
Bir alışveriş sitesinde şu varlıklar yer alabilir:  
**Müşteri**, **Ürün**, **Sipariş**

AMA nasıl bağlılar?  
Kim hangi ürünü aldı?  
Hangi tarihlerde?

Bu sorular henüz burada cevaplanmaz.  
AMA varlıklar bellidir.

> 📊 Grafik Açıklaması:  
Varlık-ilişki diyagramında üç kutu: Müşteri, Ürün, Sipariş  
Arada oklarla bağlantılar var ama detay yok  

---

## 2. Mantıksal Veri Modeli  

Tanım: Veri öğelerinin yapısını ve ilişkilerini detaylı şekilde tanımlayan model.

### Sistem Nasıl Tanımlanmalı?

Burada varlıklar daha net tanımlanır.  
Nitelikler belirlenir.  
Anahtarlar seçilmeye başlanır.

AMA yine de teknolojiden bağımsız kalınır.  
Yani SQL mi NoSQL mi kullanılacağı burada karar verilmez.

#### Özellikler:
- Nitelikler detaylandırılır  
- Primary key belirlenir  
- Foreign key tanımlanır  
- Normalleştirme yapılır  
- İlişkiler netleştirilir  

#### Örnek:
**Müşteri** varlığına bakalım:

- `MusID` – Tam sayı (PK)  
- `MusAdı` – Karakter  
- `MusSoyadı` – Karakter  
- `DogumTar` – Tarih  

**Ürünler**:

- `UrunNo` – Tam sayı (PK)  
- `UrunAdı` – Karakter  
- `Fiyatı` – Para  
- `StokAdedi` – Tam sayı  

İlişkiler kurulur.  
AMA tablo isimleri veya indexler henüz yoktur.

> 📊 Grafik Açıklaması:  
Tabloya benzeyen kutular.  
Her kutuda nitelikler listelenmiş.  
Bağlantılar çizilmiş.  
AMA fiziksel sütun tipleri ve sistem detayları yok.

---

## 3. Fiziksel Veri Modeli  

Tanım: Belirli bir veritabanı yönetim sisteminde uygulanacak teknik model.

### Gerçek Ortama Göre Yapılandırma

Bu model, veritabanına uygulanacak son yapıdır.  
Her şey netleştirilir.  
Primary key kullanılır.  
Foreign key tanımlanır.  
Indexler oluşturulur.  
Stored Procedure'ler yazılır.

Burada artık sistem belli bir teknolojiye bağlanmıştır.  
MySQL, PostgreSQL, Oracle gibi RDBMS’lerde çalışır.

#### Özellikler:
- Veritabanı şemasına uygun yapı  
- Tablo isimleri ve kolonlar tanımlanmış  
- PK ve FK açıkça belirtilmiş  
- Indexler ve constraint'ler tanımlanmış  
- Stored procedure ve trigger bilgisi yer alabilir  

#### Örnek:
**Müşteri Tablosu**  
```sql
CREATE TABLE musteri (
    mus_id INT PRIMARY KEY,
    mus_adi VARCHAR(50),
    mus_soyadi VARCHAR(50),
    dogum_tarihi DATE
);
```

**Ürün Tablosu**
```sql
CREATE TABLE urun (
    urun_no INT PRIMARY KEY,
    urun_adi VARCHAR(100),
    fiyat DECIMAL(10,2),
    stok_adedi INT
);
```

**Sipariş Tablosu**
```sql
CREATE TABLE siparis (
    siparis_id INT PRIMARY KEY,
    mus_id INT,
    urun_no INT,
    tarih DATE,
    FOREIGN KEY (mus_id) REFERENCES musteri(mus_id),
    FOREIGN KEY (urun_no) REFERENCES urun(urun_no)
);
```

> 📊 Grafik Açıklaması:  
Gerçek tablo yapıları.  
PK ve FK işaretlenmiş.  
Veritabanı motoruna özel yapılar.  
Indexler, ilişkiler gösterilmiş.

---

## Karşılaştırmalı Tablo: Veri Modeli Türleri

| Özellik | **Kavramsal** | **Mantıksal** | **Fiziksel** |
|--------|----------------|----------------|----------------|
| **Amacı** | Sistem kapsamını göstermek | Yapısal ilişkiyi tanımlamak | Gerçek uygulama için tasarım |
| **Kime Yönelik** | Paydaşlar | Veri analistleri | Veri mühendisleri |
| **PK / FK** | Yok | Belirlenmiş ama uygulanmamış | Uygulanmış |
| **Teknoloji Bağımlılığı** | Bağımsız | Bağımsız | Bağımlı (RDBMS’e özel) |
| **Kullanım Alanı** | Planlama | Tasarım | Gerçek üretim |

---

## Veri Modeli Diyagramı Oluşturma

Veri modeli diyagramları genellikle şu araçlarla oluşturulur:

1. **ER Diyagramları** (Varlık-İlişki diyagramları)
    
2. UML Sınıf Diyagramları
    
3. Özel veri modelleme araçları (ERwin, PowerDesigner, Lucidchart vb.)
    

Temel adımlar:

1. Varlıkları belirle
    
2. Nitelikleri tanımla
    
3. Birincil anahtarları ata
    
4. İlişkileri çiz
    
5. Kardinaliteleri belirle (1-1, 1-N, N-M)
    
6. Fiziksel özellikleri ekle (veri tipleri, kısıtlamalar)

---

## Son Söz

Veri modellemek;  
verilerin arasında bağlantı kurmaktır.  
Sayıların anlam kazanması sürecidir.

Kavramsal modelle başlayıp  
mantıksal modele geçersin.  
Sonunda fiziksel yapıyı kurarsın.

Model olmadan veri sessiz kalır.  
AMA model ile veri konuşur.  
Ve biz dinleyip anlarız.

Sayılar kendi başına anlam taşımaz.  
AMA onları doğru yapıyla düzenlersen  
bilgi doğar.  
Karar alınır.  
Geleceğe bakılır.

---


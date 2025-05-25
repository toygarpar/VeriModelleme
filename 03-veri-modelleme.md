# Veri Modelleme  
## Sayıların Anlamını Tanımlamak

Veri bilimi projelerinde her şey veriyle başlar.  
AMA veri ne anlama geliyor?  
Nasıl bir yapıyla saklanıyor?  
Hangi ilişkiler var?

Bu soruların cevabını veri modelleme verir.

Veri modelleme;  
verilerin nasıl tanımlandığını,  
nasıl yapılandırıldığını,  
ve birbirleriyle nasıl ilişkilendirildiğini gösterir.

Veri modeli, yazılımdaki mimari plan gibidir.  
Bina önceden çizilir.  
Sonra inşa edilir.  
Veri modeli olmadan sistemler düzensiz olur.  
Ve zamanla çöker.

---

## Veri Nedir?

Veri, ham maddedir.  
İşlenmemiş sayılardır.  
Metinlerdir.  
Resimlerdir.  
AMA anlam kazanmadığı sürece sessiz kalır.

Ex:  
“Ahmet” bir isimdir.  
AMA sadece “Ahmet” yazarsa, bu veri değildir.  
“Müşteri Adı: Ahmet” derse, artık bağlam kazanmıştır.

---

## Veri Modelleme Nedir?

Veri modelleme, verilerin yapısını tanımlamaktır.  
Veri tabanında neler olacak?  
Nasıl ilişkili olacaklar?  
Hangi kurallar geçerli olacak?

Bu soruların hepsi veri modellemesiyle çözülür.

### Kullanım Alanları:
- İş Zekası (Business Intelligence)  
- Veri Madenciliği  
- Veri Ambarı Geliştirme  
- Raporlama  
- Analitik Uygulamalar  

Veri modelleme ile iş süreçleri daha tutarlı hale gelir.  
Veri akışı düzenli olur.  
Analizler daha anlamlı sonuçlar verir.

---

## Veri Modelinin Önemi

Veri modeli, soyut bir plandır.  
AMA onun eksik olduğu yerde:  
- Veri tekrar eder  
- Tutarlılık bozulur  
- Kararlar yanlış olur  

### Neden Gerekli?
- Nesneler doğru temsil edilmelidir  
- Kurallar tanımlanmalıdır  
- Veri bütünlüğü sağlanmalıdır  
- Eksik veya gereksiz veriler tespit edilmelidir  

Model olmadan veri kargaşadır.  
Model ile veri anlaşılır.

---

## Veri Modeli Türleri

### 1. Kavramsal Veri Modeli – Sistem Ne İçeriyor?

Veri modelinin en üst düzeyidir.  
Teknik detay yoktur.  
Yalnızca ana nesneler ve ilişkiler belirlenir.

#### Kimler için kullanılır?
- İş analistleri  
- Yöneticiler  
- Veri mimarları  

Ex:  
Bir üniversitede öğrenciler ve dersler var.  
AMA nasıl bağlılar?  
Her öğrenci birden fazla derse kayıt olabilir mi?  
Her dersi kim öğretiyor?

Bu model, sistemin genel yapısını gösterir.

> Grafik Açıklaması:  
Varlıklar arası ilişki diyagramı.  
Öğrenci ↔ Ders ↔ Hoca  

---

### 2. Mantıksal Veri Modeli – Nasıl Tanımlanmalı?

Daha detaylıdır.  
Veri ilişkileri tanımlanır.  
AMA teknolojiden bağımsız çalışır.

#### Ne içerir?
- Varlıklar (Entities)  
- Nitelikler (Attributes)  
- İlişkiler (Relationships)  

Ex:  
Müşteri varlığına bakalım.  
ID, ad, soyad, doğum tarihi özellikleri vardır.  
Satış varlığına sahip.  
Ürünlerle ilişkilidir.  

Model, tüm bu bağlantıları gösterir.  
AMA henüz SQL ya da NoSQL’e göre yazılmamıştır.

> Grafik Açıklaması:  
Tablo benzeri yapılar.  
Her birinde kolonlar.  
Arada oklarla bağlantılar  

---

### 3. Fiziksel Veri Modeli – Gerçek Ortama Göre Yapılanma

Gerçek dünyadaki uygulama aşamasıdır.  
RDBMS'e göre yapılır.  
Veritabanına uygun şekilde şekillenir.

#### Ne içerir?
- Tablo isimleri  
- Kolon tipleri  
- Primary Key, Foreign Key  
- Indexler  

Ex:  
Müşteri tablosunda `customer_id` primary key’tir.  
Satış tablosunda `customer_id` foreign key’tir.  
Böylece iki tablo birbirine bağlanır.

> Grafik Açıklaması:  
Fiziksel tablolar.  
PK ve FK gösterimi.  
Veritabanı şeması  

---

## Veri Modeli ile İlgili Temel Kavramlar

### Varlık (Entity)  
Gerçek dünyadaki bir nesnedir.  
Müşteri, ürün, sipariş gibi.

### Nitelik (Attribute)  
Varlığın özellikleridir.  
Müşteri varsa, adı, soyadı, doğum tarihi nitelikleridir.

### İlişki (Relationship)  
Varlıklar arasındaki bağdır.  
Bir müşteri birçok ürünü satın alabilir.  
Bir ürün birçok müşteriyi çekebilir.

---

## Örnek 1: Müşteri ve Ürün Satışı

### Varlıklar:
- **Müşteri:** ID, ad, soyad  
- **Ürün:** ürün no, ürün adı, fiyatı  

### İlişki:  
Müşteri → Ürünleri satın alır.

> Grafik Açıklaması:  
Müşteri tablosu ↔ Sipariş tablosu ↔ Ürün tablosu  

---

## Örnek 2: Öğrenciler ve Dersler

### Varlıklar:
- **Öğrenci:** numara, ad, soyad, cinsiyet, doğum tarihi  
- **Ders:** dersID, dersAdı, dersHocası, dersSaati  

### İlişki:  
Öğrenci ↔ Ders kayıtları  

> Grafik Açıklaması:  
Öğrenci tablosu ↔ Kayıt tablosu ↔ Ders tablosu  

---

## Son Söz

Veri modelleme,  
veriyi anlamak için yapılan ilk adımdır.  
Sayılar arasında yatan bağlantıları gösterir.  
İş süreçlerini düzenler.  
Kararları destekler.

Kavramsal modelle başlayıp  
mantıksal modele geçer.  
Sonunda fiziksel yapıya oturturuz.

Veri bilimi projesi yapacaksan,  
modelle başlar,  
analizle devam eder,  
kararla biter.



---



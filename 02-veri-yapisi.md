# Veri Yapıları / Data Structure

## Veri Nasıl Saklanır? Nasıl Yapılanır?

Veriler farklı şekillerde saklanabilir.  
Her veri farklı bir yapıyla işlenebilir.  
Bu yüzden veri yapılarını bilmek önemlidir.

Veri yapıları, verinin nasıl düzenlendiğini gösterir.  
Modeller ise bu yapıların nasıl kullanılacağını anlatır.

Veri bilimciler bu yapılara göre karar alır.  
Analiz eder.  
Model kurar.  
Ve anlam çıkarır.

---

## Veri Yapıları ve Modeller

### 1. Hiyerarşik Model  
Veri ağaç şeklinde düzenlenir.  
Bir ana düğüm vardır.  
Alt düğümlere doğru inilir.

Ex:  
XML dosyaları hiyerarşik yapıya sahiptir.  
Ana kategori → Alt kategoriler → Ürünler gibi.

### 2. Ağ Modeli  
Hiyerarşik değil, ama bağlantılıdır.  
Birden fazla ilişki olabilir.  
Her düğüm birden fazla başka düğüme bağlanabilir.

Ex:  
Sosyal ağlar – kişi A ile B, C ile D ilişkili olabilir.

### 3. İlişkisel Model  
En yaygın modellerden biridir.  
Tablolar arasında ilişki kurulur.  
SQL ile sorgulanır.

Ex:  
Müşteri tablosu → Sipariş tablosu  
İki tablo ortak bir alan üzerinden bağlanır (customer_id)

### 4. Nesne Yönelimli Model  
Veriler nesnelerle tanımlanır.  
Her nesnenin özellikleri vardır.  
Metotları vardır.  
Bu yapılar programlamada sıkça kullanılır.

Ex:  
Python’da bir “müşteri” sınıfı oluşturulabilir.  
Adı, soyadı, siparişleri bu sınıfta tanımlanır.

---

## Veri Analizi Adımları

Veri yapısını bilmek yetmez.  
Onu anlamak için adımlar vardır.

### 1. Verileri İnceleme  
Sayılara bakılır.  
Dağılım incelenir.  
Boş değerler tespit edilir.  
Outlier’lar görülür.

### 2. Verileri Temizleme  
Eksik veriler tamamlanır.  
Yanlış satırlar silinir.  
Tutarlılık sağlanır.

### 3. Verileri Dönüştürme  
Veri yeni forma sokulur.  
Özellikler çıkarılır.  
Değişkenler dönüştürülür.  
Feature engineering yapılır.

### 4. Modelleme  
Veri artık anlamlıdır.  
Şimdi model kurulur.  
Regresyon mu? Sınıflandırma mı?  
Uygun model seçilir.

---

## Veri Analiz Yöntemleri

### 1. İstatistiksel Yöntemler  
Ortalama, medyan, standart sapma gibi temel istatistikler kullanılır.  
Sayılar arasında bağlantı kurulur.  
Trendler bulunur.  
Gelecek tahmin edilir.

### 2. Veri Madenciliği  
Gizlenmiş desenleri bulmak içindir.  
Sınıflandırma, kümeleme, regresyon gibi teknikler kullanılır.  
Veriden bilgi çıkarılır.

---

## Büyük Veri Kavramı

Veri arttıkça eski yöntemler yetersiz kalır.  
Veri çok büyükse, çok hızlıysa ya da çok çeşitliyse,  
bu veriye **Büyük Veri (Big Data)** denir.

AMA büyük veri ne demektir?  
Veri tek sunucuda işlem yapamıyorsa,  
veri her dakika yenisiyle büyüyor ve değişiyorsa,  
ve onu anlamak için özel araçlara ihtiyaç varsa,  
bu veri büyük veridir.

---

## Büyük Verinin Özellikleri – 6V

### 1. Volume (Hacim)  
Veri çok büyüktür.  
Milyonlarca satır olabilir.  
Diskte yer tutar.  
AMA değeri yoksa, hacim önemsizdir.

### 2. Velocity (Hız)  
Veri sürekli gelir.  
Her milisaniyede yeni veri oluşur.  
Gerçek zamanlı analiz gerekir.

Ex:  
Twitter tweetleri, IoT cihazlarından gelen veriler

### 3. Variety (Çeşitlilik)  
Veri hem sayı olabilir hem de resim.  
CSV, JSON, XML, video, ses gibi birçok formatta olabilir.  
Çeşitli kaynaklardan gelir.

### 4. Veracity (Doğruluk)  
Veri güvenilir mi?  
Kaynağı nedir?  
Yanlış mı? Eksik mi?  
Düzenlenmemiş mi?

Veracity, veri kalitesini ölçer.  
Kalitesiz veri, yanlış karar verir.

### 5. Value (Değer)  
Veri toplanmış ama faydası yoksa,  
bu veri gereksizdir.  
Elde edilen veri, şirketin işine yaramalıdır.  
Değilse, depolanması bile boşuna olur.

### 6. Visualization (Görselleştirme)  
Sayılar bazen sessiz kalır.  
Görseller konuşur.  
Grafikler trendleri gösterir.  
Dashboard’lar karar verir.

---

## Karşılaştırmalı Tablo: Veri Modelleri

| Model Türü | Açıklama | Kullanım Alanı |
|------------|----------|------------------|
| **Hiyerarşik** | Ağaç yapısı | XML, organizasyon yapıları |
| **Ağ** | Serbest bağlantılar | Sosyal ağlar |
| **İlişkisel** | Tablo + ilişki | SQL veritabanları |
| **Nesne Yönelimli** | Nesnelerle yapılandırma | Python, Java |

---

## Son Söz

Veri yapıları, veriyi anlamak için ilk adımın atılmasıdır.  
Hiyerarşi, ağ, ilişki, nesne…  
Her yapı farklıdır.  
AMA hepsi aynı amaca hizmet eder:  
**Veriyi işlenebilir hale getirmek.**

Büyük veri ise,  
veriyi yönetmek için yeni yöntemler doğurmuştur.  
Hız, hacim, çeşitlilik, doğruluk, değer ve görselleştirme  
bütün bu V’ler birleşince  
veri bilimi gerçek büyüklük kazanır.

Veri olmadan analiz yoktur.  
Yapı olmadan veri anlamsızdır.  
Ve büyük veri olmadan geleceğe dair fikir çıkmaz.

Veriler sessizken,  
biz onları dinlemeliyiz.  
Ve onların hangi yapıda olduğunu bilmeliyiz.
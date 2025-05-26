# Veri Kalitesi ve Bütünlüğü  
## Sayılar Sessizken, Kalite Konuşur

Veri bilimi projelerinde veri her şeydir.  
AMA veri kaliteli değilse,  
analiz eksik olur.  
Karar yanlış alınır.

Veri kalitesi,  
verinin doğru mu,  
güvenilir mi,  
eksik mi,  
tutarlı mı  
olduğunu gösterir.

Ve veri bütünlüğü,  
bu verilerin yaşam döngüsü boyunca  
nasıl korunduğunu ifade eder.

---

## Veri Nedir?

Veri kalitesi, verinin kullanım amacına uygun olup olmadığını gösterir. İyi bir veri, belirlenen gereksinimleri karşılar.

**Veri Kalitesi Unsurları:** Doğruluk, Güvenilirlik, Tamlık, Zamanlılık, Kapsamlılık, Tutarlılık, Detaylılık.

- **Doğruluk:** Verinin doğru ve geçerli olması.
- **Güvenilirlik:** Verinin toplanma, işlenme, saklanma ve kullanma süreçlerinde tutarlılık göstermesi.
- **Tamlık:** Gerekli tüm verilerin eksiksiz, güncel ve uygun şekilde bulunması.
- **Zamanlılık:** Veriye ait zaman bilgisinin doğru ve güncel olması.
- **Kapsamlılık:** Gerekli tüm veri öğelerinin ve verinin bütününün, belirlenen kapsam dahilinde toplanması.
- **Tutarlılık:** Verinin güvenilir olması ve tüm uygulamalarda aynı sonuçları vermesi.
- **Detaylılık:** Verinin yeterli miktarda alt bilgiyi içermesi.

Veri, bilginin işlenmemiş halidir.  
Sayılar, harfler, işaretlerdir.  
AMA anlam kazanması için yapılandırılmalıdır.

Ex:  
“Ahmet” → sadece bir isimdir.  
AMA “Müşteri Adı: Ahmet” dersek, artık bağlam kazanmıştır.

---

## Veri Kalitesi Nedir?

Kaliteli veri,  
doğru zamanda,  
doğru biçimde,  
ve doğru amaca hizmet eden veridir.

### Veri Kalitesinin Temel Özellikleri

#### 1. Doğruluk  
Veri gerçekliği yansıtmalıdır.  
Yanlış yazılmış bir yaş ya da fiyat,  
kararları bozar.

#### 2. Güvenilirlik  
Veri toplanırken, işlenirken, saklanırken  
her aşamada aynı sonucu vermeli.  
Çünkü güvenilir veri, doğru karar demektir.

#### 3. Tamlık  
Tüm gerekli veriler mevcut olmalı.  
Eksik satırlar yok olmalı.  
Veri, analiz için tam olmalı.

#### 4. Zamanlılık  
Veri güncel olmalı.  
Eski veri geçmişe aittir.  
AMA biz gelecekteki kararlar için kullanıyoruz.

#### 5. Kapsamlılık  
Veri, belirlenen tüm alanları kapsamalı.  
Eksik bırakılan nokta, eksik analiz demektir.

#### 6. Tutarlılık  
Farklı sistemlerdeki veri aynı olmalı.  
Bir yerde “Erkek”, başka yerde “E” dememeli.  
Tutarlılık, sistemin temelidir.

#### 7. Detaylılık  
Veri, istenen düzeyde detay içermeli.  
Az detayla tahmin zordur.  
Çok fazla detay ise yavaşlatır.

---

## Veri Kalitesini Bozan Etmenler

Veri her zaman ideal değildir.  
Kimisi hatalıdır.  
Kimisi eksiktir.  
Kimisi tekrar eder.  
Kimisi de tutarsızdır.

### En Yaygın Kalite Sorunları:
- **İnsan hatası:** Yanlış girilen değerler  
- **Sistem hatası:** Yazılım çökmesi, veri kaybı  
- **Hatalı cihazlar:** Sensörlerden gelen anormal veri  
- **Tekrarlı veri:** Aynı müşteri iki kez kayıt olmuş  
- **Eksik veri:** Bir hücre boş bırakılmış  
- **Geçersiz veri:** Yaş 200 yazılmış  

---

## Veri Temizleme Süreci

Temiz veri, temiz analiz demektir.  
AMA veri her zaman temiz gelmez.  
Bu yüzden adım adım ilerlemek gerekir.

### 1. **Analiz**
Veriyi incele.  
Nerede eksiklik var?  
Nerede hata var?  
Nasıl bir yol izlenecek?

### 2. **Planlama**
Nasıl düzelteceksin?  
Eksik veri nasıl doldurulacak?  
Outlier’lar nasıl işlenecek?

### 3. **Geliştirme**
Ham veriyi düzenle.  
Eksik veriye ortalama ver.  
Ya da sil.  
Ya da regresyonla tahmin et.

### 4. **Test ve Doğrulama**
Temizlenmiş veriyi test et.  
Doğru sonuç verecek mi?  
Hala tutarsız veri var mı?

### 5. **Kaliteli Veri**
Artık veri analiz edilebilir.  
Model kurulabilir.  
Karar verilebilir.

---

## Eksik Veri Nasıl İşlenir?

| Yöntem | Açıklama |
|--------|----------|
| `dropna()` | Eksik satırları silmek için kullanılır |
| `fillna(0)` | Eksik değerleri sabit bir sayı ile doldurmak için |
| `fillna(mean)` | Ortalama ile doldurma |
| `fillna(class mean)` | Sınıf ortalaması ile doldurma |
| **Regresyon modeli** | Eksik değeri tahmin edebilirsin |

---

## Veri Optimizasyonu

Büyük veri kümelerinin işlenmesi ve zaman kısıtlamaları nedeniyle veri optimizasyonu gerekebilir. Optimizasyondan önce veri temizliği yapılması önemlidir.

Veri çok büyükse işlem zorlaşır.  
AMA veri azaltıldığında bile bilgi kaybolmazsa,  
optimizasyon yapılabilir.

### Hangi Yollarla?
- **Veri birleştirme:** Birden fazla tabloyu tek hale getir  
- **Veri küpü:** Farklı boyutlardan bakmak için  
- **Boyut indirgeme:** Çok fazla sütun varsa azaltılabilir (PCA gibi yöntemlerle)  
- **Örnekleme:** Büyük veriden küçük örnek almak  
- **Boyut sıkıştırma:** Bellekten tasarruf sağlamak  

> Grafik Açıklaması:  
Eksik verilerin doldurulduğu diyagram.  
Boyut indirgenmiş veriyle ML model eğitimi.  

---

## Veri Bütünlüğü Nedir?

Veri bütünlüğü,  
verinin yaşam döngüsü boyunca  
doğruluğunun ve tutarlılığın  
korunmasını sağlar.

AMA bazı şeyler bu bütünlüğü bozabilir:

### Veri Bütünlüğünü Bozanlar:
- **Kötü niyetli işlemler** – kötü amaçlı erişim  
- **İnsan hatası** – yanlış veri girişi  
- **Donanım hatası** – disk arızaları, sensör sorunları  
- **Tasarım hatası** – uygunsuz veri yapısı  

### Veri Bütünlüğünü Sağlayanlar:
- **Standart prosedürler:** Herkes aynı kurallara göre çalışmalı  
- **Veritabanı tasarımı:** Primary key, foreign key tanımları ile bütünlük sağlanır  
- **Düzenli bakım:** Veri yıpranmaz ama yazılım bozulabilir  
- **Veri doğrulama kuralları:** Giriş sırasında kontrol sağlanması, veri doğrulama kurallarının oluşturulmasıdır. 

---

## Son Söz

Veri bilimi, veriyle başlar.  
AMA veri kaliteli değilse,  
sonuçlar yanıltıcı olur.

Veri temizlenmelidir.  
Optimize edilmelidir.  
Bütün kalitede korunmalıdır.


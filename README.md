# MLSAI_MLProject

# PROJENİN AMACI:
  Perakende satış işlemleri verilerini kullanarak hem gözetimli hem de gözetimsiz öğrenme tekniklerini uygulamaktır. Bu bağlamda, gözetimli öğrenme ile müşteri davranışlarını ve satın alma eğilimlerini tahmin edecek modeller geliştirilecek, gözetimsiz öğrenme ile ise müşterilerin benzerliklerine göre segmente edilmesi sağlanacaktır.

  Projenin iki ana hedefi şunlardır:

***Müşteri Harcama Tahmini (Gözetimli Öğrenme - Doğrusal Regresyon)***: Müşterilerin harcama tutarlarını ve alışveriş davranışlarını tahmin eden modeller oluşturmak. Bu tahminler, mağazaların gelecekteki talepleri öngörmesine ve stratejik kararlar almasına yardımcı olacaktır.

***Müşteri Segmentasyonu (Gözetimsiz Öğrenme - K-Means Clustering)***: Müşterileri, satın aldıkları ürünlerin toplam maliyeti ve miktarı gibi özellikler kullanılarak segmente etmek. Bu segmentasyon, farklı müşteri gruplarının belirlenmesine ve özelleştirilmiş pazarlama stratejilerinin geliştirilmesine olanak sağlayacaktır.

  Bu projeyle, perakende sektöründeki müşteri davranışlarının analizi ve tahmini yapılırken, işletmelerin karar verme süreçlerini optimize eden veri odaklı çözümler sunulacaktır.

# VERİ SETİ:
Kullanılan dataset, 1000000 satırdan ve 13 sütundan oluşmaktadır. Sütun isimleri ise sırasıyla şu şekilde:

* Transaction_ID: Her işlem için 10 basamaklı bir sayı olarak gösterilen benzersiz bir tanımlayıcı. Bu sütun her satın alımı benzersiz şekilde tanımlamak için kullanılır.
* Date: İşlemin gerçekleştiği tarih ve saat. Her satın alımın zamanını kaydeder.
* Customer_Name: Satın alma işlemini gerçekleştiren müşterinin adıdır. Müşterinin kimliği hakkında bilgi sağlar.
* Product: İşlemde satın alınan ürünlerin listesi. Satın alınan ürünlerin adlarını içerir.
* Total_Items: İşlemde satın alınan toplam ürün sayısı. Satın alınan ürün miktarını temsil eder.
* Total_Cost: Satın alma işleminin toplam maliyeti, para birimi cinsinden. İşlemin finansal değerini temsil eder.
* Payment_Method: İşlemde ödeme için kullanılan yöntem (kredi kartı, banka kartı, nakit veya mobil ödeme gibi). 
* City: Satın alma işleminin gerçekleştiği şehir. İşlemin yerini belirtir.
* Store_Type: Alışverişin yapıldığı mağazanın türü (süpermarket, market, alışveriş merkezi vb.).
* Discount_Applied: İşleme indirim uygulanıp uygulanmadığını gösteren ikili gösterge (True/False).
* Customer_Category: Müşterinin geçmişini veya yaş grubunu temsil eden bir kategori.
* Season: Satın alma işleminin gerçekleştiği mevsim (ilkbahar, yaz, sonbahar veya kış gibi).
* Promotion: İşlem için uygulanan promosyon türü, örneğin "Hiçbiri", "BOGO (Bir Al Bir Bedava)" veya "Seçili Ürünlerde İndirim".

# DEĞİŞKENLER:
Gözetimli Öğrenme için: Bağımlı değişken(y) "Total_Cost" sütunu, bağımsız değişkenler(x) ise "Total_Cost" sütunu hariç tüm sütunlar olarak belirlenmiştir. Çeşitli regresyon algoritmaları denenerek bağımlı değişkeni bulmaya çalışılır.

Gözetimsiz Öğrenme için: "Total_Cost" ve "Total_Items" gibi sayısal sütunları kullanarak gruplama yapıldı.

# MODEL SEÇİMİ:
Gözetimli Öğrenme için: En iyi performansı veren algoritma seçildi ve seçilen algoritmanın değerlendirilmesi yapıldı. Bu projede en iyi performansı veren regresyon modelinin Doğrusal Regresyon olduğuna karar verilmiştir. Değerlendirme sürecinde bu projede "Ortalama Karesel Hata(Mean Squared Error)", "R^2 score" kullanılmıştır. Buna ek olarak modelin nasıl tahmin yaptığını tam anlamak için ek analizler yapmak faydalı olabileceğinden; tahmin ve gerçek değerlerin karşılaştırılması yapıldı, hata analizini yapmak için tahmin edilen değerlerle gerçek değerler arasındaki farkları incelendi ve modelin genel performansını doğrulamak için Cross-Validation yapıldı.

Gözetimsiz Öğrenme için:  K-means algoritmasıyla müşteri segmentasyonu yapılması daha uygun görüldü.

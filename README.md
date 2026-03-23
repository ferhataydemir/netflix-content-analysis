\# Netflix İçerik Analizi ve Sınıflandırma Projesi

**Bu proje portföy geliştirme amacıyla hazırlanmıştır.**

&#x20;

\## Proje Hakkında

Netflix platformundaki 8.800+ içerik üzerinde keşifsel veri analizi yapılmış,  

ardından bir içeriğin Film mi yoksa TV Show mu olduğunu tahmin eden  

bir makine öğrenmesi modeli geliştirilmiştir. Model yüksek performans 

gösterse de, problem yapısı gereği sınıflandırma kolay olabilir.

&#x20;

\## Kullanılan Teknolojiler

Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn

&#x20;

\## EDA Bulguları

|Grafik|Bulgu|
|-|-|
|Film vs TV Show|\~6.100 Film, \~2.700 TV Show|
|Yıllara göre içerik|2015 sonrası hızlı artış, 2019'da zirve (\~2.000)|
|Top 10 Ülke|ABD (\~2.800) baskın, ardından Hindistan ve İngiltere|
|Top 10 Tür|International Movies, Dramas, Comedies öne çıkıyor|
|Film süresi|80–100 dakika aralığında yoğunlaşıyor, sağa çarpık dağılım|

> \\\*\\\*Veri kalitesi notu:\\\*\\\* `rating` sütununda `74 min`, `84 min` gibi hatalı değerler tespit edilmiştir.
> Bu değerler `duration` sütunundan kaynaklanmakta olup model öncesinde temizlenmiştir.



\## Feature Engineering

> `duration` sütunundan sayısal değer çıkarıldı (dakika / sezon)

> `date\\\_added` sütunundan `year\\\_added` ve `month\\\_added` türetildi

> `listed\\\_in` sütunundan `genre\\\_count` özelliği oluşturuldu

> `description` sütunundan karakter uzunluğu (`desc\\\_length`) hesaplandı

> Eksik değerler ilgili sütunun modu/medyanı ile dolduruldu

&#x20;

\## Makine Öğrenmesi

**Hedef:** `type` → Movie (0) / TV Show (1)

**Model:** Random Forest Classifier

**Test Sonuçları:**

|Metrik|Değer|
|-|-|
|Accuracy|\~%99.97|
|Precision (Movie)|1.00|
|Precision (TV Show)|0.99|
|Recall|1.00|
|F1-Score|1.00|

> \\\*\\\*Yüksek accuracy notu:\\\*\\\* Model %99.97 doğruluk elde etmiştir.
> Bu sonuç, `duration` gibi sütunların hedef değişken (`type`) ile doğrudan ilişkili olmasından kaynaklanıyor olabilir.
> Filmler dakika, diziler sezon cinsinden süre içerdiğinden model kısayol buluyor olabilir.
> Gerçek bir üretim senaryosunda bu tür özellikler dikkatli değerlendirilmelidir.



\## Genel Bulgular



> Netflix içerik sayısı 2015–2019 arasında \~20 kat artmıştır

> Filmler, içerik kitaplığının yaklaşık %70'ini oluşturmaktadır

> ABD tek başına toplam içeriğin yaklaşık üçte birini üretmektedir

> Uluslararası içerik ve Drama kategorileri platformda öne çıkmaktadır



\## Veri Seti

**Kaynak:** [Netflix Movies and TV Shows — Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)






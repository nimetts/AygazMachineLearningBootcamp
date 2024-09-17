# AygazMachineLearningBootcamp
## Movie Sentiment Analysis
Bu proje, Türkçe film yorumları veri setini kullanarak duygu analizi yapmayı amaçlamaktadır. Hem gözetimli hem de gözetimsiz öğrenme algoritmalarını kullanarak veriyi analiz ettim ve model performansını değerlendirdim.

## İçerik
- Veri Yükleme ve Ön İşleme
- Keşifsel Veri Analizi (EDA)
- Gözetimli Öğrenme Modelleri
- Gözetimsiz Öğrenme Modelleri
- Model Seçimi ve Hiperparametre Optimizasyonu
- Sonuçlar
- Kurulum ve Kullanım
## Veri Seti
Proje, turkish_movie_sentiment_dataset.csv adlı bir CSV dosyasını kullanmaktadır. Bu veri seti, film isimleri, yorumlar ve puanlar içermektedir. Veri setindeki bazı boş değerler temizlenmiş ve puanlar normalleştirilmiştir.

## Veri Ön İşleme
- Boş Değerlerin Temizlenmesi: Boş değerler içeren satırlar kaldırıldı.
- Yorum Temizleme: Yorumlardaki fazlalık karakterler ve boşluklar temizlendi.
- Puanların Normalleştirilmesi: Puanlar 0 ile 1 arasına ölçeklendirildi.
- Duygu Etiketleme: Puanlara göre yorumlar 'pozitif', 'nötr', 'negatif' olarak etiketlendi.
- Kategorik Verilerin Kodlanması: Film isimleri ve duygu etiketleri sayısal değerlere dönüştürüldü.
## Keşifsel Veri Analizi (EDA)
Veri setinin temel özelliklerini anlamak için:

- Duygu etiketlerinin dağılımı
- Normalleştirilmiş puanların dağılımı
- Duygu etiketleri ile normalleştirilmiş puanlar arasındaki ilişki
Grafikler:

- Duygu etiketlerinin dağılımını gösteren çubuk grafik
- Normalleştirilmiş puanların dağılımını gösteren histogram
- Normalleştirilmiş puanlar ile duygu etiketleri arasındaki ilişkiyi gösteren dağılım grafiği
## Gözetimli Öğrenme Modelleri
### Lojistik Regresyon:

- Model eğitildi ve test edildi.
- Performans metrikleri: Accuracy, Classification Report
### Nearest Neighbors (KNN):

- Model eğitildi ve test edildi.
- Performans metrikleri: Accuracy, Classification Report
## Gözetimsiz Öğrenme Modelleri
### K-Means:

- Model veriye uygulandı ve kümelendi.
- Silhouette skoru hesaplandı.
- Kümeleme sonuçları görselleştirildi.
### DBSCAN:

- Model veriye uygulandı ve kümelendi.
- Silhouette skoru hesaplandı.
- Kümeleme sonuçları görselleştirildi.
### Model Seçimi ve Neden Lojistik Regresyon Daha İyi Oldu?
### Veri Seti Özellikleri
Proje, Türkçe film yorumlarını ve bu yorumlara bağlı puanları içeren bir veri seti kullanmaktadır. Bu veri seti, duygu analizi ve sınıflandırma problemlerinde gözetimli öğrenme algoritmalarının etkili olabileceği bir yapı sunar. Özellikle:

- Duygu Sınıflandırması: Puanlar, yorumların duygu etiketlerine (pozitif, nötr, negatif) dönüştürülür. Bu, gözetimli öğrenme algoritmalarının etiketli verilerle eğitim yapmasını sağlar.
- Metin Özellikleri: Yorumlar, TF-IDF gibi tekniklerle sayısal verilere dönüştürülür. Bu özellikler, Lojistik Regresyon gibi algoritmaların metin verilerini işleyip sınıflandırma yapabilmesi için uygundur.
### Lojistik Regresyon ve Neden Daha İyi Oldu?
Lojistik Regresyon, özellikle duygu analizi ve sınıflandırma problemlerinde neden daha etkili bir model olduğunu aşağıdaki nedenlerle açıklayabiliriz:

#### Doğrusal Sınıflandırma:

Lojistik Regresyon, veri noktalarını doğrusal bir sınırla ayırır. Bu, özellikler arasındaki doğrusal ilişkileri öğrenmek için etkili bir yöntemdir. Duygu analizi gibi sınıflandırma problemlerinde, özelliklerin (örneğin, TF-IDF özellikleri) doğrusal olarak ayrılabilir olması sıkça görülür.
#### Ayrıştırma Kapasitesi:

Lojistik Regresyon, sınıflar arasında net ayrımlar yapma kapasitesine sahiptir. Bu, veri setindeki sınıfların (pozitif, nötr, negatif) belirgin bir şekilde ayrılmasını sağlar.
#### Sade ve Yorumlanabilir:

Lojistik Regresyon, modelin iç yapısını anlamayı ve yorumlamayı kolaylaştırır. Özellikle metin verileri ve duygu etiketleri gibi açıklayıcı sonuçlar sağlar.
#### Hızlı Eğitim ve Tahmin:

Model genellikle hızlı bir şekilde eğitim alır ve tahmin yapar. Büyük veri setleriyle çalışırken bu avantaj sağlar.
#### Aşırı Öğrenme Öncesi:

Küçük ve orta ölçekli veri setlerinde, aşırı öğrenme riskini minimize eder. Özellikle çok sayıda özelliğin bulunduğu durumlarda düzenleme (regularization) yapabilme yeteneği sağlar.
## Diğer Gözetimli Modellerle Karşılaştırma
### K-Nearest Neighbors (KNN):

KNN, komşuluk tabanlı bir modeldir ve genellikle daha fazla hesaplama gücü gerektirir. Büyük veri setlerinde yavaşlayabilir ve yüksek boyutlu veri setlerinde performansı düşebilir.
### SVM ve Diğer Algoritmalar:

Destek Vektör Makineleri (SVM) ve diğer karmaşık algoritmalar daha yüksek doğruluk sağlayabilir, ancak hiperparametre ayarlamaları ve eğitim süreci daha karmaşıktır. Bu proje için Lojistik Regresyon daha uygun olabilir çünkü daha hızlı ve daha basit bir model sunar.
## Sonuç
Veri setimizin özellikleri ve sınıflandırma probleminin doğası göz önüne alındığında, Lojistik Regresyon, özellikler arasındaki doğrusal ilişkileri öğrenme ve açıklayıcı sonuçlar sunma yeteneği nedeniyle en iyi performansı göstermiştir. Özellikle metin verileri ve duygu sınıflandırması gibi uygulamalarda, Lojistik Regresyon basitliği ve etkinliği ile öne çıkmaktadır.

## Kurulum ve Kullanım:

Gerekli kütüphaneleri yükleyin

```bash
pip install pandas numpy scikit-learn seaborn matplotlib
```
Proje dosyalarını indirin ve turkish_movie_sentiment_dataset.csv dosyasını veri dosyası ile aynı dizine yerleştirin.

Kodları çalıştırın.


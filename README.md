# Card Image Classification - Iskambil Kartları Görsel Sınıflandırma

## **Giriş**
Proje kapsamında, her biri farklı iskambil kart sınıflarına ait 53 sınıftan oluşan bir görsel veri seti kullanılmıştır. Amaç, bu görselleri doğru şekilde sınıflandırabilen bir model oluşturmak ve değerlendirmektir.

### **Kullanılan Yöntemler**
- Görüntü ön işleme ve normalizasyon  
- Convolutional Neural Network (CNN) modeli oluşturma  
- Transfer Learning ile önceden eğitilmiş VGG16 modelinin kullanımı  
- Model karşılaştırması ve iyileştirme  
- Veri artırımı (Data Augmentation)  
- Performans ölçümü: Doğruluk (Accuracy), karmaşıklık matrisi, sınıflandırma raporu  

## **Temel CNN Modeli**
- 3 adet evrişim bloğu  
- BatchNormalization, Dropout ve MaxPooling kullanımı  
- GlobalAveragePooling ile özellik düzleştirme  
- 53 sınıfa softmax ile çıktı  
- Test doğruluğu: **%91.32**  

## **Transfer Learning (VGG16)**
- ImageNet üzerinde eğitilmiş VGG16 modeli kullanıldı  
- Üst katmanlar yeniden eğitildi  
- Eğitim süresi daha kısa, ancak başarı daha düşük: **%53.21 doğruluk**  

### **Optimizer Karşılaştırması**
| Optimizer | Test Doğruluğu |
|-----------|----------------|
| Adam      | %91.32         |
| RMSprop   | %89.06         |
| SGD       | %86.04         |

## **Elde Edilen Sonuçlar**
- En yüksek başarı Temel CNN modeli ile elde edildi  
- Transfer Learning daha düşük performans gösterdi ancak küçük veri ile hızlı prototip için avantajlı olabilir  
- Adam optimizasyon algoritması en iyi sonucu verdi  
- Model, test setindeki kartları **%91’in üzerinde doğrulukla** tahmin edebildi  

## **Örnek Tahminler**
- Doğru ve yanlış tahmin örnekleri görselleştirildi  
- Karmaşıklık matrisi üzerinden hatalı sınıflamalar analiz edildi  
- Öznitelik haritaları (feature maps) ile modelin içsel çalışması gözlemlendi  

## **Ek Özellikler**
- Veri artırımı (`ImageDataGenerator`) ile overfitting azaltıldı  
- Eğitim süresi ve doğruluklar takip edilerek `early stopping` ve `learning rate decay` uygulandı  

## **Veri Seti**
Veri seti Kaggle üzerinden alınmış özel bir kart görsel veri setidir
- 53 sınıf  
- Toplam 7889 resim (eğitim + test)  
- Resimler: 128x128 piksel boyutunda renkli görseller  

## **Gelecek Çalışmalar**
- Modelin mobil veya web uygulaması üzerinden denenmesi gerçekleştirilebilir  
- Transfer Learning için farklı modellerle test edilme sağlanabilir  
- Gerçek zamanlı kart tanıma sistemi geliştirilebilir  
- Verinin genişletilmesi ve daha fazla çeşit içeren örneklerle zenginleştirme yapılabilir  

## **Sonuç**
Bu proje ile hem temel CNN mimarisi hem de transfer learning teknikleri uygulanarak başarılı bir görsel sınıflandırma sistemi geliştirilmiştir. Model doğruluğu, görselleştirmeler ve optimizasyon teknikleriyle desteklenerek proje derinleştirilmiştir  

## **Kullanılan Araçlar**
- Python  
- TensorFlow & Keras  
- Matplotlib, Seaborn  
- Kaggle GPU ortamı  

## **Projenin Kaggle Linki**
https://www.kaggle.com/code/essraayildirim/card-classification-cnn

## **Kullanılan Veri Seti**
https://www.kaggle.com/datasets/gpiosenka/cards-image-datasetclassification


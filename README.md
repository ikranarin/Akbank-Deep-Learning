# Akbank Deep Learning Project

## Giriş
Bu projede Microsoft Cats vs Dogs veri seti kullanılarak görüntü sınıflandırma yapılmıştır.  
Projenin amacı, **sıfırdan CNN modeli** tasarlayarak kedileri ve köpekleri ayırt edebilen bir yapay zekâ modeli geliştirmektir.

## Kullanılan Yöntemler
- **Convolutional Neural Network (CNN)**: Conv2d, BatchNorm, ReLU, MaxPooling, Dropout, Fully Connected katmanlar
- **Veri Önişleme ve Augmentation**: Resize, normalize, horizontal flip, rotation, color jitter
- **Model Değerlendirme**: Accuracy, Confusion Matrix, Classification Report
- **Açıklanabilirlik**: Grad-CAM ile modelin dikkat ettiği bölgelerin görselleştirilmesi
- Proje yalnızca scratch’tan CNN modeli kullanılarak yapılmıştır. Transfer learning gibi ek yöntemler opsiyonel olarak bırakılmıştır, kullanılmamıştır.

## Kullanılan Dataset
[Kaggle: Microsoft Cats vs Dogs Dataset](https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset)

## Model Performansı
Eğitim sonucunda elde edilen test seti performansı:

- **Accuracy**: ~%77
- **Precision**: %77 (Cat), %78 (Dog)
- **Recall**: %78 (Cat), %76 (Dog)
- **F1-score**: Ortalama ~%77

### Yorum
- Model yalnızca 3 epoch ve CPU ile eğitilmiş olmasına rağmen %77 doğruluk elde etmiştir.
- Eğitim epoch sayısı artırıldığında doğruluk oranının %85 seviyelerine çıkması beklenmektedir.
- Grad-CAM görselleri modelin çoğunlukla hayvanların yüz ve kulak bölgelerine odaklandığını göstermektedir.

## Ek Çalışmalar
- **Data Augmentation**: Eğitim sırasında daha dengeli öğrenme için random flip, rotation, color jitter uygulanmıştır.
- **Grad-CAM**: Modelin hangi bölgelerden etkilendiği görselleştirilmiştir.
- CPU üzerinde hızlı demo için eğitim kısa tutulmuştur (3 epoch).

## Sonuç ve Gelecek Çalışmalar
Bu proje, scratch’tan tasarlanmış bir CNN modelinin kısa eğitim süresiyle bile anlamlı bir doğruluk elde edebileceğini göstermiştir.  

Gelecek çalışmalar:
- Daha uzun eğitim (10–15 epoch) ve GPU kullanımıyla %85+ doğruluk
- Farklı CNN mimarilerinin (VGG, EfficientNet) denenmesi
- Daha güçlü regularization (L2 penalty, farklı dropout oranları)
- Veri seti dengesizliğini azaltmak için gelişmiş augmentation teknikleri
- Kullanıcı arayüzü (ör. Streamlit) eklenerek modelin interaktif hâle getirilmesi

## Linkler
[Kaggle Kodum](https://www.kaggle.com/code/ikranarinsoran/akbank-deep-learning-bootcamp-eyl-l-2025)

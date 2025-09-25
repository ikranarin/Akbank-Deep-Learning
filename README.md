# Akbank Deep Learning Project
## Giriş
Bu projede Microsoft Cats vs Dogs veri seti kullanılarak görüntü sınıflandırma yapılmıştır.  
Projenin amacı, **sıfırdan CNN modeli** tasarlayarak kedileri ve köpekleri ayırt edebilen bir yapay zekâ modeli geliştirmektir.
### Kullanlan Yöntemler
- **Convolutional Neural Network (CNN)**: Conv2d, BatchNorm, ReLU, MaxPooling, Dropout, Fully Connected katmanlar
- **Veri Önişleme ve Augmentation**: Resize, normalize, horizontal flip, rotation, color jitter
- **Model Değerlendirme**: Accuracy, Confusion Matrix, Classification Report
- **Açıklanabilirlik**: Grad-CAM ile modelin dikkat ettiği bölgelerin görselleştirilmesi
Proje yalnızca scratch’tan CNN modeli kullanılarak yapılmıştır. Transfer learning gibi ek yöntemler opsiyonel olarak bırakılmış, kullanılmamıştır.
### Kullandığım Dataset
https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset
## Metrikler
Eğitim sonucunda elde edilen test seti performansı:
- **Accuracy**: ~%77
- **Precision**: %77 (Cat), %78 (Dog)
- **Recall**: %78 (Cat), %76 (Dog)
- **F1-score**: Ortalama ~%77
### Yorumum:
- Model 3 epoch CPU üzerinde eğitilmesine rağmen %77 doğruluk elde etmiştir.
- Eğitim epoch sayısı artırıldığında doğruluk oranının %85 seviyelerine çıkması beklenmektedir.
- Grad-CAM görselleri modelin çoğunlukla hayvanların yüz ve kulak bölgelerine odaklandığını göstermektedir.
## Ekler
Projeye dair ek çalışmalar:
- **Data Augmentation**: Eğitim sırasında daha dengeli öğrenme için random flip, rotation, color jitter uygulanmıştır.
- **Grad-CAM**: Modelin hangi bölgelerden etkilendiği görselleştirilmiştir.
- GPU imkânı olmadığı için eğitim CPU üzerinde daha kısa tutulmuş (3 epoch) ve hızlı bir demo yapılmıştır.
## Sonuç ve Gelecek Çalışmalar
Bu proje sonucunda scratch’tan tasarlanmış bir CNN modelinin, kısa eğitim süresiyle bile anlamlı bir doğruluk elde edebildiği görülmüştür.
Gelecek çalışmalar:
- Daha uzun eğitim (10–15 epoch) ve GPU kullanımıyla %85+ doğruluk
- Farklı CNN mimarilerinin (VGG, EfficientNet) denenmesi
- Daha güçlü regularization (L2 penalty, daha farklı dropout oranları)
- Veri seti dengesizliğini azaltmak için advanced augmentation teknikleri
- Kullanıcı arayüzü (ör. Streamlit) eklenerek modelin interaktif hale getirilmesi
## Linkler
Çalışmama ait kaggle linkim:
https://www.kaggle.com/code/ikranarinsoran/akbank-deep-learning-bootcamp-eyl-l-2025

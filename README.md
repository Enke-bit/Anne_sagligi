# Maternal Health Risk Prediction

Bu proje, anne sağlığı risklerini tahmin etmek için oluşturulmuş bir makine öğrenmesi modelini içerir. Model, annelerin çeşitli sağlık ölçütlerini kullanarak risk seviyelerini (düşük, orta, yüksek) tahmin etmeyi amaçlamaktadır.

## Veri Seti

Bu projede kullanılan veri seti, Kaggle'dan alınmıştır ve aşağıdaki başlıkları içermektedir:

- **Age**: Anne yaşı
- **SystolicBP**: Sistolik kan basıncı (mm Hg)
- **DiastolicBP**: Diastolik kan basıncı (mm Hg)
- **BS**: Kan şekeri (mg/dL)
- **BodyTemp**: Vücut sıcaklığı (°F)
- **HeartRate**: Kalp atış hızı (bpm)
- **RiskLevel**: Risk seviyesi (low risk, mid risk, high risk)

Veri setine [buradan](https://www.kaggle.com/datasets/csafrit2/maternal-health-risk-data) ulaşabilirsiniz.

# Model

Model, Keras kullanılarak oluşturulmuştur ve aşağıdaki yapıya sahiptir:

```python
# Model oluşturma
model = Sequential([
    Dense(64, activation='relu', input_shape=(X_train.shape[1],)),
    Dropout(0.25),  # Dropout oranı %25
    Dense(32, activation='relu'),
    Dropout(0.25),  # Dropout oranı %25
    Dense(1, activation='sigmoid')
])

## Modeli derleme
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])


## Maternal Health Risk Prediction

Bu proje, anne sağlığı risklerini tahmin etmek için oluşturulmuş bir makine öğrenmesi modelini içerir. Model, annelerin çeşitli sağlık ölçütlerini kullanarak risk seviyelerini (düşük, orta, yüksek) tahmin etmeyi amaçlamaktadır.

## Veri Seti

Bu projede kullanılan veri seti, Kaggle'dan alınmıştır ve aşağıdaki başlıkları içermektedir:

- **Age**: Anne yaşı
- **SystolicBP**: Sistolik kan basıncı (mm Hg)
- **DiastolicBP**: Diastolik kan basıncı (mm Hg)
- **BS**: Kan şekeri (mg/dL)
- **BodyTemp**: Vücut sıcaklığı (°F)
- **HeartRate**: Kalp atış hızı (bpm)
- **RiskLevel**: Risk seviyesi (low risk, mid risk, high risk)

Veri setine [buradan](https://www.kaggle.com/datasets/csafrit2/maternal-health-risk-data) ulaşabilirsiniz.

## Model

Model, Keras kullanılarak oluşturulmuştur ve aşağıdaki yapıya sahiptir:

```python
# Model oluşturma
model = Sequential([
    Dense(64, activation='relu', input_shape=(X_train.shape[1],)),
    Dropout(0.25),  # Dropout oranı %25
    Dense(32, activation='relu'),
    Dropout(0.25),  # Dropout oranı %25
    Dense(1, activation='sigmoid')
])

# Modeli derleme
model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
Eğitim ve Değerlendirme
Model, eğitim süreci boyunca aşağıdaki sınıflandırma raporunu üretmiştir:

Classification Report:
               precision    recall  f1-score   support

           0       0.79      0.55      0.65        47
           1       0.46      0.99      0.63        80
           2       0.00      0.00      0.00        76

    accuracy                           0.52       203
   macro avg       0.42      0.51      0.43       203
weighted avg       0.37      0.52      0.40       203

Sonuçlar
Modelin sonuçları gösteriyor ki, bazı sınıflar üzerinde modelin performansı düşüktür. Özellikle '2' sınıfı (muhtemelen orta risk) için f1-skora 0.00 çıkmıştır. Modelin performansını artırmak için daha fazla veri ve daha karmaşık modelleme teknikleri kullanılabilir.

Katkıda Bulunma
Katkıda bulunmak isterseniz, lütfen bir issue açın veya bir pull request gönderin. Her türlü geri bildirim ve katkı değerlidir.

\# 🏠 California Housing Price Prediction (End-to-End ML)



\[!\[Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)

\[!\[Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange.svg)](https://scikit-learn.org/)

\[!\[License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)



Bu proje, California'daki konut fiyatlarını etkileyen faktörleri analiz eder ve \*\*Random Forest\*\* algoritması kullanarak ev fiyatlarını tahmin eder. Proje, veri temizlemeden hiperparametre optimizasyonuna kadar tam bir pipeline (boru hattı) yapısına sahiptir.



\## 📊 Model Performans Özeti

Modelimiz, test setinde aşağıdaki metriklerle başarısını kanıtlamıştır:



| Metrik | Değer |

| :--- | :--- |

| \*\*R² Skoru (Başarı Oranı)\*\* | \*\*%82.42\*\* |

| \*\*MAPE (Ortalama Hata Payı)\*\* | \*\*%18.23\*\* |

| \*\*RMSE (Kök Ortalama Kare Hata)\*\* | \*\*49,898.99 $\*\* |



\## 🛠️ Veri Mühendisliği ve Analiz

Sadece ham veriyi kullanmakla kalmadık, domain bilgisiyle yeni özellikler (Features) ürettik:

\* `rooms\_per\_hhold`: Hane başına düşen oda sayısı.

\* `pop\_per\_hhold`: Hane başına düşen nüfus yoğunluğu.

\* `bedrooms\_per\_room`: Evin toplam odaları içindeki yatak odası oranı.







\## 🚀 Hızlı Başlangıç (Quick Start)



Modeli kendi yerelinizde test etmek veya projenize dahil etmek çok kolaydır.



\### 1. Kurulum

```bash

\# Repoyu klonlayın

git clone \[https://github.com/yigiterenalp/california-housing-ml.git](https://github.com/yigiterenalp/california-housing-ml.git)

cd california-housing-ml



\# Sanal ortamı hazırlayın ve kütüphaneleri yükleyin

conda activate california\_housing

pip install -r requirements.txt



2\. Modeli Kullanma (Python)



Kaydettiğimiz .pkl dosyasını kullanarak anında tahmin alabilirsiniz:



Python



import joblib

import pandas as pd



\# Modeli ve Pipeline'ı yükle

full\_package = joblib.load("california\_housing\_model.pkl")

model = full\_package # Eğer sadece modeli kaydettiysen



\# Örnek bir veriyle tahmin yap (Veri seti formatında olmalı)

sample\_data = pd.DataFrame({

&nbsp;   'longitude': \[-122.23], 'latitude': \[37.88], 'housing\_median\_age': \[41.0],

&nbsp;   'total\_rooms': \[880.0], 'total\_bedrooms': \[129.0], 'population': \[322.0],

&nbsp;   'households': \[126.0], 'median\_income': \[8.3252], 'ocean\_proximity': \['NEAR BAY']

})



prediction = model.predict(sample\_data)

print(f"Tahmin Edilen Ev Fiyatı: {prediction\[0]:.2f} $")

🔍 Önemli Çıkarımlar

Modelin en çok önem verdiği 3 faktör sıralaması:



Median Income: Gelir seviyesi en güçlü belirleyici.



Inland Status: Denize uzaklık fiyatı doğrudan düşürüyor.



Population density: Hane başına düşen nüfus.



📄 Lisans

Bu proje MIT License altında lisanslanmıştır.


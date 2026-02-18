# 🏠 California Housing Price Prediction (End-to-End ML)

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Bu proje, California eyaletindeki konut fiyatlarını etkileyen faktörleri analiz eder ve **Random Forest** algoritması kullanarak fiyat tahmini yapar. Veri temizlemeden hiperparametre optimizasyonuna kadar tam bir makine öğrenmesi boru hattı (pipeline) sunar.

---

## 📊 Model Performans Özeti
Modelimiz, test setinde aşağıdaki metriklerle başarısını kanıtlamıştır:

| Metrik | Değer |
| :--- | :--- |
| **R² Skoru (Başarı Oranı)** | **%82.42** |
| **MAPE (Ortalama Hata Payı)** | **%18.23** |
| **RMSE (Hata Tutarı)** | **49,898.99 $** |

---

## 🛠️ Veri Mühendisliği ve Analiz
Ham veriye ek olarak, domain bilgisiyle aşağıdaki yeni özellikleri (features) türettik:
* `rooms_per_hhold`: Hane başına düşen oda sayısı.
* `pop_per_hhold`: Hane başına düşen nüfus yoğunluğu.
* `bedrooms_per_room`: Odalar içindeki yatak odası oranı.

---

## 🚀 Hızlı Başlangıç (Quick Start)

### 1. Kurulum
```bash
# Repoyu klonlayın
git clone [https://github.com/yigiterenalp/California-Housing-Price-Prediction.git](https://github.com/yigiterenalp/California-Housing-Price-Prediction.git)
cd California-Housing-Price-Prediction

# Gerekli kütüphaneleri yükleyin
pip install -r requirements.txt

import joblib
import pandas as pd

# Modeli yükle
model = joblib.load("california_housing_model.pkl")

# Örnek veri girişi
sample_data = pd.DataFrame({
    'longitude': [-122.23], 'latitude': [37.88], 'housing_median_age': [41.0],
    'total_rooms': [880.0], 'total_bedrooms': [129.0], 'population': [322.0],
    'households': [126.0], 'median_income': [8.3252], 'ocean_proximity': ['NEAR BAY']
})

prediction = model.predict(sample_data)
print(f"Tahmin Edilen Ev Fiyatı: {prediction[0]:.2f} $")
```
🔍 Önemli Çıkarımlar
Modelin fiyatı belirlerken en çok önem verdiği 3 faktör:

Median Income: Gelir seviyesi en güçlü belirleyicidir.

Inland Status: İç kesimde olmak fiyatı doğrudan düşürmektedir.

Population Density: Hane başına düşen nüfus.

📄 Lisans
Bu proje MIT License altında lisanslanmıştır.

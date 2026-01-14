# 🐾 Austin Animal Center Outcomes – Makine Öğrenmesi Projesi

Bu proje, **Austin Animal Center Outcomes** veri seti kullanılarak barınaktaki hayvanların çıkış sonuçlarını (**Outcome Type**) tahmin etmeyi amaçlamaktadır.  
Hayvanların yaş, tür ve cinsiyet bilgileri kullanılarak makine öğrenmesi tabanlı bir sınıflandırma modeli geliştirilmiştir.

---

## 📌 Proje Amacı

Hayvan barınaklarında tutulan kayıtlar, hayvanların sahiplenme, transfer veya diğer sonuçlarını analiz etmek için önemli bilgiler sunar.  
Bu proje kapsamında:

- Veri seti analiz edilmiştir
- Veri temizleme ve ön işleme adımları uygulanmıştır
- Kategorik ve sayısal veriler dönüştürülmüştür
- **Karar Ağacı (Decision Tree)** modeli eğitilmiş ve değerlendirilmiştir

---

## 📊 Veri Seti

- **Kaynak:** Austin Animal Center Outcomes
- **Bağımlı Değişken:** `Outcome Type`
- **Bağımsız Değişkenler:**
  - `Age in Days`
  - `Animal Type`
  - `Sex upon Outcome`

---

## 🗂️ Proje Dosya Yapısı

Austin_Animal_Center_Project/
│
├── data/
│ ├── raw
│ │   └── Austin_Animal_Center_Outcomes.csv
│ └── processed
│     └── Austin_Animal_processed.csv
│ 
├── notebooks/
│ ├── 01_data_exploration.ipynb
│ ├── 02_data_preprocessing.ipynb
│ └── 03_data_modeling.ipynb
│
├── outputs/
│ ├── confusion_matrix.png
│ ├── feature_importance.png
│ ├── classification_report.txt
│ └── model_accuracy.txt
│
├── README.md


---

## 🧹 Veri Ön İşleme Adımları

Projede aşağıdaki ön işleme adımları uygulanmıştır:

- `Name` sütununda **Unknown** ve boş değerlerin çıkarılması
- `Outcome Type` ve `Outcome Subtype` sütunlarındaki eksik verilerin işlenmesi
- `Sex upon Outcome` sütunundaki eksik değerlerin en sık görülen değer ile doldurulması
- `Age upon Outcome` sütununun sayısal formata çevrilerek **Age in Days** oluşturulması
- Kategorik değişkenlere **Label Encoding** uygulanması
- Sayısal değişkenlere **Min-Max Normalizasyonu** uygulanması

---

## 🤖 Kullanılan Model

### Karar Ağacı (Decision Tree Classifier)

- Algoritma: `DecisionTreeClassifier`
- Maksimum Derinlik: 5
- Eğitim / Test Oranı: %80 / %20

---

## 📈 Model Performansı

- **Doğruluk (Accuracy):** ~0.73

Detaylı performans çıktıları:
- `outputs/classification_report.txt`
- `outputs/model_accuracy.txt`

---

## 🔍 Özellik Önem Analizi (Feature Importance)

Karar Ağacı modeli kullanılarak yapılan analiz sonucunda:

- **Age in Days** değişkeninin model üzerinde en yüksek etkiye sahip olduğu görülmüştür
- Hayvanın yaşı, barınaktan çıkış sonucunu belirlemede önemli bir faktördür

Grafik çıktısı:
- `outputs/feature_importance.png`

---

## 🛠️ Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## 🚀 Geliştirilebilecek Noktalar

- Sınıf dengesizliğini azaltmak için SMOTE gibi yöntemlerin kullanılması
- Random Forest, Gradient Boosting gibi modellerin denenmesi
- Hiperparametre optimizasyonu yapılması
- Breed ve Color gibi ek özelliklerin modele dahil edilmesi
- Modelin Flask veya FastAPI ile web uygulamasına dönüştürülmesi
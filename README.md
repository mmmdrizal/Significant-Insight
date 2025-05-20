<div align="center">

---
# Significant-Insight
---

  <img width="1920" height="250" src="https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Header%20Github%20Significant%20Insight%20-%20Project%20Akhir%20Praktikum%20SML.png">

---
### Pengelompokan Daerah Rawan Pangan untuk Mendukung Pencapaian SDGs ke-2 Zero Hunger Menggunakan Machine Learning
---





[Sekilas Project](#-sekilas-project)
•
[Work Flow](#-Work-Flow)
•
[Data dan Metode](#-data-dan-metode)
•
[Significant-Insight](#panda_face-ASK-Man)

</div>

# 🌍 Sekilas Project
Project ini berfokus pada analisis data dan machine learning pada isu ketahanan pangan di Indonesia. Dengan memanfaatkan data dari 514 kabupaten/kota selama enam tahun, proyek ini bertujuan untuk:

- Mengidentifikasi wilayah-wilayah rawan pangan
- Memprediksi tingkat kerentanan pangan di masa depan
- Memberikan wawasan berbasis data untuk mendukung kebijakan pemerintah

Proyek ini didesain sebagai kontribusi terhadap pencapaian Tujuan Pembangunan Berkelanjutan (SDGs) nomor 2: **Zero Hunger**, dengan mengintegrasikan teknik klasifikasi dan clustering menggunakan algoritma machine learning seperti **Random Forest**, **XGBoost**, **Hierarchical Clustering**, dan **DBSCAN**.

Dengan pendekatan ini, diharapkan pengambilan kebijakan ketahanan pangan di Indonesia dapat menjadi lebih tepat sasaran dan berkelanjutan.


# 🔄 Work Flow
![Work Flow](https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Work%20Flow.png)
Workflow ini dirancang dalam menemukan model klasifikasi terbaik berbasis machine learning untuk mengidentifikasi daerah rentan pangan dan melakukan clustering untuk mengungkap karakteristik tiap daerah. Proses dimulai dengan analisis data eksploratif, dilanjutkan dengan pembagian data (70% training, 30% testing). Tiga model utama yang digunakan adalah Random Forest, LightGBM, dan XGBoost, dengan berbagai teknik penanganan outlier dan data imbalance. Model terbaik dievaluasi menggunakan data testing. Selanjutnya, fitur penting dipilih untuk proses clustering menggunakan algoritma DBSCAN dan HDBSCAN. Hasil clustering diinterpretasikan untuk memahami pola kerentanan pangan antar daerah.

# 📁 Data dan Metode
### 📁 Dataset
- **Sumber:** Portal Data Indonesia ([data.go.id](https://data.go.id)), Badan Pusat Statistik ([bps.go.id](https://bps.go.id))
- **Cakupan:** 514 kabupaten/kota di Indonesia selama 6 tahun (3.084 observasi)
- **Fitur:** Beragam indikator sosial-ekonomi dan pangan

### ⚙️ Model Machine Learning
- **Random Forest**: Klasifikasi & feature importance
- **XGBoost**: Model boosting yang cepat dan akurat
- **Hierarchical Clustering**: Identifikasi grup wilayah berdasarkan kesamaan karakteristik
- **DBSCAN**: Klasterisasi berbasis densitas dan noise handling

## 🧠 Metodologi

### 🔍 Eksplorasi & Preprocessing
- Deteksi dan penanganan outlier dengan boxplot & z-score
- Penanganan class imbalance: oversampling, undersampling, atau class weight adjustment

### ⚙️ Model Machine Learning
- **Random Forest**: Klasifikasi & feature importance
- **XGBoost**: Model boosting yang cepat dan akurat
- **Hierarchical Clustering**: Identifikasi grup wilayah berdasarkan kesamaan karakteristik
- **DBSCAN**: Klasterisasi berbasis densitas dan noise handling




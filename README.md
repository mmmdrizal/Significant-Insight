<div align="center">
  <img width="1920" height="250" src="https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Header%20Github%20Significant%20Insight%20-%20Project%20Akhir%20Praktikum%20SML.png">


---
# Significant-Insight  
### Pengelompokan Daerah Rawan Pangan untuk Mendukung Pencapaian SDGs ke-2 Zero Hunger Menggunakan Machine Learning




---





[Sekilas Project](#-sekilas-project)
•
[Work Flow](#Work-Flow)
•
[Demo dan Alur Project](#books-Demo)
•
[ASK-Man](#panda_face-ASK-Man)

</div>

# 📌 Sekilas Project
Project ini berfokus pada analisis data dan machine learning pada isu ketahanan pangan di Indonesia. Dengan memanfaatkan data dari 514 kabupaten/kota selama enam tahun, proyek ini bertujuan untuk:

- Mengidentifikasi wilayah-wilayah rawan pangan
- Memprediksi tingkat kerentanan pangan di masa depan
- Memberikan wawasan berbasis data untuk mendukung kebijakan pemerintah

Proyek ini didesain sebagai kontribusi terhadap pencapaian Tujuan Pembangunan Berkelanjutan (SDGs) nomor 2: **Zero Hunger**, dengan mengintegrasikan teknik klasifikasi dan clustering menggunakan algoritma machine learning seperti **Random Forest**, **XGBoost**, **Hierarchical Clustering**, dan **DBSCAN**.

Dengan pendekatan ini, diharapkan pengambilan kebijakan ketahanan pangan di Indonesia dapat menjadi lebih tepat sasaran dan berkelanjutan.


# 🌍 Latar Belakang
Ketahanan pangan merupakan isu global yang krusial, terlebih di negara berkembang seperti Indonesia. Ketimpangan distribusi pangan antar wilayah mengharuskan adanya pendekatan berbasis data yang efisien dan akurat untuk:

- Mengidentifikasi daerah rawan pangan
- Menganalisis indikator utama ketahanan pangan
- Memberikan rekomendasi strategis berbasis data

# Work Flow
![Work Flow](https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Work%20Flow.png)

# Significant Insight - Machine Learning for Food Security Analysis

**Significant Insight** adalah proyek akhir dari Praktikum SML (Statistik dan Machine Learning) yang bertujuan untuk mendukung pencapaian *Sustainable Development Goals* (SDGs) ke-2: **Zero Hunger**, melalui analisis dan prediksi tingkat kerentanan ketahanan pangan di Indonesia.


## ❓ Rumusan Masalah

1. Bagaimana karakteristik daerah berdasarkan tingkat kerentanan pangan?
2. Bagaimana membangun model prediksi kerentanan pangan dengan machine learning?
3. Apa indikator utama yang memengaruhi tingkat ketahanan pangan?

## 🎯 Tujuan Proyek

- Mengelompokkan wilayah berdasarkan tingkat kerawanan pangan.
- Memprediksi tingkat kerentanan pangan menggunakan algoritma machine learning.
- Mengidentifikasi indikator paling berpengaruh dalam menentukan ketahanan pangan.

## 📁 Dataset

- **Sumber:** Portal Data Indonesia ([data.go.id](https://data.go.id)), Badan Pusat Statistik ([bps.go.id](https://bps.go.id))
- **Cakupan:** 514 kabupaten/kota di Indonesia selama 6 tahun (3.084 observasi)
- **Fitur:** Beragam indikator sosial-ekonomi dan pangan

## 🧠 Metodologi

### 🔍 Eksplorasi & Preprocessing
- Deteksi dan penanganan outlier dengan boxplot & z-score
- Imputasi nilai hilang dengan median provinsi
- Penanganan class imbalance: oversampling, undersampling, atau class weight adjustment

### ⚙️ Model Machine Learning
- **Random Forest**: Klasifikasi & feature importance
- **XGBoost**: Model boosting yang cepat dan akurat
- **Hierarchical Clustering**: Identifikasi grup wilayah berdasarkan kesamaan karakteristik
- **DBSCAN**: Klasterisasi berbasis densitas dan noise handling

## 🧪 Studi Kasus

Analisis dilakukan pada seluruh kabupaten/kota di Indonesia, dengan tujuan untuk:

- Pemerataan pembangunan daerah
- Penanganan kerawanan pangan secara tepat sasaran
- Penyusunan kebijakan nasional berbasis data

## 📊 Output

- Peta sebaran tingkat kerentanan pangan
- Klaster wilayah berdasarkan karakteristik pangan
- Model prediktif dengan evaluasi akurasi
- Visualisasi feature importance

## 🌱 Harapan & Manfaat

Dengan menggunakan pendekatan machine learning, proyek ini diharapkan dapat:
- Memberikan insight untuk pengambilan kebijakan berbasis data
- Mendukung strategi percepatan eliminasi kelaparan (Zero Hunger - SDGs 2)
- Menjadi referensi untuk pengembangan model serupa di bidang kebijakan publik

## 📎 Struktur Proyek



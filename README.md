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

- Memprediksi tingkat kerentanan pangan di masa depan
- Mengidentifikasi wilayah-wilayah rawan pangan
- Memberikan wawasan berbasis data untuk mendukung kebijakan pemerintah

Proyek ini didesain sebagai kontribusi terhadap pencapaian Tujuan Pembangunan Berkelanjutan (SDGs) nomor 2: **Zero Hunger**, dengan mengintegrasikan teknik klasifikasi (Random Forest, LightGBM, dan XGBoost) dan clustering (DBSCAN dan HDBSCAN). Dengan pendekatan ini, diharapkan pengambilan kebijakan ketahanan pangan di Indonesia dapat menjadi lebih tepat sasaran dan berkelanjutan.


# 📁 Dataset
- **Sumber:** Portal Data Indonesia ([data.go.id](https://data.go.id)) dan Badan Pusat Statistik ([bps.go.id](https://bps.go.id))
- **Cakupan:** 514 kabupaten/kota di Indonesia selama 6 tahun (3.084 observasi)
- **Fitur:** Beragam indikator sosial-ekonomi dan pangan


# 🔄 Work Flow
![Work Flow](https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Work%20Flow.png)
Workflow ini dirancang dalam menemukan model klasifikasi terbaik berbasis machine learning untuk mengidentifikasi daerah rentan pangan dan melakukan clustering untuk mengungkap karakteristik tiap daerah. Proses dimulai dengan analisis data eksploratif, dilanjutkan dengan pembagian data (70% training, 30% testing). Tiga model utama yang digunakan adalah Random Forest, LightGBM, dan XGBoost, dengan berbagai teknik penanganan outlier dan data imbalance. Model terbaik dievaluasi menggunakan data testing. Selanjutnya, fitur penting dipilih untuk proses clustering menggunakan algoritma DBSCAN dan HDBSCAN. Hasil clustering diinterpretasikan untuk memahami pola kerentanan pangan antar daerah.

atau

Analisis dimulai dengan eksplorasi data (EDA) dan dilanjutkan dengan penanganan outlier menggunakan beberapa teknik: IQR, Z-Score, Isolation Forest, dan Local Outlier Factor (LOF). Selanjutnya, dilakukan pemodelan klasifikasi menggunakan tiga algoritma utama: Random Forest, LightGBM, dan XGBoost. Berdasarkan hasil evaluasi, kombinasi penanganan outlir menggunakan IQR dan LightGBM menjadi model terbaik untuk memprediksi status ketahanan pangan kabupaten/kota. Dari model ini, diperoleh enam variabel terpenting yang berpengaruh besar terhadap ketahanan pangan: NCPR, Kemiskinan (%), Tanpa Air Bersih (%), Angka Harapan Hidup (tahun), Jumlah Penduduk (rasio), dan Tanpa Listrik (%).

# Clustering Wilayah Rawan Pangan (Tahun 2023)

Untuk mendalami karakteristik wilayah rawan pangan, dilakukan proses clustering hanya pada data tahun 2023 menggunakan enam variabel terpenting hasil klasifikasi. Dua metode clustering digunakan, yaitu DBSCAN dan HDBSCAN. Hasil evaluasi menunjukkan bahwa keduanya mampu mengelompokkan wilayah ke dalam beberapa klaster, dengan cluster kecil yang memiliki karakteristik sangat rentan secara sosial dan infrastruktur.

Contohnya, cluster 1 dari hasil DBSCAN terdiri dari hanya 9 kabupaten/kota dengan tingkat kemiskinan sangat tinggi (rata-rata 35,55%), tanpa air bersih mencapai 86,83%, dan tanpa listrik sebesar 27,09%. Hasil serupa juga diperoleh dari HDBSCAN, yang mengidentifikasi cluster 1 sebagai wilayah yang sangat membutuhkan intervensi.

# Rekomendasi Kebijakan

Temuan dari analisis ini dapat menjadi dasar kebijakan berbasis data bagi pemerintah. Wilayah-wilayah dalam klaster paling rentan perlu dijadikan prioritas utama dalam intervensi. Beberapa rekomendasi kebijakan yang disarankan:

- Pembangunan infrastruktur dasar seperti air bersih dan listrik.
- Program pengurangan kemiskinan berbasis wilayah.
- Intervensi gizi dan kesehatan masyarakat yang difokuskan ke daerah dengan skor kerentanan tinggi.
- Monitoring indikator kunci secara berkelanjutan melalui sistem informasi nasional.

# Penutup
Dengan memanfaatkan pendekatan machine learning, proyek ini menunjukkan bagaimana data dapat dimanfaatkan untuk mengidentifikasi masalah krusial dalam ketahanan pangan secara objektif. Kombinasi teknik klasifikasi dan clustering mampu memberikan arah yang lebih presisi bagi pengambil kebijakan untuk menentukan wilayah prioritas dan mengalokasikan sumber daya secara lebih efektif dan berkelanjutan.

# Tim
- Wawan Saputra
- Muhammad Rizal
- Siti Nuradilla
- Nisa Nur Aisyah






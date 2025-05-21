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
- **Fitur:** NCPR Kemiskinan (%), Pengeluaran Pangan (%), Tanpa Listrik (%), Tanpa Air Bersih (%), Lama Sekolah Perempuan (tahun), Rasio Tenaga Kesehatan, Angka Harapan Hidup (tahun), Prevalensi of Undernourishment (%), Jumlah Penduduk (Rasio), Penduduk Undernourish (Rasio), Stunting (%), Status Ketahanan Pangan (target label untuk klasifikasi).


# 🔄 Work Flow
![Work Flow](https://github.com/mmmdrizal/Significant-Insight/blob/main/Image/Work%20Flow.png)
Workflow ini dirancang dalam menemukan model klasifikasi terbaik berbasis machine learning untuk mengidentifikasi daerah rentan pangan dan melakukan clustering untuk mengungkap karakteristik tiap daerah. Proses dimulai dengan analisis data eksploratif, dilanjutkan dengan pembagian data (70% training, 30% testing). Tiga model utama yang digunakan adalah Random Forest, LightGBM, dan XGBoost, dengan berbagai teknik penanganan outlier dan data imbalance. Model terbaik dievaluasi menggunakan data testing. Selanjutnya, fitur penting dipilih untuk proses clustering menggunakan algoritma DBSCAN dan HDBSCAN. Hasil clustering diinterpretasikan untuk memahami pola kerentanan pangan antar daerah.

atau

Analisis diawali dengan eksplorasi data (EDA) untuk memahami distribusi, hubungan antar variabel, serta mendeteksi potensi masalah data seperti outlier. Penanganan outlier dilakukan menggunakan beberapa metode, yakni IQR (Interquartile Range), Z-Score, Isolation Forest, dan Local Outlier Factor (LOF). Selain itu, karena distribusi kelas dalam data bersifat tidak seimbang (imbalanced), dilakukan beberapa pendekatan untuk menanganinya: tanpa penanganan (baseline), SMOTE (Synthetic Minority Over-sampling Technique), dan undersampling.

Selanjutnya, dilakukan pemodelan klasifikasi untuk memprediksi status ketahanan pangan menggunakan tiga algoritma utama: Random Forest, LightGBM, dan XGBoost. Berdasarkan hasil evaluasi model, kombinasi terbaik diperoleh dari data yang telah ditangani dengan metode IQR (untuk outlier), tanpa penanganan imbalance, serta model LightGBM. Model ini memberikan hasil prediksi paling optimal dan digunakan untuk mengekstraksi enam feature importance yang berkontribusi terhadap status ketahanan pangan, yaitu: NCPR, Kemiskinan (%), Tanpa Air Bersih (%), Angka Harapan Hidup (tahun), Jumlah Penduduk (rasio), dan Tanpa Listrik (%).

Untuk memahami lebih dalam karakteristik wilayah rawan pangan, dilakukan proses clustering pada data tahun 2023 untuk menggambarkan kondisi terkini dengan hanya menggunakan enam feature importance hasil dari klasifikasi sebelumnya. Dua metode clustering yang digunakan adalah DBSCAN dan HDBSCAN. Evaluasi menunjukkan bahwa keduanya berhasil membentuk klaster dengan baik, ditandai oleh nilai Silhouette Score di atas 0.55, yang menandakan pemisahan klaster yang cukup jelas.

Hasil dari DBSCAN menunjukkan tiga kelompok: klaster utama yang mencakup 493 kabupaten/kota, klaster minor dengan 9 kabupaten/kota yang memiliki tingkat kerentanan tinggi, serta 12 wilayah lainnya yang termasuk kategori moderat. Sedangkan hasil dari HDBSCAN membentuk pola serupa, dengan klaster utama berisi 488 kabupaten/kota, klaster rentan sebanyak 5 kabupaten/kota, dan 21 wilayah lainnya yang dikategorikan sebagai moderat.

# Clustering DBSCAN

| Cluster | NCPR   | Kemiskinan (%) | Tanpa Air Bersih (%) | Angka Harapan Hidup (tahun) | Jumlah Penduduk (Rasio) | Tanpa Listrik (%) |
|----------------|--------|----------------|------------------------|-----------------------------|--------------------------|--------------------|
| -1             | 3.68   | 26.74          | 64.81                  | 63.82                       | 1,013,888                | 33.16              |
| 0              | 1.16   | 10.88          | 28.82                  | 70.16                       | 538,180                 | 1.13               |
| 1              | 5.00   | 35.55          | 86.83                  | 65.49                       | 134,059                 | 27.09              |

Berdasarkan hasil clustering menggunakan metode DBSCAN, ditemukan tiga kelompok wilayah. Cluster 1 terdiri dari sembilan kabupaten/kota yang menunjukkan kondisi paling rentan: tingkat kemiskinan sangat tinggi (rata-rata 35,55%), mayoritas penduduk tidak memiliki akses terhadap air bersih (86,83%), dan sekitar 27% tidak memiliki listrik. Angka harapan hidup di wilayah ini juga lebih rendah dibanding klaster lain. Wilayah dalam klaster ini tergolong sangat tertinggal, terpencil, dan membutuhkan perhatian lintas sektor secara menyeluruh. Oleh karena itu, klaster ini dinamakan Prioritas Utama.

Sementara itu, Cluster 0 mencakup mayoritas wilayah (493 kabupaten/kota) yang menunjukkan kondisi relatif stabil. Tingkat kemiskinan cukup rendah (10,88%), akses air dan listrik memadai, dan angka harapan hidup berada di kisaran tertinggi (70,15 tahun). Wilayah dalam klaster ini cenderung mandiri dan bisa difokuskan pada pemeliharaan serta penguatan program yang sudah berjalan. Klaster ini diberi nama Stabil dan Mandiri. Di sisi lain, terdapat 12 wilayah yang tergolong outlier (Cluster -1), dengan ciri populasi besar (lebih dari 1 juta), namun masih memiliki tingkat kemiskinan tinggi, akses listrik dan air bersih yang buruk, serta angka harapan hidup rendah. Karena sifatnya yang tidak masuk ke dalam pola umum dan memiliki beban tinggi, kelompok ini disebut Perhatian Khusus.

# Clustering HDBSCAN
| Cluster | NCPR   | Kemiskinan (%) | Tanpa Air Bersih (%) | Angka Harapan Hidup (tahun) | Jumlah Penduduk (Rasio) | Tanpa Listrik (%) |
|-----------------|--------|----------------|------------------------|-----------------------------|--------------------------|--------------------|
| -1              | 3.77   | 25.95          | 65.37                  | 64.30                       | 656,779                 | 25.97              |
| 0               | 1.15   | 10.81          | 28.53                  | 70.21                       | 541,456                 | 1.06               |
| 1               | 5.00   | 36.82          | 94.83                  | 66.20                       | 134,703                 | 27.12              |

Hasil clustering menggunakan HDBSCAN juga menunjukkan pola yang konsisten. Cluster 1 (5 kabupaten/kota) memiliki karakteristik mirip dengan DBSCAN Cluster 1: kemiskinan ekstrem (36,82%), tanpa air bersih hampir total (94,83%), dan tanpa listrik lebih dari seperempat penduduknya. Klaster ini diberi label Kritis dan Terisolasi karena menggambarkan daerah dengan ketertinggalan infrastruktur dan sosial yang sangat mendalam. Sementara itu, Cluster 0 (488 kabupaten/kota) menunjukkan ciri wilayah dengan ketahanan pangan yang relatif baik. Infrastruktur dasar tersedia, angka harapan hidup tinggi, dan tingkat kemiskinan rendah, sehingga dinamakan Stabil dan Aman.

Terakhir, 21 wilayah di luar dua klaster utama dikategorikan sebagai outlier oleh HDBSCAN (Cluster -1). Mereka menunjukkan karakteristik yang lebih variatif dan kompleks—kemiskinan relatif tinggi, kualitas layanan dasar buruk, dan penduduk dalam jumlah sedang. Kelompok ini tidak homogen, sehingga perlu pendekatan berbasis kajian lebih lanjut agar solusi intervensi dapat disesuaikan dengan kebutuhan masing-masing daerah. Klaster ini dinamakan Tertinggal dan Tidak Merata.


# Rekomendasi Kebijakan

Hasil analisis clustering memberikan gambaran nyata mengenai perbedaan tingkat kerentanan antar wilayah di Indonesia. Oleh karena itu, strategi kebijakan yang diambil sebaiknya diferensiatif—artinya, menyesuaikan intervensi berdasarkan tingkat kebutuhan dan kerentanan masing-masing klaster. Melalui pendekatan ini, tujuan utama adalah mendorong transformasi wilayah paling rentan (Cluster 1) menjadi wilayah yang setara secara infrastruktur dan kesejahteraan. Sementara itu, wilayah stabil (Cluster 0) dipertahankan dan dikembangkan agar menjadi pusat ketahanan pangan yang berkelanjutan, dan wilayah tidak merata (Cluster -1) diarahkan agar bergerak ke arah kestabilan melalui intervensi kontekstual dan berbasis data.

## 🟥 Cluster 1 – Prioritas Utama / Kritis dan Terisolasi
Wilayah dalam klaster ini memiliki indikator kerentanan yang sangat tinggi: kemiskinan ekstrem, akses air bersih yang sangat minim (bahkan mendekati tidak ada), tingkat elektrifikasi rendah, serta angka harapan hidup yang relatif pendek.

Rekomendasi kebijakan:

- Pembangunan infrastruktur dasar secara agresif, terutama penyediaan air bersih dan listrik melalui program padat karya dan energi terbarukan (solar panel, sumur bor bersubsidi, dll).
- Program penanggulangan kemiskinan terpadu, berbasis komunitas dan didampingi secara aktif oleh pemerintah daerah dan pusat.
- Layanan kesehatan dan gizi berbasis komunitas (puskesmas keliling, bantuan gizi ibu & anak), mengingat angka harapan hidup dan kemungkinan prevalensi stunting yang tinggi.
- Pendekatan lintas sektor dan cepat, karena kondisi klaster ini bisa menjadi sumber ketimpangan dan kerawanan sosial yang meluas jika tidak ditangani segera.

## 🟩 Cluster 0 – Stabil dan Mandiri / Stabil dan Aman
Klaster ini berisi mayoritas wilayah yang memiliki ketahanan pangan relatif baik, infrastruktur memadai, dan angka harapan hidup tinggi. Namun bukan berarti tanpa risiko—potensi kemunduran tetap ada jika tidak dipelihara.

Rekomendasi kebijakan:
- Fokus pada peningkatan kualitas layanan publik, seperti efisiensi distribusi pangan, transparansi bantuan sosial, dan modernisasi pertanian.
- Program pencegahan kerentanan baru, seperti perlindungan terhadap guncangan ekonomi (inflasi pangan, bencana alam) dan digitalisasi sistem monitoring pangan lokal.
- Penguatan tata kelola dan inovasi lokal, termasuk pelibatan pemerintah daerah dan komunitas dalam perencanaan dan pengawasan distribusi pangan.

## 🟨 Cluster -1 – Perhatian Khusus / Tertinggal dan Tidak Merata
Wilayah-wilayah dalam klaster ini memiliki karakteristik yang variatif dan kompleks. Sebagian memiliki populasi sangat besar tapi tetap rentan (DBSCAN), sebagian lain menunjukkan kombinasi indikator sedang-tinggi namun tidak homogen (HDBSCAN). Mereka tidak sepenuhnya ekstrem, namun menunjukkan pola risiko yang tidak konsisten.

Rekomendasi kebijakan:
- Diagnostik lanjutan berbasis lokal diperlukan untuk memahami penyebab kerentanan spesifik per wilayah. Bisa melalui pengumpulan data lapangan tambahan atau integrasi data sektoral (kemiskinan, sanitasi, pendidikan).
- Desain intervensi adaptif dan fleksibel, misalnya dengan memberikan dana insentif berbasis indikator kinerja daerah (performance-based grant) agar solusi ditentukan oleh daerah masing-masing.
- Pendampingan dan penguatan kapasitas pemerintah daerah, terutama dalam perencanaan dan pemanfaatan dana pembangunan daerah yang lebih tepat sasaran.


# Penutup
Dengan memanfaatkan pendekatan machine learning, proyek ini menunjukkan bagaimana data dapat dimanfaatkan untuk mengidentifikasi masalah krusial dalam ketahanan pangan secara objektif. Kombinasi teknik klasifikasi dan clustering mampu memberikan arah yang lebih presisi bagi pengambil kebijakan untuk menentukan wilayah prioritas dan mengalokasikan sumber daya secara lebih efektif dan berkelanjutan.

# Tim
- [Wawan Saputra](https://github.com/wawan2105)
- [Muhammad Rizal](https://github.com/mmmdrizal)
- [Siti Nuradilla](https://github.com/nradillas) 
- [Nisa Nur Aisyah](https://github.com/nisanuraisyah)






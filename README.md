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

Analisis dimulai dengan eksplorasi data (EDA) dan dilanjutkan dengan penanganan outlier menggunakan beberapa teknik: IQR, Z-Score, Isolation Forest, dan Local Outlier Factor (LOF). Selanjutnya, dilakukan pemodelan klasifikasi menggunakan tiga algoritma utama: Random Forest, LightGBM, dan XGBoost. Berdasarkan hasil evaluasi, kombinasi penanganan outlir menggunakan IQR dan LightGBM menjadi model terbaik untuk memprediksi status ketahanan pangan kabupaten/kota. Dari model ini, diperoleh enam variabel terpenting yang berpengaruh besar terhadap ketahanan pangan: NCPR, Kemiskinan (%), Tanpa Air Bersih (%), Angka Harapan Hidup (tahun), Jumlah Penduduk (rasio), dan Tanpa Listrik (%).

Untuk mendalami karakteristik wilayah rawan pangan, dilakukan proses clustering hanya pada data tahun 2023 menggunakan enam variabel terpenting hasil klasifikasi. Dua metode clustering digunakan, yaitu DBSCAN dan HDBSCAN. Hasil evaluasi menunjukkan bahwa kedua metode berhasil mengelompokkan wilayah dengan cukup baik, ditandai dengan nilai Silhouette Score di atas 0.55. DBSCAN menghasilkan tiga kelompok, yaitu klaster utama dengan 493 kabupaten/kota, klaster minor dengan 9 kabupaten/kota, dan 12 wilayah yang dianggap sebagai outlier (tidak masuk ke dalam klaster mana pun). Sementara itu, HDBSCAN membentuk klaster utama dengan 488 anggota, klaster minor dengan 5 anggota, dan 21 wilayah yang dikategorikan sebagai outlier. Distribusi ini menunjukkan bahwa sebagian besar wilayah tergolong dalam klaster utama, tetapi terdapat sejumlah kecil daerah yang secara konsisten dikelompokkan sebagai klaster rentan atau outlier, yang patut menjadi perhatian utama dalam kebijakan intervensi.

# Clustering
Berdasarkan hasil clustering menggunakan metode DBSCAN, ditemukan tiga kelompok wilayah. Cluster 1 terdiri dari sembilan kabupaten/kota yang menunjukkan kondisi paling rentan: tingkat kemiskinan sangat tinggi (rata-rata 35,55%), mayoritas penduduk tidak memiliki akses terhadap air bersih (86,83%), dan sekitar 27% tidak memiliki listrik. Angka harapan hidup di wilayah ini juga lebih rendah dibanding klaster lain. Wilayah dalam klaster ini tergolong sangat tertinggal, terpencil, dan membutuhkan perhatian lintas sektor secara menyeluruh. Oleh karena itu, klaster ini dinamakan Prioritas Utama.

Sementara itu, Cluster 0 mencakup mayoritas wilayah (493 kabupaten/kota) yang menunjukkan kondisi relatif stabil. Tingkat kemiskinan cukup rendah (10,88%), akses air dan listrik memadai, dan angka harapan hidup berada di kisaran tertinggi (70,15 tahun). Wilayah dalam klaster ini cenderung mandiri dan bisa difokuskan pada pemeliharaan serta penguatan program yang sudah berjalan. Klaster ini diberi nama Stabil dan Mandiri. Di sisi lain, terdapat 12 wilayah yang tergolong outlier (Cluster -1), dengan ciri populasi besar (lebih dari 1 juta), namun masih memiliki tingkat kemiskinan tinggi, akses listrik dan air bersih yang buruk, serta angka harapan hidup rendah. Karena sifatnya yang tidak masuk ke dalam pola umum dan memiliki beban tinggi, kelompok ini disebut Perhatian Khusus.

Hasil clustering menggunakan HDBSCAN juga menunjukkan pola yang konsisten. Cluster 1 (5 kabupaten/kota) memiliki karakteristik mirip dengan DBSCAN Cluster 1: kemiskinan ekstrem (36,82%), tanpa air bersih hampir total (94,83%), dan tanpa listrik lebih dari seperempat penduduknya. Klaster ini diberi label Kritis dan Terisolasi karena menggambarkan daerah dengan ketertinggalan infrastruktur dan sosial yang sangat mendalam. Sementara itu, Cluster 0 (488 kabupaten/kota) menunjukkan ciri wilayah dengan ketahanan pangan yang relatif baik. Infrastruktur dasar tersedia, angka harapan hidup tinggi, dan tingkat kemiskinan rendah, sehingga dinamakan Stabil dan Aman.

Terakhir, 21 wilayah di luar dua klaster utama dikategorikan sebagai outlier oleh HDBSCAN (Cluster -1). Mereka menunjukkan karakteristik yang lebih variatif dan kompleks—kemiskinan relatif tinggi, kualitas layanan dasar buruk, dan penduduk dalam jumlah sedang. Kelompok ini tidak homogen, sehingga perlu pendekatan berbasis kajian lebih lanjut agar solusi intervensi dapat disesuaikan dengan kebutuhan masing-masing daerah. Klaster ini dinamakan Tertinggal dan Tidak Merata.



# Rekomendasi Kebijakan

Temuan dari analisis ini dapat menjadi dasar kebijakan berbasis data bagi pemerintah. Wilayah-wilayah dalam klaster paling rentan perlu dijadikan prioritas utama dalam intervensi. Beberapa rekomendasi kebijakan yang disarankan:

- Pembangunan infrastruktur dasar seperti air bersih dan listrik.
- Program pengurangan kemiskinan berbasis wilayah.
- Intervensi gizi dan kesehatan masyarakat yang difokuskan ke daerah dengan skor kerentanan tinggi.
- Monitoring indikator kunci secara berkelanjutan melalui sistem informasi nasional.

# Penutup
Dengan memanfaatkan pendekatan machine learning, proyek ini menunjukkan bagaimana data dapat dimanfaatkan untuk mengidentifikasi masalah krusial dalam ketahanan pangan secara objektif. Kombinasi teknik klasifikasi dan clustering mampu memberikan arah yang lebih presisi bagi pengambil kebijakan untuk menentukan wilayah prioritas dan mengalokasikan sumber daya secara lebih efektif dan berkelanjutan.

# Tim
- [Wawan Saputra](https://github.com/wawan2105)
- [Muhammad Rizal](https://github.com/mmmdrizal)
- [Siti Nuradilla](https://github.com/nradillas) 
- [Nisa Nur Aisyah](https://github.com/nisanuraisyah)






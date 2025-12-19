# 📘 Judul Proyek
*(Isi judul proyek Anda di sini)*

## 👤 Informasi
- **Nama:** [Ilham Putra Arysila]  
- **Repo:** [(https://github.com/Ilhamaris/uas-dataScience.git)]  
- **Video:** [...]  

---

# 1. 🎯 Ringkasan Proyek
- Menyelesaikan permasalahan sesuai domain  
- Melakukan data preparation  
- Membangun 3 model: **Baseline**, **Advanced**, **Deep Learning**  
- Melakukan evaluasi dan menentukan model terbaik  

---

# 2. 📄 Problem & Goals
**Problem Statements:**  
1.  **Dampak Duplikasi Data**: Kehadiran sejumlah besar baris duplikat (sekitar 47% dari dataset awal) berpotensi bias dalam pelatihan model dan menghasilkan metrik kinerja yang tidak akurat, sehingga perlu penanganan yang efektif.
2.  **Identifikasi Phishing yang Akurat**: Dibutuhkan pengembangan model *machine learning* yang mampu mengklasifikasikan URL sebagai *phishing* atau *legitimate* dengan akurasi tinggi, serta meminimalkan *false positives* (URL sah diklasifikasikan sebagai *phishing*) dan *false negatives* (URL *phishing* diklasifikasikan sebagai sah) yang terbukti dari hasil *confusion matrix* model *baseline*.
3.  **Optimalisasi Fitur**: Dengan banyaknya fitur yang tersedia (30 fitur asli ditambah fitur rekayasa baru), perlu diidentifikasi dan dimanfaatkan fitur-fitur yang paling berpengaruh dalam deteksi *phishing* untuk meningkatkan efisiensi dan interpretasi model.
4.  **Keseimbangan Performa dan Interpretasi**: Model yang dikembangkan harus mampu memberikan kinerja prediksi yang tinggi tanpa mengorbankan interpretasi fitur-fitur kunci, mengingat pentingnya memahami indikator *phishing* yang spesifik.

**Goals:**  
1.  **Menangani Duplikasi Data**: Berhasil menghapus semua entri duplikat dari dataset untuk memastikan integritas data dan mencegah pelatihan model yang bias.
2.  **Mengevaluasi Kinerja Model**: Mengevaluasi kinerja berbagai model *machine learning* (Logistic Regression, Random Forest, MLP) menggunakan metrik seperti akurasi, presisi, *recall*, F1-score, dan *confusion matrix* untuk membandingkan efektivitasnya dalam deteksi *phishing*.
3.  **Mengoptimalkan Fitur**: Melakukan rekayasa fitur baru (`Suspicious_Score`) dan seleksi fitur menggunakan Random Forest untuk mengidentifikasi set fitur yang paling prediktif dan efisien (misalnya, 15 fitur dengan kepentingan > 0.01) guna mengoptimalkan pelatihan dan kinerja model.
4.  **Memilih Model Optimal**: Memilih model dengan kinerja terbaik berdasarkan metrik evaluasi, dengan prioritas pada model yang mencapai akurasi tinggi dan keseimbangan yang baik antara *false positives* dan *false negatives*, yang mampu membedakan URL *phishing* dari yang *legitimate*.

---
## 📁 Struktur Folder
```
project/
│
├── data/                   # Dataset (tidak di-commit, download manual)
│
├── notebooks/              # Jupyter notebooks
│   └── ML_Project.ipynb
│
├── src/                    # Source code
│   
├── models/                 # Saved models
│   ├── model_baseline.pkl
│   ├── model_rf.pkl
│   └── model_cnn.h5
│
├── images/                 # Visualizations
│   └── Visualisasi_Perbandingan.png
│   └── confusion_Multilayer_Perceptron_MPL.png
│   └── confusion_logistic_regression.png
│   └── confusion_random_forest.pngconfusion_random_forest.png
│   └── visualisasi_boxplot1.png
│   └── visualisasi_boxplot2.png  
│   └── visualisasi_heatmap.png
│   └── visualisasi_histogram.png
│
├── requirements.txt        # Dependencies
├── .gitignore
└── README.md
```
---

# 3. 📊 Dataset
- **Sumber:** (https://archive.ics.uci.edu/dataset/327/phishing+websites)  
- **Jumlah Data:** 11055  
- **Tipe:** Tabular  

### Fitur Utama
| Nama Fitur | Tipe Data | Deskripsi | Contoh Nilai |
|------------|-----------|-----------|--------------|
| having_IP_Address | Categorical | Menggunakan alamat IP atau nama domain | 1 = Ya, -1 = Tidak, 0 = Netral |
| URL_Length | Categorical | Menunjukkan panjang URL | 1 = Ya, -1 = Tidak, 0 = Netral |
| Shortining_Service | Categorical | Menunjukkan apakah URL menggunakan layanan pemendek URL | 1 = Ya, -1 = Tidak, 0 = Netral |
| having_At_Symbol | Categorical | Menunjukkan apakah simbol `@` ada dalam URL | 1 = Ya, -1 = Tidak, 0 = Netral |
| double_slash_redirecting | Categorical | Menunjukkan apakah ada pengalihan ganda (misal, `//www.example.com`).  | 1 = Ya, -1 = Tidak, 0 = Netral |
| Prefix_Suffix | Categorical | Menunjukkan apakah ada awalan atau akhiran yang dipisahkan oleh `-` dalam nama domain (misal, `login-bank.com`).  | 1 = Ya, -1 = Tidak, 0 = Netral |
| having_Sub_Domain | Categorical | Menunjukkan jumlah *sub-domain* dalam URL | 1 = Ya, -1 = Tidak, 0 = Netral |
| SSLfinal_State | Categorical | Menunjukkan status sertifikat SSL (HTTPS) | 1 = Ya, -1 = Tidak, 0 = Netral |
| Domain_registeration_length | Categorical | Menunjukkan berapa lama nama domain terdaftar | 1 = Ya, -1 = Tidak, 0 = Netral |
| Favicon | Categorical | Menunjukkan apakah *favicon* (ikon situs web) dimuat dari domain yang berbeda.  | 1 = Ya, -1 = Tidak, 0 = Netral |
| port | Categorical | Menunjukkan apakah ada penggunaan *port* yang tidak standar dalam URL | 1 = Ya, -1 = Tidak, 0 = Netral |
| HTTPS_token | Categorical | Menunjukkan apakah token 'HTTPS' ada dalam nama domain (misal, `https-login.com`) | 1 = Ya, -1 = Tidak, 0 = Netral |
| Request_URL | Categorical | Menunjukkan apakah objek yang diminta (gambar, video, dll.) dimuat dari domain yang berbeda | 1 = Ya, -1 = Tidak, 0 = Netral |
| URL_of_Anchor | Categorical | Menunjukkan apakah URL *anchor* (link yang terlihat) mengarah ke domain yang berbeda dari domain utama | 1 = Ya, -1 = Tidak, 0 = Netral |
| Links_in_tags | Categorical | Menunjukkan persentase tautan dalam tag HTML (`<a>`, `<form>`, `<iframe>`, `<script>`) yang mengarah ke domain yang berbeda. | 1 = Ya, -1 = Tidak, 0 = Netral |
| SFH | Categorical | Menunjukkan apakah URL formulir aman atau tidak (*Server Form Handler*).  | 1 = Ya, -1 = Tidak, 0 = Netral |
| Submitting_to_email | Categorical | Menunjukkan apakah informasi formulir dikirimkan langsung ke alamat email. Ini adalah metode yang sering digunakan *phisher*. | 1 = Ya, -1 = Tidak, 0 = Netral |
| Abnormal_URL | Categorical | Menunjukkan apakah URL memiliki karakter atau struktur yang tidak biasa atau mencurigakan. | 1 = Ya, -1 = Tidak, 0 = Netral |
| Redirect | Categorical | Menunjukkan jumlah pengalihan. Situs *phishing* sering menggunakan beberapa pengalihan untuk menyembunyikan tujuan akhir. | 1 = Ya, -1 = Tidak, 0 = Netral |
| on_mouseover | Categorical | Menunjukkan apakah fungsi `onMouseOver` mengubah status bar.  | 1 = Ya, -1 = Tidak, 0 = Netral |
| RightClick | Categorical | Menunjukkan apakah klik kanan dinonaktifkan. | 1 = Ya, -1 = Tidak, 0 = Netral |
| popUpWidnow | Categorical | Menunjukkan apakah ada jendela *pop-up* yang muncul. | 1 = Ya, -1 = Tidak, 0 = Netral |
| Iframe | Categorical | Menunjukkan apakah ada penggunaan *iframe*. | 1 = Ya, -1 = Tidak, 0 = Netral |
| age_of_domain | Categorical | Menunjukkan usia domain. | 1 = Ya, -1 = Tidak, 0 = Netral |
| DNSRecord | Categorical | Menunjukkan apakah ada catatan DNS untuk domain tersebut. | 1 = Ya, -1 = Tidak, 0 = Netral |
| web_traffic | Categorical | Menunjukkan peringkat lalu lintas web situs. | 1 = Ya, -1 = Tidak, 0 = Netral |
| Page_Rank | Categorical | Menunjukkan peringkat halaman Google situs. . | 1 = Ya, -1 = Tidak, 0 = Netral |
| Google_Index | Categorical | Menunjukkan apakah situs diindeks oleh Google.  | 1 = Ya, -1 = Tidak, 0 = Netral |
| Links_pointing_to_page | Categorical | Menunjukkan jumlah tautan yang mengarah ke halaman tersebut. | 1 = Ya, -1 = Tidak, 0 = Netral |
| Statistical_report | Categorical | Menunjukkan apakah ada laporan statistik terkait domain tersebut | 1 = Ya, -1 = Tidak, 0 = Netral |
| Result | Categorical | Ini adalah variabel target, yang mengindikasikan apakah URL tersebut adalah *phishing* (`1` atau `-1`) atau tidak (`0` atau `1`) | 1 = Ya, -1 = Tidak, 0 = Netral |

---

# 4. 🔧 Data Preparation
## Cleaning
### 1. Handling missing values
* **Hasil**: Tidak ada nilai yang hilang yang terdeteksi dalam DataFrame awal (`df`).
* **Alasan**: Pemeriksaan menggunakan `df.isnull().sum()` mengungkapkan bahwa semua kolom memiliki nol entri yang hilang, menunjukkan dataset lengkap tanpa perlu imputasi atau penghapusan baris/kolom karena data yang hilang.

### 2. Removing duplicates
* **Proses**: Metode `df.duplicated().sum()` digunakan untuk mengidentifikasi baris duplikat dalam DataFrame asli.
* **Hasil**: Sejumlah besar **5206 baris duplikat** ditemukan, yang merupakan sekitar **47%** dari total 11055 baris. Duplikat ini kemudian dihapus menggunakan `df.drop_duplicates().copy()`, menghasilkan DataFrame yang bersih (`df_cleaned`) dengan **5849 baris unik**.
* **Alasan**: Menghapus duplikat sangat penting untuk mencegah pelatihan model yang bias, mengurangi pemborosan sumber daya komputasi, dan memastikan bahwa analisis statistik tidak dipengaruhi oleh pengamatan yang berlebihan.

### 3. Handling outliers
* **Pendekatan**: Mengingat sebagian besar fitur dalam dataset bersifat kategorikal atau ordinal dengan nilai utama `-1`, `0`, atau `1`, metode deteksi outlier statistik tradisional (misalnya, IQR untuk data kontinu) tidak dapat diterapkan secara langsung. Sebagai gantinya, analisis outlier berfokus pada identifikasi kategori 'minoritas' atau nilai yang jarang muncul dalam distribusi setiap fitur.

* **Temuan**: Beberapa fitur menunjukkan kategori dengan kemunculan yang jauh lebih sedikit, yang dianggap berpotensi informatif daripada kesalahan data:

* `URL_Length`: 96 entri memiliki nilai `0` (panjang yang mencurigakan), menunjukkan bahwa ini adalah kasus yang jarang tetapi berpotensi penting.
* `RightClick`: Hanya 287 entri yang memiliki nilai `-1` (klik kanan dinonaktifkan), menunjukkan bahwa karakteristik minoritas ini dapat menjadi indikator yang kuat.
* `Redirect`: 771 entri menunjukkan nilai `1` (adanya pengalihan), yang lebih jarang tetapi sering dikaitkan dengan URL berbahaya.

* Fitur lain seperti `popUpWidnow`, `Iframe`, `Shortining_Service`, `Favicon`, `port`, `HTTPS_token`, `Abnormal_URL`, `on_mouseover`, `Statistical_report`, `Google_Index`, dan `Links_pointing_to_page` juga menunjukkan pola serupa dari kategori minoritas informatif.
* **Alasan**: Pendekatan ini memungkinkan pemahaman tentang pola data yang tidak biasa yang relevan dengan domain masalah, di mana kejadian yang jarang mungkin menandakan karakteristik kritis dari upaya phishing.

## Transformation
Berdasarkan analisis dan pra-pemrosesan data yang telah dilakukan di notebook ini, fitur-fitur dalam dataset sudah dalam format numerik (`int64`) dengan nilai-nilai yang terbatas pada `-1`, `0`, dan `1`. Ini berarti data sudah secara efektif di-*encode* secara numerik, baik sebagai biner (dua nilai) atau ordinal (tiga nilai dengan urutan).

## Data Splitting

**Strategi Pembagian Data:**

*   **Training set**: 70% (4094 samples)
*   **Test set**: 30% (1755 samples)
*   **Random state**: 42 untuk reproducibility

---

# 5. 🤖 Modeling
- **Model 1 – Baseline:** Logistic Regression  
- **Model 2 – Advanced ML:** Random Forest  
- **Model 3 – Deep Learning:** Multilayer Perceptron MLP  

---

# 6. 🧪 Evaluation
**Metrik:** Accuracy

### Hasil Singkat
| Model | Accuracy | Precision | Recall | F1-Score | ROC_AUC |
|-------|----------|-----------|--------|----------|---------------|
| Logistic Regression | 0.9060 | 0.9062 | 0.9060 | 0.9060 | 0.9694 |
| Random Forest | 0.9402 | 0.9403 | 0.9402 | 0.9402 | 0.9861 |
| Multilayer Perceptron MLP | 0.9242 | 0.9259 | 0.9242 | 0.9242 | 0.9826 |

---

# 7. 🏁 Kesimpulan
**Model Terbaik:**
Model **Random Forest (Tuned)** adalah model terbaik yang berhasil dikembangkan dalam proyek ini.

**Alasan:**
Model Random Forest (Tuned) unggul karena mencapai metrik evaluasi tertinggi di antara ketiga model yang dibandingkan:
*   **Akurasi Tertinggi**: 0.9402
*   **ROC-AUC Tertinggi**: 0.9861
*   **F1-Score Tertinggi**: 0.9402
*   Model ini juga menunjukkan keseimbangan terbaik dalam meminimalkan kedua jenis kesalahan, yaitu *False Positives* (58) dan *False Negatives* (47), yang sangat penting dalam konteks deteksi *phishing*.

**Insight dari Data:**
-   **Data Cleaning Krusial**: Deteksi dan penghapusan duplikasi data (sekitar 47%) adalah langkah terpenting dalam *data preparation* untuk memastikan integritās data dan mencegah bias model.
-   **Sifat Data Kategorikal/Ordinal**: Sebagian besar fitur bersifat kategorikal/ordinal (`-1`, `0`, `1`), sehingga deteksi *outlier* tradisional tidak relevan. Namun, kategori minoritas dalam fitur-fitur seperti `URL_Length` atau `RightClick` terbukti sangat informatif dan memiliki potensi prediktif yang tinggi.
-   **Class Balance yang Baik**: Dataset menunjukkan distribusi kelas yang relatif seimbang untuk variabel target (`Result`), sehingga tidak diperlukan teknik *data balancing* khusus.
-   **Fitur Rekayasa dan Seleksi Efektif**: Pembuatan fitur `Suspicious_Score` dan seleksi fitur berbasis Random Forest secara signifikan meningkatkan kualitas fitur yang digunakan untuk pemodelan, dengan fitur terkait SSL/HTTPS dan *anchor* menjadi yang paling penting.

**Insight dari Modeling:**
-   **Superioritas Model Ensemble**: Random Forest menunjukkan performa yang jauh lebih baik dibandingkan model linear (Logistic Regression) dan sedikit lebih baik dari model *deep learning* (MLP), membuktikan kemampuannya dalam menangani kompleksitas dan interaksi antar fitur.
-   **Trade-off Error**: Meskipun MLP memiliki *False Negatives* yang sedikit lebih rendah, Random Forest berhasil menyeimbangkan *False Positives* dan *False Negatives* dengan lebih baik, yang krusial untuk aplikasi deteksi *phishing* di mana kedua jenis kesalahan memiliki konsekuensi yang signifikan.
-   **Konvergensi Model Deep Learning**: Model MLP yang dilatih dengan TensorFlow/Keras menunjukkan konvergensi yang baik tanpa *overfitting* yang signifikan, berkat penggunaan *EarlyStopping* dan arsitektur yang sesuai.

---

# 8. 🔮 Future Work
- [ ] Tambah data  
- [ ] Tuning model  
- [ ] Coba arsitektur DL lain  
- [ ] Deployment  

---

# 9. 🔁 Reproducibility
Gunakan environment:
**Python Version:** `3.11`

**Main Libraries & Versions:**
```
numpy==1.24.3
pandas==2.0.3
scikit-learn==1.3.0
matplotlib==3.7.2
seaborn==0.12.2
tensorflow==2.14.0
scipy==1.11.1 # for .arff file loading
```
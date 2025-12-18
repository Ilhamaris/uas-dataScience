## INFORMASI PROYEK

**Judul Proyek:** Klasifikasikan situs web sebagai situs phishing atau sah menggunakan model Machine Learning

**Nama Mahasiswa:** Ilham Putra Arysila  
**NIM:** 233307051  
**Program Studi:** Teknologi Informasi  
**Mata Kuliah:** Data Science  
**Dosen Pengampu:** Gus Nanang Syaifuddin, S.Kom., M.Kom.  
**Tahun Akademik:** 2025/5B  
**Link GitHub Repository:** (https://github.com/Ilhamaris/uas-dataScience.git)  
**Link Video Pembahasan:** URL Repository

---

## 1. LEARNING OUTCOMES
Pada proyek ini, mahasiswa diharapkan dapat:
1. Memahami konteks masalah dan merumuskan problem statement secara jelas
2. Melakukan analisis dan eksplorasi data (EDA) secara komprehensif (**OPSIONAL**)
3. Melakukan data preparation yang sesuai dengan karakteristik dataset
4. Mengembangkan tiga model machine learning yang terdiri dari (**WAJIB**):
   - Model baseline
   - Model machine learning / advanced
   - Model deep learning (**WAJIB**)
5. Menggunakan metrik evaluasi yang relevan dengan jenis tugas ML
6. Melaporkan hasil eksperimen secara ilmiah dan sistematis
7. Mengunggah seluruh kode proyek ke GitHub (**WAJIB**)
8. Menerapkan prinsip software engineering dalam pengembangan proyek

---

## 2. PROJECT OVERVIEW

### 2.1 Latar Belakang
Keamanan siber menjadi isu kritis karena pertumbuhan aktivitas digital yang semakin intens, terutama pada sektor keuangan, pendidikan, dan layanan publik. Serangan phishing terus meningkat setiap tahun dan menimbulkan kerugian besar, mulai dari pencurian data pribadi hingga akses ilegal ke akun finansial. Laporan oleh Verizon Data Breach Investigations Report (2023) menunjukkan bahwa phishing tetap menjadi salah satu metode serangan paling umum pada insiden pelanggaran data. Kondisi ini menunjukkan perlunya sistem otomatis yang mampu mengklasifikasikan situs web berbahaya secara cepat dan akurat.
Pada praktiknya, pengguna internet seringkali kesulitan membedakan situs asli dan situs palsu karena tampilan visual yang semakin mirip, strategi rekayasa sosial (social engineering) yang makin canggih, serta kurangnya literasi digital. Penelitian sebelumnya seperti Abdelhamid et al. (2014) menunjukkan bahwa fitur URL, struktur halaman, dan perilaku jaringan dapat menjadi indikator penting untuk mendeteksi phishing, namun tanpa otomasi yang kuat, deteksi manual tidak realistis dilakukan oleh pengguna umum maupun institusi. Tantangan lain adalah tingginya dinamika teknik baru yang digunakan penyerang, sehingga diperlukan model yang adaptif dan berbasis data.
Proyek klasifikasi phishing berbasis Machine Learning menawarkan manfaat strategis. Bagi pengguna, sistem ini dapat memberikan perlindungan real-time tanpa membutuhkan keahlian teknis. Bagi bisnis dan instansi, model ini mendukung peningkatan keamanan operasional, mengurangi risiko kebocoran data, dan menekan biaya penanganan insiden. Dari sisi penelitian, proyek ini memperkaya pengembangan metode deteksi ancaman berbasis data dan membuka peluang eksplorasi fitur-fitur baru yang lebih robust terhadap teknik phishing modern. Pendekatan ini memperkuat ekosistem cybersecurity yang lebih cerdas dan responsif terhadap ancaman siber masa kini.

## 3. BUSINESS UNDERSTANDING / PROBLEM UNDERSTANDING  
### 3.1 Problem Statements  

1.  **Dampak Duplikasi Data**: Kehadiran sejumlah besar baris duplikat (sekitar 47% dari dataset awal) berpotensi bias dalam pelatihan model dan menghasilkan metrik kinerja yang tidak akurat, sehingga perlu penanganan yang efektif.
2.  **Identifikasi Phishing yang Akurat**: Dibutuhkan pengembangan model *machine learning* yang mampu mengklasifikasikan URL sebagai *phishing* atau *legitimate* dengan akurasi tinggi, serta meminimalkan *false positives* (URL sah diklasifikasikan sebagai *phishing*) dan *false negatives* (URL *phishing* diklasifikasikan sebagai sah) yang terbukti dari hasil *confusion matrix* model *baseline*.
3.  **Optimalisasi Fitur**: Dengan banyaknya fitur yang tersedia (30 fitur asli ditambah fitur rekayasa baru), perlu diidentifikasi dan dimanfaatkan fitur-fitur yang paling berpengaruh dalam deteksi *phishing* untuk meningkatkan efisiensi dan interpretasi model.
4.  **Keseimbangan Performa dan Interpretasi**: Model yang dikembangkan harus mampu memberikan kinerja prediksi yang tinggi tanpa mengorbankan interpretasi fitur-fitur kunci, mengingat pentingnya memahami indikator *phishing* yang spesifik.

### 3.2 Goals

1.  **Menangani Duplikasi Data**: Berhasil menghapus semua entri duplikat dari dataset untuk memastikan integritas data dan mencegah pelatihan model yang bias.
2.  **Mengevaluasi Kinerja Model**: Mengevaluasi kinerja berbagai model *machine learning* (Logistic Regression, Random Forest, MLP) menggunakan metrik seperti akurasi, presisi, *recall*, F1-score, dan *confusion matrix* untuk membandingkan efektivitasnya dalam deteksi *phishing*.
3.  **Mengoptimalkan Fitur**: Melakukan rekayasa fitur baru (`Suspicious_Score`) dan seleksi fitur menggunakan Random Forest untuk mengidentifikasi set fitur yang paling prediktif dan efisien (misalnya, 15 fitur dengan kepentingan > 0.01) guna mengoptimalkan pelatihan dan kinerja model.
4.  **Memilih Model Optimal**: Memilih model dengan kinerja terbaik berdasarkan metrik evaluasi, dengan prioritas pada model yang mencapai akurasi tinggi dan keseimbangan yang baik antara *false positives* dan *false negatives*, yang mampu membedakan URL *phishing* dari yang *legitimate*.

### 3.3 Solution Approach

#### **Model 1 – Baseline Model**
Model sederhana sebagai pembanding dasar.
**Menggunakan model Logistic Regression**
Karena dataset ini adalah untuk deteksi phishing, yang merupakan masalah klasifikasi biner (mengklasifikasikan apakah situs web itu phishing atau bukan), model yang paling cocok adalah model logistic regression. Ini adalah algoritma klasifikasi yang banyak digunakan untuk masalah klasifikasi biner dan merupakan baseline yang bagus karena sederhana dan efektif.

#### **Model 2 – Advanced / ML Model**
Model machine learning yang lebih kompleks.
**Menggunakan model Random Forest**
Random Forest adalah metode ensemble berbasis pohon keputusan yang sangat kuat untuk tugas klasifikasi. Random Forest menggabungkan banyak pohon keputusan untuk mengurangi overfitting dan meningkatkan akurasi secara signifikan dibandingkan dengan satu pohon keputusan. Untuk klasifikasi phishing yang kompleks, Random Forest memiliki akurasi dan ketahanannya yang tinggi

#### **Model 3 – Deep Learning Model (WAJIB)**
Model deep learning yang sesuai dengan jenis data.
**Menggunakan model Tabular Data: Multilayer Perceptron (MLP) / Neural Network**
MLP, juga dikenal sebagai feedforward neural network, adalah arsitektur dasar deep learning yang sangat efektif untuk masalah klasifikasi pada data tabular. Dengan setidaknya 2 hidden layers, jaringan ini dapat mempelajari pola non-linear yang kompleks dalam data untuk membedakan antara situs phishing dan non-phishing. Ini akan bekerja dengan baik karena data sudah dalam format feature yang terstruktur.

---

## 4. DATA UNDERSTANDING
### 4.1 Informasi Dataset
**Sumber Dataset:** UCI ML Repository

**Deskripsi Dataset:**
- Jumlah baris (rows): 11055
- Jumlah kolom (columns/features): 31
- Tipe data: Tabular
- Ukuran dataset: 738 KB
- Format file: .arff

### 4.2 Deskripsi Fitur
Jelaskan setiap fitur/kolom yang ada dalam dataset.
**Contoh tabel:**
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

### 4.3 Kondisi Data

Setelah melakukan analisis komprehensif terhadap dataset, berikut adalah rangkuman masalah kualitas data yang teridentifikasi:

1.  **Missing Values (Nilai Hilang)**:
    *   **Status**: Tidak ada *missing values* yang terdeteksi dalam DataFrame awal (`df`) maupun setelah pemrosesan (`df_processed`). Ini menunjukkan kebersihan data yang baik dalam hal kelengkapan entri.

2.  **Duplicate Data (Data Duplikat)**:
    *   **Status**: Ditemukan **5206 baris duplikat** dalam DataFrame awal, yang merupakan sekitar 47% dari total baris. Ini adalah masalah signifikan yang berpotensi menyebabkan bias model dan pemborosan sumber daya.
    *   **Penanganan**: Baris duplikat telah berhasil dihapus, menghasilkan `df_processed` dengan 5849 baris unik.

3.  **Outliers (Pencilan) & Distribusi Fitur**:
    *   **Status**: Karena sifat data yang sebagian besar kategorikal/ordinal (nilai `-1`, `0`, `1`), konsep *outlier* tradisional tidak berlaku. Namun, beberapa fitur menunjukkan distribusi nilai yang sangat miring atau adanya kategori minoritas yang signifikan:
        *   **`URL_Length`**: Terdapat 96 entri dengan nilai `0` (panjang mencurigakan) yang relatif jarang dibandingkan kategori lainnya.
        *   **`RightClick`**: Hanya 287 entri yang menonaktifkan klik kanan (`-1`), menunjukkan minoritas yang mungkin informatif.
        *   **`Redirect`**: 771 entri menunjukkan adanya pengalihan (`1`), yang merupakan minoritas tetapi seringkali indikator *phishing*.
        *   Fitur lain seperti `popUpWidnow`, `Iframe`, `Shortining_Service`, `Favicon`, `port`, `HTTPS_token`, `Abnormal_URL`, `on_mouseover`, `Statistical_report`, `Google_Index`, dan `Links_pointing_to_page` juga memiliki satu kategori yang jauh lebih jarang muncul.
    *   **Implikasi**: Kategori minoritas ini mungkin bukan *error* data tetapi bisa menjadi indikator penting yang perlu diperhatikan oleh model.

4.  **Class Imbalance (Ketidakseimbangan Kelas)**:
    *   **Status**: Variabel target `Result` menunjukkan distribusi yang relatif seimbang:
        *   Phishing (`-1`): 3019 sampel
        *   Legitimate (`1`): 2830 sampel
    *   **Implikasi**: Perbedaan ini tidak signifikan (sekitar 6.6%), sehingga tidak memerlukan penanganan *class imbalance* khusus pada tahap awal.

5.  **Potensi Noise dan Masalah Kualitas Data Lainnya**:
    *   **Sifat Data Kategorikal/Ordinal**: Interpretasi 'noise' lebih mengacu pada inkonsistensi nilai dalam kategori yang telah didefinisikan (meskipun saat ini tidak ada nilai di luar `-1, 0, 1`).
    *   **Keterangan Fitur yang Samar**: Penjelasan beberapa fitur, seperti `URL_Length` dengan nilai `0` (sangat panjang atau sangat pendek), dapat menimbulkan ambiguitas atau potensi *noise* dalam interpretasi.
    *   **Potensi Inkonsistensi Labeling**: Selalu ada risiko *false positive/negative* dalam label `Result` dalam dataset *phishing* yang kompleks.
    *   **Ketergantungan Fitur**: Beberapa fitur mungkin berkorelasi tinggi, berpotensi memperkenalkan redundansi atau *noise* dalam model.

Secara keseluruhan, masalah duplikasi data adalah isu utama yang berhasil ditangani. Dataset kini bersih dari nilai hilang dan memiliki distribusi kelas yang seimbang. Analisis mendalam terhadap fitur-fitur kategorikal telah mengidentifikasi beberapa kategori minoritas yang mungkin informatif, dan perlunya perhatian terhadap potensi *noise* yang berkaitan dengan interpretasi fitur dan konsistensi labeling.

### 4.4 Exploratory Data Analysis (EDA) - (**OPSIONAL**)

**Requirement:** Minimal 3 visualisasi yang bermakna dan insight-nya.
**Contoh jenis visualisasi yang dapat digunakan:**
Jadi, fokuslah pada Histogram, Boxplot, Heatmap Korelasi, Bar Plot (termasuk Class Distribution Plot), dan setelah melatih model, Confusion Matrix Heatmap.


#### Visualisasi 1: Histogram
![Visualisasi 1: Histogram](images\visualisasi_histogram.png)

**Insight:**  
1.  **Distribution of `having_IP_Address`:**
    *   Histogram ini menunjukkan distribusi apakah URL menggunakan alamat IP (`1`) atau nama domain (`-1`).
    *   Terlihat bahwa ada sekitar 2500 URL yang tidak menggunakan alamat IP (nilai `-1`, menunjukkan nama domain), dan sekitar 3200 URL yang menggunakan alamat IP (nilai `1`).
    *   Ini mengindikasikan bahwa penggunaan alamat IP sebagai bagian dari URL lebih sering terjadi dalam dataset ini dibandingkan URL yang tidak menggunakannya.

2.  **Distribution of `URL_Length`:**
    *   Histogram ini menggambarkan panjang URL.
    *   Mayoritas URL memiliki panjang yang wajar (nilai `-1`), dengan jumlah lebih dari 4000.
    *   Ada sekitar 1200 URL yang memiliki panjang mencurigakan (nilai `1`).
    *   URL dengan nilai `0` (yang berarti sangat panjang atau sangat pendek) memiliki jumlah yang sangat sedikit, kurang dari 500. Ini menunjukkan bahwa URL dengan panjang yang 'mencurigakan' dalam arti ekstrem adalah kasus yang jarang.

3.  **Distribution of `Shortining_Service`:**
    *   Histogram ini menunjukkan apakah URL menggunakan layanan pemendek URL (nilai `-1`) atau tidak (nilai `1`).
    *   Sebagian besar URL (lebih dari 4500) tidak menggunakan layanan pemendek (`1`).
    *   Hanya sebagian kecil URL (kurang dari 1000) yang menggunakan layanan pemendek (`-1`). Ini menunjukkan bahwa penggunaan layanan pemendek URL cenderung jarang dalam dataset ini.

4.  **Distribution of `Result`:**
    *   Histogram ini menunjukkan distribusi variabel target, yaitu apakah URL tersebut adalah *phishing* (`-1`) atau *legitimate* (`1`).
    *   Jumlah URL *phishing* (`-1`) sekitar 3000.
    *   Jumlah URL *legitimate* (`1`) sedikit di bawah 3000.
    *   Visualisasi ini mengkonfirmasi observasi sebelumnya bahwa dataset memiliki distribusi kelas yang relatif seimbang antara URL *phishing* dan *legitimate*, yang merupakan kondisi baik untuk pelatihan model tanpa memerlukan penanganan *class imbalance* yang intensif.

#### Visualisasi 2: Box Plot

![Visualisasi 2: Box Plot](images\visualisasi_boxplot1.png)
![Visualisasi 2: Box Plot](images\visualisasi_boxplot2.png)

**Insight:**  
1.  **Box Plot of `URL_Length` by Result:**
    *   Untuk kedua kategori (`Phishing` dan `Legitimate`), sebagian besar URL memiliki `URL_Length` bernilai `-1` (panjang URL wajar). Ini diindikasikan oleh garis tebal di sekitar `-1` pada kedua box plot.
    *   Namun, ada *outlier* (titik-titik di luar "kumis" box plot) yang menunjukkan nilai `0` (panjang mencurigakan) dan `1` (panjang wajar) untuk kedua jenis URL. Kehadiran `0` (sangat panjang/pendek) pada kedua kategori menunjukkan bahwa panjang URL ekstrem bisa ditemukan di *phishing* maupun *legitimate*, meskipun mungkin lebih sering di salah satu kategori (yang tidak begitu jelas terlihat dari box plot ini saja).
    *   Secara umum, fitur ini memiliki distribusi yang sangat terkonsentrasi pada `-1`, dengan sedikit variasi.

2.  **Box Plot of `having_Sub_Domain` by Result:**
    *   Untuk URL *phishing* (`-1`), distribusi `having_Sub_Domain` menunjukkan sebagian besar nilainya berada di sekitar `0` atau `-1`, yang berarti URL *phishing* cenderung memiliki sedikit *sub-domain* atau tidak ada sama sekali. Ada juga beberapa URL *phishing* dengan `1` (*sub-domain* banyak).
    *   Untuk URL *legitimate* (`1`), sebagian besar nilainya terkonsentrasi pada `1` (memiliki banyak *sub-domain*), menunjukkan bahwa situs sah cenderung memiliki struktur *sub-domain* yang lebih kompleks. Mediannya lebih tinggi dibandingkan URL *phishing*.
    *   Perbedaan distribusi ini menunjukkan bahwa `having_Sub_Domain` adalah indikator yang cukup baik untuk membedakan antara URL *phishing* dan *legitimate*.

3.  **Box Plot of `age_of_domain` by Result:**
    *   Kedua kategori (`Phishing` dan `Legitimate`) menunjukkan bahwa sebagian besar `age_of_domain` memiliki nilai `-1` atau `1`. Dalam konteks fitur ini, `-1` mungkin berarti domain baru dan `1` berarti domain tua.
    *   Tampaknya mayoritas domain, baik *phishing* maupun *legitimate*, memiliki nilai `1` (domain tua). Hal ini mungkin karena representasi data dalam fitur ini cenderung biner dan tidak menunjukkan gradasi usia yang halus.
    *   Perbedaan antara kedua kategori tidak terlalu mencolok dari visualisasi ini, menunjukkan bahwa fitur ini mungkin tidak terlalu kuat dalam membedakan kedua kelas secara langsung dalam bentuk box plot ini.

4.  **Box Plot of `web_traffic` by Result:**
    *   Untuk URL *phishing* (`-1`), distribusi `web_traffic` cenderung ke arah `0` dan `-1`. Ini berarti URL *phishing* umumnya memiliki peringkat lalu lintas web yang rendah (`-1`) atau netral (`0`).
    *   Untuk URL *legitimate* (`1`), distribusi `web_traffic` cenderung ke arah `1`, menunjukkan bahwa situs sah umumnya memiliki peringkat lalu lintas web yang lebih tinggi.
    *   Perbedaan yang jelas antara median dan rentang nilai untuk kedua kategori menunjukkan bahwa `web_traffic` adalah fitur yang informatif untuk membedakan URL *phishing* dari *legitimate*.

#### Visualisasi 3: Confusion Matrix Heatmap

![Visualisasi 3: Confusion Matrix Heatmap](images\visualisasi_heatmap.png)

**Insight:**  
Matriks ini memiliki empat komponen utama:

1.  **True Positive (TP)**: Jumlah prediksi positif yang benar. (Misal: Model memprediksi *Phishing*, dan aktualnya memang *Phishing*).
2.  **True Negative (TN)**: Jumlah prediksi negatif yang benar. (Misal: Model memprediksi *Non-Phishing*, dan aktualnya memang *Non-Phishing*).
3.  **False Positive (FP)**: Jumlah prediksi positif yang salah (Type I error). (Misal: Model memprediksi *Phishing*, tapi aktualnya *Non-Phishing*). Ini juga dikenal sebagai *false alarm*.
4.  **False Negative (FN)**: Jumlah prediksi negatif yang salah (Type II error). (Misal: Model memprediksi *Non-Phishing*, tapi aktualnya *Phishing*). Ini juga dikenal sebagai *miss*.

Dalam visualisasi *heatmap* ini (mengacu pada `inline_data_5` yang menampilkan tiga *Confusion Matrix*), setiap matriks merepresentasikan kinerja satu model:

#### 1. Confusion Matrix Logistic Regression
*   **True Negative (Kiri Atas): 848**
    *   Model dengan benar mengidentifikasi 848 URL sebagai *Non-Phishing*.
*   **False Positive (Kanan Atas): 70**
    *   Model salah mengidentifikasi 70 URL sebagai *Phishing*, padahal sebenarnya *Non-Phishing*.
*   **False Negative (Kiri Bawah): 60**
    *   Model salah mengidentifikasi 60 URL sebagai *Non-Phishing*, padahal sebenarnya *Phishing*.
*   **True Positive (Kanan Bawah): 777**
    *   Model dengan benar mengidentifikasi 777 URL sebagai *Phishing*.

#### 2. Confusion Matrix Random Forest
*   **True Negative (Kiri Atas): 880**
    *   Model dengan benar mengidentifikasi 880 URL sebagai *Non-Phishing*.
*   **False Positive (Kanan Atas): 38**
    *   Model salah mengidentifikasi 38 URL sebagai *Phishing*, padahal sebenarnya *Non-Phishing*.
*   **False Negative (Kiri Bawah): 46**
    *   Model salah mengidentifikasi 46 URL sebagai *Non-Phishing*, padahal sebenarnya *Phishing*.
*   **True Positive (Kanan Bawah): 791**
    *   Model dengan benar mengidentifikasi 791 URL sebagai *Phishing*.

#### 3. Confusion Matrix Multilayer Perceptron (MLP)
*   **True Negative (Kiri Atas): 865**
    *   Model dengan benar mengidentifikasi 865 URL sebagai *Non-Phishing*.
*   **False Positive (Kanan Atas): 53**
    *   Model salah mengidentifikasi 53 URL sebagai *Phishing*, padahal sebenarnya *Non-Phishing*.
*   **False Negative (Kiri Bawah): 49**
    *   Model salah mengidentifikasi 49 URL sebagai *Non-Phishing*, padahal sebenarnya *Phishing*.
*   **True Positive (Kanan Bawah): 788**
    *   Model dengan benar mengidentifikasi 788 URL sebagai *Phishing*.

### Analisis Perbandingan:

Dari ketiga matriks ini, kita dapat melihat bahwa:
*   **Random Forest** memiliki jumlah *False Positive* (38) dan *False Negative* (46) yang paling rendah dibandingkan dua model lainnya. Ini menunjukkan bahwa Random Forest memiliki keseimbangan yang baik antara mengidentifikasi URL *phishing* dengan benar dan tidak salah mengklasifikasikan URL sah sebagai *phishing*.
*   **Logistic Regression** memiliki *False Positive* (70) dan *False Negative* (60) yang sedikit lebih tinggi, menunjukkan kinerja yang sedikit di bawah Random Forest dan MLP.
*   **MLP** berada di tengah, dengan *False Positive* (53) dan *False Negative* (49) yang lebih baik dari Logistic Regression tetapi sedikit lebih tinggi dari Random Forest.

Secara keseluruhan, *Confusion Matrix Heatmap* ini sangat membantu dalam membandingkan secara visual di mana setiap model unggul atau kurang dalam tugas klasifikasi *phishing* vs *non-phishing*.



---

## 5. DATA PREPARATION

Bagian ini menjelaskan **semua** proses transformasi dan preprocessing data yang dilakukan.
### 5.1 Data Cleaning
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

### 4. Data type conversion
* **Eksekusi**: Semua kolom fitur, yang awalnya dimuat sebagai string byte (misalnya, `b'-1'`, `b'1'`), dikonversi menjadi bilangan bulat `int64`.

* **Alasan**: Konversi ini diperlukan untuk memungkinkan analisis numerik dan pelatihan model yang tepat, karena algoritma pembelajaran mesin biasanya membutuhkan input numerik. Konversi tersebut melibatkan iterasi melalui setiap kolom dan menerapkan fungsi lambda untuk mendekode string byte ke UTF-8 dan kemudian mengonversinya menjadi bilangan bulat.
* **Hasil**: DataFrame `df_cleaned` diubah menjadi `df_processed`, dengan semua fitur yang diketik dengan tepat sebagai `int64`, sehingga dataset siap untuk pemodelan.

### 5.2 Feature Engineering
### 1. Pembuatan Fitur Baru: `Suspicious_Score`

**Tujuan**: Membuat fitur agregat baru yang dapat menangkap "risiko *phishing* kumulatif" untuk setiap URL. Fitur ini dirancang untuk menggabungkan indikator-indikator aktivitas mencurigakan dari beberapa fitur yang sudah ada menjadi satu skor tunggal. Hal ini diharapkan dapat memberikan sinyal yang lebih kuat kepada model.

**Metodologi**:
*   Kolom baru bernama `Suspicious_Score` ditambahkan ke `df_processed` dan diinisialisasi dengan nilai `0`.
*   Sebuah kamus `suspicious_conditions` didefinisikan, yang memetakan nama fitur ke daftar nilai yang dianggap mencurigakan (misalnya, `having_IP_Address: [1]` berarti URL yang memiliki alamat IP dianggap mencurigakan).
*   Iterasi dilakukan melalui setiap fitur dalam kamus `suspicious_conditions`.
*   Untuk setiap URL, jika nilai fitur cocok dengan salah satu kondisi mencurigakan yang ditentukan, nilai `1` ditambahkan ke `Suspicious_Score` URL tersebut. Dengan demikian, `Suspicious_Score` adalah jumlah dari semua indikator mencurigakan yang terpenuhi oleh suatu URL.

**Alasan di Balik Pendekatan Ini**:
*   **Agregasi Informasi**: Banyak fitur biner atau trinari mungkin memiliki dampak kecil secara individual, tetapi secara kolektif dapat memberikan sinyal yang kuat. `Suspicious_Score` mengagregasi sinyal-sinyal ini.
*   **Interpretasi**: Skor tunggal lebih mudah diinterpretasikan sebagai tingkat risiko *phishing* secara umum.
*   **Potensi Peningkatan Model**: Fitur ini berpotensi membantu model untuk lebih mudah mengidentifikasi pola yang melibatkan kombinasi beberapa atribut mencurigakan, yang mungkin sulit ditangkap oleh model hanya dengan melihat fitur-fitur individual.

### 2. Pemilihan Fitur (Feature Selection) menggunakan Random Forest Classifier

**Tujuan**: Mengurangi jumlah fitur yang digunakan untuk pelatihan model dengan hanya mempertahankan fitur-fitur yang paling informatif dan prediktif. Ini bertujuan untuk meningkatkan kinerja model (akurasi, kecepatan pelatihan) dan mengurangi *overfitting*.

**Metodologi**:
*   **Pemisahan Fitur dan Target**: Dataset `df_processed` dibagi menjadi fitur (`X`) dan variabel target (`y`, yaitu kolom 'Result').
*   **Pelatihan Random Forest**: Sebuah model `RandomForestClassifier` diinisialisasi dan dilatih pada seluruh dataset `X` dan `y`.
*   **Ekstraksi *Feature Importances***: Dari model Random Forest yang telah dilatih, nilai *feature importances* diekstrak. Random Forest secara intrinsik dapat mengukur seberapa besar kontribusi setiap fitur terhadap keputusan klasifikasi.
*   **Pemeringkatan dan Visualisasi**: *Feature importances* diubah menjadi objek `pandas Series`, diurutkan secara menurun, dan 10 fitur teratas ditampilkan. Selain itu, sebuah *bar plot* dibuat untuk memvisualisasikan skor kepentingan semua fitur.
*   **Pemilihan Fitur Berbasis Ambang Batas**: Fitur-fitur yang memiliki skor kepentingan di atas ambang batas yang ditentukan (dalam kasus ini, `0.01`) dipilih. Ambang batas ini dipilih setelah meninjau distribusi kepentingan fitur untuk memastikan bahwa fitur yang cukup relevan dipertahankan sambil membuang fitur yang kurang penting.
*   **Pembentukan DataFrame Baru**: Sebuah DataFrame baru (`X_selected`) dibuat, yang hanya berisi fitur-fitur yang telah dipilih.

**Alasan di Balik Pendekatan Ini**:
*   **Mengurangi Kompleksitas Model**: Dengan lebih sedikit fitur, model cenderung lebih sederhana dan lebih cepat untuk dilatih dan dievaluasi.
*   **Mencegah *Overfitting***: Fitur yang kurang informatif atau *noisy* dapat menyebabkan *overfitting*. Dengan menghilangkannya, model dapat belajar pola yang lebih umum.
*   **Meningkatkan Interpretasi**: Fokus pada fitur-fitur penting dapat membantu dalam memahami faktor-faktor utama yang berkontribusi pada deteksi *phishing*.

### 3. Mengapa Reduksi Dimensi Tradisional (seperti PCA) Tidak Diterapkan

Reduksi dimensi seperti Principal Component Analysis (PCA) biasanya digunakan untuk mengurangi jumlah fitur dalam dataset dengan menciptakan kombinasi linier dari fitur asli. Namun, dalam konteks dataset ini, PCA atau metode serupa tidak diterapkan karena beberapa alasan:

*   **Sifat Fitur Kategorikal/Ordinal**: Sebagian besar fitur dalam dataset ini bersifat kategorikal atau ordinal dengan nilai diskrit (`-1`, `0`, `1`). PCA bekerja paling baik dengan data kontinu di mana hubungan linier antar fitur lebih bermakna. Menggabungkan fitur-fitur kategorikal secara linier dapat menghasilkan *principal components* yang sulit diinterpretasikan dan mungkin tidak secara efektif menangkap hubungan non-linier yang ada.
*   **Kehilangan Interpretasi**: Tujuan utama dari banyak model deteksi *phishing* adalah tidak hanya untuk membuat prediksi yang akurat tetapi juga untuk memahami *mengapa* suatu URL diklasifikasikan sebagai *phishing*. Fitur asli (misalnya, `having_IP_Address`, `SSLfinal_State`) memiliki makna domain yang jelas. PCA akan mengubah fitur-fitur ini menjadi komponen-komponen abstrak yang kehilangan interpretasi langsung, sehingga menyulitkan untuk menjelaskan hasil model.
*   ***Feature Selection* Sudah Cukup Efektif**: Metode *feature selection* berbasis *tree-based model* seperti Random Forest secara efektif mengidentifikasi dan memilih fitur-fitur yang paling informatif tanpa mengubah sifat aslinya. Ini memungkinkan kita untuk mempertahankan interpretasi fitur sambil tetap mengurangi dimensi secara signifikan (dari 31 menjadi 15 fitur).

Dengan demikian, fokus pada pembuatan fitur yang bermakna domain dan *feature selection* berbasis kepentingan telah menjadi strategi yang lebih sesuai untuk dataset ini.

### 5.3 Data Transformation

## Encoding dan Scaling

Berdasarkan analisis dan pra-pemrosesan data yang telah dilakukan di notebook ini, fitur-fitur dalam dataset sudah dalam format numerik (`int64`) dengan nilai-nilai yang terbatas pada `-1`, `0`, dan `1`. Ini berarti data sudah secara efektif di-*encode* secara numerik, baik sebagai biner (dua nilai) atau ordinal (tiga nilai dengan urutan). Oleh karena itu:

*   **Encoding (Label Encoding, One-Hot Encoding, Ordinal Encoding)**: Tidak diperlukan lagi karena fitur-fitur tersebut sudah memiliki representasi numerik. Misalnya, `having_IP_Address` dengan nilai `-1` dan `1` sudah seperti *label encoding* biner.
*   **Scaling (Standardization, Normalization, MinMaxScaler)**: Untuk dataset ini, *scaling* kemungkinan besar tidak akan memberikan manfaat yang signifikan. Semua fitur berada dalam rentang yang sangat sempit (`-1` hingga `1`), sehingga varians dan skala antar fitur sudah relatif seragam. Model *tree-based* seperti Random Forest tidak sensitif terhadap *scaling*, dan untuk model seperti *Logistic Regression* atau MLP, rentang nilai yang seragam ini sudah cukup baik.

### 5.4 Data Splitting

**Strategi Pembagian Data:**

*   **Training set**: 70% (4094 samples)
*   **Test set**: 30% (1755 samples)
*   **Random state**: 42 untuk reproducibility

**Penjelasan dan Alasan Strategi Splitting:**

Strategi pembagian data yang digunakan adalah `train_test_split` dari `sklearn.model_selection` dengan rasio 70% untuk *training set* dan 30% untuk *test set*. Fitur (`X`) dan variabel target (`y`) diambil dari `df_processed` yang telah bersih dari duplikat dan fitur-fiturnya sudah direkayasa serta diseleksi.

Alasan di balik pilihan ini adalah sebagai berikut:

1.  **Standard Practice**: Pembagian 70/30 atau 80/20 adalah rasio yang umum dan direkomendasikan dalam *machine learning* untuk dataset berukuran menengah. Ini memberikan cukup data bagi model untuk belajar pola (70%) sambil menyisakan porsi yang cukup besar untuk evaluasi yang tidak bias (30%).
2.  **Reproducibility**: Penggunaan `random_state=42` memastikan bahwa setiap kali kode dijalankan, pembagian data akan selalu sama. Ini sangat penting untuk debugging, perbandingan model, dan memastikan hasil eksperimen dapat direproduksi.
3.  **Class Distribution**: Berdasarkan analisis `Class Imbalance` sebelumnya, variabel target `Result` memiliki distribusi yang relatif seimbang (Phishing: 3019 sampel, Legitimate: 2830 sampel). Oleh karena itu, *stratified splitting* (yang memastikan proporsi kelas yang sama di *training* dan *test set*) tidak secara eksplisit diatur, namun dengan `test_size=0.3` dan `random_state` yang tetap, diharapkan distribusi kelas tetap terjaga dengan baik dalam subset data.

### 5.5 Data Balancing (jika diperlukan)
Berdasarkan analisis ketidakseimbangan kelas yang telah dilakukan sebelumnya, dataset ini tidak menunjukkan masalah class imbalance yang signifikan. Distribusi kelas antara URL phishing dan legitimate relatif seimbang (3019 vs 2830 sampel, sekitar 6.6% perbedaan). Oleh karena itu, tidak dibutuhkan teknik data balancing seperti SMOTE, Random Undersampling, Class weights, atau Ensemble sampling pada dataset ini.

### 5.6 Ringkasan Data Preparation

### 1. Data Cleaning
*   **Apa yang dilakukan**: Menangani *missing values*, menghapus data duplikat, dan menganalisis *outliers*.
*   **Mengapa penting**: Menjamin integritas data, mencegah bias model, mengurangi pemborosan sumber daya, dan memastikan analisis statistik yang akurat.
*   **Bagaimana implementasinya**: 
    *   **Missing Values**: Dilakukan pengecekan menggunakan `df.isnull().sum()`. Hasilnya, tidak ditemukan *missing values*, sehingga tidak ada tindakan lebih lanjut yang diperlukan.
    *   **Removing Duplicates**: Menggunakan `df.duplicated().sum()` untuk mengidentifikasi 5206 baris duplikat (sekitar 47%). Baris duplikat kemudian dihapus dengan `df.drop_duplicates().copy()` untuk menghasilkan `df_cleaned` dengan 5849 baris unik.
    *   **Handling Outliers**: Karena fitur bersifat kategorikal/ordinal (-1, 0, 1), deteksi *outlier* tradisional tidak diterapkan. Fokus pada identifikasi kategori minoritas yang berpotensi informatif melalui `value_counts` untuk setiap fitur (misalnya, `URL_Length` dengan nilai 0, `RightClick` dengan -1, `Redirect` dengan 1).
    *   **Data Type Conversion**: Semua kolom yang awalnya *byte strings* (misal, `b'-1'`) dikonversi ke tipe data `int64` menggunakan fungsi `apply` dengan `decode('utf-8')` dan `int()`. Ini penting agar data dapat diproses oleh algoritma *machine learning* yang memerlukan input numerik.

### 2. Feature Engineering: `Suspicious_Score`
*   **Apa yang dilakukan**: Membuat fitur baru bernama `Suspicious_Score` dengan menjumlahkan indikator aktivitas mencurigakan dari fitur-fitur yang sudah ada.
*   **Mengapa penting**: Mengagregasi sinyal-sinyal mencurigakan yang mungkin lemah secara individual menjadi satu skor yang lebih kuat, meningkatkan interpretasi sebagai tingkat risiko *phishing*, dan berpotensi membantu model menangkap pola kompleks dengan lebih baik.
*   **Bagaimana implementasinya**: Kolom `Suspicious_Score` diinisialisasi ke 0. Sebuah kamus `suspicious_conditions` mendefinisikan nilai-nilai mencurigakan untuk setiap fitur. Iterasi dilakukan untuk setiap fitur, menambahkan 1 ke `Suspicious_Score` jika nilai fitur memenuhi kondisi mencurigakan yang ditentukan.

### 3. Feature Selection: Random Forest Classifier
*   **Apa yang dilakukan**: Mengidentifikasi dan memilih fitur-fitur yang paling informatif dan prediktif menggunakan *feature importances* dari Random Forest.
*   **Mengapa penting**: Mengurangi kompleksitas model, mencegah *overfitting*, meningkatkan kecepatan pelatihan, dan mempertahankan interpretasi fitur yang jelas.
*   **Bagaimana implementasinya**: 
    *   Dataset dibagi menjadi fitur (`X = df_processed.drop('Result', axis=1)`) dan target (`y = df_processed['Result']`).
    *   Model `RandomForestClassifier` dilatih pada seluruh dataset untuk mendapatkan *feature importances*.
    *   *Feature importances* diurutkan dan divisualisasikan. 
    *   Fitur-fitur dengan skor kepentingan di atas ambang batas 0.01 dipilih, menghasilkan `X_selected` dengan 15 fitur (dari 31 fitur awal). Fitur `SSLfinal_State`, `URL_of_Anchor`, dan `Suspicious_Score` termasuk yang paling penting.

### 4. Data Transformation: Encoding dan Scaling
*   **Apa yang dilakukan**: Menentukan apakah *encoding* atau *scaling* diperlukan.
*   **Mengapa penting**: Memastikan data dalam format yang tepat untuk model ML. *Encoding* mengubah data non-numerik menjadi numerik, sedangkan *scaling* menyamakan rentang nilai fitur.
*   **Bagaimana implementasinya**: 
    *   **Encoding**: Tidak diperlukan karena semua fitur sudah dalam format numerik (`int64`) dengan nilai diskrit (-1, 0, 1), yang sudah efektif sebagai *encoding* biner atau ordinal.
    *   **Scaling**: Tidak diperlukan karena semua fitur berada dalam rentang yang sangat sempit (`-1` hingga `1`), sehingga varians dan skala sudah relatif seragam. Model *tree-based* juga tidak sensitif terhadap *scaling*.

### 5. Data Splitting
*   **Apa yang dilakukan**: Membagi dataset menjadi *training set* dan *testing set*.
*   **Mengapa penting**: Untuk melatih model pada sebagian data (*training set*) dan mengevaluasi kinerja model secara tidak bias pada data yang belum pernah dilihat (*testing set*), memastikan generalisasi model yang baik.
*   **Bagaimana implementasinya**: Menggunakan `train_test_split` dari `sklearn.model_selection`.
    *   `X` dan `y` diambil dari fitur-fitur yang telah diseleksi (`X_selected`) dan variabel target (`df_processed['Result']`).
    *   Rasio pembagian yang digunakan adalah 70% untuk *training set* (4094 sampel) dan 30% untuk *testing set* (1755 sampel).
    *   `random_state=42` digunakan untuk memastikan *reproducibility* hasil.
    *   *Stratified splitting* tidak secara eksplisit diatur karena distribusi kelas yang sudah seimbang.

### 6. Data Balancing
*   **Apa yang dilakukan**: Menganalisis kebutuhan akan teknik *data balancing*.
*   **Mengapa penting**: Menghindari model yang bias terhadap kelas mayoritas dalam kasus *class imbalance*.
*   **Bagaimana implementasinya**: Berdasarkan analisis `Class Imbalance` di awal, variabel target memiliki distribusi yang relatif seimbang (Phishing: 3019 sampel, Legitimate: 2830 sampel). Perbedaan yang kecil (sekitar 6.6%) ini tidak dianggap signifikan, sehingga **tidak diperlukan** teknik *data balancing* seperti SMOTE, Random Undersampling, *class weights*, atau *ensemble sampling*.

---

## 6. MODELING
### 6.1 Model 1 — Baseline Model
#### 6.1.1 Deskripsi Model

**Nama Model:** Logistic Regression  
**Teori Singkat:**  
Logistic Regression adalah model klasifikasi yang bekerja dengan menghitung kombinasi linear dari setiap fitur input menggunakan bobot tertentu, kemudian hasil perhitungan tersebut dimasukkan ke dalam fungsi sigmoid untuk menghasilkan nilai probabilitas antara 0 dan 1. Probabilitas ini merepresentasikan kemungkinan suatu data termasuk ke dalam kelas tertentu, biasanya kelas positif. Selanjutnya, model membandingkan probabilitas tersebut dengan nilai ambang (threshold), umumnya 0,5, untuk menentukan label kelas akhir. Proses pembelajaran dilakukan dengan menyesuaikan bobot agar nilai kesalahan berbasis log loss (cross-entropy) menjadi minimum, sehingga probabilitas yang dihasilkan sesuai dengan distribusi data. Model ini sederhana, cepat, dan mudah diinterpretasikan, tetapi kurang efektif jika hubungan antara fitur dan kelas bersifat non-linear.  
**Alasan Pemilihan:**  
Algoritma klasifikasi yang banyak digunakan untuk masalah klasifikasi biner dan merupakan baseline yang bagus karena sederhana dan efektif.  

#### 6.1.2 Hyperparameter
**Parameter yang digunakan:**
```
- 'C': 1.0  
- 'class_weight': None  
- 'dual': False  
- 'fit_intercept': True  
- 'intercept_scaling': 1  
- 'l1_ratio': None  
- 'max_iter': 100  
- 'multi_class': 'deprecated'  
- 'n_jobs': None  
- 'penalty': 'l2'  
- 'random_state': 42  
- 'solver': 'lbfgs'  
- 'tol': 0.0001  
- 'verbose': 0  
- 'warm_start': False
```

#### 6.1.3 Implementasi (Ringkas)
```python
from sklearn.linear_model import LogisticRegression

# 1. Inisialisasi model Logistic Regression
model = LogisticRegression(
    penalty='l2',
    C=1.0,
    solver='liblinear',
    max_iter=100,
    random_state=42
)

# 2. Training model using the globally defined X_train and y_train
model.fit(X_train, y_train)

# 3. Prediksi using the globally defined X_test
y_pred = model.predict(X_test)

print("Logistic Regression (Baseline) Model trained and predictions made.")
```

#### 6.1.4 Hasil Awal

Accuracy Logistic Regression (Baseline): 0.905982905982906

---

### 6.2 Model 2 — ML / Advanced Model
#### 6.2.1 Deskripsi Model

**Nama Model:** Random Forest  
**Teori Singkat:**  
Random Forest adalah metode ensemble berbasis pohon keputusan yang sangat kuat untuk tugas klasifikasi. Random Forest menggabungkan banyak pohon keputusan untuk mengurangi overfitting dan meningkatkan akurasi secara signifikan dibandingkan dengan satu pohon keputusan. 

**Alasan Pemilihan:**  
Untuk klasifikasi phishing yang kompleks, Random Forest memiliki akurasi dan ketahanannya yang tinggi

**Keunggulan:**
- Akurasi tinggi pada dataset kompleks  
- Mengurangi overfitting dibanding pohon tunggal  
- Relatif tahan terhadap noise dan outlier  
- Dapat menangani missing values secara implisit  
- Mendukung fitur numerik dan kategorikal  
- Tidak memerlukan feature scaling  
- Menyediakan feature importance  
- Stabil karena berbasis ensemble

**Kelemahan:**
- Sulit diinterpretasikan (cenderung black box)  
- Membutuhkan memori dan komputasi besar  
- Waktu prediksi lebih lambat  
- Kurang optimal untuk data sangat sparse  
- Bias pada fitur dengan banyak level  
- Tidak mampu melakukan ekstrapolasi

#### 6.2.2 Hyperparameter

**Parameter yang digunakan:**
```
- 'bootstrap': True  
- 'ccp_alpha': 0.0  
- 'class_weight': None  
- 'criterion': 'gini'  
- 'max_depth': None  
- 'max_features': 'sqrt'  
- 'max_leaf_nodes': None  
- 'max_samples': None  
- 'min_impurity_decrease': 0.0  
- 'min_samples_leaf': 1  
- 'min_samples_split': 2  
- 'min_weight_fraction_leaf': 0.0  
- 'monotonic_cst': None  
- 'n_estimators': 100  
- 'n_jobs': None  
- 'oob_score': False  
- 'random_state': 42  
- 'verbose': 0  
- 'warm_start': False
```

**Hyperparameter Tuning (jika dilakukan):**
- Metode: Grid Search  
- Best parameters: ['max_depth': None, 'min_samples_leaf': 1, 'min_samples_split': 5, 'n_estimators': 50]

#### 6.2.3 Implementasi (Ringkas)
```python
from sklearn.ensemble import RandomForestClassifier

# Implement the Random Forest model using the best parameters found by GridSearchCV
# The best_params_rf variable is already available from the previous GridSearchCV cell.
rf_model_tuned = RandomForestClassifier(
    n_estimators=best_params_rf['n_estimators'],
    max_depth=best_params_rf['max_depth'],
    min_samples_leaf=best_params_rf['min_samples_leaf'],
    min_samples_split=best_params_rf['min_samples_split'],
    random_state=42 # Ensure reproducibility
)

# Train the model
print("Melatih model Random Forest (tuned) dengan parameter terbaik...")
rf_model_tuned.fit(X_train, y_train)
print("Model Random Forest (tuned) selesai dilatih.\n")

# Make predictions on the test set
y_pred_rf_tuned = rf_model_tuned.predict(X_test)

print("Random Forest (tuned) model trained and predictions made.")
```

#### 6.2.4 Hasil Model

Akurasi Random Forest (tuned): 0.9402
---

### 6.3 Model 3 — Deep Learning Model (WAJIB)

#### 6.3.1 Deskripsi Model

**Nama Model:** Multilayer Perceptron (MLP)

** (Centang) Jenis Deep Learning: **
- [✅] Multilayer Perceptron (MLP) - untuk tabular
- [ ] Convolutional Neural Network (CNN) - untuk image
- [ ] Recurrent Neural Network (LSTM/GRU) - untuk sequential/text
- [ ] Transfer Learning - untuk image
- [ ] Transformer-based - untuk NLP
- [ ] Autoencoder - untuk unsupervised
- [ ] Neural Collaborative Filtering - untuk recommender

**Alasan Pemilihan:**  
Karena data sudah dalam format feature yang terstruktur.

#### 6.3.2 Arsitektur Model

**Deskripsi Layer:**

Berikut adalah arsitektur model Multilayer Perceptron (MLP):
1. Input Layer: shape (15,)
2. Hidden Layer 1: 100 units, activation='relu'
3. Hidden Layer 2: 50 units, activation='relu'
4. Output Layer: 2 units, activation='softmax' (default for multi-class in MLPClassifier with Adam solver)

Total parameters: 6752
Trainable parameters: 6752
```

#### 6.3.3 Input & Preprocessing Khusus

**Input shape:** 15  
**Preprocessing khusus untuk DL:**
Data input (X_train, X_test) sudah dalam format numerik (int64) dengan nilai antara -1, 0, dan 1 setelah proses Data Cleaning dan Feature Selection. Oleh karena itu, tidak ada encoding atau scaling tambahan yang diterapkan sebelum pelatihan model MLP, karena model tree-based dan MLP umumnya dapat bekerja dengan baik pada rentang nilai yang seragam ini tanpa memerlukan normalisasi atau standarisasi.

#### 6.3.4 Hyperparameter

**Training Configuration:**
```
Hyperparameter Model:

- hidden_layer_sizes: (100, 50) - Dua hidden layer dengan 100 dan 50 neuron.  
- activation: 'relu' - Fungsi aktivasi ReLU digunakan untuk hidden layer.  
- solver: 'adam' - Optimizer yang digunakan adalah Adam.  
- max_iter: 500 - Jumlah maksimum iterasi (epoch) pelatihan.  
- random_state: 42 - Untuk reproducibility.  

Training Configuration:

- Optimizer: Adam  
- Learning rate: Default (0.001) untuk solver 'adam'.  
- Loss function: Log Loss (setara dengan Binary Cross-Entropy untuk klasifikasi - biner seperti ini).  
- Metrics: Akurasi dihitung secara terpisah setelah pelatihan untuk evaluasi.  
- Batch size: Default ('auto'), yang berarti min(200, n_samples). Untuk dataset - ini, sekitar 200.  
- Epochs: 235 (model konvergen sebelum mencapai max_iter=500).  
- Validation split: Tidak ada validation split internal; data dipecah menjadi training dan testing set secara terpisah (X_train, y_train untuk pelatihan, X_test, y_test untuk evaluasi).  
- Callbacks: MLPClassifier dari scikit-learn tidak mendukung callbacks secara langsung seperti framework deep learning lainnya.
```

#### 6.3.5 Implementasi (Ringkas)

**Framework:** TensorFlow/Keras / PyTorch
```python
# Contoh kode TensorFlow/Keras
import tensorflow as tf
from tensorflow import keras

model_dl = keras.Sequential([
    keras.layers.Dense(128, activation='relu', input_shape=(input_dim,)),
    keras.layers.Dropout(0.3),
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dropout(0.3),
    keras.layers.Dense(num_classes, activation='softmax')
])

model_dl.compile(
    optimizer='adam',
    loss='categorical_crossentropy',
    metrics=['accuracy']
)

history = model_dl.fit(
    X_train, y_train,
    validation_split=0.2,
    epochs=50,
    batch_size=32,
    callbacks=[early_stopping]
)
```

#### 6.3.6 Training Process

**Training Time:**

- **TensorFlow/Keras :** Proses pelatihan model MLP dengan TensorFlow/Keras membutuhkan waktu sekitar **1.95 detik**.
- **Scikit-learn MLPClassifier :** Waktu pelatihan adalah **11.97 detik** dengan jumlah epoch yang dijalankan sebanyak 235.

**Computational Resource:**

Pelatihan dilakukan menggunakan **CPU** di platform **Google Colab** (runtime default).

**Training History Visualization:**

![Training History Visualization](images\Training_History_Visualization.png)

**Analisis Training:**

- **Apakah model mengalami overfitting?** Tidak. Seperti yang terlihat dari kedua plot (Loss dan Accuracy), kurva pelatihan (`Training Loss`/`Training Accuracy`) dan kurva validasi (`Validation Loss`/`Validation Accuracy`) bergerak relatif dekat satu sama lain. Tidak ada divergensi yang signifikan di mana *training loss* terus menurun sementara *validation loss* mulai naik, atau *training accuracy* terus meningkat sementara *validation accuracy* mendatar atau menurun. Ini menunjukkan bahwa model berhasil melakukan generalisasi dengan baik ke data yang tidak terlihat selama pelatihan.
- **Apakah model sudah converge?** Ya. Pada plot *Loss*, terlihat bahwa baik *training loss* maupun *validation loss* menurun dengan cepat di awal epoch dan kemudian cenderung mendatar serta stabil setelah sekitar 20-30 epoch (untuk model TensorFlow/Keras). Hal ini mengindikasikan bahwa model telah menemukan set bobot yang optimal dan tidak lagi membuat kemajuan signifikan dalam mengurangi *error*. Penggunaan `EarlyStopping` dengan `patience=10` juga memastikan bahwa pelatihan berhenti begitu *validation loss* tidak membaik selama beberapa epoch, yang merupakan indikator konvergensi yang baik.
- **Apakah perlu lebih banyak epoch?** Tidak. Mengingat model telah menunjukkan konvergensi dan `EarlyStopping` telah menghentikan pelatihan pada titik optimal (setelah 44 epoch, jauh sebelum `epochs=100` yang ditentukan dalam konfigurasi awal TensorFlow/Keras), menambahkan lebih banyak *epoch* kemungkinan besar tidak akan meningkatkan performa model. Sebaliknya, hal tersebut justru dapat meningkatkan risiko *overfitting* jika tidak ada mekanisme regulasi yang kuat, meskipun dalam kasus ini, model sudah stabil dan tidak menunjukkan tanda-tanda *overfitting*.

#### 6.3.7 Model Summary

![Model Summary](images\Model_Summary.png)

---

## 7. EVALUATION

### 7.1 Metrik Evaluasi

Menggunakan Confusion matrix, berfungsi untuk mengevaluasi kinerja model klasifikasi dengan menunjukkan perbandingan antara label aktual dan hasil prediksi secara rinci. Matriks ini menampilkan jumlah prediksi benar dan salah untuk setiap kelas dalam bentuk True Positive, True Negative, False Positive, dan False Negative, sehingga kita tidak hanya melihat seberapa banyak prediksi yang benar, tetapi juga jenis kesalahan apa yang dibuat model. Dengan confusion matrix, kita dapat menilai apakah model cenderung salah mengklasifikasikan kelas tertentu, serta menjadi dasar perhitungan metrik lain seperti accuracy, precision, recall, dan F1-score, yang sangat penting terutama ketika data tidak seimbang

### 7.2 Hasil Evaluasi Model

#### 7.2.1 Model 1 (Baseline) Logistic Regression

**Metrik:**
```
- Accuracy: 0.9060
- Precision: 0.9062
- Recall: 0.9060
- F1-Score: 0.9060
- ROC-AUC: 0.9694
```

**Confusion Matrix / Visualization:**  
![LConfusion Matrix ogistic Regression](images\confusion_logistic_regression.png)

#### 7.2.2 Model 2 (Advanced/ML) Random Forest

**Metrik:**
```
- Accuracy: 0.9402
- Precision: 0.9403
- Recall: 0.9402
- F1-Score: 0.9402
- ROC-AUC: 0.9861
```

**Confusion Matrix / Visualization:**  
![Confusion Matrix Random Forest](images\confusion_random_forest.png)

**Feature Importance (jika applicable):**  
[Insert plot feature importance untuk tree-based models]

#### 7.2.3 Model 3 (Deep Learning) Multilayer Perceptron MPL

**Metrik:**
```
- Accuracy: 0.9242
- Precision: 0.9259
- Recall: 0.9242
- F1-Score: 0.9242
- ROC-AUC: 0.9826
```

**Confusion Matrix / Visualization:**  
![Confusion Matrix Multilayer Perceptron MPL](images\confusion_Multilayer_Perceptron_MPL.png)

**Training History:**  
[Sudah diinsert di Section 6.3.6]

### 7.3 Perbandingan Ketiga Model

**Tabel Perbandingan:**

| Model | Accuracy | Precision | Recall | F1-Score | ROC_AUC |
|-------|----------|-----------|--------|----------|---------------|
| Logistic Regression | 0.9060 | 0.9062 | 0.9060 | 0.9060 | 0.9694 |
| Random Forest | 0.9402 | 0.9403 | 0.9402 | 0.9402 | 0.9861 |
| Multilayer Perceptron MLP | 0.9242 | 0.9259 | 0.9242 | 0.9242 | 0.9826 |

**Visualisasi Perbandingan:**  
![Visualisasi Perbandingan](images\Visualisasi_Perbandingan.png)

### 7.4 Analisis Hasil

**Interpretasi:**

Berdasarkan hasil pelatihan dan evaluasi tiga model (Logistic Regression, Random Forest, dan Multilayer Perceptron), berikut adalah analisis detailnya:

1.  **Model Terbaik:**
    Model **Random Forest (Tuned)** adalah yang terbaik. Ini ditunjukkan oleh metrik evaluasi yang superior:
    *   **Akurasi Tertinggi**: 0.9402
    *   **ROC-AUC Tertinggi**: 0.9861
    *   **F1-Score Tertinggi**: 0.9402
    *   **Kesalahan Klasifikasi Terendah**: Memiliki jumlah *False Positives* (58) dan *False Negatives* (47) terendah dari semua model. Ini sangat krusial dalam deteksi *phishing* karena meminimalkan risiko URL sah yang salah diklasifikasikan sebagai *phishing* (FP) dan, yang lebih penting, URL *phishing* yang terlewat (FN).

2.  **Perbandingan dengan Baseline:**
    *   **Peningkatan Signifikan dari Logistic Regression (Baseline)**: Akurasi Logistic Regression adalah 0.9060, sedangkan Random Forest (Tuned) mencapai 0.9402. Ini adalah peningkatan akurasi sekitar 3.42%. Demikian pula, ROC-AUC meningkat dari 0.9694 menjadi 0.9861. Perbaikan ini menunjukkan bahwa model yang lebih kompleks seperti Random Forest, dengan kemampuannya menangani hubungan non-linier dan interaksi fitur, mampu mengekstraksi pola yang lebih baik dari data dibandingkan model linear.
    *   **Mengungguli MLP**: Random Forest (Tuned) juga sedikit lebih baik dari MLP (TensorFlow/Keras) yang memiliki akurasi 0.9242 dan ROC-AUC 0.9826. Meskipun MLP juga menunjukkan kinerja yang baik, Random Forest berhasil meminimalkan kedua jenis kesalahan (FP dan FN) secara lebih seimbang.

3.  **Trade-off:**
    *   **Performa vs. Kompleksitas**: Random Forest (Tuned) memberikan performa terbaik, namun ini datang dengan kompleksitas model yang lebih tinggi dibandingkan Logistic Regression. Random Forest adalah *ensemble* dari banyak pohon keputusan, membuatnya lebih sulit diinterpretasikan secara langsung dibandingkan koefisien linear pada Logistic Regression. MLP, sebagai model *deep learning*, juga memiliki kompleksitas yang tinggi dengan banyak parameter dan *hidden layer*.
    *   **Performa vs. Waktu Training**: Logistic Regression adalah yang tercepat untuk dilatih. Random Forest (Tuned) membutuhkan waktu lebih lama karena proses *GridSearchCV* untuk *tuning hyperparameter*, namun setelah *tuning*, waktu pelatihan model akhir masih relatif cepat. MLP (TensorFlow/Keras) memiliki waktu pelatihan yang lebih lama dibandingkan Logistic Regression tetapi lebih cepat dari Scikit-learn MLPClassifier yang tidak di-*tune* secara ekstensif.
    *   **Memori/Sumber Daya**: Model Random Forest dan MLP cenderung membutuhkan lebih banyak memori dan sumber daya komputasi dibandingkan Logistic Regression, terutama selama pelatihan dan *inference* jika model sangat besar.

4.  **Error Analysis:**
    *   **False Positives (FP)**: Model MLP (TensorFlow/Keras) memiliki jumlah FP tertinggi (93), yang berarti model ini paling sering salah mengklasifikasikan URL sah sebagai *phishing*. Logistic Regression juga memiliki FP yang tinggi (91). Dalam konteks deteksi *phishing*, FP bisa mengganggu pengguna yang sah. Random Forest memiliki FP terendah (58).
    *   **False Negatives (FN)**: Logistic Regression memiliki FN tertinggi (74), yang merupakan masalah serius karena berarti banyak URL *phishing* yang terlewat. MLP memiliki FN terendah (40), sedikit lebih rendah dari Random Forest (47). Meminimalkan FN sangat penting dalam deteksi *phishing* untuk mencegah ancaman keamanan yang sebenarnya.
    *   **Kasus Sulit Diprediksi**: URL yang memiliki karakteristik campuran antara *phishing* dan *legitimate*, atau URL *phishing* yang sangat canggih dan menyerupai URL sah, kemungkinan besar menjadi sumber kesalahan ini. Misalnya, URL *phishing* yang menggunakan sertifikat SSL valid atau *domain* yang sudah lama terdaftar bisa jadi lebih sulit dideteksi.

5.  **Overfitting/Underfitting:**
    *   **Logistic Regression (Baseline)**: Ada kemungkinan model ini sedikit *underfitting* karena merupakan model yang sangat sederhana (linear) dan mungkin tidak mampu menangkap semua kompleksitas pola dalam data. Performa yang lebih rendah dibandingkan model lain mendukung hipotesis ini.
    *   **Random Forest (Tuned)**: Berdasarkan evaluasi, model ini tidak menunjukkan tanda-tanda *overfitting* yang signifikan. Proses *tuning hyperparameter* dengan *GridSearchCV* dan validasi silang membantu menemukan parameter optimal yang menyeimbangkan *bias* dan *variance*. Akurasi yang tinggi pada data *test* menunjukkan kemampuan *generalisasi* yang baik.
    *   **Multilayer Perceptron (TensorFlow/Keras)**: Analisis kurva *loss* pelatihan dan validasi menunjukkan bahwa model ini tidak mengalami *overfitting*. Kedua kurva bergerak beriringan dan stabil, serta penggunaan *EarlyStopping* efektif menghentikan pelatihan sebelum *validation loss* mulai meningkat, memastikan *generalisasi* yang baik.

---

## 8. CONCLUSION

### 8.1 Kesimpulan Utama

**Model Terbaik:**  
[Sebutkan model terbaik berdasarkan evaluasi]

**Alasan:**  
[Jelaskan mengapa model tersebut lebih unggul]

**Pencapaian Goals:**  
[Apakah goals di Section 3.2 tercapai? Jelaskan]

### 8.2 Key Insights

**Insight dari Data:**
- [Insight 1]
- [Insight 2]
- [Insight 3]

**Insight dari Modeling:**
- [Insight 1]
- [Insight 2]

### 8.3 Kontribusi Proyek

**Manfaat praktis:**  
[Jelaskan bagaimana proyek ini dapat digunakan di dunia nyata]

**Pembelajaran yang didapat:**  
[Jelaskan apa yang Anda pelajari dari proyek ini]

---

## 9. FUTURE WORK (Opsional)

Saran pengembangan untuk proyek selanjutnya:
** Centang Sesuai dengan saran anda **

**Data:**
- [ ] Mengumpulkan lebih banyak data
- [ ] Menambah variasi data
- [ ] Feature engineering lebih lanjut

**Model:**
- [ ] Mencoba arsitektur DL yang lebih kompleks
- [ ] Hyperparameter tuning lebih ekstensif
- [ ] Ensemble methods (combining models)
- [ ] Transfer learning dengan model yang lebih besar

**Deployment:**
- [ ] Membuat API (Flask/FastAPI)
- [ ] Membuat web application (Streamlit/Gradio)
- [ ] Containerization dengan Docker
- [ ] Deploy ke cloud (Heroku, GCP, AWS)

**Optimization:**
- [ ] Model compression (pruning, quantization)
- [ ] Improving inference speed
- [ ] Reducing model size

---

## 10. REPRODUCIBILITY (WAJIB)

### 10.1 GitHub Repository

**Link Repository:** [URL GitHub Anda]

**Repository harus berisi:**
- ✅ Notebook Jupyter/Colab dengan hasil running
- ✅ Script Python (jika ada)
- ✅ requirements.txt atau environment.yml
- ✅ README.md yang informatif
- ✅ Folder structure yang terorganisir
- ✅ .gitignore (jangan upload dataset besar)

### 10.2 Environment & Dependencies

**Python Version:** [3.8 / 3.9 / 3.10 / 3.11]

**Main Libraries & Versions:**
```
numpy==1.24.3
pandas==2.0.3
scikit-learn==1.3.0
matplotlib==3.7.2
seaborn==0.12.2

# Deep Learning Framework (pilih salah satu)
tensorflow==2.14.0  # atau
torch==2.1.0        # PyTorch

# Additional libraries (sesuaikan)
xgboost==1.7.6
lightgbm==4.0.0
opencv-python==4.8.0  # untuk computer vision
nltk==3.8.1           # untuk NLP
transformers==4.30.0  # untuk BERT, dll

```

## INFORMASI PROYEK

**Judul Proyek:** Klasifikasikan situs web sebagai situs phishing atau sah menggunakan model Machine Learning

**Nama Mahasiswa:** Ilham Putra Arysila  
**NIM:** 233307051  
**Program Studi:** Teknologi Informasi  
**Mata Kuliah:** Data Science  
**Dosen Pengampu:** Nama Dosen  
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
Tuliskan 2–4 pernyataan masalah yang jelas dan spesifik.

**Contoh (universal):**
1. Model perlu mampu memprediksi nilai target dengan akurasi tinggi
2. Sistem harus dapat mengidentifikasi pola pada citra secara otomatis
3. Dataset memiliki noise sehingga perlu preprocessing yang tepat
4. Dibutuhkan model deep learning yang mampu belajar representasi fitur kompleks

**[Tulis problem statements Anda di sini]**

### 3.2 Goals

Tujuan harus spesifik, terukur, dan selaras dengan problem statement.
**Contoh tujuan:**
1. Membangun model ML untuk memprediksi variabel target dengan akurasi > 80%
2. Mengukur performa tiga pendekatan model (baseline, advanced, deep learning)
3. Menentukan model terbaik berdasarkan metrik evaluasi yang relevan
4. Menghasilkan sistem yang dapat bekerja secara reproducible

**[Tulis goals Anda di sini]**

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
MLP, juga dikenal sebagai feedforward neural network, adalah arsitektur dasar deep learning yang sangat efektif untuk masalah klasifikasi pada data tabular. Dengan setidaknya 2 hidden layers, jaringan ini dapat mempelajari pola non-linear yang kompleks dalam data untuk membedakan antara situs phishing dan non-phishing. Ini akan bekerja dengan baik karena data Anda sudah dalam format feature yang terstruktur.

**Minimum Requirements untuk Deep Learning:**
- ✅ Model harus training minimal 10 epochs
- ✅ Harus ada plot loss dan accuracy/metric per epoch
- ✅ Harus ada hasil prediksi pada test set
- ✅ Training time dicatat (untuk dokumentasi)

**Tidak Diperbolehkan:**
- ❌ Copy-paste kode tanpa pemahaman
- ❌ Model tidak di-train (hanya define arsitektur)
- ❌ Tidak ada evaluasi pada test set

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

## Summary of Identified Data Issues

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

CS2025\images\visualisasi_boxplot1.png
CS2025\images\visualisasi_boxplot2.png

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

[Insert gambar/plot]

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
**Aktivitas:**
- Handling missing values
- Removing duplicates
- Handling outliers
- Data type conversion
**Contoh:**
```
Missing Values:
- Fitur 'age' memiliki 50 missing values (5% dari data)
- Strategi: Imputasi dengan median karena distribusi skewed
- Alasan: Median lebih robust terhadap outliers dibanding mean
```

**[Jelaskan langkah-langkah data cleaning yang Anda lakukan]**



### 5.2 Feature Engineering
**Aktivitas:**
- Creating new features
- Feature extraction
- Feature selection
- Dimensionality reduction

**[Jelaskan feature engineering yang Anda lakukan]**

### 5.3 Data Transformation

**Untuk Data Tabular:**
- Encoding (Label Encoding, One-Hot Encoding, Ordinal Encoding)
- Scaling (Standardization, Normalization, MinMaxScaler)

**Untuk Data Text:**
- Tokenization
- Lowercasing
- Removing punctuation/stopwords
- Stemming/Lemmatization
- Padding sequences
- Word embedding (Word2Vec, GloVe, fastText)

**Untuk Data Image:**
- Resizing
- Normalization (pixel values 0-1 atau -1 to 1)
- Data augmentation (rotation, flip, zoom, brightness, etc.)
- Color space conversion

**Untuk Time Series:**
- Creating time windows
- Lag features
- Rolling statistics
- Differencing

**[Jelaskan transformasi yang Anda lakukan]**

### 5.4 Data Splitting

**Strategi pembagian data:**
```
- Training set: [X]% ([jumlah] samples)
- Validation set: [X]% ([jumlah] samples) - jika ada
- Test set: [X]% ([jumlah] samples)
```
**Contoh:**
```
Menggunakan stratified split untuk mempertahankan distribusi kelas:
- Training: 80% (8000 samples)
- Test: 20% (2000 samples)
- Random state: 42 untuk reproducibility
```

**[Jelaskan strategi splitting Anda dan alasannya]**



### 5.5 Data Balancing (jika diperlukan)
**Teknik yang digunakan:**
- SMOTE (Synthetic Minority Over-sampling Technique)
- Random Undersampling
- Class weights
- Ensemble sampling

**[Jelaskan jika Anda melakukan data balancing]**

### 5.6 Ringkasan Data Preparation

**Per langkah, jelaskan:**
1. **Apa** yang dilakukan
**[Jelaskan ]**
2. **Mengapa** penting
**[Jelaskan Mengapa ?]**
3. **Bagaimana** implementasinya
**[Jelaskan Bagaimana]**

---

## 6. MODELING
### 6.1 Model 1 — Baseline Model
#### 6.1.1 Deskripsi Model

**Nama Model:** [Nama model, misal: Logistic Regression]
**Teori Singkat:**  
[Jelaskan secara singkat bagaimana model ini bekerja]
**Alasan Pemilihan:**  
[Mengapa memilih model ini sebagai baseline?]

#### 6.1.2 Hyperparameter
**Parameter yang digunakan:**
```
[Tuliskan parameter penting, contoh:]
- C (regularization): 1.0
- solver: 'lbfgs'
- max_iter: 100
```

#### 6.1.3 Implementasi (Ringkas)
```python
# Contoh kode (opsional, bisa dipindah ke GitHub)
from sklearn.linear_model import LogisticRegression

model_baseline = LogisticRegression(C=1.0, max_iter=100)
model_baseline.fit(X_train, y_train)
y_pred_baseline = model_baseline.predict(X_test)
```

#### 6.1.4 Hasil Awal

**[Tuliskan hasil evaluasi awal, akan dijelaskan detail di Section 7]**

---

### 6.2 Model 2 — ML / Advanced Model
#### 6.2.1 Deskripsi Model

**Nama Model:** [Nama model, misal: Random Forest / XGBoost]
**Teori Singkat:**  
[Jelaskan bagaimana algoritma ini bekerja]

**Alasan Pemilihan:**  
[Mengapa memilih model ini?]

**Keunggulan:**
- [Sebutkan keunggulan]

**Kelemahan:**
- [Sebutkan kelemahan]

#### 6.2.2 Hyperparameter

**Parameter yang digunakan:**
```
[Tuliskan parameter penting, contoh:]
- n_estimators: 100
- max_depth: 10
- learning_rate: 0.1
- min_samples_split: 2
```

**Hyperparameter Tuning (jika dilakukan):**
- Metode: [Grid Search / Random Search / Bayesian Optimization]
- Best parameters: [...]

#### 6.2.3 Implementasi (Ringkas)
```python
# Contoh kode
from sklearn.ensemble import RandomForestClassifier

model_advanced = RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    random_state=42
)
model_advanced.fit(X_train, y_train)
y_pred_advanced = model_advanced.predict(X_test)
```

#### 6.2.4 Hasil Model

**[Tuliskan hasil evaluasi, akan dijelaskan detail di Section 7]**

---

### 6.3 Model 3 — Deep Learning Model (WAJIB)

#### 6.3.1 Deskripsi Model

**Nama Model:** [Nama arsitektur, misal: CNN / LSTM / MLP]

** (Centang) Jenis Deep Learning: **
- [ ] Multilayer Perceptron (MLP) - untuk tabular
- [ ] Convolutional Neural Network (CNN) - untuk image
- [ ] Recurrent Neural Network (LSTM/GRU) - untuk sequential/text
- [ ] Transfer Learning - untuk image
- [ ] Transformer-based - untuk NLP
- [ ] Autoencoder - untuk unsupervised
- [ ] Neural Collaborative Filtering - untuk recommender

**Alasan Pemilihan:**  
[Mengapa arsitektur ini cocok untuk dataset Anda?]

#### 6.3.2 Arsitektur Model

**Deskripsi Layer:**

[Jelaskan arsitektur secara detail atau buat tabel]

**Contoh:**
```
1. Input Layer: shape (224, 224, 3)
2. Conv2D: 32 filters, kernel (3,3), activation='relu'
3. MaxPooling2D: pool size (2,2)
4. Conv2D: 64 filters, kernel (3,3), activation='relu'
5. MaxPooling2D: pool size (2,2)
6. Flatten
7. Dense: 128 units, activation='relu'
8. Dropout: 0.5
9. Dense: 10 units, activation='softmax'

Total parameters: [jumlah]
Trainable parameters: [jumlah]
```

#### 6.3.3 Input & Preprocessing Khusus

**Input shape:** [Sebutkan dimensi input]  
**Preprocessing khusus untuk DL:**
- [Sebutkan preprocessing khusus seperti normalisasi, augmentasi, dll.]

#### 6.3.4 Hyperparameter

**Training Configuration:**
```
- Optimizer: Adam / SGD / RMSprop
- Learning rate: [nilai]
- Loss function: [categorical_crossentropy / mse / binary_crossentropy / etc.]
- Metrics: [accuracy / mae / etc.]
- Batch size: [nilai]
- Epochs: [nilai]
- Validation split: [nilai] atau menggunakan validation set terpisah
- Callbacks: [EarlyStopping, ModelCheckpoint, ReduceLROnPlateau, etc.]
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
[Sebutkan waktu training total, misal: 15 menit]

**Computational Resource:**  
[CPU / GPU, platform: Local / Google Colab / Kaggle]

**Training History Visualization:**

[Insert plot loss dan accuracy/metric per epoch]

**Contoh visualisasi yang WAJIB:**
1. **Training & Validation Loss** per epoch
2. **Training & Validation Accuracy/Metric** per epoch

**Analisis Training:**
- Apakah model mengalami overfitting? [Ya/Tidak, jelaskan]
- Apakah model sudah converge? [Ya/Tidak, jelaskan]
- Apakah perlu lebih banyak epoch? [Ya/Tidak, jelaskan]

#### 6.3.7 Model Summary
```
[Paste model.summary() output atau rangkuman arsitektur]
```

---

## 7. EVALUATION

### 7.1 Metrik Evaluasi

**Pilih metrik yang sesuai dengan jenis tugas:**

#### **Untuk Klasifikasi:**
- **Accuracy**: Proporsi prediksi yang benar
- **Precision**: TP / (TP + FP)
- **Recall**: TP / (TP + FN)
- **F1-Score**: Harmonic mean dari precision dan recall
- **ROC-AUC**: Area under ROC curve
- **Confusion Matrix**: Visualisasi prediksi

#### **Untuk Regresi:**
- **MSE (Mean Squared Error)**: Rata-rata kuadrat error
- **RMSE (Root Mean Squared Error)**: Akar dari MSE
- **MAE (Mean Absolute Error)**: Rata-rata absolute error
- **R² Score**: Koefisien determinasi
- **MAPE (Mean Absolute Percentage Error)**: Error dalam persentase

#### **Untuk NLP (Text Classification):**
- **Accuracy**
- **F1-Score** (terutama untuk imbalanced data)
- **Precision & Recall**
- **Perplexity** (untuk language models)

#### **Untuk Computer Vision:**
- **Accuracy**
- **IoU (Intersection over Union)** - untuk object detection/segmentation
- **Dice Coefficient** - untuk segmentation
- **mAP (mean Average Precision)** - untuk object detection

#### **Untuk Clustering:**
- **Silhouette Score**
- **Davies-Bouldin Index**
- **Calinski-Harabasz Index**

#### **Untuk Recommender System:**
- **RMSE**
- **Precision@K**
- **Recall@K**
- **NDCG (Normalized Discounted Cumulative Gain)**

**[Pilih dan jelaskan metrik yang Anda gunakan]**

### 7.2 Hasil Evaluasi Model

#### 7.2.1 Model 1 (Baseline)

**Metrik:**
```
[Tuliskan hasil metrik, contoh:]
- Accuracy: 0.75
- Precision: 0.73
- Recall: 0.76
- F1-Score: 0.74
```

**Confusion Matrix / Visualization:**  
[Insert gambar jika ada]

#### 7.2.2 Model 2 (Advanced/ML)

**Metrik:**
```
- Accuracy: 0.85
- Precision: 0.84
- Recall: 0.86
- F1-Score: 0.85
```

**Confusion Matrix / Visualization:**  
[Insert gambar jika ada]

**Feature Importance (jika applicable):**  
[Insert plot feature importance untuk tree-based models]

#### 7.2.3 Model 3 (Deep Learning)

**Metrik:**
```
- Accuracy: 0.89
- Precision: 0.88
- Recall: 0.90
- F1-Score: 0.89
```

**Confusion Matrix / Visualization:**  
[Insert gambar jika ada]

**Training History:**  
[Sudah diinsert di Section 6.3.6]

**Test Set Predictions:**  
[Opsional: tampilkan beberapa contoh prediksi]

### 7.3 Perbandingan Ketiga Model

**Tabel Perbandingan:**

| Model | Accuracy | Precision | Recall | F1-Score | Training Time | Inference Time |
|-------|----------|-----------|--------|----------|---------------|----------------|
| Baseline (Model 1) | 0.75 | 0.73 | 0.76 | 0.74 | 2s | 0.01s |
| Advanced (Model 2) | 0.85 | 0.84 | 0.86 | 0.85 | 30s | 0.05s |
| Deep Learning (Model 3) | 0.89 | 0.88 | 0.90 | 0.89 | 15min | 0.1s |

**Visualisasi Perbandingan:**  
[Insert bar chart atau plot perbandingan metrik]

### 7.4 Analisis Hasil

**Interpretasi:**

1. **Model Terbaik:**  
   [Sebutkan model mana yang terbaik dan mengapa]

2. **Perbandingan dengan Baseline:**  
   [Jelaskan peningkatan performa dari baseline ke model lainnya]

3. **Trade-off:**  
   [Jelaskan trade-off antara performa vs kompleksitas vs waktu training]

4. **Error Analysis:**  
   [Jelaskan jenis kesalahan yang sering terjadi, kasus yang sulit diprediksi]

5. **Overfitting/Underfitting:**  
   [Analisis apakah model mengalami overfitting atau underfitting]

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

# Laporan Proyek Machine Learning - Gold Stein Maxwell Massie

## Domain Proyek

Latar Belakang
Kesehatan masyarakat merupakan aspek penting dalam pembangunan nasional dan kualitas hidup individu. Dalam beberapa dekade terakhir, gaya hidup modern seperti pola makan tidak sehat, kurang aktivitas fisik, konsumsi alkohol, dan merokok menjadi faktor utama yang memicu meningkatnya kasus penyakit tidak menular (PTM), seperti diabetes, hipertensi, dan penyakit jantung. Menurut laporan Riskesdas 2018 oleh Kementerian Kesehatan Republik Indonesia, prevalensi PTM semakin meningkat seiring perubahan pola hidup masyarakat yang tidak sehat [1].

Selain itu, dampak gaya hidup terhadap kesehatan belum selalu terukur secara kuantitatif dan sistematis. Oleh karena itu, penting untuk membangun model prediksi yang dapat membantu memahami pengaruh relatif berbagai faktor gaya hidup terhadap skor kesehatan individu secara objektif. Model ini dapat menjadi alat bantu dalam pengambilan keputusan untuk intervensi preventif, edukasi kesehatan, serta perumusan kebijakan berbasis data.

Studi internasional juga menunjukkan bahwa penyakit tidak menular semakin menjadi tantangan serius di negara-negara berkembang, dengan faktor risiko yang sangat kontekstual dan memerlukan kebijakan khusus di tiap negara. Penelitian di Kenya menegaskan bahwa faktor-faktor seperti pendapatan, lokasi tempat tinggal, pendidikan, usia, dan jenis kelamin berkontribusi signifikan terhadap insiden PTM, sehingga pendekatan preventif berbasis risiko ini menjadi solusi jangka panjang yang lebih efektif dibandingkan penanganan pasca penyakit [2].

Masalah yang Ingin Diselesaikan

- Bagaimana hubungan antara variabel-variabel gaya hidup (usia, BMI, kualitas diet, durasi tidur, frekuensi olahraga, status merokok, konsumsi alkohol) terhadap Health_Score seseorang?
- Faktor mana yang paling berpengaruh terhadap peningkatan atau penurunan skor kesehatan?
- Dapatkah dibuat model prediksi untuk mengestimasi skor kesehatan berdasarkan data gaya hidup?

Penyakit tidak menular yang disebabkan oleh gaya hidup buruk menyumbang beban besar pada sistem kesehatan dan ekonomi nasional. Dengan memahami hubungan antara variabel gaya hidup dan skor kesehatan, serta mengidentifikasi faktor yang paling dominan, intervensi dapat lebih tepat sasaran dan efektif. Hal ini mendukung upaya pencegahan yang lebih baik dan meningkatkan kualitas hidup masyarakat secara keseluruhan.

**Referensi**

[1] Kementerian Kesehatan Republik Indonesia, Laporan Nasional Riskesdas 2018, Jakarta: Kemenkes RI, 2018. [Online]. Tersedia: https://repository.badankebijakan.kemkes.go.id/id/eprint/3514/1/Laporan%20Riskesdas%202018%20Nasional.pdf

[2] D. Mwai dan M. Muriithi, "Non-Communicable Diseases Risk Factors And Their Contribution To Ncd Incidences In Kenya," European Scientific Journal, vol. 11, no. 30, 2015. [Online]. Tersedia: https://eujournal.org/index.php/esj/article/view/6367

## Business Understanding

Dalam beberapa dekade terakhir, gaya hidup masyarakat mengalami perubahan signifikan akibat perkembangan teknologi, urbanisasi, dan perubahan sosial. Dampak dari gaya hidup modern seperti kurang tidur, pola makan tidak sehat, serta kebiasaan merokok dan konsumsi alkohol memunculkan tantangan besar dalam bidang kesehatan masyarakat.

Namun, belum tersedia banyak model prediktif yang secara kuantitatif mampu mengukur kontribusi masing-masing faktor gaya hidup terhadap kesehatan individu.

### Problem Statements

1. Faktor gaya hidup manakah yang paling berpengaruh terhadap Health Score seseorang?
2. Dapatkah dibangun model prediktif untuk mengestimasi Health Score hanya berdasarkan data gaya hidup?
3. Seberapa baik performa model dan model terbaik sebagai solusi ?

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Mengidentifikasi faktor-faktor gaya hidup yang paling berdampak terhadap Health Score.
- Membangun model regresi prediktif berbasis data gaya hidup.
- Mengevaluasi performa model menggunakan metrik R², MAE, dan RMSE.

### Solution Statement

- **Solusi 1**: Menggunakan **Linear Regression** untuk mengestimasi Health Score berdasarkan variabel gaya hidup.

- **Solusi 2**: Menggunakan **GradientBoostingRegressor** untuk meningkatkan akurasi prediksi dan mengidentifikasi faktor gaya hidup paling berpengaruh. Selain itu, melakukan **analisis *feature importance*** untuk mengidentifikasi faktor gaya hidup paling dominan yang memengaruhi Health Score menurut model ini.

### Evaluasi Keberhasilan
Keberhasilan proyek ini akan diukur menggunakan tiga metrik evaluasi utama dalam regresi:
- **MAE (Mean Absolute Error)**: Menghitung rata-rata selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin akurat prediksi model.
- **MSE (Mean Squared Error)**: Mengukur rata-rata kuadrat dari selisih antara nilai prediksi dan nilai aktual. MSE memberikan penalti lebih besar terhadap kesalahan prediksi yang besar, sehingga membantu mengidentifikasi seberapa stabil dan sensitif model terhadap outlier.
- **R² (Koefisien Determinasi)**: Mengukur proporsi variansi dari Health Score yang dapat dijelaskan oleh model. Nilai R² yang mendekati 1 menunjukkan bahwa model memiliki kemampuan prediksi yang baik.

## Data Understanding
Dataset ini digunakan untuk menganalisis dampak berbagai faktor gaya hidup terhadap Health Score seseorang dengan pendekatan regresi. Data ini mencakup variabel-variabel seperti usia, indeks massa tubuh (BMI), frekuensi olahraga, kualitas diet, durasi tidur, status merokok, dan konsumsi alkohol. Dataset ini sangat cocok untuk eksplorasi data, pembangunan model machine learning, serta pemahaman hubungan antara gaya hidup dan kesehatan. 
- Health and Lifestyle Data for Regression: [Kaggle](https://www.kaggle.com/datasets/pratikyuvrajchougule/health-and-lifestyle-data-for-regression/).

### Variabel-variabel pada Health and Lifestyle Data for Regression dataset adalah sebagai berikut:
- **Age**: Usia individu dalam satuan tahun. Bertipe _continuous variable_.
- **BMI**: Body Mass Index (Indeks Massa Tubuh) individu, digunakan untuk mengukur status berat badan. Bertipe _continuous variable_.
- **Exercise_Frequency**: Jumlah hari dalam seminggu individu melakukan olahraga. Bertipe _categorical_ dengan nilai 0–7.
- **Diet_Quality**: Indeks kualitas pola makan, di mana nilai yang lebih tinggi mencerminkan pola makan yang lebih sehat. Skala 0–100, bertipe _continuous_.
- **Sleep_Hours**: Rata-rata jam tidur individu setiap malam. Bertipe _continuous_.
- **Smoking_Status**: Status merokok individu, di mana 0 = Non-smoker dan 1 = Smoker. Bertipe _binary categorical_.
- **Alcohol_Consumption**: Rata-rata jumlah konsumsi alkohol per minggu dalam satuan unit. Bertipe _continuous_.
- **Health_Score**: Skor kesehatan yang dihitung berdasarkan faktor-faktor gaya hidup di atas, mencerminkan status kesehatan secara keseluruhan. Skala 0–100, bertipe _continuous_.

### Exploratory Data Analysis (EDA)

#### Menampilkan Info dataset

| No | Kolom                | Jumlah Non-Null | Tipe Data |
|----|----------------------|------------------|-----------|
| 0  | Age                  | 1000 non-null    | float64   |
| 1  | BMI                  | 1000 non-null    | float64   |
| 2  | Exercise_Frequency   | 1000 non-null    | int64     |
| 3  | Diet_Quality         | 1000 non-null    | float64   |
| 4  | Sleep_Hours          | 1000 non-null    | float64   |
| 5  | Smoking_Status       | 1000 non-null    | int64     |
| 6  | Alcohol_Consumption  | 1000 non-null    | float64   |
| 7  | Health_Score         | 1000 non-null    | float64   |

Total entri: **1000**  
Tipe data: **float64 (6 kolom)**, **int64 (2 kolom)**  
Ukuran memori: ~62.6 KB

dari hasil df.info() dapat lihat:
- Jumlah data: 1000 baris dengan 8 kolom
- 6 kolom numerik (float64) dan 2 kolom integer (int64)

#### Menampilkan Deskriptif Dataset

![image](https://github.com/user-attachments/assets/237d0386-7abf-493a-a173-6bd98748bd00)


dari hasil df.describe() dapat lihat:

Statistik deskriptif menunjukkan bahwa dataset terdiri dari 1.000 entri dengan 8 fitur. Rata-rata usia peserta adalah 40 tahun, dengan BMI sekitar 25. Aktivitas olahraga rata-rata 2–3 kali per minggu, diet bernilai sekitar 70, dan waktu tidur sekitar 7 jam. Setengah dari peserta merokok, dan konsumsi alkohol rata-rata sekitar 3 unit. Skor kesehatan rata-rata berada di angka 85, dengan nilai minimum sekitar 29 dan maksimum 100, menunjukkan sebaran yang cukup luas antar individu.

#### Mengecek & Menampilkan Missing Value

| Kolom                | Missing Values |
|----------------------|----------------|
| Age                  | 0              |
| BMI                  | 0              |
| Exercise_Frequency   | 0              |
| Diet_Quality         | 0              |
| Sleep_Hours          | 0              |
| Smoking_Status       | 0              |
| Alcohol_Consumption  | 0              |
| Health_Score         | 0              |

**Total Missing Values di Dataset: 0**

dari hasil df.isnull() dapat lihat:
tidak da misisng value pada dataset, sehingga tidak perlu dilakukan imputasi atau pembersihan khusus terkait data yang hilang sebelum melanjutkan analisis dan pemodelan.

#### Mengecek & Menampilkan Duplikat Data

| Keterangan          | Jumlah |
|---------------------|--------|
| Data Duplikat       | 0      |

dari hasil df.duplicated() dapat lihat:
Hasilnya menunjukkan jumlah data duplikat adalah 0, yang berarti tidak ada baris data yang sama persis, sehingga dataset benar-benar bersih dan siap digunakan untuk proses selanjutnya tanpa perlu penghapusan data duplikat.

### Univariate Analysis
#### Distribution of Age & Boxplot of Age
![image](https://github.com/user-attachments/assets/e3be7175-d520-4890-b216-fc0d8c62aa75)
Distribusi usia dalam dataset cenderung berbentuk normal dengan sebagian besar data terpusat antara 25 hingga 55 tahun, berpuncak di sekitar 40 tahun. Meskipun sebarannya luas dari usia sangat muda hingga lansia, boxplot menunjukkan adanya beberapa outlier di kedua ujung, terutama usia yang sangat muda (mendekati 0) yang perlu diverifikasi validitasnya karena berpotensi menjadi data entry error

#### Distribution of BMI & Boxplot of BMI
![image](https://github.com/user-attachments/assets/ffc64835-f176-4662-8a63-572254492a34)
Distribusi BMI menunjukkan pola yang mendekati normal (bell-shaped) dengan sebagian besar individu berada di rentang BMI 20 hingga 30, yang mencakup kategori berat badan normal hingga sedikit kelebihan berat badan, dengan puncak di sekitar 25. Meskipun sebaran data cukup luas, boxplot mengindikasikan adanya beberapa outlier di kedua sisi ekstrem (BMI sangat rendah sekitar 10 dan sangat tinggi sekitar 40) yang merupakan kasus yang kurang umum namun valid dalam konteks indeks massa tubuh.

#### Distribution of Exercise_Frequency & Boxplot of Exercise_Frequency
![image](https://github.com/user-attachments/assets/5181417c-6080-4089-a94f-3cca04ef4199)
Distribusi frekuensi olahraga (Exercise_Frequency) menunjukkan pola yang cenderung seragam atau merata di antara setiap kategori (0 hingga 6 hari per minggu), dengan tidak ada satu frekuensi pun yang mendominasi secara signifikan. Boxplot mengonfirmasi sebaran data yang luas meliputi semua nilai yang mungkin tanpa adanya outlier, menunjukkan variasi frekuensi olahraga yang relatif seimbang di seluruh dataset.

#### Distribution of Diet_Quality & Boxplot of Diet_Quality
![image](https://github.com/user-attachments/assets/8e92627b-6130-454c-a588-c5772149d286)
Distribusi kualitas diet (Diet_Quality) menunjukkan pola yang mendekati normal, dengan sebagian besar individu memiliki kualitas diet menengah hingga baik, terpusat di sekitar nilai 70-80. Meskipun sebagian besar data berada dalam rentang wajar, boxplot mengidentifikasi adanya outlier di sisi bawah (kualitas diet sangat rendah) dan, yang lebih penting, di sisi atas (nilai di atas 100) yang harus diverifikasi dan ditangani karena melebihi skala maksimum yang ditentukan (0-100).

#### Distribution of Sleep_Hours & Boxplot of Sleep_Hours
![image](https://github.com/user-attachments/assets/996e7f60-3388-4b60-82b0-af3a3766093c)
Distribusi durasi tidur (Sleep_Hours) menunjukkan pola yang mendekati normal, dengan mayoritas individu tidur antara 6 hingga 8 jam per malam, mencerminkan durasi tidur yang direkomendasikan. Meskipun sebagian besar data terpusat di rentang tersebut, boxplot mengidentifikasi beberapa outlier di kedua sisi ekstrem, yaitu individu dengan durasi tidur yang sangat singkat (sekitar 3 jam) dan durasi tidur yang sangat panjang (mendekati 12 jam).

#### Distribution of Smoking_Status & Boxplot of Smoking_Status
![image](https://github.com/user-attachments/assets/c470112b-c4bc-4edc-8e04-7356cb390dd3)
Distribusi status merokok (Smoking_Status) menunjukkan pola biner yang hampir seimbang, dengan sekitar 500 individu dikategorikan sebagai non-perokok (nilai 0) dan sekitar 500 lainnya sebagai perokok (nilai 1). Karena ini adalah variabel kategori, boxplot tidak memberikan informasi tentang outlier dan hanya mengonfirmasi adanya dua kategori yang jelas terpisah.

#### Distribution of Alcohol_Consumpttion & Boxplot of Alcohol_Consumpttion
![image](https://github.com/user-attachments/assets/f520f3d0-e1f9-472f-9855-16d1ec2d2397)
Distribusi konsumsi alkohol (Alcohol_Consumption) menunjukkan pola yang mendekati normal, dengan sebagian besar individu mengonsumsi alkohol antara 2 hingga 5 unit per minggu. Namun, boxplot dengan jelas mengidentifikasi adanya beberapa outlier di kedua sisi ekstrem, terutama nilai negatif (sekitar -3 hingga -4) yang merupakan anomali data dan harus ditangani karena konsumsi alkohol tidak mungkin bernilai negatif, serta beberapa individu dengan konsumsi yang sangat tinggi (sekitar 11 unit).

#### Distribution of Health_Score & Boxplot of Health_Score
![image](https://github.com/user-attachments/assets/13ebc96c-eb3d-4be3-9040-85a655a7ed7f)
Distribusi Health_Score menunjukkan kemiringan ke kiri (left-skewed) yang kuat, dengan sebagian besar individu memiliki skor kesehatan tinggi, bahkan banyak yang mencapai skor sempurna 100. Meskipun demikian, boxplot mengidentifikasi beberapa outlier di sisi bawah (skor kesehatan sangat rendah, di bawah 40), menunjukkan adanya segelintir individu dengan kondisi kesehatan yang jauh lebih buruk dibandingkan mayoritas populasi.


### Multivariate  Analysis
#### Pairplot beberapa fitur dan Health_Score
![aprplot](https://github.com/user-attachments/assets/297c6bf7-ae0c-48ac-bc8d-eefbb9fbeaec)
Pairplot ini mengilustrasikan hubungan antar variabel gaya hidup dan Health_Score. Terlihat jelas bahwa Diet_Quality memiliki korelasi positif yang kuat dengan Health_Score, menunjukkan bahwa diet yang lebih baik berhubungan dengan skor kesehatan yang lebih tinggi. Sebaliknya, Age dan BMI cenderung berkorelasi negatif dengan Health_Score, mengindikasikan bahwa peningkatan usia atau BMI umumnya berkaitan dengan penurunan skor kesehatan.
Sementara itu, Exercise_Frequency dan Sleep_Hours menunjukkan hubungan yang lebih menyebar dengan Health_Score, menandakan bahwa pengaruhnya mungkin tidak sekuat tiga variabel sebelumnya dan memerlukan analisis lebih lanjut. Penting juga dicatat bahwa secara visual, tidak ada indikasi multikolinearitas yang parah di antara fitur-fitur prediktor, yang merupakan kondisi baik untuk pembangunan model regresi.

#### Health_Score berdasarkan Smoking_Status
![image](https://github.com/user-attachments/assets/a5a46d9e-680b-47d6-a00e-c26e81c6fee3)
Berdasarkan box plot tersebut, terlihat bahwa Health Score untuk kedua kelompok Smoking Status (0 dan 1) memiliki median yang relatif tinggi, sekitar 85-90. Namun, kelompok Smoking Status 0 menunjukkan rentang interkuartil (IQR) yang lebih lebar, dengan nilai-nilai yang cenderung lebih rendah dan beberapa outlier di bawah 50, bahkan mendekati 40. Sementara itu, kelompok Smoking Status 1 memiliki IQR yang sedikit lebih sempit dan juga menunjukkan beberapa outlier di bawah 45, bahkan mendekati 30. Secara umum, meskipun median Health Score serupa, distribusi Health Score untuk perokok (Smoking Status 1) sedikit lebih menyebar ke bawah dibandingkan non-perokok (Smoking Status 0).

#### Scatter plot BMI vs Health_Score
![image](https://github.com/user-attachments/assets/54579400-c71e-4af6-b905-bbd63d3c1127)
Berdasarkan scatter plot BMI vs Health Score, terlihat bahwa tidak ada korelasi linear yang kuat antara kedua variabel tersebut. Meskipun sebagian besar Health Score cenderung tinggi (di atas 70) terutama pada rentang BMI sekitar 15-25, sebaran titik-titik data menunjukkan pola yang menyebar tanpa tren naik atau turun yang jelas. Hal ini mengindikasikan bahwa perubahan BMI tidak secara konsisten memprediksi perubahan Health Score, dan banyak individu dengan berbagai nilai BMI dapat memiliki Health Score yang bervariasi.

#### Correlation Map
![image](https://github.com/user-attachments/assets/44411c86-fd32-4d89-a1d3-c0dfdd23f4c0)
Berdasarkan heatmap korelasi, terlihat bahwa variabel 'Health_Score' memiliki korelasi positif yang cukup kuat dengan 'Diet_Quality' (0.68) dan 'Sleep_Hours' (0.27), menunjukkan bahwa diet yang baik dan tidur yang cukup cenderung berhubungan dengan Health Score yang lebih tinggi. Sebaliknya, 'Health_Score' memiliki korelasi negatif yang cukup kuat dengan 'BMI' (-0.42) dan 'Age' (-0.19), yang mengindikasikan bahwa BMI dan usia yang lebih tinggi cenderung berhubungan dengan Health Score yang lebih rendah. Variabel lain seperti 'Exercise_Frequency', 'Smoking_Status', dan 'Alcohol_Consumption' menunjukkan korelasi yang sangat lemah atau hampir tidak ada dengan 'Health_Score'.



## Data Preparation
1. Memisahkan fitur(Independent) dan target(dependent).
```python
# memisahkan variable independent dan dependent
X = df.drop('Health_Score', axis=1)
y = df['Health_Score']
```

2. Membagi dataset menjadi data train dan test agar model dapat dilatih dan dievaluasi secara objektif pada data yang belum pernah dilihat sebelumnya
```python
# Membagi data menjadi train dan test (80% train, 20% test)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

3. Melakukan standardisasi pada fitur numerik supaya semua fitur memiliki skala yang seragam, sehingga model dapat belajar lebih efektif dan prediksi menjadi lebih akurat.
```python
# Daftar fitur numerik untuk distandarisasi
num_features = ['Age', 'BMI', 'Exercise_Frequency', 'Diet_Quality', 'Sleep_Hours', 'Alcohol_Consumption']

# Inisialisasi scaler
scaler = StandardScaler()

# Fit scaler hanya di data train, lalu transformasi train dan test
X_train[num_features] = scaler.fit_transform(X_train[num_features])
X_test[num_features] = scaler.transform(X_test[num_features])
```

## Pembangunan Model Solution
### 1. Model Solution dengan Linear Regression
Pada tahap ini, model pertama yang digunakan adalah Linear Regression, yang merupakan algoritma regresi linier sederhana dan interpretatif. Model ini diinisialisasi tanpa parameter khusus, karena scikit-learn telah menyediakan nilai default yang umumnya cukup baik untuk baseline.

#### Alasan Pemilihan Linear Regression
Linear Regression dipilih sebagai baseline karena sifatnya yang sederhana, cepat, dan mudah diinterpretasikan. Ini memungkinkan evaluasi awal performa model sebelum melanjutkan ke model yang lebih kompleks.

**Kelebihan Linear Regression**:
- ✅ **Interpretabilitas Tinggi**: Koefisien regresi dapat digunakan untuk mengukur pengaruh setiap fitur terhadap target.
- ⚡ **Kecepatan Pelatihan**: Linear Regression sangat cepat dalam proses pelatihan, bahkan pada dataset skala besar.
- 🎯 **Cocok untuk Baseline**: Karena kesederhanaannya, model ini ideal untuk memberikan gambaran awal terhadap performa model lain.

**Kekurangan Linear Regression**:
- ❌ **Tidak Menangkap Hubungan Non-Linear**: Model ini hanya efektif jika hubungan antar variabel bersifat linier.
- ⚠️ **Sensitif terhadap Outlier**: Kehadiran outlier dapat secara signifikan memengaruhi garis regresi yang dihasilkan.
- 🔁 **Rentan terhadap Multikolinearitas**: Ketika dua atau lebih fitur sangat berkorelasi, model dapat menjadi tidak stabil dan koefisien sulit diinterpretasikan.

#### Code Program Linear Regression
melatih model dengan data X_train dan y_train
```python
# Inisialisasi model Linear Regresi
lr_model = LinearRegression()
# melatih model dengan data training
lr_model.fit(X_train, y_train)
```

### 2. Model Solution dengan GradientBoostingRegressor
Pada tahap ini, model kedua yang digunakan adalah Gradient Boosting Regressor (GBR), yaitu algoritma ensemble learning yang bekerja dengan membangun model secara bertahap dan menggabungkan banyak pohon keputusan (decision trees) yang lemah untuk membentuk prediksi yang kuat. Model ini terkenal karena kemampuannya dalam menangani hubungan non-linear secara efektif.
Model diinisialisasi menggunakan parameter default dari ```sklearn.ensemble.GradientBoostingRegressor```, dengan penambahan ```random_state=42``` untuk memastikan bahwa proses pelatihan dapat direplikasi dengan hasil yang konsisten.

#### parameter default ```random_state=42```
bertujuan untuk mengontrol randomness selama pelatihan, seperti proses pembentukan pohon dan sampling data. Dengan menetapkan random_state=42, kita memastikan hasil pelatihan model akan konsisten dan dapat direplikasi di berbagai eksperimen.
Angka 42 sering digunakan sebagai nilai default karena sifatnya yang netral dan banyak digunakan dalam praktik data science.

**Kelebihan Gradient Boosting Regressor**:
- **Mampu Menangkap Hubungan Non-Linear**: Cocok untuk data dengan pola yang kompleks dan tidak linier.
- **Performa Tinggi**: Model ini seringkali menghasilkan akurasi yang tinggi dibandingkan algoritma regresi lainnya.
= **Robust terhadap Outlier**: Lebih tahan terhadap pengaruh data ekstrem dibandingkan model linier.
- **Interaksi Fitur**: Dapat menangani interaksi antar fitur tanpa perlu eksplisit mendefinisikannya.

**Kekurangan Gradient Boosting Regressor**:
- **Training Time Lebih Lama**: Dibandingkan dengan model sederhana seperti Linear Regression, GBR membutuhkan waktu komputasi lebih tinggi.
- **Memerlukan Hyperparameter Tuning**: Agar performa optimal, model ini memerlukan penyesuaian parameter

#### Code Program Gradient Boosting Regressor
melatih model dengan data X_train dan y_train
```python
# Inisialisasi model GradientBoostingRegressor
gbr_model = GradientBoostingRegressor(random_state=42)
# melatih model dengan data training
gbr_model.fit(X_train, y_train)
```

#### Pemilihan Model Terbaik
Pemilihan model terbaik akan dilakukan berdasarkan hasil evaluasi metrik regresi (MAE, MSE, dan R²) yang akan dijelaskan di tahap selanjutnya.

### 3. Feature Importances
Pada tahap Feature Importance, dengan menggunakan model Gradient Boosting Regressor yang telah dilatih untuk mengevaluasi seberapa besar kontribusi masing-masing fitur dalam memprediksi Health_Score. Hasilnya ditampilkan dalam bentuk tabel dan visualisasi bar chart.
#### kode Feature Importances
```python
# Mendapatkan nilai feature importance dari model Gradient Boosting
importances = gbr_model.feature_importances_

# Mendapatkan nama fitur
feature_names = X.columns  # asumsi X adalah DataFrame berisi fitur

# Menggabungkan dalam DataFrame agar mudah dianalisis
feature_importance_df = pd.DataFrame({
    'Feature': feature_names,
    'Importance': importances
}).sort_values(by='Importance', ascending=False)

# menampilkan data tabular feature importance
print(feature_importance_df)

plt.figure(figsize=(10, 6))
sns.barplot(x='Importance', y='Feature', data=feature_importance_df, palette='viridis')
plt.title('Feature Importance - Gradient Boosting Regressor')
plt.xlabel('Importance Score')
plt.ylabel('Features')
plt.tight_layout()
plt.show()
```

#### Output Feature Importances
![image](https://github.com/user-attachments/assets/e416560c-e2bb-4a18-b0a6-25d8151e2400)
Berdasarkan grafik Feature Importance dari model Gradient Boosting Regressor, Diet_Quality merupakan faktor yang paling penting dalam memprediksi Health Score dengan importance score tertinggi (0.522). Disusul oleh BMI (0.212), Exercise_Frequency (0.087), dan Sleep_Hours (0.082) yang juga memiliki pengaruh signifikan. Sementara itu, Age, Alcohol_Consumption, dan Smoking_Status menunjukkan tingkat kepentingan yang relatif jauh lebih rendah dalam memprediksi Health Score.


## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.


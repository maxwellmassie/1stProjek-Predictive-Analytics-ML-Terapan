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

| Statistik | Age       | BMI       | Exercise_Frequency | Diet_Quality | Sleep_Hours | Smoking_Status | Alcohol_Consumption | Health_Score |
|-----------|-----------|-----------|---------------------|--------------|--------------|-----------------|----------------------|---------------|
| count     | 1000.000000 | 1000.000000 | 1000.000000         | 1000.000000  | 1000.000000  | 1000.000000     | 1000.000000          | 1000.000000   |
| mean      | 40.231985 | 25.354181 | 2.888000            | 69.952977   | 6.973135     | 0.499000        | 3.079377             | 85.479947     |
| std       | 11.750591 | 4.987272  | 1.995354            | 14.972061   | 1.517218     | 0.500249        | 2.084564             | 13.633845     |
| min       | 1.104792  | 10.298057 | 0.000000            | 19.907497   | 2.431107     | 0.000000        | -3.592506            | 29.106017     |
| 25%       | 32.228916 | 21.968792 | 1.000000            | 59.945481   | 5.903351     | 0.000000        | 1.644111             | 76.430819     |
| 50%       | 40.303607 | 25.315386 | 3.000000            | 69.975151   | 6.990847     | 0.000000        | 3.064261             | 87.498996     |
| 75%       | 47.775327 | 28.644411 | 5.000000            | 80.527839   | 8.054595     | 1.000000        | 4.489293             | 99.762644     |
| max       | 86.232778 | 40.965538 | 6.000000            | 110.265186  | 11.638962    | 1.000000        | 11.105100            | 100.000000    |



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



## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

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


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

---
Referensi
[1] Kementerian Kesehatan Republik Indonesia, Laporan Nasional Riskesdas 2018, Jakarta: Kemenkes RI, 2018. [Online]. Tersedia: http://www.depkes.go.id/resources/download/info-terkini/hasil-riskesdas-2018.pdf

[2] D. Mwai dan M. Muriithi, "Non-Communicable Diseases Risk Factors And Their Contribution To Ncd Incidences In Kenya," European Scientific Journal, vol. 11, no. 30, 2015. [Online]. Tersedia: https://eujournal.org/index.php/esj/article/view/6367

## Business Understanding

Pada bagian ini, kamu perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

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


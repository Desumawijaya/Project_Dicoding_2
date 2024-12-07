# Laporan Proyek Machine Learning - I Putu Gede Suma Wijaya

## Project Overview

Sistem  rekomendasi  merupakan  solusi  yang  efektif  untuk  membantu  pengguna  menemukan buku yang sesuai dengan preferensi mereka [SISTEM REKOMENDASI BUKU DENGANMETODEK-NEAREST NEIGHBOR(K-NN)PADA GRAMEDIA](https://journal.unilak.ac.id/index.php/zn/article/view/12203/4667). Sistem rekomendasi memberikan berbagai keuntungan bagi pengguna dalam menemukan buku yang sesuai dengan preferensi mereka. Dengan fitur ini, pengguna tidak perlu mencari secara manual, sehingga waktu dan tenaga dapat dihemat secara signifikan. Selain itu, rekomendasi yang dihasilkan bersifat personal, karena didasarkan pada minat dan kebutuhan pengguna, menjadikan pengalaman mereka lebih menyenangkan. Tak hanya itu, sistem ini juga membantu pengguna mengeksplorasi berbagai pilihan buku baru yang relevan dan menarik.Pembuatan sistem rekomendasi ini berfokus pada perbandingan antara dua pendekatan berbeda untuk memberikan saran buku, yaitu CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity. Data yang digunakan dalam sistem ini terdiri dari 10.000 buku yang paling direkomendasikan sepanjang waktu, yang dikumpulkan sebagai bagian dari upaya pribadi untuk menemukan buku-buku yang mungkin disukai seseorang berdasarkan buku yang telah dibaca sebelumnya. Tujuan utama dari sistem ini adalah untuk meningkatkan pengalaman rekomendasi. Dengan membandingkan kedua teknik, diharapkan dapat ditemukan metode yang lebih akurat dalam memberikan rekomendasi buku yang relevan

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

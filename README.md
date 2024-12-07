# Laporan Proyek Machine Learning - I Putu Gede Suma Wijaya

## Project Overview

Sistem  rekomendasi  merupakan  solusi  yang  efektif  untuk  membantu  pengguna  menemukan buku yang sesuai dengan preferensi mereka [(dharmawan,dkk.,2023)](https://journal.unilak.ac.id/index.php/zn/article/view/12203/4667). Sistem rekomendasi memberikan berbagai keuntungan bagi pengguna dalam menemukan buku yang sesuai dengan preferensi mereka. Dengan fitur ini, pengguna tidak perlu mencari secara manual, sehingga waktu dan tenaga dapat dihemat secara signifikan. Selain itu, rekomendasi yang dihasilkan bersifat personal, karena didasarkan pada minat dan kebutuhan pengguna, menjadikan pengalaman mereka lebih menyenangkan. Tak hanya itu, sistem ini juga membantu pengguna mengeksplorasi berbagai pilihan buku baru yang relevan dan menarik.Pembuatan sistem rekomendasi ini berfokus pada perbandingan antara dua pendekatan berbeda untuk memberikan saran buku, yaitu CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity. Data yang digunakan dalam sistem ini terdiri dari 10.000 buku yang paling direkomendasikan sepanjang waktu, yang dikumpulkan sebagai bagian dari upaya pribadi untuk menemukan buku-buku yang mungkin disukai seseorang berdasarkan buku yang telah dibaca sebelumnya. Tujuan utama dari sistem ini adalah untuk meningkatkan pengalaman rekomendasi. Dengan membandingkan kedua teknik, diharapkan dapat ditemukan metode yang lebih akurat dalam memberikan rekomendasi buku yang relevan

## Business Understanding
UNESCO mengungkapkan bahwa Indeks minat baca masyarakat Indonesia sangat rendah, hanya mencapai 0,001%, yang berarti dari setiap 1.000 orang, hanya satu orang yang gemar membaca. Selain itu, Kementerian Komunikasi dan Informatika (Kemenkominfo) melalui laman resminya pernah membagikan hasil penelitian "World’s Most Literate Nations Ranked" oleh Central Connecticut State University pada Maret 2016. Penelitian tersebut menunjukkan bahwa Indonesia menempati posisi ke-60 dari 61 negara dalam hal minat baca, tepat di bawah Thailand (peringkat 59) dan di atas Botswana (peringkat 61). Ironisnya, meskipun minat bacanya rendah, Indonesia sebenarnya memiliki infrastruktur pendukung membaca yang lebih baik dibandingkan negara-negara Eropa [(https://www.rri.co.id/)](https://www.rri.co.id/daerah/649261/unesco-sebut-minat-baca-orang-indonesia-masih-rendah). Dengan adanya sistem rekomendasi buku diharapkan dapat menumbuhkan minat baca masyarakat karena memungkinkan memberikan saran rekomendasi buku yang sesuai dengan pembaca.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity.  untuk dataset buku.
- Bagimana hasil implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity untuk dataset buku
- Bagaimana hasil perbandingan kedua metode, metode mana yang unggul.

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Untuk mengetahui bagaimana implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity.  untuk dataset buku.
- Untuk mengetahui bagimana hasil implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity untuk dataset buku
- Untuk mengetahui bagaimana hasil perbandingan kedua metode, metode mana yang unggul.




    ### Solution statements
    - Dalam implementasi ini untuk memberikan hasil sistem rekomendasi yang baik menggunakan dataset yang cukup besar dengan 10.000 data
    - Menerapkan 2 metode untuk menemukan metode yang lebih akurat dalam memberikan rekomendasi buku

## Data Understanding

Data Best Books (10k) Multi-Genre yang tersedia di  [Kaggle](https://www.kaggle.com/datasets/ishikajohari/best-books-10k-multi-genre-data).
merupakan kumpulan 10.000 buku yang paling direkomendasikan sepanjang masa. Data ini dikumpulkan sebagai upaya pribadi untuk membantu individu menemukan lebih banyak buku yang sesuai dengan preferensi mereka, berdasarkan buku-buku yang mungkin telah mereka baca sebelumnya. Dengan menganalisis pola dan genre buku yang telah dibaca, sistem ini berupaya untuk memberikan rekomendasi yang lebih akurat, mencocokkan minat dan kecenderungan pembaca.   

Variabel-variabel pada  dataset adalah sebagai berikut:
- Book : Nama buku. Terkadang ini termasuk detail tentang seri yang menjadi bagian dari buku tersebut di dalam tanda kurung. Informasi ini dapat diekstraksi lebih lanjut untuk menganalisis hanya seri-seri tersebut.
- Author : Nama penulis buku
- Description :Deskripsi buku seperti yang tercantum di Goodreads
- Genres :Beberapa genre yang diklasifikasikan di Goodreads.
- Average Rating :Rating rata-rata (dari 5) yang diberikan di Goodreads
- Number of Ratings : Jumlah pengguna yang memberikan rating
- URL  : URL Goodreads untuk halaman detail buku

Berikut ilustrasi informasi dari  dataset yang digunakan:
![Informasi dataset](https://raw.githubusercontent.com/Desumawijaya/ASSET_DICODING/main/IMAGES/Screenshot%202024-11-18%20052928.png)


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

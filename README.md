# Laporan Proyek Machine Learning - I Putu Gede Suma Wijaya

## Project Overview

Sistem  rekomendasi  merupakan  solusi  yang  efektif  untuk  membantu  pengguna  menemukan buku yang sesuai dengan preferensi mereka [(dharmawan,dkk.,2023)](https://journal.unilak.ac.id/index.php/zn/article/view/12203/4667). Sistem rekomendasi memberikan berbagai keuntungan bagi pengguna dalam menemukan buku yang sesuai dengan preferensi mereka. Dengan fitur ini, pengguna tidak perlu mencari secara manual, sehingga waktu dan tenaga dapat dihemat secara signifikan. Selain itu, rekomendasi yang dihasilkan bersifat personal, karena didasarkan pada minat dan kebutuhan pengguna, menjadikan pengalaman mereka lebih menyenangkan. Tak hanya itu, sistem ini juga membantu pengguna mengeksplorasi berbagai pilihan buku baru yang relevan dan menarik.Pembuatan sistem rekomendasi ini berfokus pada perbandingan antara dua pendekatan berbeda untuk memberikan saran buku, yaitu CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity. Data yang digunakan dalam sistem ini terdiri dari 10.000 buku yang paling direkomendasikan sepanjang waktu, yang dikumpulkan sebagai bagian dari upaya pribadi untuk menemukan buku-buku yang mungkin disukai seseorang berdasarkan buku yang telah dibaca sebelumnya. Tujuan utama dari sistem ini adalah untuk meningkatkan pengalaman rekomendasi. Dengan membandingkan kedua teknik, diharapkan dapat ditemukan metode yang lebih akurat dalam memberikan rekomendasi buku yang relevan

## Business Understanding
UNESCO mengungkapkan bahwa Indeks minat baca masyarakat Indonesia sangat rendah, hanya mencapai 0,001%, yang berarti dari setiap 1.000 orang, hanya satu orang yang gemar membaca. Selain itu, Kementerian Komunikasi dan Informatika (Kemenkominfo) melalui laman resminya pernah membagikan hasil penelitian "World’s Most Literate Nations Ranked" oleh Central Connecticut State University pada Maret 2016. Penelitian tersebut menunjukkan bahwa Indonesia menempati posisi ke-60 dari 61 negara dalam hal minat baca, tepat di bawah Thailand (peringkat 59) dan di atas Botswana (peringkat 61). Ironisnya, meskipun minat bacanya rendah, Indonesia sebenarnya memiliki infrastruktur pendukung membaca yang lebih baik dibandingkan negara-negara Eropa [(https://www.rri.co.id/)](https://www.rri.co.id/daerah/649261/unesco-sebut-minat-baca-orang-indonesia-masih-rendah). Dengan adanya sistem rekomendasi buku diharapkan dapat menumbuhkan minat baca masyarakat karena memungkinkan memberikan saran rekomendasi buku yang sesuai dengan pembaca.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity.  untuk dataset buku?
- Bagimana hasil implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity untuk dataset buku dengan metrik precision dan recall?
- Bagaimana hasil perbandingan kedua metode, metode mana yang unggul?

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Untuk mengetahui  implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity untuk dataset buku.
- Untuk mengetahui  hasil implementasi sistem rekomendasi dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity untuk dataset buku dengan metrik precision dan recall.
- Untuk mengetahui  hasil perbandingan kedua metode, metode mana yang unggul.




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

![Informasi dataset](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20110935.png)

Pada Dataset terdiri atas 8 kolum dengan jumlah data 10.000 data, namun  terdapat 1 kolom yang memiliki kurang dari 10.000 data yaitu pada kolom Description yang menandakan adanya missing values.

Melakukan pengecekan jumlah missing values dan berikut hasilnya:

![Missing Values](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20112732.png)

Dari gambar di atas terlihat kolom Description memiliki missing values sebanyak 77 data.

Melakukan pengecekan 10 besar penulis dengan buku terbanyak dan visualisai nya sebagai berikut.

![Top 10 Autors](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20111016.png)

Dari gambar di atas saya memdapatkan informasi terkait 10 besar nama penulis dengan jumlah buku terbanyak.

Melakukan visualisasi untuk melihat data nama buku terpanjang, sebagai berikut.

![Top length book](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20111039.png)

Visualisasi tersebut menunjukkan distribusi panjang nama buku, di mana mayoritas buku memiliki panjang nama antara 20 hingga 50 karakter, dengan frekuensi tertinggi pada sekitar 30 karakter. Distribusi ini bersifat right-skewed, menunjukkan bahwa sebagian kecil buku memiliki nama yang jauh lebih panjang (di atas 100 karakter). Data ini mengindikasikan bahwa nama buku yang lebih pendek lebih umum, yang dapat membantu dalam pengoptimalan sistem rekomendasi berbasis content based filtering

Melakukan visualisasi Kata-kata yang paling banyak muncul dalam deskripsi buku sebagai berikut.

![word popular](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20111103.png)

Pada Visualisasi di atas menunjukkan bahwa ada beberapa kata yang ukurannya besar dimana semakin besar ukuran kata menunjukkan bahwa kata tersebut paling banyak muncul, seperti kata "Life", "One", " World", dan lainnya.

Melakukan visualisasi 5 Genre Teratas. sebagai berikut.

![genre popular](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20111124.png)

Visualisasi ini memberikan insight Genre yang paling banyak tersedia dimana "Fiction" menempati peringkat teratas.





## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.
1. Menghapus kolom Yang tidak diperlukan
   
Saya menghapus kolom Unnamed: 0 biasanya merupakan indeks tambahan yang dihasilkan saat membaca dataset, sedangkan kolom URL hanya berisi tautan ke detail buku di Goodreads, yang tidak memberikan informasi signifikan untuk analisis atau pembuatan rekomendasi. Dengan menghapus kolom-kolom ini, dataset menjadi lebih bersih dan fokus pada fitur yang relevan untuk meningkatkan efisiensi sistem rekomendasi.

2. Menangani Missing Values pada kolom Description

Saya menangani nilai yang hilang (missing values) pada kolom Description. Pendekatan ini menggantikan nilai yang hilang dengan string kosong ('') agar kolom tersebut tetap konsisten dan dapat digunakan dalam analisis atau pemrosesan lebih lanjut. 

3. Mengubah kolom jumlah rating (Num_Ratings) menjadi numerik

Saya mengubah data pada kolom Num_Ratings menjadi tipe numerik. Pertama, fungsi .str.replace(',', '') menghapus tanda koma dalam angka agar dapat dikenali sebagai angka. Langkah ini penting untuk memastikan data konsisten dan dapat digunakan dalam analisis statistik atau pemrosesan lebih lanjut.

4. Mengubah deskripsi menjadi lowercase dan menghilangkan tanda baca
   
Saya mengubah semua kata menjadi huruf kecil agar tidak ada kata yang sama namun diartikan berbeda karena memiliki struktur tulisan berbeda.

5. Menghapus stopwords pada deskripsi
   
Untuk menyederhanakan deskripsi saya menghilangkan kata-kata yang kurang penting dan mempertahankan kata unik pada deskripsi dengan melakukan penghapusan stopwords.

6. Feature Extraction

Feature extraction dengan TF-IDF dan CountVectorizer adalah bagian dari tahap data preparation, lebih tepatnya disebut vectorization, yang bertujuan mengubah data teks menjadi representasi numerik yang dapat digunakan oleh algoritma pemrosesan atau pembelajaran mesin. CountVectorizer bekerja dengan menghitung jumlah kemunculan kata (word count) dalam dokumen, sedangkan TF-IDF (Term Frequency-Inverse Document Frequency) memberikan bobot pada kata berdasarkan frekuensi kemunculannya di suatu dokumen relatif terhadap dokumen lain. Kedua metode ini sangat penting untuk merepresentasikan teks sebagai vektor numerik, memungkinkan perhitungan kesamaan cosine similarity dan analisis lebih lanjut untuk rekomendasi.

6.1 CountVectorizer
   
Count Vectorizer adalah alat yang tersedia dalam library Scikit-Learn yang berfungsi untuk mengubah data teks menjadi bentuk vektor berdasarkan jumlah kemunculan setiap kata dalam teks. Dengan menggunakan Count Vectorizer, sebuah matriks dibuat untuk merepresentasikan kata-kata unik dalam huruf kecil yang diurutkan secara alfabet pada setiap kolom, sementara baris mewakili teks dari dokumen. Setiap sel dalam matriks diisi dengan frekuensi kemunculan kata dalam dokumen tersebut [(dewi,dkk.,2022)](https://www.strategi.it.maranatha.edu/index.php/strategi/article/view/335/238).

6.2 TF-IDF

   TF-IDF, atau Term Frequency-Inverse Document Frequency, adalah metode untuk mengukur seberapa penting suatu kata dalam kumpulan dokumen. Setiap kata diberikan skor yang mencerminkan tingkat kepentingannya dalam dokumen tertentu. Teknik ini digunakan untuk mengonversi kata-kata menjadi representasi numerik[(dewi,dkk.,2022)](https://www.strategi.it.maranatha.edu/index.php/strategi/article/view/335/238).
Untuk Menghitung TF-IDF:
- Term Frequency (TF)
Mengukur frekuensi kemunculan sebuah kata dalam dokumen tertentu:

$$
\text{TF}(t, d) = \frac{\text{Jumlah kemunculan kata } t \text{ dalam dokumen } d}{\text{Total kata dalam dokumen } d}
$$

- Inverse Document Frequency (IDF)

$$
\text{IDF}(t) = \log{\left( \frac{\text{Total jumlah dokumen}}{\text{Jumlah dokumen yang mengandung kata } t} \right)}
$$

- TF-IDF

$$
\text{TF-IDF}(t, d) = \text{TF}(t, d) \times \text{IDF}(t)
$$


   
## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi dilakukan dengan metode CountVectorizer dan Cosine Similarity serta TF-IDF dan Cosine Similarity.  
Berikut penjelasan tentang  Metode tersebut:
- Cosine Similarity : 
Cosine similarity adalah metode yang digunakan untuk menilai tingkat kemiripan antara dua vektor yang bukan nol dengan mengukur nilai cosinus dari sudut yang terbentuk di antara kedua vektor tersebut[(dewi,dkk.,2022)](https://www.strategi.it.maranatha.edu/index.php/strategi/article/view/335/238).

$$
\text{Cosine Similarity} = \frac{A \cdot B}{\|A\| \|B\|}
$$


**Implementasi Modeling**: 
- Metode CountVectorizer dan Cosine Similarity
Model rekomendasi menggunakan CountVectorizer dan Cosine Similarity bekerja dengan cara mengubah deskripsi teks buku menjadi representasi numerik berdasarkan frekuensi kata yang muncul di dalam teks menggunakan CountVectorizer. Selanjutnya, Cosine Similarity digunakan untuk mengukur kesamaan antara buku yang satu dengan buku lainnya berdasarkan vektor yang dihasilkan. Model ini akan memberikan rekomendasi buku-buku yang memiliki kesamaan tertinggi dengan buku yang dipilih, memungkinkan sistem untuk merekomendasikan buku serupa berdasarkan deskripsi teksnya. Metode ini efektif dalam menangkap hubungan antar buku yang berbagi kata-kata atau tema yang serupa.
  
![CountVectorizer](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20134606.png)

- Metode TF-IDF dan Cosine Similarity.
Dalam sistem rekomendasi, TF-IDF pertama-tama mengubah deskripsi buku menjadi vektor numerik, yang kemudian digunakan untuk menghitung Cosine Similarity antara buku yang sedang dianalisis dan buku-buku lainnya. Nilai cosine similarity ini menunjukkan seberapa mirip dua buku, yang digunakan untuk memberikan rekomendasi buku serupa kepada pengguna.
  
![TF-IDF](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20134638.png)

- Penjelasan perbandingan kedua metode:
Perpaduan CountVectorizer dan Cosine Similarity, serta TF-IDF dan Cosine Similarity digunakan untuk mengubah teks menjadi vektor numerik, yang kemudian diukur kesamaannya menggunakan Cosine Similarity. CountVectorizer mengubah teks menjadi vektor berdasarkan frekuensi kata, sementara TF-IDF memberikan bobot lebih pada kata yang jarang muncul namun penting dalam dokumen. Kombinasi CountVectorizer dan Cosine Similarity cocok untuk teks dengan frekuensi kata sederhana, sedangkan TF-IDF dan Cosine Similarity lebih efektif untuk menilai pentingnya kata-kata dalam konteks yang lebih spesifik. Keduanya menghasilkan vektor yang digunakan untuk mengukur kesamaan antar dokumen, dengan Cosine Similarity menghitung seberapa mirip dua vektor tersebut.


## Evaluation

Untuk mengetahui keakuratan   dua model CountVectorizer + Cosine Similarity dan TF-IDF + Cosine Similarity, model rekomendasi ini diuji menggunakan dua metrik evaluasi utama, yaitu precision dan recall, untuk mengukur seberapa baik model dalam memberikan rekomendasi yang relevan. Precision mengukur seberapa banyak rekomendasi yang diberikan oleh model yang benar-benar relevan, yaitu perbandingan antara jumlah rekomendasi yang benar dengan total rekomendasi yang diberikan. Sedangkan recall mengukur seberapa banyak buku yang relevan berhasil direkomendasikan oleh model, yaitu perbandingan antara jumlah rekomendasi yang benar dengan jumlah buku relevan yang seharusnya direkomendasikan. Dengan kedua metrik ini, saya dapat mengevaluasi seberapa akurat dan lengkap hasil rekomendasi yang dihasilkan oleh model.

Evaluasi model rekomendasi ini dilakukan menggunakan dua metrik utama sebagai berikut:

1. Precision: Metrik ini mengukur seberapa banyak rekomendasi yang diberikan oleh model yang benar-benar relevan. Precision dihitung dengan rumus:

$$ 
\text{Precision} = \frac{\text{True Positives}}{\text{True Positives} + \text{False Positives}}
$$

3. Recall: Metrik ini mengukur seberapa banyak buku yang relevan berhasil direkomendasikan oleh model. Recall dihitung dengan rumus:

$$ 
\text{Recall} = \frac{\text{True Positives}}{\text{True Positives} + \text{False Negatives}}
$$



*Hasil Evaluasi*

| Model            | Precision | Recall |
|------------------|-----------|--------|
| CountVectorizer  | 0.6655    | 1.0000 |
| TF-IDF           | 0.6499    | 1.0000 |

Visualisasi hasil evaluasi:

![Hasil Evaluasi](https://raw.githubusercontent.com/Desumawijaya/Project_Dicoding_2/main/images/Screenshot%202024-12-07%20140739.png)

Hasil evaluasi menunjukkan bahwa kedua model, TF-IDF + Cosine Similarity dan CountVectorizer + Cosine Similarity, memiliki recall sempurna (1.0000), yang berarti keduanya mampu merekomendasikan semua item relevan tanpa ada yang terlewat. Namun, dari segi precision, model CountVectorizer sedikit lebih unggul dengan nilai 0.6655 dibandingkan TF-IDF yang memiliki precision 0.6499. Hal ini menunjukkan bahwa rekomendasi dari CountVectorizer lebih akurat dalam memberikan item relevan dibandingkan TF-IDF. Secara keseluruhan, kedua model memiliki performa yang baik, dengan kelebihan masing-masing.

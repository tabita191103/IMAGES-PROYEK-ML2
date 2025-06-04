# Laporan Proyek Machine Learning - Tabita Novi Sinaga

## Project Overview
Sistem rekomendasi merupakan suatu mekanisme yang dirancang untuk memprediksi item atau data berdasarkan interaksi pengguna di masa lalu, lalu menyarankan item yang paling relevan dan sesuai kebutuhan. Sistem ini telah menjadi solusi umum dalam menangani masalah kelebihan informasi, dengan menyarankan produk atau konten yang paling sesuai untuk pengguna. Teknologi ini banyak digunakan di berbagai sektor, seperti media digital, platform layanan streaming, hingga e-commerce. Beberapa platform streaming film seperti Netflix, Vidio, WeTV, dan Viu telah mengimplementasikan sistem rekomendasi untuk meningkatkan kenyamanan pengguna. Rekomendasi diberikan berdasarkan genre yang sering dipilih pengguna, serta rating film yang diberikan oleh pengguna lain. Tujuan akhirnya adalah memudahkan pengguna dalam menemukan film yang sesuai dengan preferensi mereka, baik dari segi genre, tema, atau film dengan rating tinggi. Dalam era digital saat ini, pengguna dihadapkan pada jumlah konten yang sangat besar, khususnya dalam layanan streaming film. Tanpa sistem rekomendasi yang baik, pengguna akan kesulitan menemukan konten yang sesuai dengan preferensi mereka. Hal ini dapat menurunkan pengalaman pengguna dan meningkatkan kemungkinan mereka meninggalkan platform. Oleh karena itu, pengembangan sistem rekomendasi yang efektif sangat penting. Dengan menggunakan dataset MovieLens, sistem ini dapat dilatih untuk mengenali pola preferensi pengguna dan memberikan saran film yang lebih relevan. Sistem dapat dikembangkan menggunakan pendekatan berbasis konten (content-based), kolaboratif (collaborative filtering), atau gabungan dari keduanya (hybrid). Melalui pendekatan ini, sistem tidak hanya meningkatkan pengalaman pengguna tetapi juga membantu platform untuk mempertahankan pengguna lebih lama serta meningkatkan engagement secara keseluruhan.


## Business Understanding

### Problem Statements
Bagaimana metode yang dapat digunakan untuk menyarankan film sesuai dengan kesukaan pengguna?

### Goals
Sebagai solusi atas permasalahan yang diuraikan pada bagian Problem Statement, dikembangkan sebuah sistem rekomendasi yang mampu menyarankan film berdasarkan rating serta riwayat interaksi pengguna sebelumnya.

### Solution statements
Pendekatan yang diambil dalam membangun model ini adalah dengan menerapkan satu algoritma machine learning, yaitu terbatas pada Content-Based Filtering dan Collaborative Filtering. Kedua algoritma ini memiliki tujuan yang sama, yaitu memberikan rekomendasi film kepada pengguna. Algoritma Content-Based Filtering bekerja dengan menganalisis riwayat tontonan pengguna untuk menyarankan film yang memiliki kemiripan dengan preferensi sebelumnya. Sementara itu, Collaborative Filtering merekomendasikan film berdasarkan pola rating tertinggi dari pengguna lain yang memiliki kesamaan selera.
- Content Based Filtering
&nbsp;&nbsp;&nbsp;Algoritma Content-Based Filtering merupakan salah satu pendekatan dalam sistem rekomendasi yang berfokus pada analisis karakteristik atau fitur dari suatu item (misalnya film, buku, produk, dll.) untuk memberikan rekomendasi item lain yang memiliki kemiripan dengan item yang pernah disukai atau diakses oleh pengguna. Algoritma ini bekerja dengan mempelajari preferensi individu pengguna, baik berdasarkan aktivitas sebelumnya seperti riwayat penelusuran dan interaksi, maupun melalui umpan balik eksplisit seperti rating atau ulasan yang diberikan. Dalam praktiknya, Content-Based Filtering akan mengevaluasi setiap item berdasarkan atribut atau fitur yang menyusunnya—misalnya pada konteks film, fitur tersebut bisa berupa genre, sutradara, aktor, atau sinopsis. Sistem kemudian akan membandingkan kesamaan antar item berdasarkan fitur-fitur tersebut, dan mencocokkannya dengan profil preferensi pengguna. Hasilnya, pengguna akan memperoleh rekomendasi item yang secara konten memiliki kemiripan dengan item yang mereka sukai sebelumnya. Selain itu, algoritma ini juga dapat memanfaatkan informasi tambahan yang dikumpulkan tentang pengguna, seperti preferensi genre atau pola konsumsi konten, untuk meningkatkan akurasi rekomendasi. Keunggulan utama dari Content-Based Filtering adalah kemampuannya memberikan rekomendasi yang bersifat personal dan spesifik terhadap satu pengguna, tanpa memerlukan data dari pengguna lain seperti yang dibutuhkan pada pendekatan collaborative filtering. Namun, pendekatan ini juga memiliki keterbatasan, seperti risiko over-specialization, di mana sistem hanya merekomendasikan item yang sangat mirip dengan yang sudah pernah disukai, sehingga mengurangi keberagaman rekomendasi. Meskipun demikian, Content-Based Filtering tetap menjadi salah satu metode yang efektif dan banyak digunakan dalam sistem rekomendasi modern, terutama ketika informasi pengguna sangat terbatas atau baru pertama kali menggunakan layanan.
- Collaborative Filtering
&nbsp;&nbsp;&nbsp; Algoritma Collaborative Filtering merupakan salah satu pendekatan utama dalam sistem rekomendasi yang bekerja dengan cara memanfaatkan pola kesamaan baik antar pengguna maupun antar item untuk menghasilkan rekomendasi yang relevan. Inti dari metode ini adalah prinsip bahwa jika dua pengguna memiliki preferensi atau perilaku yang mirip di masa lalu, maka kemungkinan besar mereka juga akan menyukai item yang sama di masa depan. Terdapat dua jenis utama dari Collaborative Filtering, yaitu User-Based Collaborative Filtering dan Item-Based Collaborative Filtering. Pada pendekatan User-Based, sistem menganalisis dan mengidentifikasi pengguna-pengguna yang memiliki pola penilaian atau interaksi yang serupa. Setelah itu, sistem merekomendasikan item yang disukai oleh pengguna-pengguna serupa tersebut kepada pengguna target, meskipun pengguna target belum pernah melihat atau berinteraksi dengan item tersebut sebelumnya. Sementara itu, pada Item-Based Collaborative Filtering, sistem tidak fokus pada kemiripan antar pengguna, tetapi pada kemiripan antar item berdasarkan penilaian pengguna. Jika banyak pengguna memberikan rating tinggi pada dua item yang berbeda secara bersamaan, maka sistem akan menganggap kedua item tersebut memiliki hubungan. Dengan demikian, ketika seorang pengguna menyukai salah satu item, sistem dapat merekomendasikan item lainnya yang dinilai mirip berdasarkan perilaku kolektif pengguna lain. Kekuatan utama dari Collaborative Filtering adalah kemampuannya menemukan pola tersembunyi yang tidak bisa ditangkap oleh fitur konten secara langsung. Metode ini tidak membutuhkan informasi tentang fitur atau karakteristik dari item itu sendiri, sehingga sangat berguna ketika metadata atau deskripsi konten terbatas. Sebaliknya, algoritma ini hanya bergantung pada data interaksi pengguna, seperti rating, klik, atau pembelian. Namun, pendekatan ini juga memiliki beberapa kelemahan. Salah satunya adalah masalah cold start, yaitu ketidakmampuan sistem dalam memberikan rekomendasi yang akurat ketika jumlah data pengguna atau interaksi masih sangat sedikit, misalnya untuk pengguna baru atau item baru. Selain itu, algoritma ini dapat mengalami masalah sparsity, yaitu ketika data interaksi pengguna terlalu jarang, sehingga sulit menemukan kesamaan yang bermakna antar pengguna atau item. Secara keseluruhan, Collaborative Filtering adalah metode yang sangat efektif untuk memberikan rekomendasi yang bersifat sosial atau kolektif, dan menjadi dasar dari banyak sistem rekomendasi yang digunakan dalam berbagai platform besar seperti Netflix, Amazon, dan Spotify.



## Data Understanding
Dataset: [MovieLens Dataset - Kaggle](https://www.kaggle.com/datasets/ayushimishra2809/movielens-dataset)

#### Variabel
- links : merupakan daftar link eksternal dari setiap film.
- movies : merupakan daftar film yang tersedia.
- ratings : merupakan daftar penilaian (rating) yang diberikan pengguna terhadap film.
- tags : merupakan daftar kata kunci atau deskripsi dari film yang diberikan oleh pengguna.


![Jumlah Data](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/jumlah-data.png?raw=true)
Berdasarkan dataset yang digunakan, terdapat 10.329 entri data film yang mencerminkan jumlah total judul film yang tersedia dalam sistem. Sementara itu, pada dataset rating, tercatat sebanyak 105.339 data penilaian yang diberikan oleh pengguna terhadap berbagai film tersebut.

![Contoh Data](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/contoh-data.png?raw=true)
Dataset Film memuat informasi seperti ID film, judul film, dan genre, yang dapat digunakan untuk memahami konten dan karakteristik masing-masing film. Sebagai contoh, film Toy Story (1995) memiliki beberapa genre sekaligus seperti Adventure, Animation, dan Comedy, yang menunjukkan bahwa satu film bisa memiliki lebih dari satu kategori genre Sementara itu, dataset Rating mencatat interaksi pengguna berupa userId, movieId, rating, dan timestamp. Contoh data menunjukkan bahwa pengguna memberikan penilaian dalam skala numerik (misalnya 4.0 atau 1.5) terhadap film tertentu. Data ini penting untuk mengetahui preferensi pengguna dan menjadi dasar dalam membangun sistem rekomendasi yang akurat.

#### Explanatory Data Analysis
*Univariate Analysis* 

*MOVIE*
![Movie](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/movies.png?raw=true)
Dataset Film terdiri dari berbagai judul film dengan genre yang beragam. Setiap film diidentifikasi dengan movieId, memiliki judul, dan satu atau lebih genre. Terlihat bahwa film-film populer seperti Toy Story (1995) dan Jumanji (1995) memiliki beberapa genre sekaligus, seperti Adventure, Animation, Children, dan Fantasy, yang menunjukkan bahwa satu film dapat diklasifikasikan dalam berbagai kategori. Selain itu, ditemukan juga beberapa film yang tidak memiliki genre yang tercantum (misalnya Marco Polo: One Hundred Eyes (2015)), yang menunjukkan adanya data yang belum lengkap atau perlu diproses lebih lanjut. Insight ini penting dalam pembuatan sistem rekomendasi berbasis konten, karena genre merupakan salah satu fitur utama dalam menentukan kemiripan antar film.

![Info Movie](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/info-movie.png?raw=true)
![Decsribe Movie](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/movie-describe.png?raw=true)

Missing Value
Pemeriksaan nilai kosong (missing values) pada dataset movies menunjukkan jumlah nilai yang hilang di setiap kolom. 
![Missing Movie](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/movie-missing.png?raw=true)
Pada dataset movies, hasil pengecekan nilai kosong dengan movies.isna().sum() menunjukkan bahwa tidak ada data yang hilang di semua kolom, yaitu movieId, title, dan genres. Semua kolom memiliki nilai lengkap tanpa missing value.


*RATING*
![Rating](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/rating.png?raw=true)
Dataset rating terdiri dari 105.339 baris dan 4 kolom, yaitu userId, movieId, rating, dan timestamp. Setiap baris merepresentasikan interaksi pengguna terhadap film tertentu dalam bentuk penilaian (rating).

![Info Rating](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/info-rating.png?raw=true)
![Describe Rating](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/describe-rating.png?raw=true)

Missing Value
Pemeriksaan nilai kosong (missing values) pada dataset movies menunjukkan jumlah nilai yang hilang di setiap kolom. 
![Missing Rating](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/rating-missing.png?raw=true)

![Jumlah Data](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/jumlah-data.png?raw=true)

## Data Preparation
1. Menghitung Total Film Unik Berdasarkan movieId dari Kedua Dataset
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan penggabungan (concatenate) antara daftar movieId yang unik dari dua dataset berbeda, yaitu dataset movies (informasi film) dan dataset rating (data penilaian pengguna). Setelah penggabungan, dilakukan proses penyaringan nilai yang duplikat (np.unique) dan pengurutan (np.sort) untuk memperoleh daftar movieId yang benar-benar unik dan tersusun secara teratur. Proses ini bertujuan untuk memastikan konsistensi dan kelengkapan data antara metadata film dan data rating, sehingga seluruh film yang ada di kedua dataset dapat teridentifikasi dengan tepat. Dengan memiliki daftar film unik yang lengkap, tahapan ini membantu menghindari duplikasi yang dapat menyebabkan kesalahan dalam analisis atau pembangunan model, memudahkan pemetaan antara film dan rating, serta memungkinkan deteksi ketidaksesuaian data yang mungkin perlu penanganan lebih lanjut. 

2. Penggabungan Data Rating dengan Informasi Film Berdasarkan movieId
![Tahap 2](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/prep1.png?raw=true)
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan penggabungan antara dataset rating dan informasi film dengan menggunakan fungsi concat dan merge berdasarkan kolom movieId. Pertama, dataset rating dan film digabungkan secara vertikal menggunakan concat untuk mengonsolidasikan data, kemudian dilakukan penggabungan (merge) secara horizontal dengan metode left join pada kolom movieId agar setiap data rating memiliki informasi lengkap mengenai film terkait, seperti judul dan genre. Tahapan ini penting karena memungkinkan pemadanan data rating dengan metadata film sehingga analisis dan pembangunan sistem rekomendasi bisa mempertimbangkan konteks film secara menyeluruh. Dengan data yang sudah terintegrasi, model rekomendasi dapat memanfaatkan baik perilaku pengguna (rating) maupun atribut film (konten) untuk menghasilkan rekomendasi yang lebih akurat dan relevan. Selain itu, tahapan ini memastikan kelengkapan dan konsistensi data yang krusial untuk menghindari kesalahan dan meningkatkan kualitas hasil analisis.

3. Menghitung Jumlah Pengguna Unik Berdasarkan userId di Dataset Rating
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan ekstraksi nilai userId yang unik dari dataset rating dengan menggunakan fungsi unique() dan kemudian diurutkan secara ascending menggunakan np.sort(). Proses ini bertujuan untuk mengidentifikasi seluruh pengguna yang pernah memberikan rating, sehingga didapatkan daftar lengkap pengguna unik dalam dataset. Tahapan ini sangat penting karena mengetahui jumlah dan identitas pengguna unik merupakan dasar dalam analisis perilaku pengguna dan pengembangan sistem rekomendasi. Dengan data pengguna yang bersih dan terstruktur, sistem dapat memetakan interaksi setiap pengguna secara tepat dan menghindari duplikasi data yang dapat mempengaruhi akurasi model serta hasil rekomendasi.

4. Menghitung Missing Value di Movie
![Missing Val](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/mis-mov.png?raw=true)
Terdapat banyak missing value pada movie

5. Penggabungan Dataset Rating dan Film Berdasarkan movieId serta Pemeriksaan Nilai Hilang
![Tahap 5](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/prep2.png?raw=true)
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan penggabungan antara dataset rating dan dataset film menggunakan fungsi merge dengan kolom kunci movieId dan metode left join. Tujuannya adalah untuk melengkapi setiap entri rating dengan informasi detail terkait film yang dinilai, seperti judul dan genre. Setelah penggabungan, dilakukan pemeriksaan nilai kosong (missing values) pada dataset hasil gabungan untuk mengidentifikasi apakah ada data film yang tidak ditemukan atau tidak lengkap terkait dengan data rating. Tahapan ini penting karena memastikan bahwa setiap data rating memiliki konteks film yang lengkap sehingga analisis dan pengembangan sistem rekomendasi dapat dilakukan dengan akurat dan menyeluruh. Selain itu, pengecekan missing values membantu mendeteksi dan menangani potensi inkonsistensi atau kekurangan data yang dapat mempengaruhi kualitas model dan hasil rekomendasi yang dihasilkan.

6. Pengurutan Dataset Gabungan Berdasarkan movieId Secara Ascending
![Tahap 6](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/prep3.png?raw=true)
&nbsp;&nbsp;&nbsp;Pada tahap ini, dataset gabungan antara data rating dan informasi film diurutkan berdasarkan kolom movieId secara menaik menggunakan fungsi sort_values(). Proses pengurutan ini bertujuan untuk menyusun data secara teratur berdasarkan identifikasi unik film sehingga memudahkan dalam proses pencarian, pemrosesan, dan analisis data selanjutnya. Tahapan ini penting dilakukan karena data yang tersusun rapi membantu dalam mengoptimalkan efisiensi akses data, meningkatkan kejelasan struktur dataset, serta memudahkan deteksi pola atau anomali yang mungkin muncul. Pengurutan juga menjadi langkah awal yang baik sebelum melakukan operasi lanjutan seperti filtering, grouping, atau visualisasi data.

7. Menghitung Data Duplikat pada Kolom movieId
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan pengecekan terhadap jumlah nilai duplikat pada kolom movieId dalam dataset gabungan menggunakan fungsi duplicated().sum(). Proses ini bertujuan untuk mengidentifikasi apakah terdapat entri film yang muncul lebih dari sekali, yang bisa saja terjadi akibat penggabungan data atau kesalahan pencatatan. Tahapan ini penting karena duplikasi data dapat menyebabkan bias dan distorsi dalam analisis maupun model rekomendasi, seperti penghitungan rating yang tidak akurat atau pengaruh ganda pada hasil prediksi. 

np.int64(95014)
Hasil pemeriksaan menunjukkan terdapat 95.014 entri duplikat pada kolom movieId dalam dataset gabungan. 

8. Menghapus Duplikat pada movieId dan Menghitung Total Film Unik
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan penghapusan duplikasi pada kolom movieId menggunakan fungsi drop_duplicates('movieId'). Proses ini bertujuan untuk memastikan bahwa setiap film hanya muncul sekali dalam dataset, meskipun mungkin ada banyak entri rating dari pengguna yang berbeda untuk film yang sama. Setelah duplikasi dihapus, dilakukan penghitungan jumlah film unik dengan menggunakan fungsi len(all_movie['movieId']). Tahapan ini penting karena duplikasi data dapat menyebabkan analisis yang tidak akurat dan mempengaruhi hasil sistem rekomendasi. Dengan menghapus duplikat, dataset menjadi lebih bersih dan representatif, serta memastikan bahwa analisis dan model rekomendasi hanya mempertimbangkan film yang unik, bukan rating atau entri berulang untuk film yang sama.

10325
Setelah proses penghapusan duplikasi berdasarkan kolom movieId, didapatkan total 10.325 film unik dalam dataset. Jumlah ini mencerminkan banyaknya judul film yang berbeda setelah menghilangkan entri ganda, sehingga dataset siap digunakan untuk analisis dan pengembangan sistem rekomendasi dengan data yang lebih bersih dan terstruktur.

9. Pembuatan DataFrame Film Final dengan Kolom id, Title, dan Genre
![Tahap 9](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/prep4.png?raw=true)
&nbsp;&nbsp;&nbsp;Pada tahap ini, dilakukan pembuatan DataFrame baru yang diberi nama movie_fix dengan memilih kolom-kolom penting dari dataset all_movie, yaitu movieId yang diubah menjadi id, title, dan genres. Proses ini bertujuan untuk menyederhanakan dataset dengan hanya mengambil informasi utama yang relevan untuk analisis dan pengembangan sistem rekomendasi film. Tahapan ini penting karena memudahkan pengelolaan data, mengurangi kompleksitas dataset, serta fokus pada atribut yang paling berpengaruh dalam proses pemodelan dan pemrosesan data selanjutnya. Dengan dataset yang lebih ringkas dan terstruktur, proses pengolahan data dan pembuatan model dapat berjalan lebih efisien dan terorganisir.


## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Proses ini dilakukan dengan menggunakan dua algoritma, yaitu Content-Based Filtering dan Collaborative Filtering. Hasil akhir yang diharapkan dari sistem rekomendasi ini adalah memudahkan pengguna dalam menemukan film yang diinginkan, baik berdasarkan preferensi film yang serupa maupun rekomendasi yang didasarkan pada rating.

#### Content Based Filtering
Proses ini dilakukan dengan memberikan pembobotan pada fitur genre menggunakan modul TfidfVectorizer dari pustaka sklearn untuk mengidentifikasi genre-genre yang ada. Selanjutnya, digunakan modul cosine_similarity dari pustaka yang sama untuk menghitung kemiripan antar film. Fungsi movie_recommendation dengan parameter movie_name digunakan untuk membangun model rekomendasi. Dalam fungsi ini, juga ditetapkan nilai k = 5, yang berarti sistem akan memberikan rekomendasi 5 film teratas berdasarkan kesamaan genre.


- Film yang pernah disukai oleh pengguna sebelumnya, yang akan digunakan untuk mencari rekomendasi:
![Serupa](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/mirip-toy.png?raw=true)

- Film yang disarankan melalui fungsi movie_recommendation, yang kemudian menghasilkan lima film teratas dengan genre yang serupa:
![Genre Serupa](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/genre-mirip-toy.png?raw=true)

Dalam membangun Content-Based Filtering, salah satu kelebihan utamanya adalah kemampuannya untuk memberikan rekomendasi yang personal berdasarkan genre favorit pengguna, dengan menggunakan TfidfVectorizer untuk memberikan pembobotan pada fitur genre dan cosine similarity untuk menghitung kemiripan antar film. Dengan menetapkan parameter k = 5, sistem dapat memberikan rekomendasi lima film teratas yang relevan dengan genre yang disukai pengguna. Namun, ada beberapa kekurangan dari pendekatan ini. Model ini terbatas hanya pada genre, sehingga tidak mempertimbangkan faktor lain seperti rating atau aktor yang mungkin juga mempengaruhi preferensi pengguna. Selain itu, sistem ini berisiko memberikan rekomendasi yang kurang beragam, terutama jika film yang disukai pengguna memiliki genre yang sangat spesifik. Untuk dapat bekerja secara optimal, model ini juga membutuhkan data genre yang lengkap dan akurat.


#### Collaborative Filtering
Proses pelatihan dan pembuatan model RecommenderNet dilakukan menggunakan optimizer Adam dan evaluasi dengan matriks RMSE. Model RecommenderNet menghitung skor kecocokan antara dua lapisan embedding, yaitu milik pengguna dan film, melalui operasi dot_product, dan menambahkan bias pada keduanya. Skor kecocokan yang dihasilkan kemudian disesuaikan dalam skala interval 0 hingga 1 dengan menggunakan fungsi sigmoid.

- Film dengan genre yang disarankan berdasarkan rating tertinggi:
![Rating Tinggi](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/rating-tinggi.png?raw=true)

- Top 10 recommended movies
![Top](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/top.png?raw=true)

## Evaluation

#### Content Based Filtering
![Metrik 1](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/metrik1.png?raw=true)
Matriks evaluasi yang dapat digunakan adalah presisi. Presisi mengukur sejauh mana alat ukur dapat menghasilkan hasil yang konsisten jika digunakan berulang kali dalam kondisi pengukuran dan objek yang sama. Dalam konteks ini, presisi akan mengukur kemampuan model dalam memprediksi label yang benar di antara semua prediksi yang dihasilkan. Berdasarkan hasil rekomendasi yang ditampilkan pada bagian modeling, dapat disimpulkan bahwa pengguna mencari rekomendasi film yang berhubungan dengan Toy Story (1995). Sistem rekomendasi kemudian memberikan 5 film terkait yang memiliki genre yang sama, yaitu Adventure|Animation|Children|Comedy|Fantasy. Mengacu pada rumus presisi yang telah dijelaskan sebelumnya, dapat diketahui bahwa semua rekomendasi yang diberikan memiliki genre yang serupa dengan film yang dicari. Dengan demikian, presisi sistem yang dibangun mencapai 5/5 atau 100%.

#### Collaborative Filtering
![Metrik 2](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/metrik2.png?raw=true)
Note:
At : Nilai Aktual.
ft = Nilai hasil peramalan.
N = banyaknya dataset

Metrik evaluasi yang digunakan untuk menilai kinerja model adalah RMSE (Root Mean Squared Error). RMSE mengukur perbedaan antara nilai yang diprediksi oleh model dan nilai yang sebenarnya diamati, serta merupakan hasil kuadrat dari MSE. Keakuratan model diukur melalui nilai RMSE, di mana nilai yang lebih kecil menunjukkan tingkat kesalahan pengukuran yang lebih rendah. Semakin kecil nilai RMSE yang diperoleh, semakin tinggi akurasi model tersebut.
RMSE adalah metode untuk mengukur perbedaan antara nilai prediksi yang dihasilkan oleh model dengan nilai yang sebenarnya diamati. Root Mean Square Error (RMSE) diperoleh dengan mengambil akar kuadrat dari Mean Square Error (MSE). Keakuratan estimasi kesalahan pengukuran dapat dilihat dari nilai RMSE yang kecil. Semakin kecil nilai RMSE yang diperoleh, semakin akurat metode estimasi tersebut dibandingkan dengan metode lain yang memiliki nilai RMSE lebih besar. Kelebihan: RMSE memberikan penalti yang lebih besar untuk kesalahan besar, sehingga dapat memberikan hasil yang lebih akurat dalam beberapa situasi. Kekurangan: RMSE memberikan bobot yang cukup besar pada kesalahan besar, yang berarti metode ini akan lebih berguna ketika kesalahan besar sangat tidak diinginkan atau harus dihindari.


Menerapkan metrik tersebut:
![Met](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/terap.png?raw=true)

Hasil Evaluasi:
![Eval](https://github.com/tabita191103/IMAGES-PROYEK-ML2/blob/main/eval.png?raw=true)

Dari visualisasi proses training model di atas, dapat dilihat bahwa proses pelatihan berlangsung dengan cukup mulus dan model konvergen pada sekitar epoch ke-100. Pada akhir proses ini, nilai error pada data pelatihan (train) mencapai sekitar 0.20, sementara error pada data validasi (test) berakhir pada sekitar 0.21.


Referensi:
[1] [Employing opposite ratings users in a new approach to collaborative filtering](https://ijeecs.iaescore.com/index.php/IJEECS/article/viewFile/24894/15925)
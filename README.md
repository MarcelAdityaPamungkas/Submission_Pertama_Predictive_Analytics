# Laporan Proyek Machine Learning - Marcel Aditya Pamungkas

## Domain Proyek

Obesitas maupun berat badan berlebih merupakan penyakit yang dapat didefinisikan sebagai penumpukan lemak berlebih pada badan seseorang. Obesitas dapat terjadi pada seluruh manusia dari jenis kelamin apapun dan umur berapapun. Menurut World Health Organization (WHO), pada tahun 2022, sekitar 2.5 miliar orang di dunia menderita berat badan berlebih, dengan 890 juta di antaranya dikategorikan sebagai obesitas. Obesitas dapat disebabkan oleh beberapa faktor, seperti makan-makanan berkalori tinggi dalam waktu singkat, kurang melakukan aktivitas fisik, perubahan perasaan yang menyebabkan nafsu makan menaik, atau kelainan hormon. Obesitas dapat siklasifikasi menjadi 4, yaitu berat badan berlebih (*overweight*), obesitas tingkat 1, obesitas tingkat 2, dan obesitas tingkat 3. Jika dibiarkan, obesitas dapat mengganggu aktivitas sehari-hari, seperti sulit untuk bergerak maupun beraktivitas berat. Tak hanya itu, obesitas juga berpotensi menimbulkan penyakit lainnya yang berbahaya, seperti Diabetes Mellitus tipe 2, jantung koronen, maupun hipertensi. Tentu akan lebih baik jika obesitas dapat dideteksi sedini mungkin.<br>

Pada zaman sekarang, teknologi telah berkembang pesat, salah satunya adalah teknologi *machine learning*. Hingga sekarang, *machine learning* telah digunakan ke dalam berbagai bidang, salah satunya bidang kesehatan. Dengan seiringnya perkembangan *machine learning*, sekarang *machine learning* mampu mendeteksi berbagai macam penyakit dengan berbagai parameter maupun faktor yang diberikan, salah satunya adalah mendeteksi obesitas. Oleh karena itu, pada proyek ini, penulis ingin memanfaatkan *machine learning* untuk mendeteksi tingkat berat badan pada seseorang, terutama yang didiagnosis mengalami obesitas agar dapat segera dicegah maupun diobati. Penulis ingin memprediksi penyakit obesitas pada responden menggunakan 4 model, yaitu *Extreme Gradient Boosting* (XGBoost), *Support Vector Machine* (SVM), *K-Nearest Neighbors* (KNN), dan *Random Forest*. Penulis menggunakan dataset dari Kaggle yang dapat diakses pada link [berikut](https://www.kaggle.com/datasets/aravindpcoder/obesity-or-cvd-risk-classifyregressorcluster/data).

## Business Understanding

### Problem Statements
Berdasarkan latar belakang yang telah dipaparkan, berikut rincian permasalahan yang dapat dibahas pada proyek ini.
1. Berapa persentase responden yang mengalami obesitas atau *overweight*?
2. Apakah jenis kelamin yang berbeda memiliki tingkat obesitas yang berbeda?
3. Apa faktor-faktor yang memengaruhi berat badan seseorang?
4. Apakah ada faktor tertentu yang dapat ditemukan untuk suatu tingkat obesitas tertentu?
5. Apa model terbaik yang dapat digunakan untuk memprediksi penyakit obesitas?

### Goals
Berdasarkan problem statements, berikut tujuan yang ingin dicapai pada proyek ini.
1. Mengetahui total persentase responden yang mengalami obesitas atau *overweight*.
2. Mencari perbedaan tingkat obesitas yang ada pada jenis kelamin yang berbeda.
3. Mengetahui faktor-faktor yang memengaruhi berat badan seseorang.
4. Mencari suatu faktor tertentu yang sama pada tingkat obesitas tertentu.
5. Menemukan model terbaik berdasarkan akurasi tertinggi untuk memprediksi penyakit obesitas pada responden.

### Solution Statement
1. Melakukan proses *Exploratory Data Analysis* (EDA) untuk mengetahui total persentase responden yang mengalami obesitas atau *overweight*, mencari perbedaan tingkat obesitas yang ada pada jenis kelamin yang berbeda, mengetahui faktor-faktor yang memengaruhi berat badan seseorang, dan mencari suatu faktor tertentu yang sama pada tingkat obesitas tertentu.
2. Menggunakan 4 model *machine learning* untuk memprediksi penyakit obesitas pada responden, yaitu *Extreme Gradient Boosting* (XGBoost), *Support Vector Machine* (SVM), *K-Nearest Neighbors* (KNN), dan *Random Forest*.
3. Menggunakan confusion matrix dan f1 score pada masing-masing model *machine learning* untuk menemukan model terbaik berdasarkan akurasi tertinggi.

## Data Understanding
Dataset yang digunakan untuk memprediksi tingkat obesitas atau *overweight* pada responden diambil dari platform [kaggle](https://www.kaggle.com/) yang dipublikasikan oleh ARAVINDPCODER dengan usability score 10/10. Data ini didapat dari survei menggunakan platform web kepada orang-orang dari negara Mexico, Peru, dan Colombia, dengan usia di rentang 14 hingga 61 tahun dan dari berbagai jenis kondisi fisik.  Dataset ini terdiri dari 1 file csv.<br>

### Informasi Keterangan Variabel pada Data
Dataset ini memiliki 17 variabel dengan keterangan sebagai berikut.
Variabel | Keterangan
----------|----------
Gender | Jenis kelamin responden (laki-laki atau perempuan)
Age | Usia responden
Height | Tinggi responden (dalam satuan meter)
Weight | Berat responden (dalam satuan kilogram)
family_history_with_overweight | Apakah terdapat anggota keluarga responden yang juga terkena obesitas
FAVC | Apakah responden mengonsumsi makanan berkalori tinggi
FCVC | Frekuensi konsumsi sayur-sayuran dalam sehari
NCP | Frekuensi konsumsi makanan berat dalam sehari
CAEC | Konsumsi makanan di antara makan berat
SMOKE | Apakah responden merupakan perokok 
CH2O | Frekuensi Konsumsi air dalam sehari (dalam satuan liter)
SCC	| Apakah responden memantau asupan kalori
FAF	| Frekuensi aktivitas fisik dalam seminggu (0 = Tidak pernah, 1 = 1-2 hari, 2 = 3-4 hari, 3 = 5-6 hari)
TUE	| Waktu pemakaian gadget dalam sehari (0 = 0-3 jam, 1 = 4-6 jam, 2 = 6+ jam)
CALC | Frekuensi konsumsi alkohol
MTRANS | Jenis transportasi yang digunakan
NObeyesdad | Tingkat berat badan responden

### Data Cleaning
Setelah diperiksa apakah terdapat kolom yang bernilai null, hasilnya adalah tidak ada. Sementara itu, setelah diperiksa apakah terdapat data duplikat, ditemukan 24 duplikat, sehingga data duplikat ini dihapus. Oleh karena itu, setelah dilakukan pembersihan data, diperoleh deskripsi statistik data numerik sebagai berikut. 
| | Age |	Height | Weight | FCVC | NCP | CH2O | FAF | TUE |
----------|----------|----------|----------|----------|----------|----------|----------|----------
count	| 2087.000000 |	2087.000000 |	2087.000000	| 2087.000000 |	2087.000000	| 2087.000000 |	2087.000000 |	2087.000000
mean | 24.353090 | 1.702674 | 86.858730 |	2.421466 | 2.701179 |	2.004749 | 1.012812 |	0.663035
std	| 6.368801 | 0.093186 | 26.190847	| 0.534737 | 0.764614 | 0.608284 | 0.853475 | 0.608153
min	| 14.000000 |	1.450000 | 39.000000 | 1.000000 | 1.000000 | 1.000000	| 0.000000 | 0.000000
25%	| 19.915937	| 1.630178 | 66.000000 | 2.000000 | 2.697467 | 1.590922 | 0.124505 | 0.000000
50%	| 22.847618 |	1.701584 | 83.101100 | 2.396265 |	3.000000 | 2.000000 |	1.000000 | 0.630866
75%	| 26.000000 | 1.769491 | 108.015907 | 3.000000 | 3.000000 | 2.466193 | 1.678102 | 1.000000
max	| 61.000000	| 1.980000 | 173.000000 | 3.000000 | 4.000000 | 3.000000 | 3.000000 | 2.000000

Dari deskripsi data statistik di atas, disimpulkan bahwa responden memiliki rentang usia 14-61 tahun dengan tinggi rentang 1.45-1.98 meter dan berat rentang 39-173 kilogram. Selanjutnya, akan diperiksa apakah terdapat outlier pada data tersebut.

<img src = "gambar/Boxplot.png" style = "zoom : 75%;" /> <br>

Interpretasi:
1. Pada kolom `Age`, dapat dilihat bahwa mayoritas responden berusia di rentang 20-30 tahun. Terdapat beberapa outlier, yaitu usia 50 tahun ke atas. Meski demikian, outlier ini tidak akan dihapus karena sangat memungkinkan seseorang berusia 50 tahun ke atas.
2. Pada kolom `Weight`, dapat dilihat bahwa mayoritas responden memiliki berat badan di rentang 60-110 kilogram. Terdapat 1 outlier, yaitu responden dengan berat badan 173 kilogram. Meski demikian, outlier ini tidak akan dihapus karena sangat memungkinkan seseorang memiliki berat badan 173 kilogram.
3. Pada kolom `Height`, dapat dilihat bahwa mayoritas responden memiliki tinggi badan di rentang 1.6-1.8 meter. Terdapat 1 outlier, yaitu responden dengan tinggi badan 1.98 meter. Meski demikian, outlier ini tidak akan dihapus karena sangat memungkinkan seseorang memiliki tinggi badan 1.98 meter.
4. Pada kolom-kolom lainnya, dapat dilihat bahwa persebaran data merata dan tidak terdapat outlier yang signifikan.

Untuk proses analisis ini, outlier tidak akan dibuang karena sangat memungkinkan responden termasuk dalam outlier tersebut. Data sudah siap untuk diproses dan dianalisis.

### Univariate Analysis

Dari variabel-variabel yang diketahui, variabel dapat dibagi menjadi 2 jenis, yaitu variabel numerikal dan variabel kategorikal. Berikut merupakan kolom-kolom yang termasuk dalam variabel numerikal maupun kategorikal. <br>
Kolom-kolom numerikal: ['Age', 'Height', 'Weight', 'FCVC', 'NCP', 'CH2O', 'FAF', 'TUE'] <br>
Kolom-kolom kategorikal: ['Gender', 'family_history_with_overweight', 'FAVC', 'CAEC', 'SMOKE', 'SCC', 'CALC', 'MTRANS', 'NObeyesdad']

Pertama, kita akan memvisualisasikan kolom-kolom kategorikal untuk melihat jumlah-jumlah nilai kategorikal menggunakan bar plot.

<img src = "gambar/Analisis_Kategorikal.png" style = "zoom : 75%;" /> <br>

Interpretasi:
1. Dari `Plot Jumlah dari Riwayat Obesitas Dalam Keluarga`, mayoritas responden memiliki riwayat obesitas dalam keluarganya.
2. Dari `Plot Jumlah dari Frekuensi Konsumsi Makanan Berkalori Tinggi`, mayoritas responden memakan makanan berkalori tinggi.
3. Dari `Plot Jumlah dari Konsumsi Makanan Di Antara Makan Berat`, mayoritas responden memakan makanan seperti cemilan atau snacks di antara makan berat.
4. Dari `Plot Jumlah dari Perokok atau Bukan`, mayoritas responden bukan perokok.
5. Dari `Plot Jumlah dari Memantau Asupan Kalori`, mayoritas responden tidak memantau asupan kalori mereka masing-masing.
6. Dari `Plot Jumlah dari Mengonsumsi Alkohol`, sebagian besar responden terkadang minum alkohol dan sebagian kecil responden tidak meminum alkohol.
7. Dari `Plot Jumlah dari Jenis Transportasi yang Digunakan`, mayoritas responden menggunakan transportasi umum sebagai sarana transportasi mereka
8. Dari `Plot Jumlah dari Tingkat Berat Badan`, persebaran tingkat level berat badan cukup merata, dengan Obesitas tingkat 1 merupakan jumlah yang paling banyak dialami responden.

Karena fokus pada analisis adalah mendeteksi penyakit obesitas, maka kita akan melihat lebih detail mengenai `Jumlah dari Tingkat Berat Badan`. Kita akan mencari distribusi persentase tingkat berat badan menggunakan pie chart.

<img src = "gambar/Pie_Chart_Tingkat_Berat_Badan.png" style = "zoom : 75%;" /> <br>

Dari gambar di atas, total responden yang mengalami berat badan berlebih maupun obesitas berjumlah $73.7\%$, dengan $46.5\%$ di antaranya mengalami obesitas.

Selanjutnya, kita akan memvisualisasikan kolom-kolom numerikal untuk melihat persebaran nilai menggunakan histogram.

<img src = "gambar/Analisis_Numerikal.png" style = "zoom : 75%;" /> <br>

Interpretasi:
1. Plot Histogram dari `Konsumsi Air Harian`, `Frekuensi Aktivitas Fisik`, `Lama Pemakaian Gadget` tidak berdistribusi normal.
2. Plot Histogram dari `Tinggi Badan`, `Frekuensi Konsumsi Sayur-Sayuran`, `Frekuensi Konsumsi Makanan Berat` cukup berdistribusi normal.
3. Plot Histogram dari `Usia` dan `Berat Badan` memiliki distribusi data yang miring ke kanan. Artinya, mayoritas data memiliki nilai di bawah rata-rata.

### Multivariate Analysis

#### 1. Membandingkan Tingkat Berat Badan Pada Setiap Jenis Kelamin

<img src = "gambar/Barplot_1.png" style = "zoom : 50%;" /> <br>

Interpretasi:
1. Laki-laki lebih banyak memiliki berat badan berlebih tingkat 2 dan obesitas tingkat 1 dibandingkan perempuan.
2. Hampir seluruh obesitas tingkat 2 dialami oleh laki-laki, sedangkan hampir seluruh obesitas tingkat 3 dialami oleh perempuan.



## Referensi
1. WHO. (2024). Diakses pada 6 Juli 2024 dari https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight
2. Kułak, Klaudia Brygida, Izabela Magdalena Sztybór & Katarzyna Kamińska. "OBESITY - AN EPIDEMIC OF THE 21ST CENTURY – LITERATURE REVIEW", 2024, p. 1-10. Journal of Education, Health and Sport, diakses pada 7 Juli 2024.
3. Dicoding. Diakses pada 6 Juli 2024 dari https://www.dicoding.com/academies/319-machine-learning-terapan
4. Tim Promkes RSST - RSUP dr. Soeradji Tirtonegoro Klaten. (2022). Diakses pada 6 Juli 2024 dari https://yankes.kemkes.go.id/view_artikel/429/obesitas
5. Tandiono, Steven Marcelino & Samuel Ady SanjayaWise. "Machine Learning Approach of ObesityLevel Classification: A Systematic Literature Reviewof Methods and Factors", vol. 8, no. 1, 2023, p. 196-208. G-Tech : Jurnal Teknologi Terapan, diakses pada 7 Juli 2024.

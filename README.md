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

## Referensi
1. WHO. (2024). Diakses pada 6 Juli 2024 dari https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight
2. Kułak, Klaudia Brygida, Izabela Magdalena Sztybór & Katarzyna Kamińska. "OBESITY - AN EPIDEMIC OF THE 21ST CENTURY – LITERATURE REVIEW", 2024, p. 1-10. Journal of Education, Health and Sport, diakses pada 7 Juli 2024.
3. Dicoding. Diakses pada 6 Juli 2024 dari https://www.dicoding.com/academies/319-machine-learning-terapan
4. Tim Promkes RSST - RSUP dr. Soeradji Tirtonegoro Klaten. (2022). Diakses pada 6 Juli 2024 dari https://yankes.kemkes.go.id/view_artikel/429/obesitas
5. Tandiono, Steven Marcelino & Samuel Ady SanjayaWise. "Machine Learning Approach of ObesityLevel Classification: A Systematic Literature Reviewof Methods and Factors", vol. 8, no. 1, 2023, p. 196-208. G-Tech : Jurnal Teknologi Terapan, diakses pada 7 Juli 2024.

# Laporan Proyek Machine Learning - Prediksi Biaya Asuransi Kesehatan

## Domain Proyek
Regresision on Medical cost” mengacu pada penggunaan teknik regresi untuk menganalisis dan memprediksi biaya medis seseorang bersarkan berbagai factor yang relevan.Dalam Proyek ini,peneliti akan mengumpulkan data biaya medis dari sejumlah pasien serat infomasi tambahan tentang karaktersitik individu tersebut,seperti usia,jenis kelamin dan indek massa benda dan juga kebiasaan uang lainnya .

## Business Understanding
Dengan adanya metode regresi dalam proyek ini akan mencoba mengidentifikasi hubungan antara variabel independen(seperti usia,jenis kelamin,body mass index dan masih banyak lagi .dengan variabel independen(biaya medis),maka proyek ini akan memberikan wawasan yang berharag dalam mengelola resiko keuangan dan perencanaan anggaran bagi perusahaan asuransi atau penyedia layanan kesehatan

## Problem Statement
- Melakukan deskriptif statistik pada data (melihat rata-rata, median, dan nilai lainnya)
- Berdasarkan eksplorasi dataset, fitur apa saja yang mempengaruhi dalam menentukan biaya medis seseorang
- Berdasarkan pengecekkan apakah terdapat Missing data,duplicate data,dan eror data?
- Bagaimana cara Memvisualisasikan data untuk melihat pola data

## Goals
- Mengeksplorasi semua fitur yang tersedia pada dataset kemudian membuat melihat korelasi harga dari semua fitur yang sedia untuk melihat faktor apa saja yang paling berpengaruh sampai paling kurang berpengaruh
- Melakukan proses data wragling dan data preparation terhadap dataset agar dapat dibuat model predksi biaya asuransi

## Solution Statement
- untuk melakukan deskriptif statistic pada data kita dapat melakukan dua cara dengan melakukan secara manual yaitu melihat rata rata pada data,median pada data dan mencari nilai yang lainnya pada data,sedangkan cara praktis kita bisa melakukan di excel dengan cara kita memblok semua data yang tercantum kemudian kita bisa mencari rata rata dari average dan sebagainya
- Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksploasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan antar fitur.
- Data itu bisa dikatakan missing data, duplicate data dan eror pada data dengan melakukan menotalkan seluruh data kemudian kita membagikan dengan keseluruhan data melalui software excel
- Dalam melakukan visualisasi ini kita dapat melakukan pemograman baik di python kemudian pada pemograman kita memberikan perintah Visualization pada pemograman dan menginput  data yang ingin kita visualisasikan sehingga menghasilkan suatu plotan yang dimana plotan itu disebut visualisasi dari datanya
  
## Data Understanding
Data dapat diambil dari kaggle dengan nama Linear Regession On Medical Cost Personal Datasets

URL : https://www.kaggle.com/code/diannitaekaputri/regression-on-medical-cost/input

Berikut merupakan detail dari dataset yang digunakan untuk pembuatan model:
- Dataset berupa CSV
- Dataset terdiri dari 1338 rows dengan 7 buah fitur yang diukur.
- Dataset terdiri dari 3 data kategori dan 4 data numerik.
- Dataset memiliki Region  dengan southeast sebesar 51% dan northwest 49%

### Variabel-variabel pada dataset adalah sebagai berikut:
- Age (Usia) : Usia Pemenrima Manfaat Utama
- Sex (Jenis Kelamin) : Jenis kelamin kontraktor asuransi,permpuan dan laki-laki
- Bmi : Indeks massa tubuh,memberikan pemahaman tentang tubuh,berat badan yang relative tinggi atau rendah dibandingkan tinggi badan,indeks objektif berat badan(kg/m^2) menggunakan rasio tinggi badan terhadap berat badan,idealnya 18,5 hingga 24,9
- Child(Anak-anak) : Jumlah anak yang ditanggung oleh asuransi kesehatan/jumlah tanggungan
- Smoker (Perokok) : Merokok
- Region (Wilayah) : wilayah pemukiman penerima manfaat di AS,northeast,southeast,southwest,nortwest
- Charges ( Biaya) : Biaya pengobatan individu yang ditagih oleh asuransi kesehatan

Untuk memahami data lebih lanjut, dilakukan  deskriptif statistik, Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

![Screenshot 2024-03-27 015440](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/8bc2286f-44e1-4665-b778-3d64cfa07830)

Gambar 1a. Deskriptif statistik

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel. Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu dataset. Sedangkan, Analisis Multivariat tmerupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data.
Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam dataset. Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam dataset, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam dataset dalam bentuk matriks.
Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Multivariat.

![Screenshot 2024-03-26 214152](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/7fc36d00-9854-4e40-badc-04935f0f40d7)

Gambar 1b. Analisis Univariat (Data Kategori)

![Screenshot 2024-03-25 201624](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/fae9f277-3227-40e2-bc71-060a4f5369f5)

Gambar 1c. Analisis Univariat (Data Numerik)

Berdasarkan gambar 1b Analisis Univariat(Data Kategori) dengan melihat grafik tersebut,kita dapat melihat bagaimana data terbagi antara berbagai region yang mungkin diwakili oleh kategorik tertentu pada dan juga bahwa grafik 1b memiliki perbandingan jumlah yang tidak sama,untuk nilai data southeast memiliki 365 sekian lebih tinggi dari region yang lainnya sedangkan peringkat yang terendah jatuh di northeast sebanyak 320 sekian,sedangkan northwest dan southwest memiliiki jumlah yang hampir beda tipis dengan northeast.Pada Gambar 1c untuk data numeric memiliki karakteristik,yaitu : 
- Koordinat age  berada pada Matriks 18, 22,5 derajat dan 63, 67.5.koordinat inilah yang distribusinya memiliki penurunan yang sangat drastic
- Koordinat pada bmi sangat tidak stabil yang dimana titik awal koordinat berada di matrik 15.96, 17.86 kemudian menglami kenaikkan,kemudian di matriks 29.26, 31.16 mengalami kenaikkan yang drastic sehingga mencapai titik 170,tetapi setalah mengalami kenaikkan kemudian mengalami penurunan pada matriks 31.16, 33.06 sampai di matrik 46.36, 48.26 mengalami penurunan sampai menyentuh10 kebawah
- Koordinat pada children ini merupakan koordinat yang sangat tinggi hongga mencapai  550 di matriks 0, 0.38 tetapi dari koordinat ini mengalami penurunan lagi di matriks 0.38, 0.76 sampai di matriks 2.66, 3.04 tetap mengalami penurunan sehingga menyentuh 0
- Koordinat Charges  memiliki koordinat yang mencapai 350 dengan matriks 1121.8739.. pada saat matriks inilah mengalami peningkatan yang sangat drastic cuman di koordniat ini juga mengalami penurunan yang tidak stabil di matriks lainnya

![Screenshot 2024-03-31 020558](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/f9b43c63-757b-446c-87d2-35244d60e20d) ![Screenshot 2024-03-31 020850](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/bc5bf6f5-9fa1-47fc-9e61-5db5d167cfda)


Gambar 2a. Analisis Multivariat (Data Kategori)

![Screenshot 2024-03-25 203125](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/340108db-634b-43bf-92ec-8db2ba344e99)

Gambar 2b. Analisis Multivariat (Data Numerik)

![Screenshot 2024-03-26 114713](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/c002d1f3-43ca-437b-9f65-af581550ebbb)

Gambar 2c. Analisis Multivariat (Correlation Matrix)

Pada Gambar 2b tampak persebaran data ‘Scatter plot age,bmi dan children’.dengan mengamati rata rata ketiga ini terhadap fitur kategori diatas,diperoleh insight sebagai berikut:
- Pada fitur’Age’,rata rata cenderung bervariasi yang dimana memiliki rentang dari 0 hingga 60.000 tetapi pada rentang ini memiliki jumlah yang sangat tinggi daripada plot yang lainnya.
- Nilai bmi dan children merupakan plotan yang beda tipis jaraknya dan pada plotan kedua ini merupakan salah satu yang rendah dibandingan di age
- Kesimpulan akhir,fitur kategori ahwa kedua variabel dengan menampilkan titik pada data bidang kartesian maka hubungan antara usia dan variabel lainnya dapat,pola umumnya dari sebaran titik data,kita dapat melakukan outlier dan korelasi dengan adanya grafik diatas.

Pada Gambar 2c. dengan menggunakan fungsi pairplot dari library seaborn,tampak terlihat bahwa relasi pasangan dalam dataset.pada pila sebaran data grafik paiplot,terlihat bahwa children memiliki korelasi dengan fitur terseut,sedangkan kedua fitur lainnya memperlihat korelasi yang rendah karena adanya penyebaran tidak membentuk pola

## Data Preparation
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning. Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas. Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:

- Duplicate data (data yang serupa dengan data lainnya)
- Missing value (data atau informasi yang "hilang" atau tidak tersedia)
- Outlier (data yang menyimpang dari rata-rata sekumpulan data yang ada)

Pada kasus proyek ini tidak ditemukan data duplikat. Pada proyek ini tidak ditemukan Missing Value

    print("Total missing values:", data.isna().sum().sum())

  Total missing values: 0

## Modeling
Seperti yang dijelaskan di awal, model yang dipilih adalah model regresi karena merupakan salah satu algoritma yang paling umum digunakan dalam pembuatan model prediksi. Dalam bentuk yang sederhana, regresi terdiri dari intersep dan slope yang dituliskan dalam rumusan berikut

    Y = a + bX
dimana:

- y adalah variabel kriterium (variabel terikat yang digunakan untuk memprediksi)
- a adalah intersep (variabel konstan yang memiliki arti sebagai titik perpotongan suatu garis dengan sumbu Y),
- b adalah slope (nilai koefisien yang menyatakan ukuran kemiringan suatu garis), dan
- X adalah variabel prediktor (variabel yang digunakan untuk memprediksi atau menjelaskan variabel lain dalam suatu model)

Secara umum, regresi ini itu sendiri digunakan untuk meramalkan pengaruh variabel prediktor terhadap variabel kriterium atau membuktikan ada atau tidaknya hubungan fungsional antara variabel bebas (X) dengan variabel terikat (y).

Namun begitu terdapat kelebihan dan kekurangan dari model regresi, yaitu:

Kelebihan regresi:

- Kemudahan untuk digunakan
- Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
- Dapat memprediksi nilai/tren di masa yang mendatang

Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada.

## Evaluation
- ![Screenshot_2024-04-02_112953-removebg-preview](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/c21f457d-e67c-41b0-8d7a-774fb2b69ff8)
- ![Screenshot_2024-04-02_100533-removebg-preview](https://github.com/BaskaraGunarso/jupyter-notebook/assets/162326053/fda1220d-0315-4f46-87be-260f9152e864)

Berikut merupakan penjelasan kegunaan dari masing-masing metrik yang digunakan:

- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.
- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.
- R2 digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen

       # prediction on training data
      training_data_prediction =regressor.predict(X_train)

      # R squared value
      r2_train = metrics.r2_score(Y_train, training_data_prediction)
      print('R squared vale : ', r2_train)
    R squared vale :  0.751505643411174

      # prediction on test data
      test_data_prediction =regressor.predict(X_test)

      # R squared value
      r2_test = metrics.r2_score(Y_test, test_data_prediction)
      print('R squared vale : ', r2_test)
  R squared vale :  0.7447273869684077
  
## Referensi
- [1] 	D. D. M. B. P. R. M. M. S. P. P. Mukund Kulkarni, "Medical Insurance Cost Prediction using Machine Learning," Ijraset Journal For Research in Applied Science and Engineering Technology, 2022. 
- [2] 	A. Tike, "A MEDICAL PRICE PREDICTION SYSTEM," Master's Project, 2018. 
- [3] 	T. W. B. H. Y. L. L. T. Lin Sun, "Explainable and Personalized Medical Cost Prediction Based on Multitask Learning over Mobile Devices," 2022. 
- [4] 	R. M. A. E.-A. H. M. A. A.-A. H. E.-B. Ahmed I. Taloba, "Estimation and Prediction of Hospitalization and Medical Care Costs Using Regression in Machine Learning," J Healthc Eng., 2022. 
- [5] 	U. O. a. E. Ukwandu, "Machine Learning For An Explainable Cost Prediction of Medical Insurance," Department of Computer Science, pp. 19-20, 2022. 


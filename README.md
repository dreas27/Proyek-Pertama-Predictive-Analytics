# Laporan Proyek Machine Learning - Prediksi Harga Rumah

## Domain Proyek

Harga merupakan faktor utama dalam pengambilan keputusan dalam aktivitas jual beli [[1](https://ejournal.undiksha.ac.id/index.php/JJPE/article/view/20041/12010)]. Kemampuan memprediksi harga dapat membantu pembeli sebagai bahan pertimbangan sebelum melakukan transaksi jual beli. 

Dalam hal jual beli rumah harga sangat bergantung pada beberapa faktor, seperti lokasi geografis, demografi, jumlah ruangan, dan lainnya [[2](https://journal.stiebpbatam.ac.id/tractare/article/download/66/38)]. Oleh karena itu, dengan mempertimbangkan faktor-faktor tersebut kita bisa mengestimasi harga dari suatu rumah dengan beberapa kondisi yang dimilikinya. 

Dalam membuat model regresi ada banyak cara algoritma yang bisa dipilih. Salah satu algoritma yang paling populer dan sederhana adalah regresi [[3](https://www.neliti.com/id/publications/130812/estimasi-model-regresi-linier-dengan-metode-median-kuadrat-terkecil)]. Dengan menggunakan regresi dan memasukkan faktor-faktor dari rumah yang dituju diharapkan kita bisa memprediksi harga rumah yang dimaksud.
  
## Referensi:
[1] [ANALISIS FAKTOR-FAKTOR YANG MEMPENGARUHI TINGKAT HARGA PERUMAHAN DI KABUPATEN BULELENG](https://ejournal.undiksha.ac.id/index.php/JJPE/article/view/20041/12010) 

[2] [ANALISIS FAKTOR-FAKTOR YANG MEMPENGARUHI HARGA RUMAH DI KOTA BATAM](https://journal.stiebpbatam.ac.id/tractare/article/download/66/38) 

[3] [Estimasi Model Regresi Linier Dengan Metode Median Kuadrat Terkecil](https://www.neliti.com/id/publications/130812/estimasi-model-regresi-linier-dengan-metode-median-kuadrat-terkecil) 

## Business Understanding

### Problem Statements
- Berdasarkan eksplorasi dataset, fitur apa saja yang mempengaruhi dalam menentukan estimasi harga rumah?
- Bagaimana mengolah dataset agar dapat dibuat model prediksi harga rumah?
- Bagaimanna cara meningkatkan nilai perfoma model prediksi harga rumah?

### Goals
- Mengeksplorasi semua fitur yang tersedia pada dataset kemudian membuat melihat korelasi harga dari semua fitur yang sedia untuk melihat faktor apa saja yang paling berpengaruh sampai paling kurang berpengaruh terhadap harga rumah
- Melakukan proses data wragling dan data preparation terhadap dataset agar dapat dibuat model predksi harga rumah
- Melakukan beberapa variasi model untuk mendapatkan model yang paling baik dari beberapa model yang telah dibuat untuk prediksi harga rumah


### Solution statements
- Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksploasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan antar fitur. Teknik yang digunakan adalah menggunakan catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari fitur-fitur yang dimiliki.
- Agar didapatkan model prediksi yang baik maka dilakukan proses Data Wragling yang meliputi Data Gathering, Data Assessing, dan Data Cleaning.
- Untuk mengetahui perfoma model dilakukan pengecekan performa dengan metrik evaluasi.

## Data Understanding
Data yang digunakan dalam pembuatan model merupakan data sekunder. Data diambil dari Kaggle. 

URL: https://www.kaggle.com/datasets/shibumohapatra/house-price

### Variabel-variabel pada dataset adalah sebagai berikut:
- longitude : posisi bujur
- latitude : posisi lintang
- housing_median_age : usia rata-rata rumah
- total_rooms : jumlah kamar
- total_bedrooms : jumlah kamar tidur
- population : populasi
- households : jumlah rumah tangga
- median_income : median pendapatan
- ocean_proximity : kedekatan terhadap laut
- median_house_value : median harga rumah

Untuk memahami data lebih lanjut, dilakukan teknik visualisasi data seperti menggunakan catplot, pairplot, dan heatmap. Serta dilakukan juga exploratory data analysis.

## Data Preparation
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning.
Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas.
Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:
- Invalid value
- Inaccurate value
- Inconsistent value
- Missing value
- Duplicate data
- Outlier
 
Pada proses Data Cleaning, secara garis besar, terdapat tiga metode yang dapat digunakan antara lain seperti berikut:
- Dropping
- Imputation
- Interpolation
 
Semua proses ini diperlukan dalam rangka membuat model yang baik.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.
Model yaang digunakan pada proyek ini adalah model regresi. Pada proyek dikerjakan, algoritma regresi yang coba dibandingkan adalah regresi linear, regresi ridge, random forest regressor, dan random forest regressor dengan hyperparamter tuning. Adapun paramater yang dituning antara lain n_estimators', 'max_depth', 'min_samples_split', dan 'min_samples_leaf. Untuk memudahkan proses tuning digunakan GridSearchCV.

Kelebihan regresi:
- Kemudahan untuk digunakan
- Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
- Dapat memprediksi tren di masa yang mendatang

Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada.

## Evaluation
Andapun metrik yang sebagai alat ukur perfoma model yang dibuat antara lain **MSE · MAE · R2**. Jelaskan mengenai beberapa hal berikut:
- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.
- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.
- R2 digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen

**---Ini adalah bagian akhir laporan---**

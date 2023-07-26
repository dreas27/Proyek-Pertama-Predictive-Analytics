# Laporan Proyek Machine Learning - Prediksi Harga Rumah

## Domain Proyek

Harga rumah merupakan faktor utama dalam pengambilan keputusan dalam aktivitas jual beli rumah [[1](https://www.researchgate.net/publication/353333759_Factors_Influencing_Housing_Purchase_Decision)] [[2](https://www.researchgate.net/publication/285661484_Housing_Market_A_Review_of_Purchase_Decision_of_Potential_Buyers)] [[3](https://www.researchgate.net/publication/354085963_Analysis_of_County_Consumers%27_Housing_Purchase_Intention_and_Influencing_Factors--Based_on_the_Investigation_of_Anyue_County)]. Kemampuan memprediksi harga rumah tentunya membantu pembeli sebelum melakukan transaksi jual beli rumah. 

Dalam hal jual beli rumah harga sangat bergantung pada beberapa faktor, seperti lokasi geografis, demografi, jumlah ruangan, dan lainnya. Salah satu faktor yang menarik untuk ditelusuri lebih lanjut adalah faktor view dari rumah [[4](https://www.sciencedirect.com/science/article/pii/S0264275118312241)] [[5](https://www.researchgate.net/publication/333880192_The_price_of_a_view_Estimating_the_impact_of_view_on_house_prices)]. Oleh karena itu, dengan mempertimbangkan faktor-faktor tersebut, yang juga tersedia pada dataset, maka dapat diestimasi harga dari rumah tersebut dan melihat seberapa besar korelasi pengaruh faktor-faktor tersebut.

Dalam membuat model regresi ada banyak cara algoritma yang bisa dipilih. Salah satu algoritma yang paling umum digunakan adalah regresi. Dengan menggunakan regresi dan memasukkan faktor-faktor dari rumah yang dituju diharapkan dapat memprediksi harga rumah yang dimaksud [[6](https://www.researchgate.net/publication/360473275_HOUSE_PRICE_PREDICTION_USING_LINEAR_REGRESSION_IN_ML)] [[7](https://www.researchgate.net/publication/364039805_Prediction_and_Analysis_of_Housing_Price_Based_on_the_Generalized_Linear_Regression_Model)] [[8](https://www.researchgate.net/publication/23534659_Determinants_of_House_Prices_A_Quantile_Regression_Approach)].
  
## Referensi:
[1] Hassan, Mohammad Mujaheed & Ahmad, Nobaya & Hariza, Ahmad & Hashim, Ahmad. (2021). Factors Influencing Housing Purchase Decision. 11. 429-443. 10.6007/IJARBSS/v11-i7/10295.

[2] Ariyawansa, Ranthilaka. (2009). Housing Market: A Review of Purchase Decision of Potential Buyers.

[3] Jiang, Jiaxin & Zhang, Jin. (2021). Analysis of County Consumers’ Housing Purchase Intention and Influencing Factors. 

[4] Heymann, Sommervoll. (2019). House prices and relative location

[5] Jayasekare, Ajith & Herath, Shanaka & Wickramasuriya, Rohan & Perez, Pascal. (2019). The price of a view: Estimating the impact of view on house prices. Pacific Rim Property Research Journal. 25. 1-18. 10.1080/14445921.2019.1626543. 

[6] Agarwal, Umang & Gupta, Smriti & Goyal, Madhav. (2022). House Price Prediction using Linear Regression. 10.13140/RG.2.2.11175.62887. 

[7] Li, Xinshu. (2022). Prediction and Analysis of Housing Price Based on the Generalized Linear Regression Model. Computational Intelligence and Neuroscience. 2022. 1-9. 10.1155/2022/3590224. 

[8] Zietz, Joachim & Zietz, Emily & Sirmans, G.. (2008). Determinants of House Prices: A Quantile Regression Approach. The Journal of Real Estate Finance and Economics. 37. 317-333. 10.1007/s11146-007-9053-7. 

## Business Understanding

Pengembangan model prediksi harga rumah memiliki potensi dampak atau manfaat berupa menjadi salah satu alat bantu dalam pengambilan keputusan oleh calon pembeli rumah.
Contoh potensi manfaat dari hasil prediksi harga rumah yang akurat adalag membantu pembeli dan penjual membuat keputusan jual ataupu beli yang lebih bijaksana.

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
Data yang digunakan dalam pembuatan model merupakan data sekunder. Data diambil dari Kaggle dengan nama dataset yaitu California House Price. 

URL: https://www.kaggle.com/datasets/shibumohapatra/house-price

Berikut merupakan detail dari dataset yang digunakan untuk pembuatan model:
- Dataset berupa CSV
- Dataset terdiri dari 20640 records dengan 10 buah fitur yang diukur.
- Dataset terdiri dari 1 data kategori dan 9 data numerik.
- Dataset memiliki missing value sejumlah 205 records

### Variabel-variabel pada dataset adalah sebagai berikut:
- longitude : koordinat geografis yang digunakan untuk menunjukkan posisi suatu titik dari arah utara ke selatan yang digunakan menentukan posisi suatu titik pada permukaan bumi (diukur dalam satuan derajat)
- latitude : koordinat geografis yang digunakan untuk menunjukkan posisi suatu titik dari arah timur ke barat yang digunakan menentukan posisi suatu titik pada permukaan bumi (diukur dalam satuan derajat)
- housing_median_age : usia rata-rata sebuah rumah dalam satu blok. angka yang lebih rendah menunjukkan bangunan yang lebih baru (dalam satuan tahun)
- total_rooms : Jumlah total kamar dalam satu blok (dalam satuan buah)
- total_bedrooms : jumlah total kamar tidur dalam satu blok (dalam satuan buah)
- population : jumlah total orang yang tinggal dalam satu blok (dalam satuan orang)
- households : jumlah total rumah tangga, sekelompok orang yang tinggal di dalam satu unit rumah, untuk satu blok (dalam satuan orang)
- median_income : pmedian endapatan untuk rumah tangga dalam satu blok rumah (diukur dalam Dolar AS)
- ocean_proximity : posisi relatif lokasi rumah terhadap lautan/laut (berupa kategori 'NEAR BAY', '<1H OCEAN', 'INLAND', 'NEAR OCEAN', 'ISLAND')
- median_house_value : median harga rumah untuk rumah tangga dalam satu blok (diukur dalam Dolar AS)

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel.  Jenis visualisasi ini umumnya digunakan untuk memberikan kita gambaran terkait distribusi sebuah variabel dalam suatu dataset. Sedangkan, Analisis Multivariat tmerupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data. 

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam dataset. 
Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam dataset, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam dataset dalam bentuk matriks.

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

Pada kasus proyek ini ditemukan Missing Value. Adapaun metode yang digunakan untuk mengatasi hal ini adalah dengan menerapkan imputation dimana data yang missing diganti dengan nilai mean. Untuk outlier sendiri dilakukan proses dropping menggunakan metode IQR. IQR sendiri didapatkan dengan cara mengurangi Q3 dengan Q1 sebagaimana rumusan berikut. 

$$ IQR = Q<sub>3</sub> - Q<sub>1</sub> $$

dimana
Q<sub>1</sub> adalah kuartil pertama dan Q<sub>3</sub> adalah kuartil ketiga.

Dengan menggunakan metode IQR, kita bisa menentukan outlier melalui suatu nilai batas yang ditentukan. Setelah menggunakan metode IQR dimana dataset yang sebelumnya berjumlah 20640 menjadi 17609.
 
Semua proses ini diperlukan dalam rangka membuat model yang baik. Gambar 1a & 1b berikut merupakan perbandingan data sebelum dan setelah melalui proses Data Cleaning.
![Screenshot 2023-07-27 013748](https://github.com/ahmadsuaif/Proyek-Pertama-Predictive-Analytics/assets/66425290/89132f98-8fe3-4dda-912f-d289b6b4450f)
Gambar 1a. Sebelum Data Cleaning 

![Screenshot 2023-07-27 013748](https://github.com/ahmadsuaif/Proyek-Pertama-Predictive-Analytics/assets/66425290/9c4fd4c3-829d-4eef-ba73-36c3c55dfc19)
Gambar 1b. Setelah Data Cleaning 

Setelah melalui proses Data Cleaning, dataset dibagi menjadi data train dan data test untuk proses Modeling, dimana rasio pembagian data yang dipilih adalah 90:10 mengingat data test untuk rasio tersebut sudah terbilang cukup. 
Adapun detail dari dataset tersebut adalah:
- Total sampel di dalam dataset train: 15848
- Total sampel di dalam dataset test: 1761

## Modeling
Seperti yang dijelaskan di awal, model yang dipilih adalah model regresi karena merupakan salah satu algoritma yang paling umum digunakan dalam pembuatan model prediksi. Namun begitu terdapat kelebihan dan kekurangan dari model regresi, yaitu:
Kelebihan regresi:
- Kemudahan untuk digunakan
- Kekuatan Prediktor dalam mengidentifikasi sekuat apa pengaruh yang diberikan oleh variabel prediktor (variabel independen) terhadap variabel lainnya (variabel dependen).
- Dapat memprediksi nilai/tren di masa yang mendatang
Kelemahan dari model regresi adalah karena hasil ramalan dari analisis regresi merupakan nilai estimasi sehingga kemungkinan untuk tidak sesuai dengan data aktual tetaplah ada.

Pada proyek yang dikerjakan, algoritma regresi yang coba dibandingkan adalah regresi linear, regresi ridge, random forest regressor, dan random forest regressor dengan hyperparamter tuning. Regresi linear adalah teknik analisis data yang memprediksi nilai data yang tidak diketahui dengan menggunakan nilai data lain yang terkait dan diketahui dimana secara matematis dimodelkan sebagai persamaan linier, regresi ridge merupakan metode estimasi koefisien regresi yang diperoleh melalui penambahan konstanta bias c, dan random forest adalah suatu algoritma yang digunakan pada klasifikasi data dalam jumlah yang besar dimana teknik klasifikasi random forest dilakukan melalui penggabungan pohon dengan melakukan training pada sampel data yang dimiliki.

Untuk meningkatkan model, dilakukan hyperparamter tuning. Adapun paramater yang dituning antara lain n_estimators', 'max_depth', 'min_samples_split', dan 'min_samples_leaf. Untuk memudahkan proses tuning digunakan GridSearchCV. GridSearchCV itu sendiri merupakan bagian dari modul scikit-learn yang dapat digunakan untuk mendapatkan nilai hyperparameter secara otomatis. Grid Search adalah metode yang digunakan untuk mencari parameter yang paling tepat untuk meningkatkan performa model dengan mencoba seluruh kombinasi hyperparameter yang diberikan.

## Evaluation
Andapun metrik yang sebagai alat ukur perfoma model yang dibuat antara lain **MSE · MAE · R2**. 

Berikut merupakan rumus dan penjelasan dari masing-masing metrik yang digunakan:

$$ MAE = (1/n) Σ |y<sub>i</sub> - ŷ<sub>i</sub>| $$

- MAE menghitung rata-rata dari selisih absolut antara nilai prediksi dan nilai aktual. Semakin kecil nilai MAE, semakin baik kualitas model tersebut.

$$ MSE = (1/n) Σ (y<sub>i</sub> - ŷ<sub>i</sub>)<sup>2</sup> $$

- MSE menghitung rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual. Semakin kecil nilai MSE, semakin baik kualitas model tersebut.

$$ R<sup>2</sup> = 1 - (MSE / Var(y)) $$

- R2 digunakan untuk menilai seberapa besar pengaruh variabel independen tertentu terhadap variabel dependen

Gambar 2 berikut merupakan hasil dari evaluasi model

![Screenshot 2023-07-27 015320](https://github.com/ahmadsuaif/Proyek-Pertama-Predictive-Analytics/assets/66425290/ebefda1e-c2ec-4c52-9b6a-3220fff2ae1a)

Gambar 2. Perbandingan Model


Berdasarkan hasil evaluasi, terlihat bahwa prediksi dengan Random Forest (RF), baik RF1 (tanpa tuning) ataupun RF2 (dengan tuning) memberikan hasil yang paling mendekati y_true, dimana nilai y_true yaitu 341700 dan nilai RF1 dan RF2 masing-masing yaitu 347466.0 dan 315645.2.

**---Ini adalah bagian akhir laporan---**

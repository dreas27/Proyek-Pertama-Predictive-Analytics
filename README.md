# Laporan Proyek Machine Learning - Prediksi Harga Rumah

## Domain Proyek

Harga rumah merupakan faktor utama dalam pengambilan keputusan dalam aktivitas jual beli rumah [[1](https://www.researchgate.net/publication/353333759_Factors_Influencing_Housing_Purchase_Decision)] [[2](https://www.researchgate.net/publication/285661484_Housing_Market_A_Review_of_Purchase_Decision_of_Potential_Buyers)] [[3](https://www.researchgate.net/publication/354085963_Analysis_of_County_Consumers%27_Housing_Purchase_Intention_and_Influencing_Factors--Based_on_the_Investigation_of_Anyue_County)]. Kemampuan memprediksi harga rumah tentunya membantu pembeli sebelum melakukan transaksi jual beli rumah. 

Dalam hal jual beli rumah harga sangat bergantung pada beberapa faktor, seperti lokasi geografis, demografi, jumlah ruangan, dan lainnya. Salah satu faktor yang menarik untuk ditelusuri lebih lanjut adalah faktor view dari rumah [[4](https://www.sciencedirect.com/science/article/pii/S0264275118312241)] [[5](https://www.researchgate.net/publication/333880192_The_price_of_a_view_Estimating_the_impact_of_view_on_house_prices)]. Oleh karena itu, dengan mempertimbangkan faktor-faktor tersebut, yang juga tersedia pada dataset, kita akan mengestimasi harga dari rumah tersebut dan melihat seberapa besar korelasi pengaruh faktor-faktor tersebut.

Dalam membuat model regresi ada banyak cara algoritma yang bisa dipilih. Salah satu algoritma yang paling umum digunakan adalah regresi. Dengan menggunakan regresi dan memasukkan faktor-faktor dari rumah yang dituju diharapkan kita bisa memprediksi harga rumah yang dimaksud [[6](https://www.researchgate.net/publication/360473275_HOUSE_PRICE_PREDICTION_USING_LINEAR_REGRESSION_IN_ML)] [[7](https://www.researchgate.net/publication/364039805_Prediction_and_Analysis_of_Housing_Price_Based_on_the_Generalized_Linear_Regression_Model)] [[8](https://www.researchgate.net/publication/23534659_Determinants_of_House_Prices_A_Quantile_Regression_Approach)].
  
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

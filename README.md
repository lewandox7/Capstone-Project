# Capstone-Project

Arsenal Gehan Podhanx Rifai  (23051130035)
Muhammad Evan Widiawan S (23051130053)
Farhan Dwifaza Rosyadi (23051130062)


Problem Statement
Problem Statement Penyedia layanan bike sharing saat ini menghadapi tantangan operasional yang signifikan dalam menjaga keseimbangan ketersediaan armada di tengah fluktuasi permintaan yang sangat dinamis. Masalah utama yang dihadapi adalah lonjakan permintaan ekstrem pada jam-jam spesifik, terutama saat jam berangkat dan pulang kerja, yang sering kali tidak terantisipasi dengan baik. Ketidakmampuan untuk memprediksi pola ini mengakibatkan ketidakefisienan logistik, di mana beberapa stasiun mengalami kekosongan stok (shortage) sehingga menyebabkan potensi kehilangan pelanggan, sementara stasiun lain mengalami penumpukan sepeda yang menghambat proses pengembalian. Tanpa adanya sistem prediksi yang akurat, tim operasional kesulitan melakukan pemindahan armada (rebalancing) secara tepat waktu dan efisien .

Goals
Tujuan utama dari proyek ini adalah mengembangkan model Machine Learning tipe regresi yang mampu memprediksi jumlah total penyewaan sepeda (cnt) per jam dengan tingkat akurasi yang dapat diandalkan. Fokus utamanya adalah menangkap pola permintaan pada jam sibuk serta mengidentifikasi faktor-faktor eksternal yang paling berpengaruh, seperti kondisi cuaca, suhu, dan waktu operasional. Dengan adanya model ini, diharapkan dapat memberikan wawasan strategis bagi tim manajemen untuk menerapkan strategi Smart Rebalancing—yaitu memindahkan sepeda ke lokasi strategis sebelum lonjakan terjadi—serta mengoptimalkan alokasi tenaga kerja dan jadwal pemeliharaan armada berdasarkan prediksi kondisi di lapangan.

Analytic Approach
Untuk menjawab permasalahan tersebut, pendekatan analisis dilakukan menggunakan metode Supervised Machine Learning dengan kategori Regresi, mengingat variabel target yang diprediksi berupa data kontinu (jumlah sepeda). Proses analisis dimulai dengan Feature Engineering untuk menciptakan fitur baru is_rush_hour guna menangkap perilaku komuter, serta penerapan transformasi Logaritma (np.log1p) pada variabel target untuk menormalkan distribusi data yang miring (skewed). Selanjutnya, dilakukan proses benchmarking dengan membandingkan lima algoritma berbeda—yaitu Linear Regression, KNN, Decision Tree, Random Forest, dan Gradient Boosting—untuk menentukan model terbaik yang paling mampu menangkap pola non-linear pada data permintaan sepeda .

Metric Evaluation
Evaluasi kinerja model dilakukan secara komprehensif menggunakan empat metrik utama. RMSE (Root Mean Squared Error) digunakan sebagai acuan utama untuk mengukur rata-rata kesalahan prediksi dengan memberikan penalti lebih besar pada error yang ekstrem, di mana model mencatatkan nilai RMSE sebesar 99.42. Selain itu, MAE (Mean Absolute Error) digunakan untuk memberikan gambaran kesalahan rata-rata dalam satuan unit sepeda yang lebih mudah dipahami operasional, dengan hasil sebesar 63.68. Metrik MAPE (Mean Absolute Percentage Error) digunakan untuk melihat proporsi kesalahan relatif, dan R-Squared digunakan untuk mengukur seberapa baik model menjelaskan variasi data, di mana model ini berhasil menjelaskan sekitar 68% pola permintaan pengguna .

Fitur Utama
1. Prediksi Jumlah Penyewaan Sepeda Per Jam
   Sistem mampu memprediksi berapa banyak sepeda yang akan disewa pada setiap jam berdasarkan pola historis dan kondisi eksternal.

2. Feature Engineering: Identifikasi Jam Sibuk (Rush Hour)
   Dibuat fitur baru `is_rush_hour` yang mendeteksi jam 07–09 dan 16–19 sebagai periode lonjakan permintaan di hari kerja.

3. Benchmarking Banyak Model Regresi
   Sistem membandingkan lima model Machine Learning: Linear Regression, KNN, Decision Tree, Random Forest, dan Gradient Boosting untuk menemukan performa terbaik.

4. Tuning Model untuk Akurasi Maksimal
   Gradient Boosting dioptimalkan menggunakan RandomizedSearchCV untuk mendapatkan parameter terbaik.

5. Evaluasi Kinerja Model Secara Komprehensif
   Model dievaluasi menggunakan RMSE, MAE, R², dan MAPE untuk memastikan kualitas prediksi.

6. Analisis Feature Importance
   Menunjukkan fitur apa yang paling memengaruhi permintaan sepeda, sehingga dapat diterjemahkan menjadi insight operasional.

7. Rekomendasi Bisnis Berdasarkan Model
   Model digunakan untuk menyusun strategi Smart Rebalancing, manajemen tenaga kerja berbasis cuaca, dan penjadwalan maintenance.


Dataset yang di gunakan
Dataset yang digunakan adalah Bike Sharing Dataset, yang berisi data penyewaan sepeda per jam dengan atribut lingkungan dan waktu.
Beberapa fitur utama dalam dataset:
1. dteday
   Tanggal pencatatan.
2. hr
   Jam (0–23) yang menunjukkan waktu penyewaan.
3. season
   Musim (1–4).
4. holiday
   Indikator apakah hari tersebut libur atau tidak.
5. weathersit
   Kondisi cuaca (baik, berawan, hujan ringan, hujan lebat).
6. temp
   Suhu dalam skala normalisasi.
7. atemp
   Suhu yang dirasakan.
8. hum
   Kelembapan.
9. casual
   Jumlah penyewa non-member.
10. registered
    Jumlah penyewa member.
11. cnt
    Total penyewaan sepeda (target yang diprediksi).

Dataset ini ideal digunakan untuk modeling permintaan karena memiliki kombinasi fitur temporal, cuaca, serta data target kontinu.


Hasil Utama
1. Model Terbaik
   Dari lima model regresi, Gradient Boosting Regressor menghasilkan performa terbaik dengan RMSE paling rendah.
   
3. Nilai Evaluasi Final
    MAE: 63.68
    RMSE: 99.42
    R²: 0.68
    MAPE: 59.05%

   Model mampu menjelaskan 68% variasi permintaan. Nilai MAPE tinggi disebabkan banyaknya titik data dengan nilai permintaan sangat kecil.

4. Fitur Paling Berpengaruh
    Jam (`hr`)
    Suhu (`temp`)
    Rush hour (`is_rush_hour`)
    Kondisi cuaca (`weathersit`)

5. Insight Penting
    Puncak permintaan terjadi pada jam 07–09 dan 16–19.
    Suhu hangat meningkatkan penyewaan sepeda, sementara cuaca buruk menurunkannya.
    Model cukup stabil dan layak digunakan untuk rekomendasi operasional.

6. Implikasi Praktis
   Model dapat digunakan untuk:
    memindahkan sepeda ke stasiun tertentu sebelum jam sibuk,
    mengatur jumlah staf lapangan sesuai kondisi cuaca,
    menjadwalkan maintenance pada waktu permintaan rendah.


File Output
>-----------------------------------------------------------<

Cara Menjalankan
1. Clone repository ini
2. Install dependencies yang diperlukan
3. Jalankan notebook capstone project_Kelompok 3.ipynb
4. pkl van

Teknologi yang Digunakan
1. Python
   Bahasa pemrograman utama yang digunakan untuk analisis data dan pengembangan model Machine Learning.
2. Jupyter Notebook / Google Colab
   Lingkungan interaktif untuk eksplorasi data, visualisasi, pemodelan, dan dokumentasi.
3. Pandas
   Untuk manipulasi data, pembersihan data, dan analisis tabular.
4. NumPy
   Untuk operasi numerik dan komputasi matematis.
5. Matplotlib & Seaborn
   Digunakan untuk pembuatan grafik, heatmap, scatter plot, dan visualisasi lain selama EDA dan analisis.
6. Scikit-Learn
   Library utama untuk:
    regresi,
    cross-validation,
    hyperparameter tuning,
    preprocessing,
    evaluasi model.
7. Pipeline & TransformedTargetRegressor
   Digunakan untuk menyatukan preprocessing dan modeling, serta menerapkan transformasi log pada target.



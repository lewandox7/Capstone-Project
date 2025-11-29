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


Dataset yang di gunakan


Hasil Utama


File Output


Cara Menjalankan
1. Clone repository ini
2. Install dependencies yang diperlukan
3. Jalankan notebook capstone project_Kelompok 3.ipynb

Teknologi yang Digunakan



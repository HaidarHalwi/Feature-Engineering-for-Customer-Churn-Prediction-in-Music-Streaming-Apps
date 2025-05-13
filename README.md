# Feature-Engineering-for-Customer-Churn-Prediction-in-Music-Streaming-Apps

🧩 Problem Statement
Aplikasi streaming musik menghadapi tantangan besar dalam mempertahankan pengguna. Salah satu indikator kinerja layanan adalah tingkat churn, yaitu pengguna yang berhenti menggunakan aplikasi.
Namun, data mentah dari log aktivitas pengguna sering kali:
- Tidak terstruktur
- Berisi banyak noise (aktivitas tidak relevan)
- Tidak langsung mencerminkan potensi churn

🎯 Project Goals
1. Membersihkan dan membentuk ulang data aktivitas pengguna agar siap digunakan untuk model prediksi churn.
2. Mengurangi kompleksitas dan noise dari data mentah agar lebih informatif.
3. Menerapkan teknik preprocessing seperti:
- Imputasi nilai kosong
- Encoding variabel kategorikal
- Normalisasi fitur numerik
- Pembuatan fitur perilaku dan temporal

📂 Dataset
Nama file: streaming_platform_data.csv
Sumber: Kaggel, Dataset simulasi pengguna aplikasi streaming musik (disiapkan untuk kebutuhan akademik)
link kaggel :
https://www.kaggle.com/datasets/akashanandt/streaming-service-data
Fitur utama: Age, Gender, Region, Payment_Method, Satisfaction_Score, Monthly_Spend, Churned, dll.

🚧 Progress dan Langkah-Langkah yang Telah Dilakukan
✅ 1. Cek Struktur Data
Memahami jumlah kolom, tipe data, statistik deskriptif awal.

✅ 2. Menangani Missing Values
Imputasi rata-rata (mean) untuk fitur numerik (Satisfaction_Score)

Imputasi kategori 'Unknown' untuk fitur kategorikal (Region, Gender)

✅ 3. Menghapus Data Duplikat
Menggunakan .drop_duplicates() untuk menghindari data ganda

✅ 4. Menangani Outliers
Menghapus nilai ekstrim pada Monthly_Spend menggunakan quantile 1% dan 99%

✅ 5. Encoding Variabel Kategorikal
One-hot encoding untuk Gender, Region, dan Payment_Method menggunakan pd.get_dummies()

✅ 6. Scaling Variabel Numerik
Monthly_Spend dan Satisfaction_Score di-normalisasi menggunakan StandardScaler()

✅ 7. Feature Engineering (Fitur Baru)
- Usage_Score: kombinasi dari Monthly_Spend_Scaled * Satisfaction_Score_Scaled
- Avg_Listen_Per_Session: estimasi waktu dengar rata-rata
- Days_Since_Last_Active: simulasi perilaku terakhir user

⚠️ 8. Fitur yang Tidak Tersedia di Dataset
Beberapa fitur yang diharapkan tidak tersedia secara langsung, seperti:
- Genre dominan per user
- Perubahan pola mingguan
- Jumlah skip/like/dislik

✅ 9. Visualisasi
Distribusi churn, usia, region
Sebelum dan sesudah scaling
Korelasi antar fitur menggunakan heatmap

✅ 10. Preview Model Prediksi
Model: RandomForestClassifier
Evaluasi menggunakan classification_report (precision, recall, f1-score)
Tujuannya untuk mengecek sejauh mana data siap digunakan untuk model prediktif


📌 Kesimpulan
- Dataset berhasil dibentuk dari data mentah menjadi format siap pakai untuk prediksi churn.
- Feature engineering memainkan peran penting dalam menciptakan representasi data pengguna yang lebih informatif dan relevan
- Visualisasi dan korelasi menunjukkan adanya fitur-fitur yang berkorelasi terhadap churn, seperti Satisfaction_Score, Monthly_Spend, dan Days_Since_Last_Active.
- Model prediksi awal (Random Forest) dapat digunakan sebagai dasar untuk eksplorasi model lain seperti XGBoost, Logistic Regression, atau Neural Networks.

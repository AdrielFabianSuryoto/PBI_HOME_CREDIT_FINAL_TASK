# Final Task - Home Credit Risk Prediction Project

## 📌 Project Overview
Proyek ini bertujuan untuk membangun model **Machine Learning** yang dapat memprediksi risiko gagal bayar pelanggan berdasarkan berbagai faktor keuangan dan demografis. Dengan model ini, **Home Credit** dapat meningkatkan efisiensi dalam pemberian pinjaman dan mengurangi risiko kredit.

## 📂 Dataset
Dataset yang digunakan dalam proyek ini berasal dari **Home Credit Default Risk Dataset**, yang mencakup informasi mengenai aplikasi kredit, histori pinjaman sebelumnya, dan karakteristik pelanggan. Berikut adalah sumber dataset utama:

- **application_train.csv**: Data utama yang digunakan untuk pelatihan model, berisi informasi tentang pelanggan dan status apakah mereka gagal bayar atau tidak.
- **application_test.csv**: Dataset yang digunakan untuk melakukan prediksi terhadap pelanggan baru.
- **bureau.csv & bureau_balance.csv**: Informasi tentang pinjaman pelanggan di lembaga keuangan lain.
- **POS_CASH_balance.csv**: Catatan riwayat saldo pinjaman POS dan cash loan pelanggan.
- **credit_card_balance.csv**: Data terkait penggunaan kartu kredit pelanggan.
- **installments_payments.csv**: Catatan pembayaran cicilan dari pelanggan yang telah mengambil pinjaman sebelumnya.
- **previous_application.csv**: Riwayat aplikasi pinjaman yang pernah diajukan oleh pelanggan.

## 🛠️ Data Cleaning & Preprocessing
Dataset mentah mengandung banyak **missing values, outliers**, dan variabel dengan format yang tidak sesuai. Oleh karena itu, dilakukan beberapa langkah preprocessing untuk menghasilkan dataset yang bersih (**cleaned_application_train.csv**) sebelum digunakan dalam pemodelan:

1. **Handling Missing Values**: Menggunakan teknik seperti **imputasi dengan mean/median**, penghapusan kolom dengan terlalu banyak missing values, dan pengisian nilai berdasarkan hubungan antar variabel.
2. **Feature Engineering**: Menambahkan fitur baru berdasarkan data historis kredit pelanggan, seperti **rasio pembayaran, durasi pinjaman, dan riwayat keterlambatan pembayaran**.
3. **Encoding Data Kategorikal**: Menggunakan **One-Hot Encoding (OHE)** atau **Label Encoding** untuk variabel non-numerik agar dapat digunakan dalam model.
4. **Scaling & Normalization**: Menerapkan **StandardScaler** atau **MinMaxScaler** pada fitur numerik untuk meningkatkan performa model.
5. **Handling Imbalanced Data**: Menggunakan **SMOTE (Synthetic Minority Over-sampling Technique)** untuk menyeimbangkan distribusi kelas pelanggan yang gagal bayar dan tidak gagal bayar.

📥 **Download Datasets**: [dataset](https://rakamin-lms.s3.ap-southeast-1.amazonaws.com/vix-assets/home-credit-indonesia/home-credit-default-risk.zip)
📥 **Download Cleaned Datasets:** [cleaned dataset](https://drive.google.com/drive/folders/11Qt6dED9j_jzHeg-6l6xMlw9zwcJhse9?usp=sharing)

## 🚀 Model Development
Model yang digunakan dalam proyek ini mencakup:
- **Logistic Regression** (Baseline Model)
- **Random Forest Classifier**
- **Gradient Boosting Classifier**
- **Hyperparameter Tuning dengan RandomizedSearchCV** untuk meningkatkan performa model

## 📈 Evaluasi Model
Model dievaluasi menggunakan **precision, recall, f1-score, ROC-AUC score**, serta visualisasi **Confusion Matrix dan ROC Curve**. Berdasarkan hasil evaluasi:
- **Logistic Regression memiliki recall tertinggi untuk kelas gagal bayar (0.66) setelah menggunakan SMOTE**, tetapi precision rendah.
- **Random Forest dan Gradient Boosting memiliki akurasi tinggi tetapi cenderung bias terhadap kelas mayoritas**.

## 💡 Business Recommendations
Berdasarkan hasil pemodelan, rekomendasi untuk bisnis meliputi:
1. **Optimasi kebijakan pemberian kredit** dengan kombinasi model Logistic Regression dan Gradient Boosting.
2. **Segmentasi pelanggan berdasarkan risiko kredit** untuk menentukan suku bunga atau persyaratan pinjaman yang lebih sesuai.
3. **Monitoring model secara berkala** dan eksplorasi metode lain seperti **XGBoost atau CatBoost** untuk meningkatkan akurasi deteksi pelanggan gagal bayar.



# Klasifikasi Tingkat Berat Sampah Laut di Kawasan Pesisir

## Tentang Proyek

Proyek ini merupakan tugas Machine Learning yang bertujuan untuk mengklasifikasikan tingkat sampah laut pada suatu lokasi survei pesisir menjadi dua kategori, yaitu **Ringan** dan **Berat**.

Proyek ini berkaitan dengan **SDG 14 (Life Below Water)**, khususnya dalam mendukung pengelolaan sampah di kawasan pesisir dan ekosistem laut.

## Dataset

Dataset yang digunakan adalah `Marine Debris-Data-UoP.xlsx`.

Dataset terdiri dari:
- 120 survei pesisir
- 41 jenis item sampah
- Data berat sampah dalam satuan kilogram

Nilai median berat sampah digunakan sebagai batas untuk menentukan kelas:
- Ringan = berat ≤ 7 kg
- Berat = berat > 7 kg

## Metode

Beberapa model Machine Learning dibandingkan:
- Random Forest
- Support Vector Machine (SVM)
- Logistic Regression
- Naive Bayes
- K-Nearest Neighbors (KNN)
- Decision Tree
- Baseline

Data dibagi menjadi 80% data training dan 20% data testing. Selain akurasi data uji, digunakan juga 5-fold cross-validation.

## Hasil

Random Forest menjadi model dengan hasil cross-validation tertinggi.

- Akurasi Cross-Validation: **71,67%**
- Akurasi Data Uji: **70,83%**
- Baseline Cross-Validation: **52,50%**

## Item Sampah yang Berpengaruh

Beberapa item yang memiliki pengaruh terhadap hasil klasifikasi adalah:
1. Item_8
2. Item_4
3. Item_13
4. Item_20
5. Item_9

## Deployment

Model Random Forest disimpan dalam bentuk file `.pkl` menggunakan `pickle`, sehingga dapat dimuat kembali untuk melakukan prediksi pada data baru.

## Keterbatasan

- Dataset hanya terdiri dari 120 sampel.
- Batas kategori Ringan dan Berat menggunakan median dataset, bukan standar resmi.
- Hasil model dapat berubah jika digunakan pada dataset atau kondisi lingkungan yang berbeda.

## Kesimpulan

Random Forest menghasilkan akurasi cross-validation sebesar 71,67% dan akurasi data uji sebesar 70,83%.

Model ini dapat digunakan sebagai pendekatan awal untuk mengklasifikasikan tingkat berat sampah laut pada lokasi survei pesisir dan dapat membantu memberikan informasi awal dalam pengelolaan sampah pesisir yang berkaitan dengan SDG 14.
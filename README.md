# Klasifikasi Tingkat Berat Sampah Laut di Kawasan Pesisir

## Tentang Proyek

Proyek ini merupakan tugas Machine Learning yang bertujuan untuk mengklasifikasikan tingkat sampah laut pada suatu lokasi survei pesisir menjadi dua kategori, yaitu **Ringan** dan **Berat**.

Proyek ini berkaitan dengan **SDG 14 (Life Below Water)**, khususnya dalam mendukung pengelolaan sampah di kawasan pesisir dan ekosistem laut.

## Daftar Isi

- [Dataset](#dataset)
- [Metode](#metode)
- [Hasil](#hasil)
- [Item Sampah yang Berpengaruh](#item-sampah-yang-berpengaruh)
- [Struktur Repository](#struktur-repository)
- [Cara Menjalankan](#cara-menjalankan)
- [Deployment](#deployment)
- [Keterbatasan](#keterbatasan)
- [Kesimpulan](#kesimpulan)
- [Pengembangan Lanjutan](#pengembangan-lanjutan)

## Dataset

Dataset yang digunakan adalah `Marine Debris-Data-UoP.xlsx`.

Dataset terdiri dari:
- 120 survei pesisir
- 41 jenis item sampah
- Data berat sampah dalam satuan kilogram

Nilai median berat sampah digunakan sebagai batas untuk menentukan kelas:

- **Ringan** = berat ≤ 7 kg
- **Berat** = berat > 7 kg

Batas tersebut merupakan batas berdasarkan median dataset dan bukan standar resmi.

## Metode

Beberapa model Machine Learning dibandingkan, yaitu:

- Random Forest
- Support Vector Machine (SVM)
- Logistic Regression
- Naive Bayes
- K-Nearest Neighbors (KNN)
- Decision Tree
- Baseline

Data dibagi menjadi:
- 80% data training
- 20% data testing

Selain menggunakan data testing, model juga dievaluasi menggunakan **5-fold cross-validation**.

## Hasil

Hasil perbandingan model:

| Model | Akurasi Uji | Akurasi CV |
|---|---:|---:|
| Random Forest | 70,83% | **71,67%** |
| SVM | 66,67% | 65,00% |
| Logistic Regression | 50,00% | 64,17% |
| Naive Bayes | 50,00% | 63,33% |
| KNN | 58,33% | 59,17% |
| Decision Tree | 70,83% | 54,17% |
| Baseline | 54,17% | 52,50% |

Berdasarkan hasil cross-validation, Random Forest digunakan sebagai model utama dengan akurasi CV sebesar **71,67%** dan akurasi data uji sebesar **70,83%**.

## Item Sampah yang Berpengaruh

Berdasarkan permutation importance, beberapa item yang memiliki pengaruh terhadap hasil klasifikasi adalah:

1. Item_8
2. Item_4
3. Item_13
4. Item_20
5. Item_9

## Struktur Repository

```text
klasifikasi-marine-debris/
├── data/
├── klasifikasi_marine_debris.ipynb
├── model_marine_debris.pkl
└── README.md
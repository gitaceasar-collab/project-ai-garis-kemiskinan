# Prediksi Garis Kemiskinan di Indonesia Menggunakan Artificial Intelligence untuk Mendukung SDG 1: No Poverty

## Deskripsi Project

Project ini bertujuan untuk melakukan prediksi nilai garis kemiskinan di Indonesia menggunakan metode Artificial Intelligence (AI) atau Machine Learning.

Prediksi dilakukan berdasarkan beberapa informasi, yaitu provinsi, tahun, periode, wilayah, dan komponen garis kemiskinan.

Project ini dibuat sebagai salah satu bentuk pemanfaatan AI untuk mendukung analisis yang berkaitan dengan Sustainable Development Goal 1 (SDG 1) yaitu No Poverty.

Model yang digunakan menghasilkan prediksi nilai garis kemiskinan dan dapat digunakan sebagai informasi pendukung dalam melakukan analisis perkembangan garis kemiskinan.

> Catatan: Model ini digunakan sebagai alat bantu analisis dan bukan untuk menentukan status kemiskinan individu atau menentukan penerima bantuan sosial.

---

## Tujuan

Tujuan dari project ini adalah:

1. Menganalisis data garis kemiskinan di Indonesia.
2. Melakukan preprocessing dan eksplorasi data.
3. Membangun model Machine Learning untuk memprediksi nilai garis kemiskinan.
4. Membandingkan performa Linear Regression dan Random Forest Regression.
5. Mengevaluasi hasil prediksi menggunakan MAE, RMSE, dan R².
6. Mendukung analisis yang berkaitan dengan SDG 1: No Poverty.

---

## Dataset

Dataset yang digunakan merupakan data garis kemiskinan berdasarkan provinsi di Indonesia.

Dataset yang telah melalui proses perapihan memiliki:

- Jumlah data: 5.261 baris
- Jumlah provinsi: 35 provinsi
- Periode tahun: 2013–2022
- Periode pengamatan: Maret dan September

### Fitur Dataset

| Kolom | Keterangan |
|---|---|
| Provinsi | Nama provinsi |
| Tahun | Tahun pengamatan |
| Periode | Periode Maret atau September |
| Wilayah | Perkotaan, Perdesaan, atau Perkotaan dan Perdesaan |
| Komponen | Makanan, Non-Makanan, atau Total |
| Nilai_GK | Nilai garis kemiskinan |

Target yang digunakan dalam pemodelan adalah:

**Nilai_GK**

---

## Tahapan Project

Tahapan yang dilakukan dalam project ini adalah:

1. Problem Identification
2. Data Collection
3. Data Cleaning
4. Exploratory Data Analysis (EDA)
5. Feature Selection
6. Preprocessing
7. Train-Test Split
8. Model Training
9. Model Evaluation
10. Prediction and Interpretation

---

## Data Cleaning dan Preprocessing

Data diperiksa untuk mengetahui adanya missing values dan data duplikat.

Hasil pemeriksaan:

- Missing values: 0
- Data duplikat: 0

Data kategorikal seperti Provinsi, Periode, Wilayah, dan Komponen diubah menggunakan One-Hot Encoding.

Data tahun digunakan sebagai fitur numerik.

---

## Exploratory Data Analysis

Exploratory Data Analysis (EDA) dilakukan untuk memahami pola nilai garis kemiskinan berdasarkan:

- Tahun
- Provinsi
- Wilayah
- Komponen garis kemiskinan

Visualisasi digunakan untuk melihat perubahan dan distribusi nilai garis kemiskinan pada dataset.

---

## Algoritma Machine Learning

Dua algoritma digunakan dalam project ini.

### 1. Linear Regression

Linear Regression digunakan sebagai salah satu model regresi untuk mempelajari hubungan antara fitur dengan nilai garis kemiskinan.

Model ini juga digunakan sebagai pembanding awal terhadap model lainnya.

### 2. Random Forest Regression

Random Forest Regression digunakan karena mampu menangkap hubungan yang lebih kompleks antara fitur dan target.

Model ini terdiri dari beberapa decision tree yang digabungkan untuk menghasilkan prediksi.

---

## Pembagian Data

Pembagian data dilakukan berdasarkan waktu untuk menghindari penggunaan data masa depan dalam proses training.

### Data Training

Tahun:

**2013–2020**

### Data Testing

Tahun:

**2021–2022**

Dengan pendekatan ini, model dilatih menggunakan data tahun sebelumnya dan diuji menggunakan data pada periode setelahnya.

---

## Evaluasi Model

Evaluasi dilakukan menggunakan tiga metrik:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- R² (Coefficient of Determination)

### Hasil Linear Regression

| Metrik | Nilai |
|---|---:|
| MAE | 40.998,52 |
| RMSE | 53.579,29 |
| R² | 0,9156 |

### Hasil Random Forest

| Metrik | Nilai |
|---|---:|
| MAE | 33.048,93 |
| RMSE | 41.938,57 |
| R² | 0,9483 |

Berdasarkan pengujian pada data tahun 2021–2022, Random Forest menghasilkan nilai MAE dan RMSE yang lebih rendah serta nilai R² yang lebih tinggi dibandingkan Linear Regression pada eksperimen ini.

Nilai R² sebesar 0,9483 menunjukkan bahwa pada pembagian data pengujian tersebut, model Random Forest dapat menjelaskan sekitar 94,83% variasi nilai target.

---

## Hasil Prediksi

Hasil prediksi model Random Forest disimpan dalam file:

`hasil/hasil_prediksi_garis_kemiskinan.csv`

File tersebut berisi informasi fitur, nilai garis kemiskinan aktual, dan nilai garis kemiskinan hasil prediksi.

---

## Struktur Repository

```text
project-ai-garis-kemiskinan/
│
├── dataset/
│   ├── README.md
│   └── dataset_garis_kemiskinan_rapi (1).csv
│
├── hasil/
│   ├── .gitkeep
│   └── hasil_prediksi_garis_kemiskinan.csv
│
├── notebooks/
│   └── Prediksi_Garis_Kemiskinan.ipynb
│
└── README.md

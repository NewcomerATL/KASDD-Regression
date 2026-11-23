# TP2 - Life Expectancy Regression

Proyek ini bertujuan untuk memprediksi angka harapan hidup (**Life Expectancy**) menggunakan pendekatan model regresi. Performa model dievaluasi menggunakan metrik skor **$R^2$ (*R-squared*)**.

## 👥 Pembagian Tugas Kelompok

Berikut adalah pembagian eksplorasi dan pemodelan *machine learning* untuk masing-masing anggota tim:

| Nama Anggota | Model Regresi | Fokus Eksperimen & Pemodelan |
| :--- | :--- | :--- |
| **Anderson Tirza** | **Random Forest** | *Ensemble tree-based* (*bagging*), analisis *feature importance*, dan *hyperparameter tuning* |
| **Raymundo Rafaelito** | **CatBoost** | *Gradient boosting* yang dioptimalkan untuk penanganan fitur kategorikal secara otomatis |
| **Angelo Benhanan** | **Ridge Regression** | Model regresi linear dengan regularisasi L2 (*alpha*), *polynomial features*, dan optimasi via Optuna |
| **Jovanus Irwan** | **XGBoost** | *Extreme Gradient Boosting* (*boosting* berbasis pohon keputusan) dengan pengaturan regularisasi |

---

## 📊 Deskripsi Dataset

Dataset yang digunakan dalam proyek ini terdiri dari dua berkas utama[cite: 1]:
* `train.csv` — Berisi **10.070 baris** dan **21 kolom** (termasuk variabel target `Life expectancy`)[cite: 1].
* `test.csv` — Berisi **1.259 baris** dan **19 kolom** untuk keperluan prediksi akhir[cite: 1].

### Temuan Awal (*Exploratory Data Analysis*)
* **Missing Values:** Terdapat beberapa kolom dengan nilai kosong (*missing values*), dengan persentase tertinggi pada fitur `Population` (5.23%), `Hepatitis B` (4.53%), dan `GDP` (3.60%)[cite: 1].
* **Distribusi Target:** Distribusi `Life expectancy` menunjukkan perbedaan yang cukup kontras antara negara dengan status **Developed** (negara maju) dan **Developing** (negara berkembang)[cite: 1].

---

## ⚙️ Alur Pengerjaan (*Workflow*)

1. **Load Data & Imports:** Memuat dataset (`train.csv` dan `test.csv`) serta mengimpor pustaka analisis data dan pemodelan (`pandas`, `numpy`, `scikit-learn`, `optuna`, dll.)[cite: 1].
2. **Exploratory Data Analysis (EDA):** Menganalisis proporsi *missing values*, memvisualisasikan distribusi variabel target (`Life expectancy`), serta membandingkan tren berdasarkan status negara[cite: 1].
3. **Data Preprocessing & Pipeline:**
   * Penanganan nilai kosong (*imputation* menggunakan `SimpleImputer`)[cite: 1].
   * Penskalaan fitur numerik (*scaling* menggunakan `StandardScaler`) dan *encoding* variabel kategorikal[cite: 1].
   * *Feature engineering* (seperti ekstraksi fitur polinomial untuk model linear)[cite: 1].
4. **Modeling & Hyperparameter Tuning:**
   * Membangun dan melatih masing-masing model sesuai pembagian tugas kelompok.
   * Melakukan validasi silang (*K-Fold Cross-Validation*) dan pencarian parameter terbaik (menggunakan `Optuna` / `GridSearch`) untuk memaksimalkan skor **$R^2$**[cite: 1].
5. **Evaluasi & Submission:** Membandingkan metrik evaluasi ($R^2$, RMSE, MAE) antar model dan menghasilkan berkas prediksi dengan format `id, Life Expectancy`[cite: 1].

---

## 🛠️ Cara Menjalankan Proyek

1. Pastikan Python 3.10+ sudah terpasang beserta pustaka yang dibutuhkan:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn optuna xgboost catboost

## 📄 Format Submission
Hasil prediksi akhir disimpan dalam format CSV dengan struktur kolom berikut[cite: 1]:

Code snippet

id,Life Expectancy

0,72.4

1,68.9

...

## Documentation of Submission in Kaggle:
<img width="1457" height="753" alt="image" src="https://github.com/user-attachments/assets/9689656b-5b56-4300-93e1-ae8e2fdf4d84" />



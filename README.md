# Analisis Pasar dan Pemodelan Nilai Kopi Ritel Indonesia (2026)

Repositori ini memuat analisis kuantitatif dan implementasi pipeline Machine Learning berbasis dataset **Indonesia Coffee Chain Wars (2026)**. Penelitian ini mengevaluasi struktur harga, efisiensi promosi, serta indeks rasio nilai terhadap biaya (*Value for Money / VFM*) pada lima jaringan gerai kopi terkemuka di Indonesia: Tomoro Coffee, Kopi Kenangan, Fore Coffee, Point Coffee, dan Kopi Janji Jiwa.

---

## Ringkasan Eksekutif & Temuan Utama

1. **Jaringan Paling Ekonomis:**
   * **Tomoro Coffee** memimpin efisiensi harga dengan rata-rata harga transaksi bersih sebesar **Rp 9.456** per cangkir (diskon voucher rata-rata 33,9%), dengan harga minimum mencapai **Rp 4.086**.
2. **Jaringan dengan Rasio Nilai terhadap Biaya (VFM) Tertinggi:**
   * **Tomoro Coffee (Skor VFM: 8,50)** menempati peringkat pertama untuk konsumsi harian berkat kombinasi 78,1% penggunaan biji 100% Arabica Specialty pada rentang harga ekonomis.
   * **Fore Coffee (Skor VFM: 3,91)** menempati peringkat pertama untuk kebutuhan ruang kerja/pertemuan, didukung oleh fasilitas gerai ber-AC penuh, konektivitas internet stabil, dan bahan baku 100% Arabica Specialty di seluruh gerai (rata-rata harga bersih Rp 20.841).
3. **Kinerja Pemodelan Prediktif:**
   * Menggunakan seleksi fitur statistik `SelectKBest` (F-Regression) dan algoritma `GradientBoostingRegressor`, model memprediksi harga bersih yang dibayarkan konsumen dengan koefisien determinasi **$R^2 > 0,98$** di seluruh jaringan (rata-rata galat/MAE berkisar antara Rp 180 hingga Rp 376 per cangkir).

---

## Struktur Repositori

```text
├── data/
│   └── indonesia_coffee_chain_wars_enriched_2026.csv   # Dataset pasar ritel kopi (13.000 observasi)
├── reports/
│   ├── high_r2_net_price_prediction.png                # Grafik evaluasi prediksi R² > 0.98
│   ├── vfm_and_price_comparison.png                    # Visualisasi harga vs indeks VFM
│   └── selectkbest_top_features.png                    # Fitur statistik paling berpengaruh
├── indonesia_coffee_market_analysis.ipynb              # Notebook analisis lengkap dan pemodelan
├── .gitignore
└── README.md
```

---

## Kinerja Model Prediksi per Jaringan

| Jaringan Kopi | Koefisien Determinasi ($R^2$) | Rata-rata Galat (MAE) | Rata-rata Harga Aktual | Galat Relatif (%) |
| :--- | :---: | :---: | :---: | :---: |
| **Tomoro Coffee** | **0,9932** | Rp 184 | Rp 9.456 | **1,94%** |
| **Kopi Kenangan** | **0,9865** | Rp 306 | Rp 16.997 | **1,80%** |
| **Point Coffee** | **0,9857** | Rp 247 | Rp 16.103 | **1,53%** |
| **Kopi Janji Jiwa** | **0,9847** | Rp 257 | Rp 16.048 | **1,60%** |
| **Fore Coffee** | **0,9834** | Rp 376 | Rp 20.841 | **1,81%** |

---

## Cara Menjalankan

1. Kloning repositori ini:
   ```bash
   git clone <URL_REPOSITORI>
   cd coffee-insight
   ```
2. Pastikan dependensi terpasang:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. Buka dan jalankan notebook:
   ```bash
   jupyter notebook indonesia_coffee_market_analysis.ipynb
   ```

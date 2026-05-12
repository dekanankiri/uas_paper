# K203504 — DATA MINING
### Politeknik Statistika STIS
#### Catatan Kuliah Lengkap Pertemuan 1–6

---

# PERTEMUAN 1 — Pengantar Data Mining

## 1.1 Konsep Data, Informasi, dan Pengetahuan

Data, informasi, dan pengetahuan membentuk hierarki yang semakin bernilai:

| Level | Definisi | Contoh |
|---|---|---|
| **Data** | Fakta mentah yang direkam, belum bermakna | Catatan jam datang/pulang pegawai |
| **Informasi** | Rekap/rangkuman data yang sudah diolah dan berkonteks | Rekapitulasi kehadiran per NIP per bulan |
| **Pengetahuan** | Pola, keteraturan, atau model yang ditemukan dari data | "Pegawai paling sering terlambat di hari Senin" |

**Transformasi hierarki:**
```
Data → (diolah, diorganisasikan, diberi konteks) → Informasi
Informasi → (dicari polanya, diberi makna) → Pengetahuan
```

Dengan pengetahuan tersebut, manusia dapat:
- Melakukan estimasi dan prediksi ke depan
- Menganalisis asosiasi, korelasi, dan pengelompokan antar data
- Membantu pengambilan keputusan dan pembuatan kebijakan

**Contoh perusahaan berbasis pengetahuan:**
- Google — media/advertising terbesar, tidak membuat konten
- Alibaba — retailer paling berharga, tidak punya inventori
- Gojek — transportasi tanpa memiliki kendaraan

---

## 1.2 Definisi Data Mining

> *"Disiplin ilmu yang mempelajari metode untuk mengekstrak pengetahuan atau menemukan pola dari suatu data yang berukuran besar."*

**Definisi dari berbagai sumber:**
- Witten et al. (2011): Melakukan ekstraksi informasi penting yang *implisit* dan sebelumnya tidak diketahui
- Santosa (2007): Kegiatan menemukan keteraturan, pola, dan hubungan dalam dataset berukuran besar
- Han et al. (2011): Extraction of *interesting, non-trivial, implicit, previously unknown* and *potentially useful* patterns from huge amount of data

**Nama lain data mining:**
- Knowledge Discovery in Database (KDD)
- Big Data Analytics
- Business Intelligence
- Knowledge Extraction
- Pattern Analysis

**Syarat pola dikatakan "menarik":**  tidak sepele, implisit, tidak diketahui sebelumnya, berguna, mudah dipahami, dan memiliki derajat kepastian tertentu.

---

## 1.3 Mengapa Data Mining Dibutuhkan?

**Alasan teknis:**
- Data yang dikumpulkan jarang dilihat lagi karena terlalu banyak
- Intuisi manusia sudah tidak memadai untuk pengambilan keputusan
- Komputer semakin murah dan powerful

**Alasan komersial:**
- Web data, e-commerce, transaksi bank terus bertambah
- Tekanan kompetisi bisnis yang kuat
- Kebutuhan insight dari data historis

---

## 1.4 KDD dan Tahapan Data Mining

**KDD (Knowledge Discovery in Databases)** adalah *sekumpulan proses* untuk menemukan pengetahuan dari data. Data Mining hanyalah satu bagian dari KDD.

### Tahapan KDD / CRISP-DM

| No | Tahap | Keterangan |
|---|---|---|
| 1 | **Data Cleaning** | Menghapus noise dan inkonsistensi data |
| 2 | **Data Integration** | Menggabungkan data dari berbagai sumber |
| 3 | **Data Selection** | Memilih data yang relevan dengan tugas analisis |
| 4 | **Data Transformation** | Transformasi ke format yang sesuai (normalisasi, agregasi) |
| 5 | **Data Mining** | Penerapan metode cerdas untuk menemukan pola |
| 6 | **Pattern Evaluation** | Mengidentifikasi pola yang benar-benar menarik |
| 7 | **Knowledge Presentation** | Visualisasi dan presentasi pengetahuan kepada pengguna |

**CRISP-DM (Cross-Industry Standard Process for Data Mining)** adalah standar industri yang paling umum digunakan.

---

## 1.5 Komponen Dataset dan Tipe Data

### Struktur Dataset

```
┌──────────────────────────────────────────────────────┐
│  Attribute/Feature/Dimension  │  Class/Label/Target  │
├─────┬──────────┬──────────────┼──────────────────────┤
│  R  │ Nominal  │   Numerik    │       Target         │
│  e  ├──────────┼──────────────┤                      │
│  c  │ (Kota)   │ (Pendapatan) │ (Miskin/Tidak Miskin)│
│  o  │          │              │                      │
│  r  │          │              │                      │
│  d  │          │              │                      │
└─────┴──────────┴──────────────┴──────────────────────┘
```

### Tipe Skala Data

| Tipe | Operasi | Deskripsi | Contoh |
|---|---|---|---|
| **Ratio** | ×, ÷ | Ada titik nol absolut | Usia, berat badan, pendapatan |
| **Interval** | +, − | Tidak ada nol absolut | Suhu (°C), umur 20–30 thn |
| **Ordinal** | <, > | Ada urutan, jarak tidak pasti | Tingkat kepuasan (puas/sedang/tidak) |
| **Nominal** | =, ≠ | Hanya kategorisasi | Kode pos, jenis kelamin, nama kota |

---

## 1.6 Peran (Tugas) Data Mining

Menurut Larose (2005), terdapat 5 peran utama:

1. **Estimasi** — memprediksi nilai kontinu (misal: waktu tempuh, harga)
2. **Forecasting** — prediksi deret waktu (misal: harga saham besok)
3. **Klasifikasi** — memprediksi kelas kategoris (misal: miskin/tidak miskin)
4. **Klastering** — mengelompokkan data tanpa label
5. **Asosiasi** — menemukan aturan "jika A maka B"

### Metode per Tugas

| Tugas | Metode |
|---|---|
| Estimasi / Forecasting | Linear Regression, Neural Network, SVM, GLM |
| Klasifikasi | Decision Tree (CART, ID3, C4.5), Naive Bayes, KNN, LDA, Logistic Regression |
| Klastering | K-Means, K-Medoids, SOM, Fuzzy C-Means |
| Asosiasi | FP-Growth, Apriori, Chi-Square |

---

## 1.7 Output / Model / Pengetahuan

| Tipe Output | Contoh |
|---|---|
| **Formula/Fungsi** | `Waktu Tempuh = 0.48 + 0.6×Jarak + 0.34×LampuMerah + 0.2×Pesanan` |
| **Decision Tree** | Pohon keputusan dengan aturan if-then |
| **Rule** | `IF ips3 ≥ 2.8 THEN Lulus_Tepat_Waktu = Ya` |
| **Cluster** | Kelompok data dengan karakteristik serupa |
| **Correlation** | Korelasi antar variabel |

---

## 1.8 Kategorisasi Algoritma Data Mining

```
┌─────────────────────────────────────────────────────┐
│                  ALGORITMA DATA MINING               │
├───────────────┬───────────────┬─────────────────────┤
│  SUPERVISED   │ SEMI-SUPERVISED│   UNSUPERVISED      │
│   LEARNING    │    LEARNING   │     LEARNING         │
│               │               │                     │
│  Ada label    │ Sebagian ada  │  Tidak ada label    │
│  (estimasi,   │    label      │  (clustering,       │
│  klasifikasi, │               │   association)      │
│  forecasting) │               │                     │
└───────────────┴───────────────┴─────────────────────┘
```

---

# PERTEMUAN 2 — Data Preprocessing

## 2.1 Kualitas Data

Ukuran kualitas data meliputi:

| Dimensi | Penjelasan |
|---|---|
| **Akurasi** | Data benar atau salah, akurat atau tidak |
| **Kelengkapan** | Tidak ada nilai yang hilang |
| **Konsistensi** | Tidak ada inkonsistensi antar record |
| **Ketepatan waktu** | Pembaruan dilakukan tepat waktu |
| **Kepercayaan** | Seberapa tepercaya data tersebut |
| **Interpretability** | Seberapa mudah data dipahami |

---

## 2.2 Tugas Utama Preprocessing

```
DATA KOTOR → [Preprocessing] → DATA BERSIH
```

1. **Data Cleaning** — isi missing value, atasi noise, hapus/perbaiki outlier, tangani inkonsistensi
2. **Data Integration** — gabungkan database/file dari berbagai sumber
3. **Data Reduction** — kurangi dimensi atau jumlah data tanpa kehilangan informasi penting
4. **Data Transformation & Discretization** — normalisasi, pembuatan hierarki konsep

---

## 2.3 Data Cleaning

### Data Tidak Lengkap (Missing Values)

**Penyebab:**
- Kerusakan peralatan
- Kesalahan input/transmisi
- Data dianggap tidak penting saat itu

**Cara menangani:**
1. **Abaikan record** — jika persentase missing sangat kecil
2. **Isi manual** — membosankan, tidak skalabel
3. **Imputasi otomatis:**
   - Konstanta global (misal: "tidak diketahui")
   - **Rata-rata (mean)** — untuk distribusi normal
   - **Median** — untuk distribusi skewed atau ada outlier
   - **Modus** — untuk data kategorik
   - Nilai paling mungkin (Bayes/Decision Tree)

### Noisy Data

**Definisi:** Kesalahan random atau varians dalam variabel yang diukur.

**Penyebab:** instrumen rusak, kesalahan entri, kesalahan transmisi, inkonsistensi konvensi penamaan.

**Cara menangani:**
- **Binning** — urutkan data, partisi ke bin, haluskan dengan mean/median/batas bin
- **Regression** — haluskan dengan fungsi regresi
- **Clustering** — deteksi dan hapus outlier
- **Inspeksi manual** — kombinasi komputer dan manusia

#### Contoh Binning

```
Data harga (sorted): 4, 8, 9, 15, 21, 21, 24, 25, 26, 28, 29, 34

Equal-frequency bins (4 per bin):
  Bin 1: 4, 8, 9, 15
  Bin 2: 21, 21, 24, 25
  Bin 3: 26, 28, 29, 34

Smoothing by bin means:
  Bin 1: 9, 9, 9, 9
  Bin 2: 23, 23, 23, 23
  Bin 3: 29, 29, 29, 29

Smoothing by bin boundaries:
  Bin 1: 4, 4, 4, 15
  Bin 2: 21, 21, 25, 25
  Bin 3: 26, 26, 26, 34
```

---

## 2.4 Data Integration

**Data Integration** = menggabungkan data dari berbagai sumber ke satu penyimpanan koheren.

**Tantangan:**
- **Schema integration** — metadata dari sumber berbeda
- **Entity identification problem** — entitas yang sama bisa memiliki nama berbeda (Bill Clinton = William Clinton)
- **Deteksi redundansi** — atribut derivatif, duplikat
- **Konflik nilai** — representasi atau skala berbeda (metric vs British units)

**Solusi:** Analisis korelasi untuk deteksi redundansi; integrasi cermat untuk mengurangi inkonsistensi.

---

## 2.5 Data Reduction

**Tujuan:** Dapatkan representasi yang lebih kecil namun menghasilkan hasil analisis yang sama (atau hampir sama).

### Strategi Reduksi

#### 1. Pengurangan Dimensi
- **Wavelet Transforms**
- **PCA (Principal Component Analysis)**
- **Feature Subset Selection** — hapus fitur tidak relevan
- **Feature Creation** — buat atribut baru yang lebih informatif

**Curse of Dimensionality:** Semakin tinggi dimensi, data semakin *sparse*. Jarak antar titik kehilangan makna. Kombinasi subruang tumbuh eksponensial.

**Heuristic Feature Selection:**
- **Best step-wise forward selection** — pilih fitur terbaik satu per satu
- **Step-wise attribute elimination** — eliminasi fitur terburuk secara berulang
- **Best + elimination combination**

#### 2. Numerosity Reduction
- **Parametric** — fit model (regresi), simpan hanya parameter
- **Non-parametric** — histogram, clustering, sampling

**Regresi:**
- Linear: `Y = wX + b`
- Multiple: `Y = b₀ + b₁X₁ + b₂X₂`
- Log-linear models

**Sampling:**
- Simple random sampling
- Stratified sampling (untuk data skewed)

#### 3. Data Compression
- String compression, audio/video compression
- Kompresi *lossless* vs *lossy*

---

## 2.6 Data Transformation

**Fungsi:** Memetakan nilai atribut ke nilai pengganti baru.

### Normalisasi

#### Min-Max Normalization
Skala ke rentang `[new_min, new_max]`:

```
v' = (v - min_A) / (max_A - min_A) × (new_max - new_min) + new_min
```

**Contoh:** Income range $12,000–$98,000 → [0,1]. Nilai $73,000:
```
v' = (73,000 - 12,000) / (98,000 - 12,000) = 61,000/86,000 ≈ 0.716
```

#### Z-Score Normalization (Standardisasi)
```
v' = (v - μ) / σ
```
- μ = mean, σ = standard deviation
- Hasil: mean = 0, std = 1

**Contoh:** μ = 54,000, σ = 16,000. Nilai $73,000:
```
v' = (73,000 - 54,000) / 16,000 = 19,000/16,000 = 1.1875
```

#### Decimal Scaling
```
v' = v / 10^j
```
di mana j = integer terkecil sehingga max(|v'|) < 1.

---

## 2.7 Discretization

**Definisi:** Membagi rentang atribut kontinu menjadi interval (bin).

**Tiga tipe atribut:** Nominal, Ordinal, Numeric.

### Metode Discretization

| Metode | Tipe | Arah |
|---|---|---|
| Binning | Unsupervised | Top-down |
| Histogram | Unsupervised | Top-down |
| Clustering | Unsupervised | Top-down atau Bottom-up |
| Decision Tree | Supervised | Top-down |
| Chi-Merge (χ²) | Supervised | Bottom-up |

**Equal-width:** Range dibagi N interval berukuran sama → W = (B-A)/N  
**Equal-frequency (equi-depth):** Setiap interval berisi jumlah sampel yang kira-kira sama.

---

## 2.8 Concept Hierarchy Generation

**Tujuan:** Mengorganisasi konsep secara hierarkis untuk memudahkan drill-down dan roll-up.

**Contoh untuk nominal data:**
```
street < city < state < country
{Urbana, Champaign, Chicago} < Illinois
```

**Pembentukan otomatis:** Berdasarkan jumlah nilai berbeda per atribut.
- Atribut dengan nilai paling berbeda → tingkat terendah
- Contoh: street (674,339 nilai) → city (3,567) → province (365) → country (15)

---

# PERTEMUAN 3 — Supervised Learning & Evaluasi Model

## 3.1 Insight Law (Data Mining Law 6)

> *"Data mining memperkuat persepsi dalam domain bisnis. Masalah bisnis pada dasarnya diselesaikan oleh manusia, bukan oleh algoritma semata."*

Proses data mining = proses memahami masalah + menemukan makna dari data. Algoritma mengungkap pola, manusia menginterpretasikan.

---

## 3.2 Supervised vs Unsupervised Learning

**Supervised Learning:**
- Data memiliki label/target/class
- Algoritma belajar berdasarkan nilai variabel target
- Meliputi: estimasi, prediksi, klasifikasi

**Unsupervised Learning:**
- Tidak ada label
- Menemukan struktur tersembunyi dalam data
- Meliputi: clustering, association

---

## 3.3 Proses Data Mining Lengkap

```
Himpunan Data → Preprocessing → Modeling → Model → Evaluasi
      ↓               ↓            ↓          ↓         ↓
  (Pahami &      Data Cleaning  Estimation  Formula  Akurasi
   Persiapkan)   Integration    Prediction    Tree    Error
                 Reduction      Classif.    Cluster   Jumlah
                 Transform.     Cluster      Rule    Cluster
                                Assoc.      Correl.
```

---

## 3.4 Sumber Dataset

**Private Dataset:** Bank, Rumah Sakit, Industri, Perusahaan (memerlukan izin)

**Public Dataset:**
- UCI Repository: `http://www.ics.uci.edu/~mlearn/MLRepository.html`
- ACM KDD Cup: `http://www.sigkdd.org/kddcup/`
- Kaggle: `https://www.kaggle.com/datasets`

---

## 3.5 Evaluasi Kinerja Model

### Confusion Matrix

```
                    Prediksi
                  Yes        No
Aktual  Yes  │   TP    │   FN   │
        No   │   FP    │   TN   │
```

- **TP (True Positive)** — diprediksi positif, memang positif
- **TN (True Negative)** — diprediksi negatif, memang negatif
- **FP (False Positive)** — diprediksi positif, padahal negatif (Type I Error)
- **FN (False Negative)** — diprediksi negatif, padahal positif (Type II Error)

### Metrik Evaluasi Klasifikasi

| Metrik | Rumus | Makna |
|---|---|---|
| **Accuracy** | (TP+TN) / (TP+TN+FP+FN) | Proporsi prediksi benar secara keseluruhan |
| **Sensitivity / Recall** | TP / (TP+FN) | Kemampuan menangkap semua kasus positif (TPR) |
| **Specificity** | TN / (TN+FP) | Kemampuan mengenali negatif sebagai negatif (TNR) |
| **Precision (PPV)** | TP / (TP+FP) | Dari yang diprediksi positif, berapa yang benar? |
| **NPV** | TN / (TN+FN) | Dari yang diprediksi negatif, berapa yang benar? |
| **F1-Score** | 2×(Precision×Recall)/(Precision+Recall) | Harmonik mean presisi dan recall |

### ROC Curve & AUC

- **ROC:** Grafik 2D: TPR (y-axis) vs FPR (x-axis)
- **AUC (Area Under Curve):** Semakin mendekati 1 = semakin baik

| AUC | Klasifikasi |
|---|---|
| 0.90 – 1.00 | Excellent |
| 0.80 – 0.90 | Good |
| 0.70 – 0.80 | Fair |
| 0.60 – 0.70 | Poor |
| 0.50 – 0.60 | Failure |

### Kappa Statistics (Cohen's Kappa)

Mengukur seberapa baik classifier dibanding *chance agreement*:
- Kappa tinggi = perbedaan besar antara akurasi model vs tebakan acak
- Penting untuk dataset tidak seimbang (*imbalanced*)

### Metrik untuk Estimasi/Regresi

| Metrik | Rumus | Keterangan |
|---|---|---|
| **RMSE** | √[Σ(yᵢ - ŷᵢ)²/n] | Root Mean Square Error |
| **MSE** | Σ(yᵢ - ŷᵢ)²/n | Mean Squared Error |
| **MAPE** | (1/n)×Σ\|(yᵢ-ŷᵢ)/yᵢ\| | Mean Absolute Percentage Error |

### Metrik untuk Clustering

- **Internal:** Davies-Bouldin Index (DBI), Dunn Index
- **External:** Rand Measure, F-Measure, Jaccard Index, Confusion Matrix

---

## 3.6 Overfitting dan Underfitting

**Underfitting:** Model terlalu sederhana, high bias, low variance  
→ Training error tinggi, test error tinggi

**Overfitting:** Model terlalu kompleks, hafal training data  
→ Training error rendah, test error tinggi

**Bias-Variance Trade-off:**
```
E(MSE) = noise² + bias² + variance
```

Seiring kompleksitas model naik:
- Bias berkurang
- Variance meningkat
- Test error berbentuk kurva U

---

## 3.7 Pembagian Data Training & Testing

**Split manual atau otomatis:**
- Proporsi umum: 70:30 atau 80:20
- **Data training** — membangun model
- **Data testing** — menguji model

**Tipe sampling:**
- **Linear sampling** — urutan tidak diubah
- **Shuffled sampling** — subset acak
- **Stratified sampling** — distribusi kelas dipertahankan (⭐ direkomendasikan)

---

## 3.8 Cross-Validation (k-Fold)

**Tujuan:** Menghindari overlapping pada data testing, mendapatkan estimasi error yang lebih reliable.

**Algoritma:**
1. Bagi data menjadi k subset berukuran sama
2. Iterasi k kali: gunakan satu subset untuk testing, sisanya untuk training
3. Hitung rata-rata akurasi dari k iterasi

**Standar:** 10-fold cross-validation (terbukti secara empiris dan teoritis sebagai pilihan terbaik).

**Contoh 10-fold CV:**

| Eksperimen | Akurasi |
|---|---|
| 1 | 93% |
| 2 | 91% |
| 3 | 90% |
| ... | ... |
| 10 | 90% |
| **Rata-rata** | **92%** |

---

## 3.9 Tools Data Mining

| Tool | Keterangan |
|---|---|
| **R / RStudio** | Open source, library statistik lengkap, mendukung RMarkdown |
| **Python** | Populer untuk ML & Deep Learning, Jupyter Notebook, Google Colab |
| **KNIME** | GUI drag-and-drop, gratis, open source |
| **RapidMiner** | Berbasis GUI, award-winning platform |
| **WEKA** | Tool akademik berbasis Java |
---

# PERTEMUAN 4 — Klasifikasi: Decision Tree & Naive Bayes

## 4.1 Klasifikasi: Konsep Dasar

### Proses Dua Tahap

**Tahap 1 — Konstruksi Model:**
- Data training → model (aturan / pohon / rumus)
- Setiap tupel diasumsikan memiliki kelas yang telah ditentukan

**Tahap 2 — Penggunaan Model:**
- Estimasi akurasi menggunakan data testing
- Jika akurasi dapat diterima → gunakan untuk klasifikasi data baru

> ⚠️ *Jika data test digunakan untuk memilih model → disebut data validasi*

---

## 4.2 Decision Tree (Pohon Keputusan)

### Analogi

Decision Tree seperti permainan *"20 Pertanyaan"*: mulai dari pertanyaan paling informatif, terus bercabang berdasarkan jawaban, hingga mencapai kesimpulan.

### Terminologi

| Istilah | Pengertian |
|---|---|
| **Root Node** | Node teratas — pertanyaan pertama yang paling informatif |
| **Internal Node** | Node tengah — mengandung kondisi split |
| **Branch/Edge** | Cabang penghubung — mewakili satu kemungkinan jawaban |
| **Leaf Node** | Node terminal — tidak ada split lagi, menyimpan prediksi kelas |
| **Depth** | Kedalaman pohon dari root ke leaf terdalam |
| **Split** | Pemisahan data berdasarkan kondisi fitur |
| **Impurity** | Heterogenitas kelas dalam suatu node (Gini/Entropy) |
| **Pruning** | Pemangkasan cabang untuk mengurangi overfitting |

### Struktur Contoh

```
              PENDAPATAN?
             /           \
          < 500K        ≥ 500K
           /               \
      PENDIDIKAN?        ✓ Tidak Miskin
       /       \
    Rendah    Tinggi
      /           \
  ✗ Miskin   ✓ Tdk Miskin
```

### Cara Kerja (Greedy Algorithm)

1. Mulai dari root: cari fitur & threshold yang paling baik memisahkan kelas
2. Split data menjadi subset kiri dan kanan
3. Rekursif untuk setiap subset sampai *stopping criterion* terpenuhi
4. Beri label kelas mayoritas (klasifikasi) atau rata-rata (regresi) di setiap leaf

---

## 4.3 Teori Informasi: Entropy (Shannon, 1948)

### Rumus Entropy

```
H(S) = −Σᵢ pᵢ × log₂(pᵢ)
```

- `pᵢ` = proporsi kelas i dalam himpunan S
- log₂(0) = 0 (by convention)

### Interpretasi Nilai Entropy

| Kondisi | Nilai H | Makna |
|---|---|---|
| Semua elemen satu kelas | H = 0 | Murni (pure), tidak ada ketidakpastian |
| 50:50 (2 kelas) | H = 1 | Campuran merata, ketidakpastian maksimum |
| m kelas seragam | H = log₂(m) | Nilai maksimum untuk m kelas |

**Contoh (binary):**
```
Distribusi (4,0): H = 0.000
Distribusi (3,1): H = 0.811
Distribusi (2,2): H = 1.000
```

### Sifat-sifat Entropy

1. **Non-negatif** — H(S) ≥ 0
2. **Simetri** — tidak berubah jika urutan pᵢ dipertukarkan
3. **Maksimum seragam** — H maksimum saat distribusi seragam
4. **Minimum pasti** — H = 0 saat satu kelas p = 1
5. **Aditif (Chain Rule)** — H(X,Y) = H(X) + H(Y|X)

---

## 4.4 Kriteria Pemilihan Split

### Information Gain (ID3)

```
Gain(D, A) = H(D) − InfoA(D)

InfoA(D) = Σⱼ (|Dⱼ|/|D|) × H(Dⱼ)
```

**Langkah:**
1. Hitung H(D) — entropy total
2. Hitung InfoA(D) — expected entropy setelah split oleh A
3. Hitung Gain = H(D) − InfoA(D)
4. Pilih A* = argmax Gain(D, A)

**Kelemahan:** Bias terhadap fitur dengan banyak nilai unik (high cardinality).

---

### Gain Ratio (C4.5)

```
SplitInfo(A) = −Σⱼ (|Dⱼ|/|D|) × log₂(|Dⱼ|/|D|)

GainRatio(A) = Gain(A) / SplitInfo(A)
```

**Tujuan:** Menormalisasi Gain agar tidak bias terhadap fitur dengan banyak nilai.

**Contoh (dataset Buys_Computer, 14 record):**

| Atribut | Gain(A) | SplitInfo(A) | GainRatio(A) | Ranking |
|---|---|---|---|---|
| age | 0.246 | 1.557 | 0.158 | 1★ |
| income | 0.029 | 1.557 | 0.019 | 4 |
| student | 0.151 | 1.000 | 0.151 | 2 |
| credit_rating | 0.048 | 1.000 | 0.048 | 3 |

---

### Gini Index (CART)

```
Gini(D) = 1 − Σᵢ pᵢ²

Binary case: Gini(D) = 2p(1−p)
```

**Setelah split:**
```
GiniA(D) = (|D₁|/|D|)×Gini(D₁) + (|D₂|/|D|)×Gini(D₂)
ΔGini(A) = Gini(D) − GiniA(D)  → pilih yang terbesar
```

**Karakteristik:**
- Nilai: 0 (murni) s.d. 1−1/m (maksimum)
- CART selalu menghasilkan **binary split**

---

### Ringkasan Rumus Decision Tree

| Formula | Nama | Algoritma |
|---|---|---|
| `H(S) = −Σpᵢ log₂pᵢ` | Entropy | Semua |
| `IG(A) = H(D) − InfoA(D)` | Information Gain | ID3 |
| `GainRatio(A) = Gain(A)/SplitInfo(A)` | Gain Ratio | C4.5 |
| `Gini(D) = 1 − Σpᵢ²` | Gini Index | CART |
| `Var(t) = (1/n)Σ(yᵢ−ȳ)²` | Variance Reduction | CART Regresi |

---

## 4.5 Algoritma Decision Tree

### Pseudocode BuildTree(D, Atribut)

```
INPUT: D = dataset, Atribut = himpunan atribut
OUTPUT: decision tree T

1. Buat node root N
2. IF semua tupel D ∈ kelas C THEN return N sebagai leaf berlabel C
3. IF Atribut = {} THEN return N sebagai leaf: majority class(D)
4. Pilih A* = best_split(D, Atribut) [Gain / GainRatio / Gini]
5. Label N dengan A*
6. FOR tiap nilai vⱼ dari A* DO
     Dⱼ = subset D di mana A* = vⱼ
     IF Dⱼ = {} THEN tambah leaf: majority class(D)
     ELSE tambah subtree: BuildTree(Dⱼ, Atribut−{A*})
7. return N
```

**Kompleksitas:**
- Training: O(|D|·|A|·depth)
- Prediksi: O(depth)

---

### Perbandingan Algoritma ID3 vs C4.5 vs CART

| Aspek | ID3 | C4.5 | CART |
|---|---|---|---|
| Kriteria split | Information Gain | Gain Ratio | Gini/MSE |
| Tipe split | Multi-way | Multi-way | **Binary** |
| Fitur numerik | ✗ | ✓ | ✓ |
| Missing values | ✗ | ✓ (proporsional) | ~ Parsial |
| Pruning | ✗ | ✓ REP | ✓ CCP |
| Regresi | ✗ | ✗ | ✓ |
| scikit-learn | ✗ | ✗ | ✓ |

**C5.0 (penerus C4.5):** Lebih cepat (hingga 300×), hemat memori, mendukung boosting, rule set lebih kompak.

---

## 4.6 Pruning (Pemangkasan)

### Pre-pruning (Early Stopping)

Hentikan pertumbuhan pohon **sebelum** terlalu spesifik:

| Parameter | Penjelasan | Saran |
|---|---|---|
| `max_depth` | Batas kedalaman maksimum | 3–5 sering cukup |
| `min_samples_split` | Min. obs untuk split | Default=20 |
| `min_samples_leaf` | Min. obs di leaf | 5–20 |
| `min_impurity_decrease` | Split hanya jika penurunan ≥ threshold | 0.001 |

**Kelemahan pre-pruning:** *Horizon effect* — menghentikan split yang saat ini tidak menguntungkan tapi di level berikutnya sangat informatif.

### Post-pruning (Setelah Tumbuh Penuh)

**Cost-Complexity Pruning (CCP — CART):**
```
R_α(T) = R(T) + α × |T|
```
- R(T) = error rate pohon
- |T| = jumlah leaf
- α = ccp_alpha: parameter regularisasi
- α=0 → pohon penuh; α besar → pohon lebih kecil

**Cara memilih α optimal (R):**
```r
printcp(dt_rpart)
dt_pruned <- prune(dt_rpart, cp = dt_rpart$cptable[which.min(dt_rpart$cptable[,'xerror']), 'CP'])
```

---

## 4.7 Contoh Perhitungan Manual Decision Tree

### Dataset Play Tennis (14 record)

**Entropy Total:**
```
H(D) = −(10/14)log₂(10/14) − (4/14)log₂(4/14) = 0.86312
```

**Gain per atribut:**

| Atribut | InfoA(D) | Gain | Ranking |
|---|---|---|---|
| OUTLOOK | 0.6046 | 0.2585 | 2 |
| TEMPERATURE | 0.6793 | 0.1838 | 3 |
| **HUMIDITY** | **0.4926** | **0.3705** | **1★** |
| WINDY | 0.8571 | 0.0060 | 4 |

**Hasil akhir pohon:**
```
              HUMIDITY
            /          \
         HIGH          NORMAL
           |              |
        OUTLOOK          YES
       /   |   \
  Cloudy Rainy  Sunny
    |      |      |
   YES   WINDY   NO
        /     \
     FALSE    TRUE
       |        |
      YES       NO
```

**Rules yang dihasilkan:**
```
IF Humidity = Normal → THEN Play = Yes
IF Humidity = High AND Outlook = Cloudy → THEN Play = Yes
IF Humidity = High AND Outlook = Sunny → THEN Play = No
IF Humidity = High AND Outlook = Rainy AND Windy = False → THEN Play = Yes
IF Humidity = High AND Outlook = Rainy AND Windy = True → THEN Play = No
```

---

## 4.8 Parameter Tuning Decision Tree (caret di R)

```r
library(rpart)
library(C50)
library(caret)

# Setup 10-fold CV
ctrl <- trainControl(
  method = 'cv', number = 10,
  classProbs = TRUE,
  summaryFunction = twoClassSummary,
  savePredictions = 'final'
)

# Tuning CART via CP
tune_grid_rpart <- expand.grid(cp = c(0, 0.001, 0.005, 0.01, 0.02, 0.05, 0.1))
dt_rpart <- train(
  status ~ ., data = train_df,
  method = 'rpart',
  trControl = ctrl,
  tuneGrid = tune_grid_rpart,
  metric = 'ROC',
  control = rpart.control(minsplit=20, minbucket=7, maxdepth=10)
)

# Tuning via maxdepth
tune_grid_depth <- expand.grid(maxdepth = c(2,3,4,5,6,7,8,10))
dt_depth <- train(status ~ ., data = train_df, method = 'rpart2',
                  trControl = ctrl, tuneGrid = tune_grid_depth)

# Tuning C5.0
tune_grid_c50 <- expand.grid(
  trials = c(1, 5, 10),
  model = c('tree', 'rules'),
  winnow = c(FALSE, TRUE)
)
dt_c50 <- train(status ~ ., data = train_df, method = 'C5.0',
                trControl = ctrl, tuneGrid = tune_grid_c50, metric = 'ROC')

# Implementasi dasar rpart
dt_model <- rpart(
  status ~ ., data = train_df, method = 'class',
  control = rpart.control(minsplit=20, minbucket=7, maxdepth=5, cp=0.01)
)
rpart.plot(dt_model, type=4, extra=101, under=TRUE)

# C5.0
c50_model <- C5.0(x = X_train, y = y_train, trials = 1, rules = FALSE)
summary(c50_model)
C5imp(c50_model)   # Feature importance
```

---

## 4.9 Persiapan Data untuk Decision Tree

| Kondisi Data | Perlu Ditangani? | Urgensi |
|---|---|---|
| Scaling numerik | ✗ TIDAK PERLU | — |
| Missing Data (CART/sklearn) | Perlu imputasi | WAJIB |
| Missing Data (C4.5/C5.0) | ✓ Native | AMAN |
| Pencilan (Outlier) | ✓ Robust | AMAN |
| Data Nominal | Perlu encode (sklearn) | SEDANG |
| Data Ordinal | Label Encoding | SEDANG |
| Data Campuran | ✓ Bisa ditangani | AMAN |
| Multikolinearitas | ✓ Tidak masalah | AMAN |

> 💡 DT paling sedikit membutuhkan preprocessing dibanding SVM, KNN, dan Naive Bayes!

---

## 4.10 Kelebihan & Kekurangan Decision Tree

### ✓ Kelebihan
1. **Paling mudah diinterpretasi** — pohon = aturan if-then yang dapat dibaca manusia
2. **Tidak perlu preprocessing** — tidak butuh scaling, robust terhadap outlier
3. **Non-parametric** — tidak mengasumsikan distribusi data apapun
4. **Menangani fitur campuran** — numerik dan kategorik dalam satu model
5. **Feature selection otomatis** — fitur tidak relevan tidak akan dipilih
6. **Menangani interaksi fitur** — split berurutan = interaksi fitur implisit
7. **Cepat untuk prediksi** — O(depth) per prediksi
8. **Fondasi Ensemble** — dasar Random Forest, GBM, XGBoost

### ✗ Kekurangan
1. **Sangat mudah overfit** — tanpa pruning, hafal semua training data
2. **Tidak stabil (high variance)** — perubahan kecil data → pohon berubah drastis
3. **Boundary kaku** — piecewise constant, tidak smooth untuk regresi
4. **Bias terhadap fitur high-cardinality** — IG bias jika pakai ID3
5. **Performa kalah dari ensemble** — satu DT << Random Forest

### Kapan Gunakan Decision Tree?
- ✓ Interpretasi adalah kebutuhan utama (dokter, analis kebijakan, auditor)
- ✓ Perlu output berupa aturan keputusan yang bisa menjadi SOP
- ✓ Data campuran tanpa waktu preprocessing
- ✓ Sebagai baseline sebelum ensemble
- ✗ Jangan gunakan jika akurasi maksimal adalah prioritas utama

---

## 4.11 Aplikasi Decision Tree di Official Statistics

| Aplikasi | Contoh |
|---|---|
| Klasifikasi Kemiskinan RT | Aturan kebijakan langsung; bisa jadi SOP petugas lapangan |
| Skrining Risiko Stunting | Pohon keputusan untuk kader Posyandu |
| Zonasi Daerah Tertinggal | CHAID/C4.5 untuk klasifikasi kecamatan |
| Quality Control Data Sensus | Deteksi inkonsistensi: "Jika usia < 15 TAPI status menikah = Ya → error" |

---

# PERTEMUAN 4B — Naive Bayes Classifier

## 4B.1 Konsep Dasar Teorema Bayes

**Teorema Bayes:**
```
P(C|X) = P(X|C) × P(C) / P(X)
```

| Komponen | Nama | Makna |
|---|---|---|
| P(C\|X) | **Posterior** | Probabilitas kelas C setelah melihat data X |
| P(X\|C) | **Likelihood** | Seberapa mungkin data X muncul jika kelas adalah C |
| P(C) | **Prior** | Probabilitas kelas C sebelum melihat data |
| P(X) | **Evidence** | Probabilitas data X (normalisasi, konstan untuk semua kelas) |

---

## 4B.2 Ide Naive Bayes

**Asumsi "naif":** Semua fitur **INDEPENDEN** secara kondisional diberikan kelas:
```
P(X|C) = P(x₁|C) × P(x₂|C) × ... × P(xₙ|C)
```

**Klasifikasi:**
```
Ĉ = argmax_C [ P(C) × ∏ P(xⱼ|C) ]
```

**Mengapa "Naive"?** Karena asumsi independensi jarang terpenuhi di dunia nyata (tinggi badan dan berat badan berkorelasi, pendapatan dan pendidikan berkorelasi), namun model tetap efektif.

---

## 4B.3 Jenis-jenis Naive Bayes

| Varian | Formula | Data | Kapan |
|---|---|---|---|
| **Gaussian NB** | `P(xⱼ\|C) = (1/√2πσ²) × exp(−(x−μ)²/2σ²)` | Numerik kontinu | Default untuk fitur numerik |
| **Multinomial NB** | `P(X\|C) ∝ ∏ θⱼ^xⱼ` | Frekuensi/count | Data teks (TF-IDF) |
| **Bernoulli NB** | `P(X\|C) = ∏ P(xⱼ\|C)^xⱼ × (1−P(xⱼ\|C))^(1−xⱼ)` | Biner (0/1) | Fitur biner, survey data |
| **Complement NB** | Estimasi dari data di luar kelas C | Count, imbalanced | Data imbalanced |

---

## 4B.4 Zero Probability & Laplace Smoothing

### Masalah Zero Probability

Jika suatu kombinasi fitur-kelas tidak muncul di training data:
```
P(x='PNS'|C='Miskin') = 0/n = 0
→ P(C|X) ∝ P(C) × 0 × ... = 0  ← SALAH!
```

### Solusi: Laplace Smoothing (Add-α)

```
P(xⱼ=v|C) = (count(xⱼ=v, C) + α) / (count(C) + α × |V|)
```

- α = smoothing parameter (default = 1)
- |V| = jumlah nilai unik fitur xⱼ
- α=1 → Laplace Smoothing
- 0 < α < 1 → Lidstone Smoothing

**Contoh:** Fitur Pekerjaan punya 3 nilai (Petani, Buruh, PNS), 4 data Miskin:
```
Tanpa smoothing: P(PNS|Miskin) = 0
Dengan Laplace (α=1): P(PNS|Miskin) = (0+1)/(4+3) = 1/7 ≈ 0.143
```

### Log Probability (numerical stability)

Perkalian banyak probabilitas kecil → underflow numerik. Solusi:
```
log P(C|X) ∝ log P(C) + Σ log P(xⱼ|C)
```

---

## 4B.5 Perhitungan Manual Naive Bayes

### Dataset (n=8 RT, Klasifikasi Kemiskinan)

| No | Pekerjaan KRT | Pendidikan | Akses Air | Status |
|---|---|---|---|---|
| 1 | Petani | Rendah | Tidak | Miskin |
| 2 | Petani | Rendah | Ya | Miskin |
| 3 | Buruh | Rendah | Tidak | Miskin |
| 4 | Buruh | Rendah | Tidak | Miskin |
| 5 | PNS | Tinggi | Ya | Tidak Miskin |
| 6 | Buruh | Tinggi | Ya | Tidak Miskin |
| 7 | PNS | Tinggi | Ya | Tidak Miskin |
| 8 | Petani | Tinggi | Ya | Tidak Miskin |

**Prior:** P(Miskin) = P(Tidak Miskin) = 4/8 = 0.500

**Query baru:** Pekerjaan=Petani, Pendidikan=Rendah, Akses Air=Tidak

### Langkah 1: Likelihood dengan Laplace Smoothing (α=1)

**Kelas MISKIN (n=4, |V|_Pekerjaan=3, |V|_Pendidikan=2, |V|_Air=2):**

| Fitur | Hitung | P(·\|Miskin) |
|---|---|---|
| Petani | (2+1)/(4+3) | 0.429 |
| Buruh | (2+1)/(4+3) | 0.286 |
| PNS | (0+1)/(4+3) | 0.143 |
| Rendah | (4+1)/(4+2) | 0.833 |
| Tinggi | (0+1)/(4+2) | 0.167 |
| Air=Tidak | (3+1)/(4+2) | 0.667 |
| Air=Ya | (1+1)/(4+2) | 0.333 |

**Kelas TIDAK MISKIN (n=4):**

| Fitur | P(·\|Tidak Miskin) |
|---|---|
| Petani | (1+1)/(4+3) = 0.286 |
| Rendah | (0+1)/(4+2) = 0.167 |
| Air=Tidak | (0+1)/(4+2) = 0.167 |

### Langkah 2: Hitung Posterior

```
P(Miskin|X) ∝ 0.500 × 0.429 × 0.833 × 0.667 = 0.1194
P(TdkMiskin|X) ∝ 0.500 × 0.286 × 0.167 × 0.167 = 0.00399
```

### Langkah 3: Normalisasi

```
P(Miskin|X) = 0.1194 / (0.1194 + 0.00399) = 0.968
```
**→ PREDIKSI: MISKIN** ✓

---

## 4B.6 Parameter Tuning Naive Bayes (caret di R)

```r
library(caret)
library(naivebayes)
library(klaR)
library(e1071)

ctrl <- trainControl(
  method = 'cv', number = 10,
  classProbs = TRUE,
  summaryFunction = twoClassSummary,
  savePredictions = 'final'
)

# Gaussian NB — tuning usekernel + laplace + adjust
grid_gnb <- expand.grid(
  usekernel = c(FALSE, TRUE),
  laplace   = c(0, 0.5, 1, 2),
  adjust    = c(0.5, 1, 1.5, 2)
)

nb_model <- train(
  status ~ ., data = train_df,
  method = 'naive_bayes',
  trControl = ctrl,
  tuneGrid = grid_gnb,
  metric = 'ROC'
)

print(nb_model$bestTune)
plot(nb_model)

# Prediksi & probabilitas
pred_nb <- predict(nb_model, newdata = test_df)
prob_nb <- predict(nb_model, newdata = test_df, type = 'prob')
```

**Parameter tuning per varian:**

| Varian | Parameter | Rentang |
|---|---|---|
| Gaussian NB | `usekernel` | FALSE/TRUE |
| Gaussian NB | `adjust` | 0.5–2.0 |
| naivebayes pkg | `laplace` | 0–5 |
| Bernoulli/klaR | `fL` (Laplace factor) | 0–5 |

---

## 4B.7 Persiapan Data untuk Naive Bayes

| Kondisi | Perlu Ditangani? | Urgensi |
|---|---|---|
| Missing Data | YA — wajib imputasi (mean/median/modus) | TINGGI |
| Outlier | Bergantung varian — GNB sensitif | SEDANG (GNB) |
| Skala Numerik Berbeda | GNB: TIDAK PERLU | TIDAK PERLU |
| Data Nominal | YA — Label Encoding | SEDANG |
| Data Ordinal | YA — Label/Ordinal Encoding | SEDANG |
| Data Campuran | Bisa — Mixed NB | BISA DITANGANI |
| Multikolinearitas | Problematik | - |

> 💡 Keunggulan NB: Tidak perlu scaling! Lebih toleran terhadap data terbatas.

---

## 4B.8 Kelebihan & Kekurangan Naive Bayes

### ✓ Kelebihan
1. Training & prediksi sangat cepat — O(n×d×k)
2. Bekerja baik dengan data sedikit (efektif bahkan n=100)
3. Menghasilkan probabilitas langsung
4. Incremental learning (update tanpa retrain)
5. Robust untuk data teks & high-dimensional
6. Tidak perlu scaling (GNB)
7. Multi-class native
8. Interpretasi mudah — probabilitas kondisional langsung bermakna

### ✗ Kekurangan
1. Asumsi independensi jarang terpenuhi
2. Probabilitas sering tidak terkalibrasi (terlalu ekstrem)
3. Zero frequency tanpa smoothing
4. Tidak menangkap interaksi fitur
5. GNB mengasumsikan distribusi Gaussian
6. Tidak seoptimal boosting untuk tabular data

### Penanganan Overfitting (Jarang Terjadi)
NB secara natural **resistant** terhadap overfitting:
- Naikkan α → lebih banyak smoothing
- Untuk GNB: naikkan `var_smoothing`
- Kurangi jumlah fitur

### Penanganan Imbalance
1. Sesuaikan prior P(C): `priors=[0.2, 0.8]`
2. `fit_prior=False` → uniform prior
3. SMOTE + NB
4. Complement NB (lebih robust untuk imbalance)

---

## 4B.9 Interpretasi Naive Bayes

**Keunggulan unik NB:** Semua parameter adalah probabilitas kondisional P(xⱼ=v|C) yang langsung bermakna.

**Baca parameter model:**
```r
model_gnb$tables  # Tampilkan P(x|C) untuk setiap fitur
# Contoh output:
# $Pekerjaan
#         Miskin    Tidak
# Buruh    0.286    0.286
# Petani   0.429    0.286
# PNS      0.143    0.429
```

**Log-Odds Ratio per fitur:**
```
log-odds(xⱼ=v) = log P(xⱼ=v|C₁) − log P(xⱼ=v|C₀)
```
- Positif → fitur mendukung kelas C₁
- Negatif → fitur menolak kelas C₁

**Seleksi variabel untuk NB:**
1. Mutual Information (MI): `sklearn.feature_selection.mutual_info_classif`
2. Chi-Square test
3. Log-likelihood ratio per fitur
4. **Hapus fitur korelasi tinggi |r| > 0.8** (lebih kritis untuk NB karena asumsi independensi!)
---

# PERTEMUAN 5 — Klasifikasi Lanjutan: KNN, SVM & Ensemble

## 5.1 K-Nearest Neighbors (KNN)

### Definisi & Ide Utama

> *"Ceritakan siapa teman-temanmu, dan aku tahu siapa kamu."*

KNN adalah algoritma **lazy learning** (instance-based): tidak membangun model eksplisit — hanya menyimpan semua data training. Prediksi dibuat berdasarkan K data terdekat.

- **KNN Klasifikasi:** Label = kelas **MAYORITAS** dari K tetangga
- **KNN Regresi:** Nilai = **RATA-RATA** nilai K tetangga

---

### Konsep-Konsep Penting KNN

| Konsep | Penjelasan |
|---|---|
| **Lazy Learning** | Training O(1), Prediksi O(n·d) |
| **Metrik Jarak** | Cara mengukur kedekatan antar titik |
| **Nilai K** | Parameter terpenting — K kecil = overfit, K besar = underfit |
| **Voting** | Uniform (sama) atau distance-weighted (lebih dekat = bobot lebih besar) |
| **Curse of Dimensionality** | Di dimensi tinggi, semua titik cenderung "sama jauhnya" |
| **Decision Boundary** | Nonlinear dan adaptif terhadap distribusi data lokal |

---

### Metrik Jarak

| Metrik | Formula | Cocok Untuk | Tidak Cocok |
|---|---|---|---|
| **Euclidean** | √Σ(xᵢ−yᵢ)² | Fitur numerik kontinu, distribusi normal | Skala sangat berbeda |
| **Manhattan** | Σ\|xᵢ−yᵢ\| | Sparse, dimensi tinggi, **robust outlier** | Data kontinu presisi tinggi |
| **Minkowski** | (Σ\|xᵢ−yᵢ\|ᵖ)^(1/p) | Generalisasi (p=1→Manhattan, p=2→Euclidean) | Pemilihan p tidak tepat |
| **Hamming** | Σ(xᵢ≠yᵢ)/n | **Data kategorik/biner** | Data numerik kontinu |
| **Cosine** | 1−(x·y)/(‖x‖‖y‖) | Data teks (TF-IDF), vektor dokumen | Data dengan magnitude penting |

**Perbandingan Euclidean vs Manhattan:**
```
A=(0,0), B=(3,4):
Euclidean = √(9+16) = 5 (jarak garis lurus)
Manhattan = 3+4 = 7 (jarak jalan kota)
```

---

### Pemilihan Nilai K

| K | Kondisi | Konsekuensi |
|---|---|---|
| K=1 | Overfit | Training accuracy 100%, test rendah, Voronoi diagram |
| K=√n | Optimal (titik awal) | Aturan praktis, coba sebagai baseline |
| K=n | Underfit | Selalu prediksi kelas mayoritas |

**Strategi Pemilihan K Optimal:**
1. Siapkan data dengan scaling terlebih dahulu
2. Coba K = 1, 3, 5, 7, 9, ..., 2·√n (selalu **ganjil** untuk binary)
3. Evaluasi akurasi/F1 menggunakan k-fold cross-validation
4. Plot *elbow curve* K vs error rate, pilih K di *elbow*

---

### Perhitungan Manual KNN (K=3, Euclidean)

**Data:** Prediksi Status Gizi Balita, 6 data training (sudah Z-score):

| ID | x₁ BB/U | x₂ TB/U | Label |
|---|---|---|---|
| A | -2.0 | -1.8 | Gizi Buruk |
| B | -1.5 | -1.2 | Gizi Buruk |
| C | -0.5 | -0.3 | Gizi Kurang |
| D | 0.0 | 0.2 | Gizi Baik |
| E | 0.8 | 0.9 | Gizi Baik |
| F | 1.5 | 1.4 | Gizi Lebih |

**Query Q = (−0.8, −0.6)**

**Langkah 1: Hitung Jarak Euclidean**

| ID | Perhitungan | Jarak | Tetangga? |
|---|---|---|---|
| A | √(1.44+1.44) | 1.697 | ✓ K-2 |
| B | √(0.49+0.36) | 0.922 | ✓ **K-1** |
| **C** | **√(0.09+0.09)** | **0.424** | **✓ Terdekat (K-3)** |
| D | √(0.64+0.64) | 1.131 | — |
| E | √(2.56+2.25) | 2.193 | — |
| F | √(5.29+4.00) | 3.048 | — |

**Langkah 2: Urutkan → Ambil 3 Terdekat**

| Ranking | ID | Jarak | Label |
|---|---|---|---|
| 1 (Terdekat) | C | 0.424 | Gizi Kurang |
| 2 | B | 0.922 | Gizi Buruk |
| 3 | A | 1.697 | Gizi Buruk |

**Langkah 3: Voting Mayoritas**
```
Gizi Buruk: 2 suara | Gizi Kurang: 1 suara
→ Prediksi: GIZI BURUK (2 > 1)
```

---

### Persiapan Data untuk KNN

| Kondisi | Urgensi | Metode |
|---|---|---|
| Skala Numerik Berbeda | 🔴 **PALING KRITIS** | StandardScaler/MinMaxScaler WAJIB |
| Outlier | 🔴 SANGAT TINGGI | IQR clipping, RobustScaler |
| Missing Data | 🔴 TINGGI | KNNImputer atau imputasi biasa |
| Data Nominal | 🟡 SEDANG | OHE + pertimbangkan Hamming |
| Data Ordinal | 🟡 SEDANG | Ordinal Encoding + Scaling |
| Multikolinearitas | 🟡 SEDANG | PCA sebelum KNN |

> ⚠️ **KNN lebih sensitif terhadap skala dibanding SVM!** Fitur dengan satuan besar mendominasi jarak seluruhnya.

**Pilihan Scaler:**

| Scaler | Formula | Gunakan Jika |
|---|---|---|
| StandardScaler | z = (x−μ)/σ | Data mendekati normal, default KNN |
| MinMaxScaler | x' = (x−min)/(max−min) | Tidak ada outlier ekstrem |
| RobustScaler | x' = (x−Q2)/(Q3−Q1) | **Banyak outlier — sangat direkomendasikan** |

> ⚠️ **Fit scaler HANYA pada data training** → transform test dengan scaler yang sama (hindari data leakage)!

---

### KNN Imputer

KNN punya keunikan: bisa digunakan untuk imputasi missing values!

```r
# R
library(VIM)
data_imp <- kNN(data_raw, k=5)
```

---

### Implementasi KNN di R

```r
library(class)
library(caret)
library(VIM)

# Preprocessing: scaling
preProc <- preProcess(X_train, method = c('center', 'scale'))
X_tr <- predict(preProc, X_train)
X_te <- predict(preProc, X_test)

# KNN manual (class package)
pred_knn <- knn(train = as.matrix(X_tr), test = as.matrix(X_te),
                cl = y_train, k = 5)

# KNN dengan caret (tuning K)
ctrl <- trainControl(method='cv', number=5, classProbs=TRUE)
knn_model <- train(
  status_gizi ~ .,
  data = cbind(X_tr, y_train),
  method = 'knn',
  trControl = ctrl,
  metric = 'Kappa',
  tuneGrid = expand.grid(k = seq(1, 21, 2))
)
plot(knn_model)
```

---

### Kelebihan & Kekurangan KNN

#### ✓ Kelebihan
- Sangat mudah dipahami dan diimplementasi
- Non-parametric & non-linear — menangkap pola arbitrarily complex
- Training langsung (lazy learning) — penambahan data tidak perlu retraining
- Efektif untuk multi-class
- Adaptif secara lokal

#### ✗ Kekurangan
- **Lambat saat prediksi** — O(n·d) per prediksi
- **Memori tinggi** — semua data training harus disimpan
- **Sensitif skala** (paling kritis!)
- **Curse of dimensionality** — di dimensi tinggi, konsep tetangga terdekat kehilangan makna
- Sensitif terhadap noise & outlier
- Tidak menghasilkan probabilitas yang terkalibrasi

---

## 5.2 Support Vector Machine (SVM)

### Definisi

SVM adalah algoritma supervised learning yang mencari **hyperplane optimal** untuk memisahkan data ke dalam kelas, dengan memaksimalkan **margin** antara kelas.

**Kegunaan:** Klasifikasi (binary & multi-class), Regresi (SVR), Deteksi anomali.

---

### Konsep Kunci SVM

#### 1. Hyperplane & Margin

```
Hyperplane: w·x + b = 0
Keputusan: ŷ = sign(w·x + b)
Margin = 2 / ‖w‖
```

- **Hyperplane** = batas keputusan: titik (1D), garis (2D), bidang (3D+)
- **Margin** = jarak antara hyperplane dengan titik data terdekat dari masing-masing kelas
- **SVM:** Cari hyperplane yang **memaksimalkan margin** → generalisasi lebih baik

#### 2. Support Vectors

- Titik data **paling dekat** dengan hyperplane
- **Hanya support vectors** yang menentukan posisi dan orientasi hyperplane
- Biasanya hanya sebagian kecil dari total data
- Prediksi bergantung hanya pada support vectors → efisien

```
Positive margin plane:  w·x + b = +1
Hyperplane:             w·x + b = 0
Negative margin plane:  w·x + b = −1
Margin total = 2 / ‖w‖
```

#### 3. Hard Margin vs Soft Margin (Parameter C)

| | Hard Margin | Soft Margin |
|---|---|---|
| Asumsi | Data linearly separable | Tidak harus linearly separable |
| Pelanggaran | Tidak ada | Diizinkan (slack ξᵢ) |
| Rumusan | min ½‖w‖² s.t. yᵢ(w·xᵢ+b) ≥ 1 | min ½‖w‖² + C·Σξᵢ |
| C kecil | — | Margin lebar, toleran error |
| C besar | — | Margin sempit, sedikit error |

#### 4. Kernel Trick

**Ide:** Proyeksikan data ke ruang dimensi lebih tinggi di mana data linearly separable, tanpa menghitung koordinat eksplisit.

| Kernel | Formula | Parameter | Cocok Untuk |
|---|---|---|---|
| **Linear** | K(xᵢ,xₜ) = xᵢ·xₜ | — | Data linearly separable, data teks |
| **Polynomial** | K(xᵢ,xₜ) = (γxᵢ·xₜ+r)ᵈ | γ, r, d | Interaksi fitur, NLP |
| **RBF/Gaussian** | K(xᵢ,xₜ) = exp(−γ‖xᵢ−xₜ‖²) | γ | **Default — cocok untuk sebagian besar kasus** |
| **Sigmoid** | K(xᵢ,xₜ) = tanh(γxᵢ·xₜ+r) | γ, r | Neural network-like |

> 💡 **Tips:** Mulai selalu dengan **RBF Kernel + tuning C dan γ**. Gunakan Linear untuk data teks (high-dimensional).

---

### Contoh Perhitungan Manual SVM

**Data:** Prediksi Kelulusan Siswa (2 fitur, Linear SVM)

| ID | x₁ (Nilai) | x₂ (Kehadiran) | Label y |
|---|---|---|---|
| A (SV) | -2 | 0 | −1 (Tidak Lulus) |
| B | -2 | -1 | −1 |
| C (SV) | 0 | 2 | +1 (Lulus) |
| D | 1 | 2 | +1 |

**Langkah 1: Persamaan dari Support Vectors**
```
C=(0,2) → 2w₂ + b = 1    ...(i)
A=(−2,0) → −2w₁ + b = −1  ...(ii)
```

**Langkah 2: Selesaikan (asumsikan simetri w₁=w₂=w)**
```
(i): 2w + b = 1
(ii): −2w + b = −1
Kurangi: 4w = 2 → w = 0.5
Substitusi: b = 1 − 2(0.5) = 0
```

**Langkah 3: Hyperplane & Margin**
```
w = (0.5, 0.5), b = 0
Hyperplane: 0.5x₁ + 0.5x₂ = 0  →  x₁ + x₂ = 0
‖w‖ = √(0.5² + 0.5²) = √0.5 ≈ 0.707
Margin = 2 / ‖w‖ = 2 / 0.707 ≈ 2.83
```

**Langkah 4: Verifikasi**
```
A=(−2,0): 0.5(−2)+0.5(0) = −1 → sign(−1) = −1 ✓
C=(0,2): 0.5(0)+0.5(2) = +1 → sign(+1) = +1 ✓
```

---

### Parameter Tuning SVM

| Parameter | Default | Keterangan |
|---|---|---|
| **C** | 1.0 | Regularisasi: C kecil=margin lebar, C besar=margin sempit |
| **kernel** | 'rbf' | 'linear', 'poly', 'rbf', 'sigmoid' |
| **gamma** | 'scale' | Bandwidth RBF: besar=overfit, kecil=underfit |
| **degree** | 3 | Derajat polinomial (hanya kernel='poly') |

**Strategi tuning:** kernel → C → gamma (jika RBF/poly)

---

### Implementasi SVM di R

```r
library(e1071)
library(caret)

ctrl <- trainControl(
  method='cv', number=5,
  classProbs=TRUE,
  summaryFunction=twoClassSummary
)

svm_model <- train(
  miskin ~ ., data = train_df,
  method = 'svmRadial',
  trControl = ctrl,
  metric = 'ROC',
  tuneGrid = expand.grid(C = c(0.1, 1, 10), sigma = c(0.01, 0.1))
)

pred <- predict(svm_model, test_df)
confusionMatrix(pred, y_test)
```

---

### Persiapan Data SVM

| Kondisi | Urgensi | Metode |
|---|---|---|
| Scaling (numerik) | 🔴 TINGGI | Z-score atau Min-Max WAJIB |
| Missing Data | 🔴 TINGGI | Imputasi (tidak native) |
| Outlier | 🔴 TINGGI | IQR/Z-score/Isolation Forest |
| Data Nominal | 🟡 SEDANG | OHE |
| Data Ordinal | 🟡 SEDANG | Label Encoding + scaling |
| Multikolinearitas | 🟢 RENDAH | PCA atau hapus korelasi > 0.9 |

---

### Kelebihan & Kekurangan SVM

#### ✓ Kelebihan
1. Efektif di high-dimensional space
2. Memory efficient (hanya support vectors)
3. Fleksibel dengan berbagai kernel
4. Robust terhadap overfitting (maximum margin)
5. Solusi optimal global (konveks)
6. Cocok untuk data kecil-menengah

#### ✗ Kekurangan
1. Lambat untuk data besar (O(n²)−O(n³))
2. Sensitif terhadap scaling (wajib)
3. Tuning parameter kompleks (C, gamma, kernel)
4. Black box (terutama kernel RBF)
5. Tidak menangani missing/kategorik secara native

---

## 5.3 Ensemble Learning

### Konsep: Dari Banyak Model Lemah ke Satu yang Kuat

> *"Seratus dokter awam rata-rata lebih akurat dari satu dokter spesialis tunggal."* — Wisdom of Crowds

**Kunci keberhasilan ensemble:**
1. **Diversity** — model-model penyusun harus berbeda satu sama lain
2. **Accuracy** — setiap weak learner minimal lebih baik dari tebakan acak
3. **Aggregation** — cara menggabungkan: voting, averaging, weighted, stacking

---

### BAGGING vs BOOSTING

| Aspek | **BAGGING** | **BOOSTING** |
|---|---|---|
| Proses | **PARALEL** | **SEKUENSIAL** |
| Tujuan | Kurangi **VARIANCE** | Kurangi **BIAS** |
| Data Sampling | Bootstrap (with replacement) | Pembobotan data |
| Dependensi | Model tidak bergantung | Model berikutnya bergantung pada sebelumnya |
| Agregasi | Voting/rata-rata sederhana | Weighted vote |
| Overfitting | Rendah — tidak overfit dengan B bertambah | Lebih tinggi — perlu regularisasi |
| Kecepatan | **Cepat (paralel)** | Lebih lambat (sekuensial) |
| Noise/Outlier | **Lebih robust** | Sensitif |
| Model Utama | Random Forest, Extra Trees | AdaBoost, GBM, XGBoost, LightGBM |

---

### Bootstrap Sampling

**Definisi:** Resampling **dengan pengembalian** dari data asli untuk membuat dataset baru berukuran sama.

```
P(satu data tidak terpilih dalam bootstrap) = (1−1/n)ⁿ → e⁻¹ ≈ 0.368
P(terpilih setidaknya sekali) = 1 − 0.368 = 0.632 (≈63.2%)
```

**Out-of-Bag (OOB):** ~36.8% data yang tidak terpilih → digunakan sebagai validasi internal tanpa perlu validation set terpisah!

---

### Random Forest

**= Bagging + Feature Randomness**

**Inovasi utama:** Di setiap node split, hanya **m fitur acak** yang dipertimbangkan (bukan semua p fitur):
- Klasifikasi: m = √p
- Regresi: m = p/3

**Mengapa perlu feature randomness?**
- Tanpa feature randomness, pohon berkorelasi tinggi (fitur kuat selalu dipilih)
- Korelasi antar pohon mempengaruhi variance: `Var(rata-rata) = ρσ² + (1−ρ)σ²/B`
- ↓ korelasi (ρ) → ↓ variance ensemble

**Parameter penting:**

| Parameter | Keterangan |
|---|---|
| `n_estimators` (B) | Jumlah pohon. Lebih banyak = lebih stabil. Tidak overfit. |
| `max_features` (m) | Fitur per split. Kunci keberagaman. |
| `max_depth` | Kedalaman pohon. Default: tidak dibatasi. |
| `oob_score=TRUE` | Gratis validasi OOB! |

```r
library(randomForest)
rf_model <- randomForest(
  status ~ ., data = train_df,
  ntree = 100, mtry = floor(sqrt(ncol(train_df)-1)),
  importance = TRUE
)
varImpPlot(rf_model)
```

**Extra Trees (Extremely Randomized Trees):**  
= Random Forest + **Random Splits** (threshold acak, tidak dicari optimal)  
→ Lebih cepat, lebih keberagaman, cocok untuk data besar dengan fitur kontinu

---

### Boosting: AdaBoost

**Algoritma:**
```
1. wᵢ⁽¹⁾ = 1/n untuk semua data
2. Latih weak learner hₜ(x)
3. εₜ = Σᵢ wᵢ·𝟙[hₜ(xᵢ)≠yᵢ]   (weighted error)
4. αₜ = ½ ln((1−εₜ)/εₜ)      (bobot model)
5. Update: wᵢ⁽ᵗ⁺¹⁾ ∝ wᵢ⁽ᵗ⁾·exp(−αₜyᵢhₜ(xᵢ))
6. Final: H(x) = sign(Σ αₜhₜ(x))
```

**Kapan terbaik:** Data bersih, ukuran sedang, klasifikasi binary sederhana.  
**Kelemahan:** Sangat sensitif terhadap outlier (outlier mendapat bobot sangat besar).

---

### Boosting: GBM (Gradient Boosting Machine)

**Ide:** Gradient Descent di Function Space — setiap pohon baru memprediksi **pseudo-residual** (gradient negatif dari loss function).

```
Pseudo-residual (MSE): rᵢₜ = −∂L(yᵢ,F(xᵢ))/∂F(xᵢ) = yᵢ − F_{t-1}(xᵢ)
Update: Fₜ(x) = Fₜ₋₁(x) + η·fₜ(x)  (η = learning rate)
```

---

### XGBoost

**"XGBoost memenangkan lebih dari separuh kompetisi structured/tabular data di Kaggle 2014–2018"**

**Inovasi atas GBM standar:**
1. **Regularisasi L1+L2** — Ω(f) = γT + ½λ‖w‖² (mencegah overfitting eksplisit)
2. **Approximate Split Finding** — quantile sketch, tidak cek semua threshold
3. **Native Missing Values** — belajar arah split terbaik untuk missing values
4. **Parallel & Distributed** — paralelisasi di level node, jauh lebih cepat
5. **Early Stopping** — hentikan jika validation score tidak meningkat

**Parameter penting:**

| Parameter | Rentang | Keterangan |
|---|---|---|
| `learning_rate` (η) | 0.01–0.3 | Shrinkage per pohon |
| `n_estimators` | 100–3000 | Jumlah pohon |
| `max_depth` | 3–10 | Kedalaman pohon |
| `min_child_weight` | 1–10 | Min. sum weight per leaf |
| `subsample` | 0.5–1.0 | Fraksi data per pohon |
| `colsample_bytree` | 0.5–1.0 | Fraksi fitur per pohon |
| `reg_alpha` (L1) | 0–1 | Regularisasi L1 |
| `reg_lambda` (L2) | 1–10 | Regularisasi L2 |

---

### LightGBM

**Inovasi Microsoft (2017):**
1. **Histogram-based Split** — bin ke k bucket → O(#bins) vs O(n log n)
2. **Leaf-wise Tree Growth** — pilih leaf dengan gain terbesar (lebih akurat, tapi perlu atur `max_depth`!)
3. **GOSS** — simpan data gradient besar, sample acak gradient kecil
4. **EFB** — bundling fitur sparse
5. **Native Kategorik** — tidak perlu OHE

**10–20× lebih cepat dari XGBoost untuk dataset besar!**

---

### CatBoost

**Inovasi Yandex (2017):**
1. **Ordered Boosting** — tidak ada target leakage
2. **Native Kategorik Encoding** — Ordered Target Statistics (tidak perlu OHE)
3. **Symmetric Trees** — setiap level split sama di semua node
4. **Minimal Preprocessing** — tidak perlu scaling, handle missing native

---

### Perbandingan Model Ensemble

| Model | Tipe | Kec. Train | Kategorik | Missing | Overfit Risk | Tuning |
|---|---|---|---|---|---|---|
| **Random Forest** | Bagging | ⚡⚡⚡ | ✗ OHE | ~ | 🟢 Rendah | 🟢 Rendah |
| **Extra Trees** | Bagging | ⚡⚡⚡⚡ | ✗ OHE | ~ | 🟢 Rendah | 🟢 Rendah |
| AdaBoost | Boosting | ⚡⚡ | ✗ OHE | ✗ | 🟡 Sedang | 🟢 Rendah |
| GBM | Boosting | ⚡ | ✗ OHE | ✗ | 🟡 Sedang | 🟡 Sedang |
| **XGBoost** | Boosting | ⚡⚡⚡ | ✗ OHE | ✓✓ | 🟡 Sedang | 🔴 Tinggi |
| **LightGBM** | Boosting | ⚡⚡⚡⚡ | ✓ Baik | ✓ | 🟡 Sedang | 🔴 Tinggi |
| CatBoost | Boosting | ⚡⚡ | ✓✓ Terbaik | ✓ | 🟡 Sedang | 🟡 Sedang |

---

### Decision Guide: Kapan Gunakan Model Mana?

| Situasi | Rekomendasi | Alasan |
|---|---|---|
| Baseline cepat, data apapun | **Random Forest** | Robust, tidak perlu tuning |
| Dataset besar (>100K) | **LightGBM** | Histogram + GOSS = jauh lebih cepat |
| Banyak fitur kategorik | **CatBoost** | Ordered TS encoding tanpa leakage |
| Akurasi maksimal | **XGBoost / LightGBM** | Regularisasi kuat, tuning mendalam |
| Missing values banyak | **XGBoost** | Native missing value handling terbaik |
| Data noisy / outlier banyak | **Random Forest** | Averaging meredam noise |
| Imbalanced data | **XGBoost** (scale_pos_weight) | Fleksibel menangani imbalance |
| Interpretasi sangat penting | **Random Forest** + SHAP | Feature importance stabil |
| Data kecil (< 1000 baris) | **Random Forest** | Boosting rentan overfit di data kecil |

---

### Persiapan Data untuk Model Ensemble

| Kondisi | RF/Extra Trees | XGBoost | LightGBM | CatBoost |
|---|---|---|---|---|
| Scaling | ✗ Tidak perlu | ✗ Tidak perlu | ✗ Tidak perlu | ✗ Tidak perlu |
| Missing Values | Imputasi | ✓ Native | ✓ Native | ✓ Native |
| Kategorik | OHE / Label Enc | OHE wajib | Integer cukup | ✓ String langsung! |
| Outlier | Robust (bootstrap) | L1/L2 membantu | Cukup robust | Cukup robust |
| Multikolinearitas | Aman | Aman | Aman | Aman |
| Imbalanced | `class_weight='balanced'` | `scale_pos_weight` | `is_unbalance=True` | `class_weights` |

> 💡 **Keunggulan model tree-based ensemble: TIDAK memerlukan scaling** — berbeda fundamental dari SVM dan KNN!

---

### Feature Importance & SHAP

**Feature Importance (Bawaan):**
- **MDI (Mean Decrease Impurity)** — rata-rata penurunan impurity. Cepat tapi bias untuk high-cardinality.
- **MDA (Mean Decrease Accuracy / Permutation)** — acak nilai fitur → ukur penurunan akurasi. Lebih akurat.
- **Gain-based** (XGBoost/LightGBM) — average gain dari split.

**SHAP (SHapley Additive exPlanations) — Gold Standard:**
- Konsisten, akurat, berbasis teori game Shapley
- TreeSHAP untuk tree ensemble: O(TL²D) — efisien
- Visualisasi: summary plot, force plot, dependency plot, waterfall plot

---

### Penanganan Overfitting per Model

| Model | Cara Utama |
|---|---|
| **Random Forest** | `max_depth ↓`, `min_samples_leaf ↑`, `max_features ↓`, tambah pohon |
| **XGBoost** | `learning_rate ↓` + `n_estimators ↑`, `max_depth ↓`, early stopping |
| **LightGBM** | `num_leaves ↓` (kritis!), `min_child_samples ↑`, early stopping |
| **CatBoost** | `depth ↓`, `iterations` via early stop, `l2_leaf_reg ↑` |

**Strategi universal:** `learning_rate` kecil + banyak estimators + **early stopping** + cross-validation.

---

## 5.4 Ringkasan Perbandingan Semua Model Klasifikasi

| Aspek | Decision Tree | Naive Bayes | KNN | SVM | Random Forest |
|---|---|---|---|---|---|
| **Interpretasi** | ✓✓ Terbaik | ✓ Mudah | ✓ Lokal | ✗ Black box (RBF) | ✓ via SHAP |
| **Perlu Scaling** | ✗ Tidak | ✗ GNB tidak | ✓✓ WAJIB | ✓✓ WAJIB | ✗ Tidak |
| **Missing Values** | ~ Parsial | Perlu imputasi | KNNImputer | Perlu imputasi | ~ Parsial |
| **Overfitting** | Tinggi | Rendah | K tergantung | C tergantung | 🟢 Rendah |
| **Data Kecil** | ✓ | ✓✓ Efektif | ✓ | ✓✓ | ✗ Kurang optimal |
| **Data Besar** | ✓ | ✓✓ | ✗ Lambat | ✗ Lambat | ✓✓ |
| **Training Speed** | Cepat | Sangat cepat | Instan | Lambat (n>100K) | Cepat |
| **Non-linear** | ✓ Alami | ~ | ✓✓ | ✓ (kernel) | ✓✓ |
| **Multi-class** | ✓ Native | ✓ Native | ✓ Native | ~ One-vs-One | ✓ Native |
---

# PERTEMUAN 6 — Neural Network dan Deep Learning

## 6.1 Inspirasi Biologis

| Otak Manusia | Jaringan Syaraf Tiruan |
|---|---|
| ~86 Miliar neuron | Node / unit komputasi |
| ~100 Triliun sinapsis | Bobot (weights) |
| Dendrit (input) | Input (x₁, x₂, …, xₙ) |
| Kekuatan sinapsis | Bobot (w₁, w₂, …, wₙ) |
| Soma (akumulasi) | Net Input: z = Σwᵢxᵢ + b |
| Ambang batas | Fungsi Aktivasi f(z) |
| Akson (output) | Output: a = f(z) |

---

## 6.2 Sejarah Neural Network

| Tahun | Tokoh/Peristiwa | Dampak |
|---|---|---|
| 1943 | McCulloch & Pitts — model neuron buatan pertama | Fondasi teoritis |
| 1958 | **Perceptron** — Frank Rosenblatt | Mesin yang bisa belajar |
| **1969** | Minsky & Papert — buktikan Perceptron tidak bisa XOR | **AI Winter I** |
| 1986 | Backpropagation — Rumelhart, Hinton & Williams | Kebangkitan NN |
| 1998 | LeNet (LeCun) — CNN pertama sukses | MNIST digit recognition |
| **1993–2006** | — | **AI Winter II** |
| 2012 | AlexNet — menang ImageNet | Awal revolusi Deep Learning |
| 2017 | Transformer — "Attention Is All You Need" | Revolusi NLP |
| 2023+ | ChatGPT, Claude, Gemini | AI generatif masuk masyarakat |

---

## 6.3 Perceptron (Frank Rosenblatt, 1958)

### Formula Perceptron

```
z = Σ wᵢxᵢ + b        (Net Input)
ŷ = f(z) = 1 jika z ≥ 0, else 0   (Step Function)
```

### Contoh Perhitungan

```
Input: x₁=0.8, x₂=0.5, x₃=0.2, b=1
Bobot: w₁=0.6, w₂=0.9, w₃=0.4, w_b=0.3

z = (0.6×0.8) + (0.9×0.5) + (0.4×0.2) + (0.3×1)
  = 0.48 + 0.45 + 0.08 + 0.30 = 1.31

Aktivasi: z = 1.31 ≥ 0 → ŷ = 1 (Kelas Positif)
```

### Aturan Pembelajaran Perceptron

```
Δwᵢ = η × (y − ŷ) × xᵢ
wᵢ_baru = wᵢ_lama + Δwᵢ
```

- η = learning rate
- y = target (label asli)
- ŷ = prediksi model
- (y−ŷ) = error signal: 0 jika benar, ±1 jika salah

**Contoh update:** η=0.1, y=1, ŷ=0, x₁=0.8
```
Δw₁ = 0.1 × (1−0) × 0.8 = 0.08
w₁_baru = 0.60 + 0.08 = 0.68
```

### Kemampuan & Keterbatasan Perceptron

| ✅ Bisa | ❌ Tidak Bisa |
|---|---|
| Klasifikasi biner (0/1) | Masalah **XOR** (tidak linearly separable) |
| Belajar dari data otomatis | Pola non-linear |
| Konvergen untuk data linearly separable | Representasi kompleks (satu layer) |

**Masalah XOR (Minsky & Papert, 1969):**

| AND | OR | XOR |
|---|---|---|
| Linearly separable ✓ | Linearly separable ✓ | **NOT linearly separable ✗** |

---

## 6.4 Multi-Layer Perceptron (MLP)

**Solusi XOR:** Tambahkan **Hidden Layer** di antara input dan output.

### Perceptron vs MLP

| Aspek | Perceptron | MLP |
|---|---|---|
| Layer | 1 (input+output) | 2+ (ada hidden layer) |
| XOR | ❌ Tidak bisa | ✅ Bisa |
| Aktivasi | Step function | Sigmoid, ReLU, dll. |
| Training | Perceptron rule | **Backpropagation** |
| Non-linear | ❌ | ✅ (via aktivasi) |

**Notasi arsitektur:** MLP 2-2-1 = 2 input, 2 hidden, 1 output

---

## 6.5 Komponen Neural Network

| Komponen | Formula | Fungsi |
|---|---|---|
| **Neuron/Node** | a = f(Σ wᵢxᵢ + b) | Unit komputasi dasar |
| **Bobot (Weight)** | w ∈ ℝ (awalnya acak) | Kekuatan pengaruh input |
| **Bias** | b ∈ ℝ | Intercept — neuron aktif saat input=0 |
| **Fungsi Aktivasi** | a = f(z) | Memperkenalkan non-linearitas |
| **Loss Function** | L = ½(y−ŷ)² | Mengukur kesalahan prediksi |
| **Optimizer** | w ← w − η·∂L/∂w | Mengupdate bobot via gradient descent |

---

## 6.6 Fungsi Aktivasi

| Nama | Formula | Range | Kelebihan | Kelemahan | Digunakan di |
|---|---|---|---|---|---|
| **Step Function** | f(z) = 1 if z≥0 else 0 | {0,1} | Sederhana | Tidak differentiable | Perceptron klasik |
| **Sigmoid** | σ(z) = 1/(1+e⁻ᶻ) | (0,1) | Probabilitas output, smooth | Vanishing gradient | Output binary class |
| **Tanh** | (eᶻ−e⁻ᶻ)/(eᶻ+e⁻ᶻ) | (−1,1) | Zero-centered | Vanishing gradient | Hidden layer, RNN |
| **ReLU** | max(0,z) | [0,∞) | Cepat, sparse | **Dying ReLU** | **Hidden layer (default)** |
| **Leaky ReLU** | max(0.01z, z) | (−∞,∞) | Fix dying ReLU | α perlu dipilih | Alternatif ReLU |
| **Softmax** | eᶻⁱ/Σeᶻʲ | (0,1), sum=1 | Distribusi probabilitas | Numerically unstable | **Output multiclass** |

---

## 6.7 Arsitektur Neural Network

### Jenis Layer

| Layer | Fungsi | Keterangan |
|---|---|---|
| **Input Layer** | Menerima data mentah | Tidak melakukan komputasi; jumlah neuron = jumlah fitur |
| **Hidden Layer(s)** | Transformasi non-linear | Mengekstrak fitur abstrak secara hierarkis |
| **Output Layer** | Prediksi akhir | Aktivasi: Sigmoid (binary), Softmax (multiclass), Linear (regresi) |

**Shallow NN:** 1 hidden layer  
**Deep NN (Deep Learning):** 2+ hidden layers  
**Sangat dalam:** ResNet 152 layer, GPT-4 ~96 transformer layers

---

## 6.8 Forward Pass — Aliran Data dari Input ke Output

### Alur Forward Pass

```
Input x → Net Input z₁ = Σwᵢxᵢ+b → Aktivasi a₁=f(z₁) → Next Layer → ... → Output ŷ
```

### Contoh Lengkap (Arsitektur 2-2-1)

**Nilai awal:**

| Simbol | Nilai |
|---|---|
| x₁, x₂ | 0.05, 0.10 |
| Target t₁ | 0.01 |
| b₁ (bias hidden) | 0.35 |
| b₂ (bias output) | 0.60 |
| w₁ (x₁→h₁) | 0.15 |
| w₂ (x₂→h₁) | 0.20 |
| w₃ (x₁→h₂) | 0.25 |
| w₄ (x₂→h₂) | 0.30 |
| w₅ (h₁→o₁) | 0.40 |
| w₆ (h₂→o₁) | 0.45 |
| η (learning rate) | 0.5 |
| Aktivasi | Sigmoid σ(z)=1/(1+e⁻ᶻ) |

**Langkah FP-1: Hitung h₁**
```
z_h1 = (0.15×0.05) + (0.20×0.10) + 0.35
     = 0.0075 + 0.0200 + 0.35 = 0.3775
out_h1 = σ(0.3775) = 1/(1+e⁻⁰·³⁷⁷⁵) ≈ 0.5933
```

**Langkah FP-2: Hitung h₂**
```
z_h2 = (0.25×0.05) + (0.30×0.10) + 0.35
     = 0.0125 + 0.0300 + 0.35 = 0.3925
out_h2 = σ(0.3925) = 1/(1+e⁻⁰·³⁹²⁵) ≈ 0.5969
```

**Langkah FP-3: Hitung o₁**
```
z_o1 = (0.40×0.5933) + (0.45×0.5969) + 0.60
     = 0.2373 + 0.2686 + 0.60 = 1.1059
out_o1 = σ(1.1059) ≈ 0.7514
```

**Langkah FP-4: Hitung Loss (MSE)**
```
E = ½(t₁ − out_o1)² = ½(0.01 − 0.7514)² = ½(0.7414)² ≈ 0.2750
```

---

## 6.9 Backpropagation

### Konsep: Chain Rule dari Output ke Input

```
∂E/∂w = ∂E/∂out × ∂out/∂net × ∂net/∂w
```

**Chain Rule tiga komponen:**

| Komponen | Formula | Makna |
|---|---|---|
| ∂E/∂out_o1 | −(t₁ − out_o1) | Turunan MSE loss terhadap output |
| ∂out_o1/∂net_o1 | out_o1 × (1 − out_o1) | Turunan sigmoid: σ'(z) = σ(z)(1−σ(z)) |
| ∂net_o1/∂w | nilai input ke neuron | ∂(w·x)/∂w = x |

### Langkah BP-1: Gradien Output Layer

```
∂E/∂out_o1 = −(0.01 − 0.7514) = 0.7414
∂out_o1/∂net_o1 = 0.7514 × (1 − 0.7514) = 0.18681
δ_o1 = 0.7414 × 0.18681 = 0.1385
```

### Langkah BP-2: Update Bobot Output (w₅, w₆)

```
Rumus: w_baru = w_lama − η × δ_o1 × input_ke_neuron

∂E/∂w₅ = δ_o1 × out_h1 = 0.1385 × 0.5933 = 0.0822
w₅_baru = 0.40 − 0.5 × 0.0822 = 0.40 − 0.0411 = 0.3589

∂E/∂w₆ = δ_o1 × out_h2 = 0.1385 × 0.5969 = 0.0827
w₆_baru = 0.45 − 0.5 × 0.0827 = 0.45 − 0.0413 = 0.4087
```

### Langkah BP-3: Gradien Hidden Layer (δ_h)

Untuk hidden layer, error dihitung dengan "menjumlahkan" error yang datang dari output layer:

```
∂E/∂out_h1 = δ_o1 × w₅ = 0.1385 × 0.40 = 0.0554
δ_h1 = ∂E/∂out_h1 × out_h1 × (1 − out_h1)
      = 0.0554 × 0.5933 × (1 − 0.5933)
      = 0.0554 × 0.5933 × 0.4067 ≈ 0.01337
```

### Langkah BP-4: Update Bobot Hidden (w₁, w₂, w₃, w₄)

```
∂E/∂w₁ = δ_h1 × x₁ = 0.01337 × 0.05 = 0.000669
w₁_baru = 0.15 − 0.5 × 0.000669 = 0.15 − 0.000334 ≈ 0.1497

∂E/∂w₂ = δ_h1 × x₂ = 0.01337 × 0.10 = 0.001337
w₂_baru = 0.20 − 0.5 × 0.001337 = 0.20 − 0.000669 ≈ 0.1993
```

---

## 6.10 Hyperparameter Neural Network

| Hyperparameter | Penjelasan | Tips |
|---|---|---|
| **Learning Rate (η)** | Ukuran langkah gradient descent | 0.001–0.1; gunakan scheduler |
| **Batch Size** | Jumlah sampel per update bobot | Mini-batch 32–128 (paling umum) |
| **Epochs** | Berapa kali data training dilewati | Gunakan early stopping |
| **Arsitektur** | Jumlah layer & neuron per layer | Mulai sederhana, tambah bertahap |
| **Fungsi Aktivasi** | Nonlinearitas | ReLU untuk hidden, Softmax/Sigmoid untuk output |
| **Optimizer** | SGD, Adam, RMSprop | Adam biasanya terbaik |

**Aturan praktis arsitektur:** Jumlah hidden neuron ≈ rata-rata antara jumlah input dan output.

---

## 6.11 Regularisasi — Mencegah Overfitting

| Teknik | Formula/Cara | Keterangan |
|---|---|---|
| **L1 Regularization** | L_total = L + λΣ\|wᵢ\| | Mendorong banyak bobot = 0 (sparse model) |
| **L2 Regularization** | L_total = L + λΣwᵢ² | Mendorong bobot kecil (weight decay), paling umum |
| **Dropout** | Acak matikan p% neuron saat training | Paksa jaringan belajar fitur redundan/robust |
| **Early Stopping** | Stop jika val_loss tidak turun n epoch | Simpan bobot terbaik |
| **Data Augmentation** | Flip, rotate, crop, noise | Perbanyak data training secara sintetis |
| **Batch Normalization** | Normalisasi aktivasi per mini-batch | Stabilkan training, izinkan LR lebih besar |

---

## 6.12 Loss Functions & Metrik Evaluasi

### Loss Functions

| Nama | Formula | Tugas | Catatan |
|---|---|---|---|
| **MSE** | (1/n)Σ(yᵢ−ŷᵢ)² | Regresi | Sensitif terhadap outlier |
| **MAE** | (1/n)Σ\|yᵢ−ŷᵢ\| | Regresi | Lebih robust terhadap outlier |
| **Binary Cross-Entropy** | −[y·log(ŷ)+(1−y)·log(1−ŷ)] | Klasifikasi biner | Output Sigmoid |
| **Categorical Cross-Entropy** | −Σ yᵢ·log(ŷᵢ) | Klasifikasi multi | Output Softmax |

### Metrik Evaluasi

| Metrik | Formula | Gunakan Untuk |
|---|---|---|
| Accuracy | (TP+TN)/Total | Klasifikasi seimbang |
| Precision | TP/(TP+FP) | Minimalkan False Positive |
| Recall | TP/(TP+FN) | Minimalkan False Negative |
| F1-Score | 2×(P×R)/(P+R) | Imbalanced dataset |
| R² Score | 1−SS_res/SS_tot | Regresi |

---

## 6.13 Jenis-jenis Arsitektur Deep Learning

### Multi-Layer Perceptron (MLP / Fully Connected)
- Setiap neuron terhubung ke semua neuron layer berikutnya
- Cocok untuk: data tabular, klasifikasi, regresi

### Convolutional Neural Network (CNN)
- Layer: Convolutional → Pooling → Flatten → Dense
- Filter/kernel belajar fitur lokal secara hierarkis
- Cocok untuk: **gambar, time series, NLP** (1D)

### Recurrent Neural Network (RNN)
- Output dari satu langkah menjadi input langkah berikutnya
- Memiliki "memori" temporal
- Cocok untuk: **data sekuensial, teks, time series**
- Varian: **LSTM** (Long Short-Term Memory), **GRU** (Gated Recurrent Unit) → mengatasi vanishing gradient

### Transformer
- Mekanisme **attention** — setiap token bisa "memperhatikan" semua token lain
- Paralel (tidak sekuensial seperti RNN) → lebih cepat
- Fondasi: BERT, GPT, ChatGPT, Claude, Gemini

---

## 6.14 Implementasi Neural Network (R — paket nnet)

```r
library(nnet)
library(caret)

# Normalisasi data (WAJIB untuk NN)
preProc <- preProcess(X_train, method = c('center', 'scale'))
X_tr <- predict(preProc, X_train)
X_te <- predict(preProc, X_test)

# Model sederhana (nnet: 1 hidden layer)
nn_model <- nnet(
  status ~ ., data = cbind(X_tr, status = y_train),
  size   = 5,         # jumlah neuron hidden layer
  decay  = 0.01,      # L2 regularisasi (weight decay)
  maxit  = 200,       # max iterasi
  trace  = FALSE
)

pred_nn <- predict(nn_model, X_te, type = 'class')
confusionMatrix(as.factor(pred_nn), y_test)

# Tuning dengan caret
ctrl <- trainControl(method = 'cv', number = 5, classProbs = TRUE)
tune_grid_nn <- expand.grid(
  size  = c(3, 5, 7, 10),    # neurons di hidden layer
  decay = c(0, 0.001, 0.01, 0.1)  # L2 regularisasi
)

nn_caret <- train(
  status ~ ., data = cbind(X_tr, status = y_train),
  method    = 'nnet',
  trControl = ctrl,
  tuneGrid  = tune_grid_nn,
  trace     = FALSE
)
print(nn_caret$bestTune)
```

---

# RINGKASAN KESELURUHAN MATERI

## Alur Lengkap Data Mining

```
┌─────────────────────────────────────────────────────────────────────┐
│                    PIPELINE DATA MINING                              │
├──────────────┬──────────────┬──────────────┬────────────────────────┤
│  P1: INTRO   │  P2: PREPROC │  P3: EVAL    │  P4–P6: MODELING       │
│              │              │              │                        │
│  Data→Info   │  Cleaning    │  Split       │  Decision Tree         │
│  →Knowledge  │  Integration │  Train/Test  │  Naive Bayes           │
│              │  Reduction   │  CV (k-fold) │  KNN                   │
│  KDD/CRISP   │  Normalisasi │  Confusion   │  SVM                   │
│              │  Encoding    │  Matrix      │  Ensemble (RF, XGB)    │
│              │  Discretiz.  │  Akurasi,    │  Neural Network        │
│              │              │  F1, AUC     │                        │
└──────────────┴──────────────┴──────────────┴────────────────────────┘
```

## Quick Reference: Preprocessing

| Masalah | Solusi |
|---|---|
| Missing values (numerik) | Mean (normal) / Median (skewed) |
| Missing values (kategorik) | Modus / kategori baru |
| Outlier | IQR clipping / Winsorizing / Z-score |
| Skala berbeda | StandardScaler (Z-score) / MinMax / RobustScaler |
| Kategorik nominal | One-Hot Encoding (OHE) |
| Kategorik ordinal | Label/Ordinal Encoding |
| Dimensi tinggi | PCA / Feature Selection |

## Quick Reference: Kapan Pakai Model Apa?

| Prioritas | Model Pilihan |
|---|---|
| Interpretasi → aturan kebijakan | **Decision Tree (C4.5/rpart)** |
| Data kecil, cepat, teks | **Naive Bayes** |
| Non-linear, data kecil, pola lokal | **KNN** (wajib scaling) |
| High-dimensional, data kecil-menengah | **SVM** (wajib scaling) |
| Baseline yang kuat, robust | **Random Forest** |
| Akurasi maksimal, tabular | **XGBoost / LightGBM** |
| Banyak kategorik | **CatBoost** |
| Gambar/teks/sekuensial | **CNN / RNN / Transformer** |

## Rumus-Rumus Penting

### Entropy & Decision Tree
```
H(S) = −Σ pᵢ × log₂(pᵢ)
IG(A) = H(D) − Σⱼ (|Dⱼ|/|D|)×H(Dⱼ)
GainRatio(A) = IG(A) / SplitInfo(A)
Gini(D) = 1 − Σ pᵢ²
```

### Naive Bayes
```
P(C|X) = P(X|C) × P(C) / P(X)
Ĉ = argmax_C [ P(C) × ∏ P(xⱼ|C) ]
Laplace: P(xⱼ=v|C) = (count+α) / (n_C + α×|V|)
```

### KNN
```
Euclidean: d = √Σ(xᵢ−yᵢ)²
Manhattan: d = Σ|xᵢ−yᵢ|
Optimal K ≈ √n (titik awal)
```

### SVM
```
Hyperplane: w·x + b = 0
Margin = 2/‖w‖
Soft Margin: min ½‖w‖² + C·Σξᵢ
```

### Neural Network
```
z = Σ wᵢxᵢ + b
a = f(z)
E = ½(y − ŷ)²    [MSE]
σ'(z) = σ(z)(1−σ(z))  [turunan sigmoid]
Δw = −η × ∂E/∂w   [update bobot]
```

### Metrik Evaluasi
```
Accuracy    = (TP+TN) / (TP+TN+FP+FN)
Precision   = TP / (TP+FP)
Recall      = TP / (TP+FN)
Specificity = TN / (TN+FP)
F1          = 2×(P×R) / (P+R)
```

---

## Paket R yang Digunakan dalam Kuliah

| Paket | Fungsi |
|---|---|
| `rpart` | Decision Tree CART |
| `rpart.plot` | Visualisasi pohon keputusan |
| `C50` | Decision Tree C5.0 (C4.5 successor) |
| `e1071` | Naive Bayes + SVM |
| `naivebayes` | Naive Bayes (lebih lengkap) |
| `class` | KNN (`knn()`) |
| `randomForest` | Random Forest |
| `caret` | Unified ML framework (CV + tuning) |
| `VIM` | KNN imputer untuk missing values |
| `nnet` | Neural Network 1 hidden layer |

---

*Disusun dari materi kuliah K203504 Data Mining, Politeknik Statistika STIS*  
*Pengajar: Dr. Achmad Syahrul Choir, S.ST, M.Si.*

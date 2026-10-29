# Bank Customer Churn Analysis

Analisis customer's churn menggunakan **Microsoft Excel**, dengan fokus pada identifikasi customer segment yang memiliki tingkat churn tinggi dan potensi balance loss terbesar.

Project ini dikerjakan dalam **dua versi** dengan dataset yang sama: **versi manual tanpa AI** (PivotTable & PivotChart) dan **versi dengan bantuan AI** (dashboard berbasis formula dengan dropdown filter).

![Microsoft Excel](https://img.shields.io/badge/-Microsoft%20Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![XLOOKUP](https://img.shields.io/badge/-XLOOKUP-217346?style=flat-square)
![PivotTable](https://img.shields.io/badge/-PivotTable-217346?style=flat-square)
![COUNTIFS / SUMIFS](https://img.shields.io/badge/-COUNTIFS%20%2F%20SUMIFS-217346?style=flat-square)
![AI-assisted](https://img.shields.io/badge/-AI--assisted-8A2BE2?style=flat-square)
![Data Analysis](https://img.shields.io/badge/-Data%20Analysis-blue?style=flat-square)

---

## 📋 Ringkasan

Customer churn merupakan salah satu permasalahan penting dalam customer retention karena kehilangan customer juga dapat berarti kehilangan balance yang mereka miliki.

Project ini menggunakan data customer bank untuk melihat seberapa serius masalah churn, customer segment mana yang memiliki churn rate tertinggi, apakah bank kehilangan high-value customers, serta segment mana yang sebaiknya menjadi prioritas retention.

## 🔀 Dua Versi Project

| | Versi 1: Tanpa AI | Versi 2: Dengan AI |
|---|---|---|
| **File** | `Bank Churn Analysis.xlsx` | `Bank Churn Analysis - Copy.xlsx` |
| **Cara membuat** | Dikerjakan manual | Dikerjakan dengan bantuan AI assistant |
| **Perhitungan** | Excel PivotTable | Formula `COUNTIFS` / `SUMIFS` di sheet `Calc` |
| **Visualisasi** | PivotChart | Excel chart yang terhubung ke sheet `Calc` |
| **Filter** | - | Dropdown (Geography, Gender, Age Group) |
| **Fokus analisis** | Customer value (High / Medium / Low) | Geography, age group, number of products, active membership, dan ranking segment berdasarkan balance lost |

Kedua versi menghasilkan angka yang konsisten: **9,997 customers**, **2,037 churned (20.38%)**, dan sekitar **€185.6M balance lost**.

---

## 📊 Dataset

Dataset terdiri dari dua dataset yang saling berhubungan:

- **Account Info** — berisi informasi mengenai akun customer, seperti balance, number of products, credit card, active membership, tenure, dan churn status.
- **Customer Info** — berisi informasi customer seperti credit score, geography, gender, age, dan estimated salary.

Kedua dataset dihubungkan menggunakan **Customer ID** melalui `XLOOKUP` di Excel.

Dataset awal terdiri dari **9,998 rows**. Setelah proses pengecekan duplicate, ditemukan dan dihapus **1 duplicated row**, sehingga dataset akhir yang digunakan terdiri dari **9,997 customers**.

---

# 🅰️ Versi 1: Tanpa AI (PivotTable & PivotChart)

Dashboard dibuat menggunakan **Excel PivotTable dan PivotChart** berdasarkan pertanyaan-pertanyaan bisnis di bawah.

## 🧪 Metodologi

### 1. Merge Dataset

Account Info dan Customer Info digabungkan menggunakan `CustomerId` sebagai identifier.

`XLOOKUP` digunakan untuk mengambil informasi customer dari dataset Customer Info ke dataset Account Info.

### 2. Data Preprocessing

Setelah kedua dataset digabungkan:

- Satu duplicate row diperiksa dan dihapus.
- Beberapa kolom tambahan dibuat untuk mempermudah analisis.
- Kolom-kolom tambahan tersebut kemudian digunakan dalam PivotTable dan PivotChart.

### 3. Exploratory Analysis

Customer churn dianalisis berdasarkan beberapa karakteristik:

- Geography
- Age
- Gender
- Active Membership
- Credit Score
- Number of Products
- Tenure
- Customer Value

### 4. Dashboard

PivotTable digunakan untuk menghitung jumlah customer, churn rate, dan balance lost berdasarkan berbagai customer segment.

Hasil PivotTable kemudian divisualisasikan menggunakan PivotChart dan disusun menjadi sebuah dashboard untuk memberikan gambaran mengenai customer churn secara keseluruhan.

## 📈 Hasil

### How serious is our customer retention problem?

Dari **9,997 customers**, sebanyak **2,037 customers churned**, atau sekitar **20.38%**.

Customer yang churn tersebut menyebabkan sekitar **€185.6 million balance lost**.

### Who has the highest churn rate?

Beberapa segment dengan churn rate tertinggi adalah:

| Customer Segment | Churn Rate |
|---|---:|
| Germany | 32.46% |
| 1 Product | 27.73% |
| Non-active Member | 26.86% |
| Medium Value | 26.24% |
| Female | 25.08% |

Customer dari **Germany** memiliki churn rate tertinggi, yaitu **32.46%**.

### Are we losing high-value customers?

Yes.

| Customer Value | Total Customers | Churn Rate | Balance Lost |
|---|---:|---:|---:|
| High Value | 2,000 | 23.10% | €71.7M |
| Medium Value | 2,999 | 26.24% | €91.6M |
| Low Value | 4,998 | 15.77% | €22.3M |

Dari 2,000 high-value customers, sebanyak **462 customers churned**, dengan churn rate sebesar **23.10%** dan sekitar **€71.7 million balance lost**.

### Which customer segments should the bank prioritize?

Medium-value customers menghasilkan total balance lost terbesar karena jumlah customer yang churn cukup tinggi.

Namun, ketika mempertimbangkan **churn rate dan financial impact**, high-value customers menjadi segment yang penting untuk diprioritaskan dalam retention.

Jika high-value customers churn, potensi balance yang hilang per customer lebih besar dibandingkan customer dengan value yang lebih rendah.

## 🔎 Key Insights

- **20.38%** dari customer mengalami churn.
- Churned customers menyebabkan sekitar **€185.6M balance lost**.
- **Germany** memiliki churn rate tertinggi (**32.46%**).
- Customers dengan **1 product** memiliki churn rate sebesar **27.73%**.
- **Non-active members** memiliki churn rate sebesar **26.86%**.
- High-value customers memiliki churn rate sebesar **23.10%**.
- High-value customers yang churn menyebabkan sekitar **€71.7M balance lost**.
- High-value customers merupakan salah satu segment yang perlu diperhatikan dalam customer retention karena memiliki balance yang lebih besar untuk dipertahankan.

---

# 🅱️ Versi 2: Dengan AI (Formula-driven Dashboard)

Pada versi ini, saya menggunakan **AI assistant** untuk membantu membangun dashboard di atas workbook yang sama. Alur kerjanya: saya menentukan pertanyaan bisnis dan struktur dashboard yang diinginkan (dari sudut pandang seorang bank executive), lalu AI membantu menulis formula, membuat chart, dan menyusun layout. Semua angka kemudian saya cocokkan kembali dengan hasil versi manual.

Tujuan versi ini adalah membandingkan workflow manual dengan workflow yang dibantu AI, sekaligus menambahkan analisis yang belum ada di versi 1.

## 🧪 Metodologi

### 1. Alur Data

```text
Account_Info  +  Customer_Info
        │
        ▼
Merged_Customer_Account   (XLOOKUP)
        │
        ▼
Calc                      (COUNTIFS / SUMIFS)
        │
        ▼
Dashboard                 (chart + dropdown filter)
```

Seluruh proses ada di dalam satu workbook sehingga setiap angka di dashboard dapat ditelusuri sampai ke data mentah.

### 2. Data Preprocessing

- Sheet `Merged_Customer_Account` ditambah kolom **Unique Flag** yang menandai baris pertama untuk setiap `CustomerId`. Baris duplicate otomatis dikeluarkan dari seluruh perhitungan.
- **Named ranges** (`d_Geo`, `d_Exit`, `d_Bal`, dan lainnya) dibuat agar formula lebih mudah dibaca.
- Sheet `Calc` memiliki bagian **data checks** (jumlah baris, duplicate yang dikeluarkan, dan pengecekan konsistensi kolom).

### 3. Sheet `Calc`

Seluruh perhitungan menggunakan formula `COUNTIFS`, `SUMIFS`, dan `AVERAGEIFS` sehingga otomatis berubah ketika dropdown di Dashboard diganti. Isinya:

- KPI utama (total customers, churned, churn rate, balance at risk)
- Churn rate berdasarkan Geography, Gender, Age Group, Number of Products, dan Active Membership
- Matrix churn rate: Geography × Age Group dan Number of Products × Geography
- Ranking segment berdasarkan balance lost

### 4. Dashboard

- **4 KPI cards**: Total Customers, Churn Rate, Customers Lost, Balance at Risk
- **6 chart** dengan garis putus-putus merah sebagai overall churn rate
- **Heat map** churn rate Geography × Age Group
- **Top 5 highest-risk segments** berdasarkan balance lost
- **Key Insights** dan **Recommended Actions**
- **3 dropdown filter**: Geography, Gender, dan Age Group

<!-- Tambahkan screenshot dashboard di sini:
![Dashboard AI Version](images/dashboard-ai.png)
-->

## 📈 Hasil

### How serious is our customer retention problem?

Dari **9,997 customers**, sebanyak **2,037 customers churned (20.4%)**, dengan sekitar **€185.6M balance lost** atau **24.3%** dari total balance.

Rata-rata balance customer yang churn (**€91.1K**) lebih tinggi dibandingkan customer yang bertahan (**€72.7K**), artinya bank cenderung kehilangan customer dengan balance yang lebih besar.

### Who has the highest churn rate?

| Customer Segment | Churn Rate |
|---|---:|
| Customers dengan 3 products | 82.7% |
| Customers dengan 4 products | 100% (60 customers) |
| Age >50 | 44.6% |
| Germany | 32.5% |
| Non-active Member | 26.9% |
| Female | 25.1% |

Sebagai pembanding, customers dengan **2 products** hanya memiliki churn rate **7.6%**, dan customers **di bawah 30 tahun** hanya **7.6%**.

### Which customer segments should the bank prioritize?

Top 5 segment (Geography × Age Group) berdasarkan balance lost:

| Rank | Geography | Age Group | Churned | Churn Rate | Balance Lost |
|---:|---|---|---:|---:|---:|
| 1 | Germany | 30-50 | 554 | 31.1% | €66.6M |
| 2 | France | 30-50 | 526 | 14.8% | €37.5M |
| 3 | Germany | >50 | 213 | 59.8% | €25.7M |
| 4 | Spain | 30-50 | 270 | 15.3% | €18.4M |
| 5 | France | >50 | 239 | 40.0% | €16.5M |

**Germany, usia 30-50** adalah segment dengan balance lost terbesar. Sementara itu **Germany, usia >50** memiliki churn rate tertinggi (59.8%) dengan jumlah customer yang lebih kecil.

## 🔎 Key Insights

- **Germany** memiliki churn rate sekitar **2x lebih tinggi** dibanding France dan Spain.
- Customers **di atas 50 tahun** memiliki churn rate **44.6%**, hampir **6x lebih tinggi** dibanding customers di bawah 30 tahun.
- Customers dengan **3-4 products** hampir semuanya churn, sedangkan customers dengan **2 products** memiliki churn rate paling rendah. Ini menunjukkan perlunya review strategi cross-sell.
- **Non-active members** memiliki churn rate sekitar **2x lebih tinggi** dibanding active members.
- **Female customers** memiliki churn rate **25.1%**, lebih tinggi dibanding male customers (**16.5%**).

## ✅ Recommended Actions

1. Buat program retention untuk customers di atas 50 tahun, dimulai dari Germany.
2. Cari tahu penyebab customers dengan 3-4 products churn sebelum melakukan cross-sell lebih lanjut.
3. Re-engage non-active members lebih awal dan dorong customers dengan 1 product untuk menggunakan 2 products.

## ⚠️ Catatan Kualitas Data

- Kolom **HasCrCard** dan **IsActiveMember** memiliki nilai yang identik di seluruh baris, sehingga kemungkinan salah satu kolom merupakan salinan dari kolom lain. Pada versi 2, hanya **IsActiveMember** yang digunakan.
- Mata uang tidak dijelaskan dalam sumber dataset. Nilai balance pada project ini ditampilkan dengan simbol **€**.

---

## 📁 Struktur Project

```text
bank-churn-analysis/
│
├── Bank Churn Analysis.xlsx                # Versi 1: tanpa AI (PivotTable & PivotChart)
├── Bank Churn Analysis with Claude.xlsx    # Versi 2: dengan AI (Calc + Dashboard)
└── README.md
```

## ⚙️ Cara Menjalankan

Tidak diperlukan instalasi library atau environment khusus. Dashboard dan analisis dapat dilihat langsung melalui workbook Excel.

Untuk **Versi 2**:

1. Buka file menggunakan **Microsoft Excel desktop** (disarankan Excel 2021 / Microsoft 365 karena menggunakan `XLOOKUP` dan `IFS`).
2. Tunggu Excel selesai menghitung ulang saat file pertama kali dibuka.
3. Buka sheet `Dashboard` dan gunakan **dropdown berwarna kuning** untuk memfilter KPI, chart, heat map, dan tabel top-risk segments.

## 📜 Catatan

Project ini dibuat untuk tujuan **portfolio dan pembelajaran data analysis**. Dataset diambil dari kaggle.

## 📫 Kontak

`Rifdah Salsabila` — [LinkedIn](https://linkedin.com/in/rifdah-salsabila732998218) · [Email](mailto:rifdahdjamaan@gmail.com)

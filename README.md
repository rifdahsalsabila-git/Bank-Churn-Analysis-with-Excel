# Bank Customer Churn Analysis

Analisis customer's churn menggunakan **Microsoft Excel**, dengan fokus pada identifikasi customer segment yang memiliki tingkat churn tinggi dan potensi balance loss terbesar.

![Microsoft Excel](https://img.shields.io/badge/-Microsoft%20Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![XLOOKUP](https://img.shields.io/badge/-XLOOKUP-217346?style=flat-square)
![PivotTable](https://img.shields.io/badge/-PivotTable-217346?style=flat-square)
![Data Analysis](https://img.shields.io/badge/-Data%20Analysis-blue?style=flat-square)

---

## 📋 Ringkasan

Customer churn merupakan salah satu permasalahan penting dalam customer retention karena kehilangan customer juga dapat berarti kehilangan balance yang mereka miliki.

Project ini menggunakan data customer bank untuk melihat seberapa serius masalah churn, customer segment mana yang memiliki churn rate tertinggi, apakah bank kehilangan high-value customers, serta segment mana yang sebaiknya menjadi prioritas retention.

Dashboard dibuat menggunakan **Excel PivotTable dan PivotChart** berdasarkan pertanyaan-pertanyaan bisnis tersebut.

## 📊 Dataset

Dataset terdiri dari dua dataset yang saling berhubungan:

- **Account Info** — berisi informasi mengenai akun customer, seperti balance, number of products, credit card, active membership, tenure, dan churn status.
- **Customer Info** — berisi informasi customer seperti credit score, geography, gender, age, dan estimated salary.

Kedua dataset dihubungkan menggunakan **Customer ID** melalui `XLOOKUP` di Excel.

Dataset awal terdiri dari **9,998 rows**. Setelah proses pengecekan duplicate, ditemukan dan dihapus **1 duplicated row**, sehingga dataset akhir yang digunakan terdiri dari **9,997 customers**.

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

## 📁 Struktur Project

```text
bank-churn-analysis/
│
├── Bank Churn Analysis.xlsx
└── README.md
```

## ⚙️ Cara Menjalankan

Tidak diperlukan instalasi library atau environment khusus. Dashboard dan analisis dapat dilihat langsung melalui workbook Excel.

## 📜 Catatan

Project ini dibuat untuk tujuan **portfolio dan pembelajaran data analysis**. Dataset diambil dari kaggle

## 📫 Kontak

`Rifdah Salsabila` — [LinkedIn](https://linkedin.com/in/rifdah-salsabila732998218) · [Email](mailto:rifdahdjamaan@gmail.com)

# Analisis Akumulasi dan Distribusi Bandar di Pasar Saham Indonesia  
**Pendekatan Data Driven Berbasis Aktivitas Perdagangan 7 Hari**

---

## Ringkasan Proyek

Repositori ini berisi proyek analisis data yang bertujuan untuk **mengidentifikasi aktivitas akumulasi dan distribusi bandar** di pasar saham Indonesia secara **berbasis data resmi**, bukan rumor atau asumsi subjektif.

Dengan menggunakan **data perdagangan harian dari Bursa Efek Indonesia (IDX)** selama **7 hari bursa berturut-turut**, proyek ini membangun sebuah indikator komposit yang disebut **Bandar Accumulation Score** dan mengevaluasi dampaknya terhadap **return saham di masa depan (H+1 dan H+3)**.

Proyek ini difokuskan pada:
- Edukasi pasar modal
- Transparansi analisis
- Pendekatan yang bertanggung jawab dan tidak overclaim

---

## Tujuan Analisis

1. Mengidentifikasi saham yang terindikasi mengalami **akumulasi** dan **distribusi** oleh bandar (asing maupun domestik).
2. Mengevaluasi apakah **akumulasi 7 hari** cukup ideal sebagai acuan analisis.
3. Menguji apakah saham yang terakumulasi **selalu menghasilkan profit**.
4. Memberikan **insight berbasis data** yang mudah dipahami oleh pembaca non-teknis.
5. Menyediakan contoh proyek analisis data pasar modal yang **reproducible dan profesional**.

---

## Sumber Data

Seluruh data yang digunakan dalam proyek ini diperoleh dari:

- **Bursa Efek Indonesia (IDX)**
- Website resmi: https://www.idx.co.id  
- Jenis data: *Daily Trading Summary*
- Periode: **7 hari bursa berturut-turut**
- Jenis pasar: Pasar reguler

Data bersifat **sekunder**, **publik**, dan merepresentasikan kondisi transaksi pasar saham Indonesia secara aktual.

---

## Struktur Proyek

```text
├── data/
│   ├── R1.xlsx
│   ├── R2.xlsx
│   ├── R3.xlsx
│   ├── R4.xlsx
│   ├── R5.xlsx
│   ├── R6.xlsx
│   └── R7.xlsx
│
├── src/
│   ├── data_loading.py
│   ├── eda.py
│   ├── feature_engineering.py
│   ├── scoring_bandar.py
│   ├── validation.py
│   └── visualization.py
│
├── figures/
│   ├── high_vs_others.png
│   ├── quantile_vs_return.png
│   ├── distribution_bandar_score.png
│   └── sample_price_movement.png
│
├── report/
│   └── laporan_analisis_bandar.pdf
│
└── README.md
```

## Metodologi Singkat
1. Feature Engineering
Beberapa fitur utama yang dibangun:
- Return harian
- Foreign net flow
- Rolling foreign net (3 hari)
- Bid–offer imbalance
- Volume spike indicator

2. Normalisasi
Seluruh fitur dinormalisasi menggunakan pendekatan robust scaling:
- Median
- Interquartile Range (IQR)

3. Bandar Accumulation Score
Skor komposit dihitung sebagai kombinasi tertimbang dari seluruh fitur yang relevan dengan aktivitas bandar.
4. Validasi Prediktif
Dampak skor diuji terhadap:
- Return H+1
- Return H+3
- Termasuk analisis:
- Perbandingan grup (High Bandar vs Others)
- Analisis kuantil (Q1–Q5)

## Visualisasi
Visualisasi utama yang dihasilkan dan disertakan dalam proyek ini:
- Perbandingan Return High Bandar vs Others
- Return Masa Depan berdasarkan Kuantil Skor
- Distribusi Bandar Accumulation Score
- Contoh Pergerakan Harga Saham selama Fase Akumulasi
- Seluruh visualisasi dibuat menggunakan matplotlib dan disimpan dalam format .png.

## Lampiran Proyek
Repositori ini dilengkapi dengan lampiran lengkap sebagai berikut:
1. Dataset
- File .xlsx harian (R1–R7)
- Data mentah hasil unduhan dari website IDX
2. Kode Python
- Script terpisah untuk EDA, feature engineering, scoring, validasi, dan visualisasi
- Reproducible dan modular
3. Laporan PDF
- Laporan analisis lengkap dalam format PDF
- Disusun menggunakan LaTeX (Overleaf)
- Berisi metodologi, tabel, rumus, dan visualisasi
4. Visualisasi
- Seluruh grafik yang digunakan dalam laporan dan analisis
- Disimpan pada folder figures/

## Catatan Penting
- Proyek ini bukan rekomendasi investasi.
- Seluruh hasil bersifat deskriptif dan probabilistik, bukan deterministik.
- Akumulasi bandar tidak menjamin profit, dan risiko tetap ada.
- Analisis dibatasi oleh periode pengamatan dan ketersediaan data publik.

## Kontribusi & Pengembangan Lanjutan
Beberapa pengembangan yang dapat dilakukan di masa depan:
- Validasi pada horizon H+5 dan H+10
- Penyesuaian skor berdasarkan market capitalization
- Integrasi data fundamental dan berita
- Analisis per sektor
- Penggunaan data intraday (jika tersedia)

## Penulis
> Danang Hilal Kurniawan

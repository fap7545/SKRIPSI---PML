# Optimasi Clustering Segmentasi Pelanggan E-Commerce Shopee
### dengan Algoritma K-Means dan DBSCAN

Skripsi S1 Teknik Informatika — Metodologi Penelitian (24TIF505).
Repositori ini berisi seluruh berkas penelitian: data, literatur, notebook
analisis, model, dan draf tulisan.

## Struktur Folder

```
skripsi/
├── literatur/      # PDF artikel, tabel penelitian terdahulu, daftar pustaka
│   └── pdf/        # PDF artikel yang sudah diunduh (13/15, semuanya jurnal Sinta)
├── data/
│   ├── raw/        # data mentah — TIDAK PERNAH diubah
│   └── processed/  # data hasil cleaning & transformasi (dihasilkan kode)
├── notebook/       # Jupyter Notebook: EDA, eksperimen, pemodelan
├── model/          # model tersimpan (.pkl/.joblib), log eksperimen
├── draft/          # draf proposal, bab skripsi, artikel
├── README.md       # berkas ini
└── .gitignore      # berkas yang dikecualikan dari Git
```

## Aturan Penting

- **data/raw/** tidak pernah diedit langsung. Simpan dataset asli beserta
  catatan sumber, tanggal unduh, dan lisensi.
- **data/processed/** hanya boleh dihasilkan oleh kode, bukan pengeditan manual,
  agar penelitian dapat diulang dari nol.
- Notebook dinomori sesuai urutan proses, misalnya
  `01_eda_eksplorasi.ipynb`, `02_model_naive_bayes.ipynb`.
- Model disimpan dengan nama yang memuat tanggal atau nomor eksperimen.
- Data besar tidak dimasukkan ke Git; cukup didokumentasikan di README ini.

## Sumber Data

> Data primer: export penjualan Shopee periode Agustus 2024–Agustus 2026.
> ⚠️ Berisi PII (Nama Penerima, No. Telepon, Alamat — sudah dimasking Shopee).
> **Jangan** commit atau publikasikan; `data/raw/` sudah dikecualikan di `.gitignore`.

| Dataset | Sumber | Periode | Volume | Status |
|---------|--------|---------|--------|--------|
| Gabungan_Data_Penjualan_Agustus2024_Agustus2026.xlsx | Export Shopee (data primer) | Agu 2024–Agu 2026 | 3.584 baris / 3.250 pesanan / ~2.355 pelanggan | Data primer (bukan public — perlu konfirmasi dosen) |

## Cara Menjalankan

1. (Opsional) Buat environment terpisah:
   ```bash
   conda create -n skripsi python=3.11
   conda activate skripsi
   ```
2. Pasang pustaka dasar:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
3. Jalankan notebook dengan jalur relatif dari akar proyek, contoh:
   ```python
   import pandas as pd
   df = pd.read_excel("data/raw/Gabungan_Data_Penjualan_Agustus2024_Agustus2026.xlsx")
   ```
   ```bash
   jupyter notebook notebook/
   ```

## Studi Literatur (Poin 6)

- **15 artikel inti — semuanya dari jurnal Indonesia terakreditasi Sinta (Sinta 1–4).**
- Tabel penelitian terdahulu (format Buku Ajar + analisis celah):
  `literatur/tabel_penelitian_terdahulu.md`
- Daftar pustaka lengkap (APA + DOI): `literatur/daftar_pustaka.md`
- PDF artikel: `literatur/pdf/` (13 dari 15 terunduh, sisanya manual di browser).

## Kendali Versi

```bash
git init
git add .
git commit -m "Inisialisasi struktur proyek riset data"
git log --oneline
```

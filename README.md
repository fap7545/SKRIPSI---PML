# Skripsi — Proyek Riset Data

Repositori ini berisi seluruh berkas penelitian skripsi berbasis data.
Struktur folder mengikuti praktik standar sains data (Buku Ajar Metodologi
Penelitian, Bab II) yang memisahkan data mentah, data olahan, notebook
analisis, model, dan draf tulisan.

## Struktur Folder

```
skripsi/
├── literatur/      # PDF jurnal/prosiding, catatan tinjauan pustaka
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

> Lengkapi bagian ini untuk setiap dataset yang dipakai.

| Dataset | Sumber | Tanggal Unduh | Baris × Kolom | Lisensi |
|---------|--------|---------------|---------------|---------|
| _(contoh)_ Telco Customer Churn | Kaggle | YYYY-MM-DD | 7043 × 21 | _(isi)_ |

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
   df = pd.read_csv("data/raw/telco_churn.csv")
   ```
   ```bash
   jupyter notebook notebook/
   ```

## Kendali Versi

```bash
git init
git add .
git commit -m "Inisialisasi struktur proyek riset data"
git log --oneline
```

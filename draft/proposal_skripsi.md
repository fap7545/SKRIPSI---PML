# Proposal Skripsi

## 1. Judul Penelitian
**Optimasi Prediksi Churn Pelanggan E-Commerce Shopee menggunakan Algoritma Random Forest dan XGBoost**

> Format sesuai instruksi dosen: *optimasi [prediksi] tentang [A] menggunakan algoritma [B] dan algoritma [C]*.
> Catatan: jika dosen mewajibkan dataset **public** (bukan data primer), ganti "Shopee" sesuai dataset yang dipakai.

## 2. Topik Penelitian
Prediksi churn (ketidakaktifan) pelanggan e-commerce berbasis fitur RFM
(Recency, Frequency, Monetary) dan perilaku pembelian, dengan membandingkan
Algoritma **Random Forest** dan **XGBoost** serta mengoptimasinya
(penanganan ketidakseimbangan kelas + penyetelan hyperparameter).

## 3. Latar Belakang (singkat)
Pertahanan pelanggan (retention) lebih murah daripada akuisisi pelanggan baru.
Pada e-commerce, kemampuan mendeteksi pelanggan yang berhenti bertransaksi
(churn) sejak dini memungkinkan strategi retensi yang tepat sasaran. Penelitian
ini memanfaatkan data penjualan riil seorang penjual di Shopee periode
Agustus 2024–Agustus 2026 untuk membangun model prediksi churn dan membandingkan
Random Forest dengan XGBoost.

## 4. Rumusan Masalah / Pertanyaan Penelitian
1. Bagaimana profil dan karakteristik pelanggan pada data penjualan Shopee
   periode Agustus 2024–Agustus 2026?
2. Faktor RFM (Recency, Frequency, Monetary) dan perilaku pembelian apa saja
   yang paling berpengaruh terhadap churn pelanggan?
3. Bagaimana performa Algoritma Random Forest dan XGBoost dalam memprediksi
   churn, dan mana yang lebih baik berdasarkan F1-score, ROC-AUC, dan PR-AUC?
4. Bagaimana pengaruh optimasi (penanganan ketidakseimbangan kelas dan
   penyetelan hyperparameter) terhadap performa prediksi churn?

## 5. Tujuan Penelitian
1. Menganalisis profil pelanggan.
2. Mengidentifikasi faktor dominan penyebab churn.
3. Membandingkan performa Random Forest dan XGBoost.
4. Mengoptimasi model dan mengevaluasi peningkatan performanya.

## 6. Metode
- **Data:** data penjualan Shopee (data primer), 2 tahun, ~3.250 pesanan,
  ~2.355 pelanggan.
- **Definisi churn:** pelanggan tidak bertransaksi pada window holdout
  (Feb–Agu 2026) setelah aktif di window observasi (Agu 2024–Jan 2026).
- **Fitur:** RFM + frekuensi, nilai rata-rata, selang antar-pembelian,
  metode pembayaran, wilayah, kategori produk.
- **Model:** Random Forest vs XGBoost; optimasi dengan `class_weight`/SMOTE
  dan penyetelan hyperparameter (GridSearchCV/RandomizedSearchCV).
- **Evaluasi:** accuracy, precision, recall, F1-score, ROC-AUC, PR-AUC,
  confusion matrix; interpretasi dengan SHAP.

## 7. Keterbatasan (wajib dibahas)
- **Ketidakseimbangan kelas:** hanya ~8,3% pelanggan yang kembali beli
  (124 dari 1.487) → model "semua churn" mencapai 91,7% akurasi tapi tidak
  berguna. Evaluasi wajib pakai F1/PR-AUC, bukan akurasi.
- **Sifat produk:** produk custom berbasis acara (tas bidan, souvenir)
  membuat pembelian berulang memang rendah secara alamiah — ini bisa
  menjadi konfounding dan harus dibahas.
- **Data primer, bukan public:** perlu konfirmasi dosen, atau tambah dataset
  public sebagai pembanding.
- **Privasi:** Nama Penerima/No. Telepon/Alamat sudah dimasking Shopee;
  jangan dipublikasikan; data mentah dikecualikan dari Git.

## 8. Tabel Penelitian Terdahulu (State of the Art)

> ⚠️ Web search tidak tersedia, sehingga tabel di bawah hanya berisi
> **referensi metode/seminal yang terverifikasi**. Untuk memenuhi syarat
> "10 artikel penelitian terdahulu", **tambahkan 3–4 artikel jurnal spesifik
> topik churn/segmentasi e-commerce** dari Google Scholar/Scopus (lihat query
> di bawah). Jangan mengarang sitasi.

| No | Penulis (Tahun) | Judul | Sumber | Metode/Algoritma | Relevansi |
|----|-----------------|-------|--------|------------------|-----------|
| 1 | Breiman (2001) | Random Forests | *Machine Learning* 45(1) | Random Forest | Algoritma B |
| 2 | Chen & Guestrin (2016) | XGBoost: A Scalable Tree Boosting System | *KDD* | XGBoost | Algoritma C |
| 3 | Chawla dkk. (2002) | SMOTE: Synthetic Minority Over-sampling Technique | *JAIR* 16 | SMOTE | Penanganan imbalance |
| 4 | Cortes & Vapnik (1995) | Support-Vector Networks | *Machine Learning* 20 | SVM | Pembanding klasifikasi |
| 5 | Rish (2001) | An Empirical Study of the Naive Bayes Classifier | *IJCAI* | Naive Bayes | Baseline klasifikasi |
| 6 | Arthur & Vassilvitskii (2007) | K-means++: The Advantages of Careful Seeding | *SODA* | K-Means | Segmentasi pelanggan |
| 7 | Ester dkk. (1996) | A Density-Based Algorithm for Discovering Clusters… (DBSCAN) | *KDD* | DBSCAN | Alternatif clustering |
| 8 | Pedregosa dkk. (2011) | Scikit-learn: Machine Learning in Python | *JMLR* 12 | — | Pustaka acuan |
| 9 | Fawcett (2006) | An Introduction to ROC Analysis | *Pattern Recognition Letters* 27 | ROC/AUC | Metrik evaluasi |
| 10 | Provost & Fawcett (2013) | Data Science for Business | O'Reilly | — | Konsep churn/retention |

**Query Google Scholar untuk artikel domain (wajib diisi sendiri):**
- `"customer churn prediction" e-commerce RFM`
- `"customer churn" XGBoost "random forest" online retail`
- `customer segmentation RFM K-means e-commerce`
- `prediksi churn pelanggan e-commerce`
> Catat **DOI** setiap artikel untuk verifikasi sitasi.

## 9. Rencana Kerja
| Tahap | Output | Estimasi |
|-------|--------|----------|
| Persiapan lingkungan & dataset | Python, Jupyter, pustaka, data bersih | 1 minggu |
| EDA & rekayasa fitur RFM | `notebook/01`, `notebook/02`, `data/processed/` | 1–2 minggu |
| Pemodelan RF vs XGBoost + optimasi | `notebook/03`, `model/` | 2–3 minggu |
| Analisis hasil, SHAP, pembahasan | Bab IV–V | 1–2 minggu |
| Penulisan & revisi | Bab I–VI, `draft/` | 1–2 minggu |

## 10. Referensi Lengkap (format APA, contoh)
- Breiman, L. (2001). Random forests. *Machine Learning, 45*(1), 5–32.
- Chen, T., & Guestrin, C. (2016). XGBoost: A scalable tree boosting system. *Proceedings of the 22nd ACM SIGKDD*, 785–794.
- Chawla, N. V., Bowyer, K. W., Hall, L. O., & Kegelmeyer, W. P. (2002). SMOTE: Synthetic minority over-sampling technique. *Journal of Artificial Intelligence Research, 16*, 321–357.
- Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research, 12*, 2825–2830.

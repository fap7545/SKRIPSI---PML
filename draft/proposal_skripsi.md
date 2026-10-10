# Proposal Skripsi

## 1. Judul Penelitian
**Optimasi Clustering Segmentasi Pelanggan E-Commerce pada Data Penjualan Shopee Ramay Souvenir menggunakan Algoritma K-Means dan DBSCAN**

> Format sesuai instruksi dosen: *optimasi [clustering] tentang [A] menggunakan algoritma [B] dan algoritma [C]*.
> Catatan: jika dosen mewajibkan dataset **public** (bukan data primer), gunakan dataset public (mis. UCI Online Retail) atau tambahkan sebagai pembanding.

## 2. Topik Penelitian
Segmentasi pelanggan e-commerce berbasis RFM (Recency, Frequency, Monetary)
dengan metode **clustering**, membandingkan Algoritma **K-Means** dan
**DBSCAN**, serta mengoptimasinya (jumlah klaster k; hyperparameter
eps & min_samples) berdasarkan metrik validasi internal (Silhouette dan
Davies-Bouldin).

## 3. Latar Belakang (singkat)
Mengetahui tipe pelanggan sangat penting untuk strategi pemasaran yang
tepat sasaran. Penelitian ini mengelompokkan pelanggan usaha
(Ramay Souvenir) berdasarkan perilaku pembelian (RFM) dari data
penjualan Shopee periode Agustus 2024–Agustus 2026, membandingkan
K-Means (berbasis centroid) dan DBSCAN (berbasis densitas), lalu
memprofilkan setiap segmen dan merumuskan strategi pemasaran.

## 4. Rumusan Masalah / Pertanyaan Penelitian
1. Bagaimana profil dan karakteristik pelanggan Ramay Souvenir berdasarkan
   dimensi RFM (Recency, Frequency, Monetary)?
2. Berapa jumlah segmen pelanggan yang optimal, dan bagaimana ciri profil
   masing-masing segmen?
3. Bagaimana perbandingan Algoritma K-Means dan DBSCAN dalam membentuk
   segmen pelanggan, ditinjau dari metrik validasi internal (Silhouette
   Coefficient dan Davies-Bouldin Index)?
4. Bagaimana pengaruh optimalisasi parameter (k pada K-Means; eps dan
   min_samples pada DBSCAN) terhadap kualitas segmen (Silhouette dan
   Davies-Bouldin)?
5. Bagaimana strategi pemasaran (retensi dan pengembangan) yang sesuai
   untuk setiap segmen yang teridentifikasi?

## 5. Tujuan Penelitian
1. Menganalisis profil pelanggan berbasis RFM.
2. Menentukan jumlah segmen optimal dan memprofilkan segmen.
3. Membandingkan K-Means dan DBSCAN berdasarkan metrik validasi internal.
4. Mengoptimasi parameter dan mengukur pengaruhnya terhadap kualitas segmen.
5. Merumuskan strategi pemasaran per segmen.

## 6. Metode
- **Data:** data penjualan Shopee Ramay Souvenir (data primer), 2 tahun,
  ~3.250 pesanan, ~2.355 pelanggan.
- **Fitur:** RFM + perilaku pembelian (selang antar-beli, rata-rata nilai,
  metode pembayaran, wilayah).
- **Algoritma:** K-Means vs DBSCAN.
- **Optimasi:** elbow/silhouette untuk k; grid search eps & min_samples.
- **Evaluasi:** Silhouette Coefficient, Davies-Bouldin Index (metrik
  validasi internal — **bukan akurasi**, karena clustering unsupervised).
- **Interpretasi:** profil segmen → strategi pemasaran.

## 7. Keterbatasan (wajib dibahas)
- **Data hanya pesanan "Selesai":** tidak ada pesanan batal/gagal → bias
  seleksi; tidak bisa meneliti pembatalan/retur.
- **Sifat produk:** produk custom berbasis acara (tas bidan, souvenir)
  membuat pembelian berulang rendah secara alamiah (77% pelanggan hanya
  beli 1x) — ini memengaruhi bentuk segmen dan harus dibahas.
- **Data primer, bukan public:** perlu konfirmasi dosen (dosen pemberi
  tugas = dosen pembimbing).
- **Privasi:** Nama Penerima/No. Telepon/Alamat sudah dimasking Shopee;
  jangan dipublikasikan; data mentah dikecualikan dari Git.

## 8. Studi Literatur dan Tabel Penelitian Terdahulu

> ⚠️ Tabel penelitian terdahulu wajib berisi artikel **nyata** yang **Anda baca
> sendiri**. Sesuai Buku Ajar (Bab III, 3.7), referensi dari AI berstatus
> **terduga, bukan fakta**, sampai diverifikasi (judul persis di Google Scholar,
> DOI via doi.org/crossref, baca abstrak & metode). **Jangan mengarang sitasi.**

**Tabel penelitian terdahulu sudah dibuat** di
[`literatur/tabel_penelitian_terdahulu.md`](../literatur/tabel_penelitian_terdahulu.md)
(**15 artikel** terverifikasi — **semuanya dari jurnal Indonesia terakreditasi
Sinta** (Sinta 1–4); format Buku Ajar Tabel 3.2).
Ringkasan beberapa artikel:

| Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah |
|---|---|---|---|---|---|
| Sembiring Brahmana dkk. (2020) | 334.641 transaksi → 1.661 baris RFM | K-Means, K-Medoids, DBSCAN | DBI; Silhouette | K-Means terbaik (Sil 0,913); k = 2 | Parameter dipilih acak |
| Zahra dkk. (2026) | Online Retail II & TransJakarta | K-Means vs DBSCAN | Silhouette; DBI | Hasil bergantung normalisasi | Belum ada strategi pemasaran |
| Saputra & Yusuf (2024) | Transaksi Transjakarta (RFM) | DBSCAN vs K-Means | Silhouette; DBI | K-Means unggul tipis (Sil 0,7149 vs 0,7000) | Bukan data e-commerce; parameter belum dioptimasi |
| Monalisa dkk. (2023) | Transaksi ritel + demografi | DBSCAN (RFM) | Silhouette; k-dist | 5 klaster + 31 noise (Sil 0,4222) | Tidak dibandingkan K-Means |
| Al Hamid & Wiradinata (2026) | 3.200 transaksi / 2.637 pelanggan | K-Means (RFM) | WSS; Silhouette | 2 klaster; Sil 0,513 | Hanya K-Means |
| Djun dkk. (2024) | Transaksi UMKM | K-Means (RFM) | Elbow; Silhouette; DBI | k = 3 (Sil 0,548) | Hanya K-Means |
| Sutramiani dkk. (2024) | Data UMKM (aset & omzet) | DBSCAN vs K-Means | Optimasi ε/minPts & k | Pengelompokan UMKM | Bukan RFM/perilaku belanja |
| Fadhillah dkk. (2024) | Transaksi pelanggan | K-Means, Agglomerative, DBSCAN | Silhouette; DBI; CHI | K-Means terbaik (k=3) | Silhouette rendah; DBSCAN lemah |
| Alzami dkk. (2023) | E-commerce Brazil (Olist) | K-Means (RFM) + Streamlit | Silhouette | 4 klaster; Sil 0,470 | Hanya K-Means |
| Febrina dkk. (2025) | Toko Hanifah (ritel) | K-Means (RFM) + PCA | Silhouette; PCA | 4 klaster (reguler, pasif, loyal, potensial) | Hanya K-Means |

> **Celah penelitian (kebaruan):** "Perbandingan teroptimasi K-Means vs DBSCAN
> pada segmentasi pelanggan UMKM berbasis RFM dengan data primer berskala kecil
> dan pola pembelian *sparse*." Detail di `literatur/tabel_penelitian_terdahulu.md`.

**Kata kunci pencarian (Google Scholar, filter 5 tahun terakhir):**
- `("customer segmentation" OR "RFM") AND ("K-means" OR "DBSCAN") AND e-commerce`
- `"customer segmentation" AND ("souvenir" OR "creative industry" OR "SME")`
- `("RFM analysis") AND clustering AND retail`
- Di **Sinta** & **Garuda**: `"segmentasi pelanggan" e-commerce` (untuk jurnal Indonesia) — **hanya jurnal terakreditasi Sinta**

**Referensi dasar metode (nyata, wajib dibaca sebagai rujukan klasik):**
- Arthur, D., & Vassilvitskii, S. (2007). K-means++: The advantages of careful seeding. *SODA*, 1027–1035.
- Ester, M., dkk. (1996). A density-based algorithm for discovering clusters in large spatial databases with noise (DBSCAN). *KDD*, 226–231.
- Pedregosa, F., dkk. (2011). Scikit-learn: Machine learning in Python. *JMLR, 12*, 2825–2830.

**Alur kerja poin 6:**
1. Cari dengan kata kunci di atas (filter 5 tahun terakhir).
2. Simpan 15 artikel + metadata ke **Zotero/Mendeley** (semua jurnal Indonesia ber-Sinta).
3. Verifikasi setiap sitasi (DOI, jurnal, abstrak).
4. Isi tabel di atas (kolom: dataset–algoritma–metrik–hasil–celah).
5. Rumuskan **satu celah penelitian yang spesifik dan dapat diuji** (inilah justifikasi kebaruan skripsi Anda).

## 9. Rencana Kerja
| Tahap | Output | Estimasi |
|-------|--------|----------|
| Persiapan lingkungan & dataset | Python, Jupyter, pustaka, data bersih | 1 minggu |
| EDA & rekayasa fitur RFM | `notebook/01`, `notebook/02`, `data/processed/` | 1–2 minggu |
| Clustering K-Means vs DBSCAN + optimasi | `notebook/03`, `model/` | 2–3 minggu |
| Profil segmen, strategi, pembahasan | Bab IV–V | 1–2 minggu |
| Penulisan & revisi | Bab I–VI, `draft/` | 1–2 minggu |

## 10. Referensi
Daftar lengkap (15 artikel domain + rujukan metode klasik) ada di
[`literatur/daftar_pustaka.md`](../literatur/daftar_pustaka.md). Rujukan metode:
- Arthur, D., & Vassilvitskii, S. (2007). K-means++: The advantages of careful seeding. *SODA*, 1027–1035.
- Davies, D. L., & Bouldin, D. W. (1979). A cluster separation measure. *IEEE TPAMI, PAMI-1*(2), 224–227.
- Ester, M., Kriegel, H.-P., Sander, J., & Xu, X. (1996). A density-based algorithm for discovering clusters in large spatial databases with noise (DBSCAN). *KDD*, 226–231.
- Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *JMLR, 12*, 2825–2830.
- Rousseeuw, P. J. (1987). Silhouettes: A graphical aid to the interpretation and validation of cluster analysis. *Journal of Computational and Applied Mathematics, 20*, 53–65.

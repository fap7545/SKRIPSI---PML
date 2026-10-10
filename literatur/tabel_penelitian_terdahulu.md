# Tabel Penelitian Terdahulu (State of the Art)

**Topik:** Segmentasi pelanggan e-commerce berbasis RFM dengan clustering
(perbandingan **K-Means** dan **DBSCAN**).

**Format:** 6 kolom sesuai Buku Ajar (Tabel 3.2) —
*Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah*.

> ✅ **15 artikel** — **semuanya dari jurnal Indonesia terakreditasi Sinta**
> (peringkat lengkap: tabel pendukung di bawah). Setiap artikel sudah
> **diverifikasi** (judul, penulis, tahun, jurnal, **DOI**, abstrak) via
> **Crossref** & **Semantic Scholar**, lalu dicek isi PDF-nya.
>
> ➡️ Pembagian: **(A)** 5 artikel membandingkan K-Means vs DBSCAN, **(B)** 1
> artikel berbasis DBSCAN, **(C)** 9 artikel K-Means dengan model RFM.

## A. Perbandingan K-Means vs DBSCAN (5)

| Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah |
|---|---|---|---|---|---|
| Sembiring Brahmana, Mohammed & Chairuang (2020) | 334.641 transaksi → 1.661 baris RFM | K-Means, K-Medoids, **DBSCAN** (k = 2–6) | Davies-Bouldin Index (DBI); Silhouette | **K-Means terbaik** (DBI 0,330; Sil 0,913); k optimal = **2** → segmen "Dormant" & "Golden" | Inisialisasi centroid/eps dipilih acak; belum ada *grid search* parameter |
| Zahra, Arum, Patriawan, Pertiwi, Muslim & Faturrohman (2026) | Online Retail II & TransJakarta | **K-Means vs DBSCAN** | Silhouette; Davies-Bouldin | K-Means terbaik **tanpa** normalisasi (Sil 0,9845); DBSCAN valid **hanya setelah Z-Score**; TransJakarta: DBSCAN → 20 klaster + noise | Hasil bergantung normalisasi; belum ada strategi pemasaran per segmen |
| Fadhillah, Suyoso & Puspitasari (2024) | Data transaksi pelanggan | K-Means, Agglomerative, **DBSCAN** (RFM) | Silhouette; DBI; Calinski-Harabasz | **K-Means terbaik**: k = 3 (Sil 0,364; DBI 0,93; CHI 1.303,6); 3 segmen | Silhouette rendah; DBSCAN lemah → hasil sangat tergantung tuning parameter |
| Sutramiani, Arthana, Lampung, Aurelia, Fauzi & Darma (2024) | Data **UMKM** (nilai aset & omzet) | **DBSCAN vs K-Means** | Perbandingan parameter (ε, minPts, k) | Pengelompokan UMKM; optimasi parameter kedua algoritma | **Bukan** berbasis RFM/perilaku belanja (fokus aset/omzet) |
| Saputra & Yusuf (2024) | Data transaksi pengguna Transjakarta (RFM) | **DBSCAN vs K-Means** | Silhouette; DBI | **K-Means sedikit unggul** (Sil 0,7149; DBI 0,3658) vs DBSCAN (Sil 0,7000; DBI 0,3908); DBSCAN baik mendeteksi *outlier* bernilai tinggi | Bukan data e-commerce; parameter belum dioptimasi menyeluruh |

## B. Berbasis DBSCAN (1)

| Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah |
|---|---|---|---|---|---|
| Monalisa, Juniarti, Saputra, Muttakin & Ahsyar (2023) | Transaksi ritel + data demografi pelanggan | **DBSCAN** (RFM + demografi) | Silhouette; *k-dist graph* | ε = 0,06 & MinPts = 3 → **5 klaster + 31 noise** (Sil 0,4222); klaster 1 = pelanggan prospek, klaster 2–5 = loyal | Tidak dibandingkan dengan K-Means; Silhouette sedang (0,42) |

## C. K-Means dengan Model RFM (9)

| Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah |
|---|---|---|---|---|---|
| Gustriansyah, Suhandi & Antony (2020) | Data penjualan produk | K-Means (RFM) | **8 indeks validitas** | k optimal = **3**; *variance* 0,19113 | Fokus **produk**; hanya K-Means |
| Al Hamid & Wiradinata (2026) | 3.200 transaksi / 2.637 pelanggan (ritel alat musik) | K-Means (RFM) | WSS; Silhouette | 2 klaster optimal; Sil 0,513 | Dataset kecil & rentang singkat; hanya K-Means |
| Fauzan & Alfian (2024) | Dataset e-commerce publik | K-Means vs K-Medoids vs Fuzzy C-Means | Silhouette; DBI; Calinski-Harabasz | **K-Means terbaik** (Sil 0,67305; DBI 0,51435; CHI 5.647,89); 3 segmen (Loyal, Need Attention, Promising) | Tanpa DBSCAN; dataset publik |
| Djun, Gunadi & Sariyasa (2024) | Data transaksi **UMKM** | K-Means (RFM) | Elbow; Silhouette; DBI | k = 3 (Sil 0,548; DBI 0,76); strategi CRM per segmen | Hanya K-Means; tanpa pembanding densitas |
| Tampubolon, Butar Butar & Rochimah (2024) | Data pelanggan majalah di situs e-commerce | K-Means++ (RFM, CRISP-DM) | WSS; Silhouette | k = 3 (Sil 0,638181; WSS 843,21) | Hanya K-Means++; tanpa DBSCAN |
| Alzami, Sambasri, Nabila, Megantara, Akrom, Pramunendar, Prabowo & Sulistiyawati (2023) | E-commerce Brazil (Olist/Streamlit) | K-Means (RFM) | Silhouette | 4 klaster; Sil 0,470 | Hanya K-Means |
| Widiyanto & Witanti (2021) | Transaksi PT Coversuper Indonesia Global | K-Means (RFM) | Akurasi (uji sistem) | 4 segmen; akurasi uji 100% (29/29) | Hanya K-Means; bukan platform e-commerce |
| Maskanah (2020) | Transaksi Toko Purnama (579 pelanggan; CRISP-DM, Weka) | K-Means (RFM) | Elbow | 3 cluster: sedang (438, R↓F↓M↓), terbaik (106, R↓F↑M↑), terburuk (35, R↑F↓M↓) | Hanya K-Means; diproses manual di Weka |
| Febrina, Saputra & G (2025) | Transaksi Toko Hanifah (ritel kebutuhan harian) | K-Means (RFM) + PCA | Silhouette; PCA | 4 klaster: reguler, pasif, **loyal**, potensial | Hanya K-Means; bukan data e-commerce |

## D. Cadangan (2, opsional — semua jurnal Sinta)

| Peneliti (Tahun) | Dataset | Algoritma | Metrik | Hasil | Celah |
|---|---|---|---|---|---|
| Mado & Hendry (2025) | Transaksi e-commerce | K-Means (RFM) | Silhouette | 3 segmen utama | Hanya K-Means |
| Imanuel & Alfian (2025) | Data toko retail online | K-Means vs K-Medoids (RFM) + dashboard Looker Studio | Silhouette; DBI; Calinski-Harabasz; UAT | **K-Means unggul** atas K-Medoids (Sil 0,6558 vs 0,4677); 3 segmen | Tanpa DBSCAN |

---

## Tabel Pendukung: Akreditasi Sinta Jurnal

| # | Jurnal | Peringkat Sinta |
|---|---|---|
| 1 | Lontar Komputer (Universitas Udayana) | **Sinta 2** |
| 2 | JOISER — J. Information System Exploration and Research | **Sinta 3** |
| 3 | IJEECS — Indonesian J. Electrical Engineering and Computer Science (IAES) | **Sinta 1** |
| 4 | JAIC — J. Applied Informatics and Computing (Polibatam) | **Sinta 3** |
| 5 | JISKA — J. Informatika Sunan Kalijaga (UIN Suka) | **Sinta 3** |
| 6 | JTIM — J. Teknologi Informasi dan Multimedia | **Sinta 4** |
| 7 | JTIIK — J. Teknologi Informasi dan Ilmu Komputer (UB) | **Sinta 2** |
| 8 | MALCOM — Indonesian J. Machine Learning and Computer Science (IRPI) | **Sinta 3** (dulu 4) |
| 9 | JISEBI — J. Information Systems Engineering and Business Intelligence (Unair) | **Sinta 2** |
| 10 | ILKOM Jurnal Ilmiah (UMI) | **Sinta 2** |
| 11 | KONSTELASI — Konvergensi Teknologi dan Sistem Informasi (UAJY) | **Sinta 4** |
| 12 | TELKOMNIKA (UAD) | **Sinta 1** |
| 13 | INOVTEK Polbeng – Seri Informatika | **Sinta 3** |
| 14 | Jurnal Pustaka AI | **Sinta 4** |
| 15 | JIMIK — J. Indonesia Manajemen Informatika dan Komunikasi (cadangan) | **Sinta 4** |

> ✅ **15 dari 15 artikel utama** berasal dari jurnal **terakreditasi Sinta**
> (Sinta 1–4). Tidak ada jurnal non-Sinta maupun jurnal internasional di daftar ini.

---

## Analisis Celah Penelitian (Research Gap)

Pola dari 15 artikel:

1. **K-Means hampir selalu menang atas DBSCAN, tetapi hasilnya tidak konsisten:**
   - Sembiring Brahmana (2020): K-Means jauh menang (Sil 0,913).
   - Saputra & Yusuf (2024): K-Means menang tipis (Sil 0,7149 vs 0,7000).
   - Fadhillah (2024): K-Means menang, DBSCAN lemah (Sil 0,364).
   - Zahra (2026): pemenang **bergantung normalisasi data**.
   → Pemenang bergantung pada **preprocessing & optimasi parameter** — inilah
   ruang optimasi yang dapat diteliti.

2. **K-Means vs DBSCAN pada data *pelanggan* UMKM hampir tidak ada.**
   - Sutramiani (2024) membandingkan keduanya, **tetapi** pada data **aset/omzet
     UMKM**, bukan perilaku belanja (RFM).
   - Djun (2024) & Febrina (2025) memakai RFM ritel/UMKM, **tetapi** hanya K-Means.
   - Belum ada yang menggabungkan: **RFM + data primer UMKM + K-Means vs DBSCAN +
     optimasi parameter**.

3. **Optimasi parameter jarang sistematis & tidak ada yang membahas pola *sparse*.**
   Pelanggan UMKM *event-based* (souvenir) mayoritas membeli 1× — karakteristik
   yang menantang DBSCAN dan belum dibahas di literatur.

### Celah spesifik (kebaruan skripsi Anda)
> **"Optimasi perbandingan K-Means vs DBSCAN pada segmentasi pelanggan UMKM
> berbasis RFM dengan data primer berskala kecil dan pola pembelian *sparse*
> (mayoritas pelanggan bertransaksi 1×)."**

Kebaruan: konteks **UMKM souvenir Indonesia**, **data primer** (export Shopee),
dan **optimasi parameter eksplisit** (k untuk K-Means; ε & min_samples untuk
DBSCAN) yang dinilai dengan Silhouette & Davies-Bouldin — kombinasi yang belum
ada di 15 artikel di atas.

---

*Catatan: hasil pencarian + verifikasi otomatis. Sebelum masuk proposal final,
**baca abstrak & metode tiap artikel** lalu simpan ke Zotero/Mendeley.*
# Literatur — Poin 6

Folder ini berisi hasil **studi literatur 15 artikel + tabel penelitian terdahulu (SoA)**
untuk topik:

> Segmentasi pelanggan e-commerce berbasis RFM dengan clustering
> (perbandingan **K-Means** dan **DBSCAN**).

## Isi folder

| File | Isi |
|---|---|
| `tabel_penelitian_terdahulu.md` | **Tabel SoA** (format Buku Ajar: Peneliti–Dataset–Algoritma–Metrik–Hasil–Celah) + tabel akreditasi Sinta + analisis celah |
| `tabel_penelitian_terdahulu.csv` | Versi CSV (ditambah kolom Jurnal & Sinta) |
| `daftar_pustaka.md` | Daftar pustaka lengkap (APA) + DOI + status Sinta |
| `pdf/` | **File PDF artikel** yang sudah diunduh (12 dari 15) + status sisanya |
| `README.md` | File ini |

## Ringkasan
- **15 artikel inti — semuanya dari jurnal Indonesia terakreditasi Sinta**
  (Sinta 1–4). **Tidak ada** jurnal internasional maupun jurnal non-Sinta.
- Pembagian: **5 artikel membandingkan K-Means vs DBSCAN**, 1 artikel DBSCAN,
  9 artikel K-Means + RFM.
- + 2 cadangan (JIMIK Sinta 4, JTIIK Sinta 2).
- Sumber: **Google Scholar, Crossref, Semantic Scholar, Sinta/Garuda**.

## Status verifikasi

Semua artikel inti **sudah diverifikasi**:
- Judul, penulis, tahun, jurnal, volume-halaman → dicek lewat **Crossref**
- DOI & abstrak → dicek lewat **Semantic Scholar** / Crossref
- Angka pada kolom "Hasil" diambil **langsung dari abstrak artikel**
- Status **Sinta** setiap jurnal sudah dicek di `sinta.kemdikbud.go.id`

## Sesuai ketentuan Buku Ajar (Bab III)
| Ketentuan | Status |
|---|---|
| Kolom tabel: peneliti(tahun)–dataset–algoritma–metrik–hasil–celah | ✅ |
| Artikel nyata & terverifikasi (DOI, jurnal, volume-halaman) | ✅ |
| Rentang ≤10 tahun (Bab III 3.4) | ✅ (2020–2026) |
| Artikel jurnal primer + konteks Indonesia | ✅ |
| **Semua jurnal terakreditasi Sinta (Sinta 1–4)** | ✅ (15/15) |
| Kata kunci Boolean | ✅ (lihat bawah) |
| Celah penelitian spesifik & dapat diuji | ✅ |
| Disimpan di `literatur/` + DOI | ✅ |
| File PDF artikel didownload | ✅ **12 dari 15** (3 manual — lihat `pdf/README.md`) |
| Setiap baris dibaca sendiri + Zotero/Mendeley | ⚠️ **belum** — tugas Anda |
| 15–30 artikel untuk skripsi | ✅ (15 inti) |

## Strategi pencarian yang dipakai (bisa diulang)

**Sumber:** Google Scholar, Crossref, Semantic Scholar, **Sinta/Garuda**, situs jurnal Indonesia.

**Kata kunci:**
- `("customer segmentation" OR "RFM") AND ("K-means" OR "DBSCAN") AND e-commerce`
- `segmentasi pelanggan RFM K-Means DBSCAN UMKM e-commerce`
- `("RFM analysis") AND clustering AND retail`
- Di **Sinta/Garuda**: hanya jurnal **terakreditasi Sinta** (filter akreditasi).

**Filter:** 5–10 tahun terakhir; jurnal Indonesia **wajib terakreditasi Sinta**;
snowballing (daftar pustaka artikel).

> ⚠️ Catatan akademik (Buku Ajar Bab III 3.7): verifikasi otomatis menjamin
> artikelnya *ada*, tetapi **kesesuaian isi** tetap harus Anda cek dengan membaca
> abstrak & metode, lalu simpan ke **Zotero/Mendeley**.
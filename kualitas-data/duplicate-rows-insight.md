> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Semua panduan di file ini JUDGMENT CALL berdasarkan rule-of-thumb umum di literatur data quality management, BUKAN riset primer atau standar resmi untuk UMKM Indonesia. Review satu-satu sebelum di-approve — kalau ada panduan yang menurutmu tidak sesuai kondisi data riil, koreksi sebelum dipublish.

# Baris Duplikat — Ambang Batas Interpretasi

> **File rumus:** `duplicate-rows.md` (definisi & cara hitung, tidak berubah)

## Kenapa "sumber data" penting buat interpretasi duplikat

Sama seperti null%, ambang batas severity duplikat aplikasi ini generik untuk semua dataset. Yang beda per konteks bukan angkanya, tapi PENYEBAB PALING MUNGKIN di balik angka itu — dan penyebab itu menentukan apa yang perlu disarankan ke user.

## Kemungkinan penyebab berdasarkan pola data (bukan jenis usaha spesifik)

| Pola yang terlihat | Kemungkinan penyebab | Saran yang relevan |
|---|---|---|
| Duplikat sedikit (1-2 baris), tersebar acak di seluruh dataset | Kesalahan input manual (double-submit form, double-scan barcode) | Cek baris itu satu-satu, biasanya cukup dihapus salah satunya. |
| Duplikat banyak, berkelompok di rentang baris tertentu | File digabung dari beberapa sumber yang tumpang tindih (lihat contoh migrasi di `duplicate-rows.md`) | Tanyakan ke user apakah file ini hasil gabungan lebih dari satu export. |
| Duplikat tersebar merata di SELURUH dataset dengan persentase tinggi | Proses export/generate data itu sendiri yang bermasalah (bug di sistem sumber, bukan human error) | Sarankan cek ulang proses export di sumbernya, bukan cuma bersihkan file ini. |

**⚠️ Perlu direview:** pemetaan pola->penyebab di atas itu heuristik umum data engineering, belum divalidasi terhadap dataset UMKM riil — cocokkan dengan pengalaman nyata sebelum jadi acuan.

## Yang TIDAK boleh AI lakukan

- Jangan langsung menyimpulkan penyebab duplikat tanpa melihat POLA-nya dulu (acak vs berkelompok vs merata) — beda pola, beda kemungkinan penyebab, beda saran.
- Jangan sarankan "hapus semua duplikat" sebagai solusi otomatis tanpa disclaimer — kalau ternyata itu bukan duplikat asli (dua transaksi beda tapi kebetulan semua kolom terlihat sama, misal dataset yang kolomnya sangat sedikit), menghapus baris bisa menghilangkan data valid.

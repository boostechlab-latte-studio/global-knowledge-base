> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Semua panduan di file ini JUDGMENT CALL berdasarkan rule-of-thumb umum di literatur data quality management, BUKAN riset primer atau standar resmi untuk UMKM Indonesia. Review satu-satu sebelum di-approve — kalau ada panduan yang menurutmu tidak sesuai kondisi data riil, koreksi sebelum dipublish.

# Persentase Outlier — Ambang Batas Interpretasi

> **File rumus:** `outlier-percentage.md` (definisi & cara hitung, tidak berubah)

## Kenapa outlier butuh konteks lebih dari null%/duplikat

Null% dan duplikat itu hampir selalu masalah proses. Outlier BEDA — angka yang secara statistik "ekstrem" bisa jadi kesalahan input ATAU bisa jadi kejadian bisnis yang benar-benar terjadi dan justru PENTING untuk dilihat (bukan dibuang). Salah menganggap outlier asli sebagai "data kotor" bisa bikin insight bisnis penting terlewat.

## Sinyal pembeda: kesalahan input vs kejadian nyata

| Sinyal | Lebih mengarah ke | Kenapa |
|---|---|---|
| Nilai outlier persis kelipatan 10/100/1000 dari nilai wajar (misal 350.000 vs kisaran normal 35.000) | Kesalahan input (salah ketik nol) | Pola kelipatan bulat itu ciri khas typo, bukan variasi bisnis alami. |
| Outlier cuma 1-2 baris, dan baris itu juga punya keanehan lain (tanggal aneh, kolom lain kosong) | Kesalahan input/data rusak | Outlier yang "beneran" biasanya baris lainnya tetap konsisten/lengkap. |
| Outlier berulang di periode/pola tertentu (misal selalu di akhir bulan, atau selalu untuk 1 pelanggan tertentu) | Kejadian bisnis nyata (pesanan grosir, langganan besar) | Pola berulang menunjukkan itu bagian dari perilaku bisnis, bukan kecelakaan satu kali. |
| Outlier tersebar acak, jumlahnya kecil, tidak ada pola jelas | Bisa jadi keduanya — perlu ditanyakan ke user, jangan disimpulkan sepihak | Tanpa pola, statistik saja tidak cukup untuk memutuskan. |

**⚠️ Perlu direview:** heuristik pembeda di atas belum divalidasi terhadap kasus outlier nyata dari data UMKM Indonesia — cocokkan dengan pengalaman nyata sebelum dijadikan acuan baku.

## Yang TIDAK boleh AI lakukan

- Jangan otomatis menyarankan "hapus outlier ini" — outlier yang merupakan kejadian bisnis nyata itu justru informasi berharga (transaksi besar, pelanggan VIP), bukan sampah data.
- Jangan berhenti di "ada outlier, severity tinggi" tanpa menyebutkan KEMUNGKINAN dua arahnya (kesalahan input ATAU kejadian nyata) — narasi yang cuma bilang "datanya aneh" tanpa arah tindak lanjut kurang membantu.
- Jangan asumsikan outlier selalu di sisi "terlalu besar" — outlier bisa juga di sisi "terlalu kecil" (misalnya harga Rp 0 atau harga negatif), yang hampir selalu kesalahan input, bukan kejadian bisnis nyata.

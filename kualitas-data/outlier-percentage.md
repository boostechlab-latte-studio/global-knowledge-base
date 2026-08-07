# Persentase Outlier

> **Kategori:** kualitas-data
> **File terkait:** `outlier-percentage-insight.md` (ambang batas per konteks bisnis — file terpisah, lihat catatan di bawah)

## Kenapa ini dicek

Outlier adalah nilai di kolom angka yang jauh di luar rentang wajar dibanding nilai-nilai lain di kolom yang sama. Outlier bisa berarti dua hal yang sangat berbeda: (1) kesalahan input (salah ketik jumlah nol, satuan tertukar), atau (2) kejadian nyata yang memang ekstrem (transaksi besar yang benar-benar terjadi, misalnya pesanan grosir di tengah transaksi eceran). Membedakan keduanya butuh konteks bisnis, bukan cuma angka statistik.

## Rumus

Backend aplikasi ini mendeteksi outlier per kolom numerik memakai metode IQR (Interquartile Range) — outlier adalah nilai di luar rentang:

```
Batas Bawah = Q1 − 1.5 × (Q3 − Q1)
Batas Atas  = Q3 + 1.5 × (Q3 − Q1)
Persentase Outlier = (Jumlah nilai di luar [Batas Bawah, Batas Atas] / Jumlah nilai tidak-null di kolom itu) × 100%
```

Q1 = kuartil pertama (25% data terkecil), Q3 = kuartil ketiga (75% data terkecil). Metode IQR ini standar statistik umum untuk deteksi outlier, tidak spesifik ke satu sumber.

## Cara baca

- Persentase dihitung dari nilai yang TIDAK null saja — kolom dengan banyak null tidak otomatis punya persentase outlier yang bias, karena pembaginya sudah dikecualikan dari nilai kosong.
- Outlier dihitung PER KOLOM secara independen — outlier di kolom `harga` tidak terkait langsung dengan outlier di kolom `jumlah` pada baris yang sama, kecuali memang kebetulan baris yang sama.

## Contoh konkret

Kolom `harga` di 100 transaksi warung makan: mayoritas nilai antara Rp 8.000–Rp 35.000, tapi ada 3 baris dengan nilai Rp 350.000. Metode IQR akan menandai ketiga baris itu sebagai outlier secara statistik — TAPI itu bisa jadi katering pesanan besar yang memang benar terjadi (nilai valid, bukan kesalahan), atau salah ketik "35.000" jadi "350.000" (kesalahan input). Angka statistiknya sama; makna bisnisnya beda total — lihat `outlier-percentage-insight.md`.

## Kapan ini WAJIB diangkat AI duluan

- Outlier% di atas ambang batas severity generik aplikasi (`outlier_pct_medium`/`outlier_pct_high`) pada kolom yang berhubungan langsung dengan uang (harga, total, ongkos).
- Ada outlier di kolom angka yang secara logis punya batas wajar jelas (misalnya persentase yang > 100%, atau umur yang negatif) — ini hampir selalu kesalahan input, bukan kejadian ekstrem nyata.

> **Catatan interpretasi:** severity outlier yang dihitung aplikasi TIDAK berubah oleh file ini — lihat `outlier-percentage-insight.md` untuk cara membedakan outlier "kesalahan input" vs "kejadian nyata".

## Sumber

Metode IQR untuk deteksi outlier adalah teknik statistik standar (Tukey's fences), dipakai luas dan konsisten di berbagai referensi statistik deskriptif — bukan rumus yang berbeda per sumber. Implementasi persis (termasuk pengali 1.5) dan ambang batas severity generik (`outlier_pct_medium`, `outlier_pct_high`) ditentukan oleh aplikasi yang mengonsumsi konten ini — bukan oleh file ini.

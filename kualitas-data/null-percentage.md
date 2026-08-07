# Persentase Null (Data Kosong)

> **Kategori:** kualitas-data
> **File terkait:** `null-percentage-insight.md` (ambang batas per konteks bisnis — file terpisah, lihat catatan di bawah)

## Kenapa ini dicek

Data kosong (null) di sebuah kolom berarti backend tidak tahu nilai sebenarnya untuk baris itu — bisa karena memang belum diisi, gagal ditangkap saat input, atau kolom itu memang opsional. Persentase null yang tinggi di kolom yang PENTING (misalnya harga, tanggal transaksi) bikin analisis di atasnya jadi kurang bisa diandalkan; persentase null yang tinggi di kolom yang memang opsional (misalnya catatan tambahan) itu wajar dan tidak otomatis jadi masalah.

## Rumus

```
Persentase Null = (Jumlah baris kosong di kolom itu / Total baris) × 100%
```

Dihitung per kolom, bukan per dataset — satu dataset bisa punya kolom dengan null% tinggi berdampingan dengan kolom lain yang null%-nya 0%.

## Cara baca

- Null% dihitung dari SELURUH baris di dataset, termasuk baris yang kosong di banyak kolom sekaligus (baris "rusak total" tetap dihitung sekali per kolom yang kosong, bukan dikecualikan).
- Null% tinggi di kolom kunci (dipakai buat join, filter, atau perhitungan agregat) berdampak lebih besar dibanding null% tinggi di kolom deskriptif — satu baris dengan kolom kunci kosong biasanya tidak bisa ikut dihitung sama sekali di analisis manapun yang menyentuh kolom itu.

## Contoh konkret

Dataset transaksi warung 200 baris:
- Kolom `harga`: 4 baris kosong → Null% = 4/200 × 100% = **2%**
- Kolom `catatan_kasir` (opsional, cuma diisi kalau ada kejadian khusus): 180 baris kosong → Null% = **90%**

Kedua angka itu benar secara matematis, tapi artinya SANGAT berbeda: 2% null di `harga` layak dicek satu-satu (kolom kunci untuk hitung omset), sementara 90% null di `catatan_kasir` itu memang perilaku normal kolom opsional — lihat `null-percentage-insight.md` untuk cara membedakan keduanya lebih sistematis.

## Kapan ini WAJIB diangkat AI duluan

- Null% tinggi (lihat ambang batas skor bawaan aplikasi) muncul di kolom yang namanya mengindikasikan data inti (harga, jumlah, tanggal, nama produk) — bukan di kolom yang namanya jelas opsional/catatan.
- Null% naik dibanding pemeriksaan sebelumnya pada dataset yang sama sumbernya (kalau riwayat tersedia) — tren memburuk lebih penting dari angka snapshot satu kali.

> **Catatan interpretasi:** skor severity null% yang dihitung aplikasi (baik/sedang/tinggi) SELALU berdasarkan ambang batas generik yang sama untuk semua kolom — file ini dan `null-percentage-insight.md` TIDAK mengubah angka/severity itu, cuma menambah konteks bisnis yang bisa dipakai LLM buat menulis narasi yang lebih tepat sasaran. Lihat `null-percentage-insight.md`.

## Sumber

Rumus persentase null itu definisi matematis universal (jumlah kosong dibagi total, dikali 100%) — dipakai identik di seluruh literatur data quality management, bukan rumus yang bisa berbeda per sumber. Ambang batas severity generik aplikasi ini sendiri ada di `backend/app/configs/data_quality.json` (`null_pct_medium`, `null_pct_high`) — bukan ambang batas dari file ini.

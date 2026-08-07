# Baris Duplikat

> **Kategori:** kualitas-data
> **File terkait:** `duplicate-rows-insight.md` (ambang batas per konteks bisnis — file terpisah, lihat catatan di bawah)

## Kenapa ini dicek

Baris duplikat adalah baris yang seluruh kolomnya persis sama dengan baris lain di dataset yang sama. Ini paling sering muncul dari kesalahan proses (data yang sama ter-export/ter-import dua kali, form yang ke-submit dua kali karena double-click, atau penggabungan beberapa file yang saling tumpang tindih) — jarang sekali dua transaksi BENERAN identik persis di semua kolom sekaligus terjadi secara alami dalam jumlah besar.

## Rumus

```
Persentase Duplikat = (Jumlah baris duplikat / Total baris) × 100%
```

"Baris duplikat" di sini berarti SELURUH kolom sama persis dengan baris lain — bukan cuma satu kolom yang kebetulan sama (misalnya dua transaksi beda hari dengan harga yang sama bukan duplikat, itu cuma kebetulan nilainya sama).

## Cara baca

- Kalau dataset punya 100 baris dan 5 di antaranya adalah salinan persis dari baris lain, duplicate_row_count = 5, bukan 10 — dihitung baris yang "kelebihan", bukan seluruh kelompok yang terlibat duplikasi.
- Duplikat tinggi paling sering berarti masalah PROSES (bukan masalah bisnis) — sumber data yang sama ter-input dua kali lewat jalur berbeda, atau file yang di-upload ulang tanpa sadar sudah pernah di-upload sebelumnya.

## Contoh konkret

Toko online export data pesanan dari 2 sistem berbeda (sistem lama + sistem baru) ke satu file gabungan karena masa transisi — pesanan yang diproses SEBELUM migrasi tercatat di kedua sistem dengan data identik, jadi muncul dua kali di file gabungan. Ini duplikat murni karena proses migrasi, bukan berarti tokonya benar-benar menerima pesanan yang sama dua kali dari pelanggan.

## Kapan ini WAJIB diangkat AI duluan

- Duplicate% di atas ambang batas severity generik aplikasi (lihat `duplicate_pct_medium`/`duplicate_pct_high` di config) — wajib disinggung karena berpotensi bikin angka agregat (total omset, rata-rata) jadi lebih besar dari yang sebenarnya.
- Ada pola duplikat yang berkelompok (banyak baris duplikat muncul berurutan atau di rentang baris yang sama) — ini sinyal kuat proses import/gabung file, bukan duplikat acak.

> **Catatan interpretasi:** severity duplikat yang dihitung aplikasi TIDAK berubah oleh file ini — lihat `duplicate-rows-insight.md` untuk konteks tambahan soal kapan duplikat yang "sedikit" tetap layak dicek lebih jauh.

## Sumber

Rumus persentase duplikat itu definisi matematis langsung dari perbandingan baris (exact match seluruh kolom) — tidak ada standar/rumus alternatif yang berbeda di sumber manapun. Ambang batas severity generik (`duplicate_pct_medium`, `duplicate_pct_high`) dihitung oleh aplikasi yang mengonsumsi konten ini — bukan ditentukan oleh file ini.

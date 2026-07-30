# Margin Kotor & Margin Bersih

> **Kategori:** analyst — Fase 1: Rasio Keuangan Dasar
> **Butuh:** Laporan Laba Rugi sudah dicatat (lihat kategori `accounting` — `laporan-laba-rugi.md`)
> **File terkait:** `margin-kotor-bersih-insight.md` (ambang batas interpretasi per jenis usaha — file terpisah, lihat catatan di bawah)

## Kenapa ini dicek duluan

Margin itu pertanyaan paling dasar dari analisis usaha: **dari setiap Rp yang masuk, berapa yang beneran jadi untung?** Omset besar tidak otomatis berarti usaha sehat — usaha dengan omset kecil tapi margin tinggi bisa lebih sehat daripada omset besar dengan margin tipis.

## Rumus

### Margin Kotor (Gross Profit Margin)

```
Margin Kotor = (Laba Kotor / Penjualan Bersih) × 100%
Laba Kotor = Penjualan Bersih − Harga Pokok Penjualan (HPP)
```

Margin kotor menunjukkan seberapa efisien usaha menghasilkan laba dari harga jual dibanding biaya produksi/beli barang langsung (HPP) — belum dipotong biaya operasional (sewa, gaji, listrik, dll).

### Margin Bersih (Net Profit Margin)

```
Margin Bersih = (Laba Bersih / Penjualan Bersih) × 100%
```

Margin bersih itu angka yang lebih jujur — sudah dipotong SEMUA biaya (HPP + operasional + non-operasional). Ini yang benar-benar "nyisa" buat pemilik usaha.

## Cara baca dari Laporan Laba Rugi (`accounting`)

Struktur Laporan Laba Rugi sesuai SAK EMKM yang disederhanakan (lihat `accounting/README.md` §3):

```
Pendapatan (Penjualan Bersih)         Rp 20.000.000
(-) Harga Pokok Penjualan (HPP)       Rp 12.000.000
= Laba Kotor                          Rp  8.000.000
(-) Beban Operasional                 Rp  5.000.000
(-) Beban Non-Operasional             Rp    500.000
= Laba Bersih                         Rp  2.500.000
```

Dari contoh ini:
- Margin Kotor = 8.000.000 / 20.000.000 × 100% = **40%**
- Margin Bersih = 2.500.000 / 20.000.000 × 100% = **12,5%**

## Contoh UMKM konkret

Warung makan "Bu Sri" bulan ini:
- Penjualan bersih: Rp 15.000.000
- HPP (bahan baku): Rp 9.000.000 → Laba Kotor Rp 6.000.000 → **Margin Kotor 40%**
- Beban operasional (gas, listrik, gaji karyawan, sewa): Rp 4.200.000
- Laba Bersih: Rp 1.800.000 → **Margin Bersih 12%**

Artinya: dari tiap Rp 1.000 jualan nasi, Rp 400 "kotor" tersisa setelah bahan baku, tapi cuma Rp 120 yang beneran jadi untung bersih setelah semua biaya operasional dibayar.

## Kapan ini WAJIB diangkat AI duluan

- User baru pertama kali punya laporan laba rugi lengkap (Fase 1 data cukup) → tawarkan hitung margin kotor & bersih sekali, walau tidak diminta eksplisit.
- Margin bersih turun dibanding periode sebelumnya (2 periode berturut-turut) → wajib disinggung, walau user cuma nanya soal omset/kas.
- Margin kotor jauh lebih besar dari margin bersih (gap besar) → sinyal biaya operasional terlalu berat dibanding hasil produksi — layak diangkat sebagai insight, bukan cuma dijawab kalau ditanya.

> **Catatan interpretasi:** angka margin di atas TIDAK diberi label "bagus/jelek" di file ini dengan sengaja — ambang batas "tipis/wajar/sehat" beda-beda per jenis usaha (retail vs jasa vs kuliner) dan itu JUDGMENT CALL yang perlu divalidasi manual satu-satu. Lihat `margin-kotor-bersih-insight.md`.

## Sumber

- Rumus gross/net profit margin — konsisten di berbagai sumber akademik manajemen keuangan Indonesia (cross-check per riset 2026-07-29): [Pengertian Rasio Keuangan — bee.id](https://www.bee.id/blog/pengertian-rasio-keuangan-fungsi-dan-contohnya/), jurnal manajemen keuangan STIESIA & sumber akademik sejenis.
- Tidak ada standar resmi pemerintah untuk rumus ini (lihat `analyst/README.md` §0) — rumus matematis universal, bukan aturan yang bisa berubah per kebijakan.

# Rasio Likuiditas Sederhana (Current Ratio)

> **Kategori:** analyst — Fase 1: Rasio Keuangan Dasar
> **Butuh:** Neraca/Laporan Posisi Keuangan sudah dicatat (lihat kategori `accounting` — `neraca-posisi-keuangan.md`)
> **File terkait:** `rasio-likuiditas-sederhana-insight.md` (ambang batas aman/waspada/bahaya — file terpisah)

## Kenapa ini penting

Usaha bisa untung di atas kertas (laba bersih positif) tapi tetap kesulitan BAYAR TAGIHAN jangka pendek kalau uangnya "terkunci" di stok barang atau piutang yang belum cair. Rasio likuiditas menjawab pertanyaan: **kalau semua tagihan jangka pendek jatuh tempo sekarang, apa usaha ini punya cukup aset yang gampang dicairkan buat bayar?**

## Rumus

```
Current Ratio = Aset Lancar / Kewajiban Lancar
```

- **Aset Lancar**: kas, tabungan, piutang usaha (uang yang akan diterima dari pelanggan), persediaan/stok barang, dan aset lain yang bisa dicairkan dalam waktu ≤ 1 tahun.
- **Kewajiban Lancar**: hutang usaha, hutang jatuh tempo dekat, gaji yang belum dibayar, dan kewajiban lain yang harus dilunasi dalam ≤ 1 tahun.

Hasilnya dinyatakan sebagai angka rasio (misal "2,0" atau "2 kali"), bukan persentase.

## Cara baca dari Neraca (`accounting`)

```
ASET LANCAR
  Kas                          Rp  5.000.000
  Piutang Usaha                Rp  2.000.000
  Persediaan                   Rp  3.000.000
  Total Aset Lancar            Rp 10.000.000

KEWAJIBAN LANCAR
  Hutang Usaha                 Rp  4.000.000
  Total Kewajiban Lancar       Rp  4.000.000
```

Current Ratio = 10.000.000 / 4.000.000 = **2,5**

Artinya: setiap Rp 1 kewajiban jangka pendek, usaha ini punya Rp 2,5 aset lancar buat menutupinya.

## Contoh konkret

Toko kelontong "Pak Budi":
- Aset lancar: kas Rp 3.000.000 + piutang warung langganan Rp 1.000.000 + stok barang Rp 6.000.000 = Rp 10.000.000
- Kewajiban lancar: hutang ke distributor Rp 8.000.000
- Current Ratio = 10.000.000 / 8.000.000 = **1,25**

Walau angkanya di atas 1 (aset lancar lebih besar dari kewajiban), sebagian besar aset lancarnya "terkunci" di stok barang (Rp 6 juta dari Rp 10 juta) — bukan kas siap pakai. Ini beda penting yang perlu digali lebih lanjut (lihat bagian proaktif di bawah), bukan cuma dilihat dari angka rasio akhir saja.

**Contoh personal (individu):** konsep current ratio bisa dipakai buat cek kesiapan keuangan pribadi juga — Rina, karyawan:
- "Aset lancar" versi personal: tabungan Rp 5.000.000 + dana darurat di deposito cair Rp 3.000.000 = Rp 8.000.000
- "Kewajiban lancar" versi personal: cicilan yang jatuh tempo bulan ini (kartu kredit, cicilan motor) Rp 2.000.000
- Current Ratio = 8.000.000 / 2.000.000 = **4,0**

Artinya Rina punya 4x lipat dana siap pakai dibanding kewajiban yang mesti dibayar bulan ini — jauh lebih longgar dibanding target minimal umum (biasanya disaranin di atas 1). Sama seperti bisnis, cek juga berapa dari "aset lancar" itu beneran CAIR (tabungan/deposito) vs yang keliatan ada tapi susah dicairkan cepat.

## Kapan ini WAJIB diangkat AI duluan

- Current Ratio di bawah 1 (kewajiban lancar lebih besar dari aset lancar) → WAJIB disinggung segera, ini sinyal risiko arus kas jangka pendek, walau user tidak nanya soal utang.
- Sebagian besar aset lancar berupa persediaan/stok (bukan kas), seperti contoh di atas → AI wajib jelaskan bedanya "rasio kelihatan aman" vs "uang tunai yang beneran siap pakai" — ini kesalahpahaman umum UMKM.
- User baru pertama kali punya data neraca lengkap → tawarkan hitung rasio ini sekali walau tidak diminta.

> **Catatan interpretasi:** ambang batas "aman/waspada/bahaya" untuk current ratio TIDAK ditentukan di file ini — beda kebutuhan kas per jenis usaha (usaha jasa vs usaha dagang dengan stok besar punya kebutuhan likuiditas berbeda). Lihat `rasio-likuiditas-sederhana-insight.md`.

## Sumber

- Definisi & rumus current ratio — konsisten di sumber akademik manajemen keuangan Indonesia (cross-check per riset 2026-07-29): jurnal STIESIA, repository UMSU, dan sumber sejenis yang meninjau current ratio sebagai alat ukur likuiditas standar.
- Tidak ada standar resmi pemerintah untuk rumus ini (lihat `analyst/README.md` §0) — konsep universal manajemen keuangan.

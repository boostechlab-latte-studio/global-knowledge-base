# Rasio Profitabilitas — Return on Sales

> **Kategori:** analyst — Fase 1: Rasio Keuangan Dasar
> **Butuh:** Laporan Laba Rugi sudah dicatat (lihat kategori `accounting` — `laporan-laba-rugi.md`)
> **File terkait:** `rasio-profitabilitas-insight.md` (ambang batas rendah/wajar/tinggi per jenis usaha — file terpisah)
> **Beda dengan `margin-kotor-bersih.md`:** margin bersih (file sebelumnya) itu SALAH SATU bentuk rasio profitabilitas — file ini melihat profitabilitas dari sudut pandang lain: **efisiensi keseluruhan usaha menghasilkan laba dari tiap rupiah yang berputar**, dan jadi jembatan ke topik Fase 2 (BEP & harga).

## Kenapa ini beda dari sekadar margin

Margin bersih menjawab "berapa persen jualan yang jadi untung." Rasio profitabilitas di sini menjawab pertanyaan yang lebih praktis buat pemilik usaha: **dari tiap Rp 1.000 yang masuk kas dari penjualan, berapa rupiah yang beneran jadi untung yang bisa dipakai/ditabung/diputar lagi?** — cara bicara yang lebih konkret buat user awam dibanding istilah "margin bersih X%".

## Rumus

```
Return on Sales (ROS) = (Laba Bersih / Penjualan Bersih) × 100%
```

> Catatan: secara matematis ROS = Margin Bersih (rumus sama). File ini sengaja dipisah dari `margin-kotor-bersih.md` karena CARA BICARANYA beda — margin bersih untuk audiens yang mikir dalam persen, ROS untuk audiens yang lebih gampang mikir dalam "per Rp 1.000 jualan, sisa berapa" (lihat bagian "Cara sampaikan ke user" di bawah). AI boleh pakai kerangka mana pun sesuai gaya bicara user.

## Cara sampaikan ke user (bentuk chat, bukan cuma rumus)

Alih-alih bilang "ROS kamu 12%," lebih gampang dicerna kalau dibalik jadi:

> "Dari tiap Rp 1.000 yang masuk dari jualan, sekitar Rp 120 beneran jadi untung bersih. Sisanya Rp 880 abis buat bahan baku, gaji, sewa, dan biaya lain."

## Contoh UMKM konkret

Salon "Cantika" bulan ini:
- Penjualan bersih (jasa potong+treatment): Rp 12.000.000
- Laba bersih: Rp 1.800.000
- ROS = 1.800.000 / 12.000.000 × 100% = **15%**, atau: dari tiap Rp 1.000 jasa yang terjual, Rp 150 jadi untung bersih.

## Kapan ini WAJIB diangkat AI duluan

- User menanyakan sesuatu yang samar soal "untung nggak sih usaha saya" tanpa spesifik angka → ini topik yang tepat digali AI (lihat `contoh-alur-chat-analisis.md` untuk contoh dialognya).
- ROS turun signifikan dari periode sebelumnya padahal omset (penjualan) naik → sinyal biaya tumbuh lebih cepat dari pendapatan, WAJIB diangkat walau user cuma bangga omset naik.
- Dipakai sebagai jembatan sebelum masuk topik BEP/harga (Fase 2) — kalau ROS rendah, AI bisa proaktif menyarankan lanjut ke analisis harga jual (`strategi-penetapan-harga.md`, Fase 2) sebagai langkah berikutnya yang relevan.

> **Catatan interpretasi:** kapan ROS dianggap "rendah" beda-beda drastis per jenis usaha (usaha jasa biasanya ROS lebih tinggi dari usaha dagang volume tinggi-margin tipis). Ambang batasnya ada di `rasio-profitabilitas-insight.md`, bukan di sini.

## Sumber

- Return on Sales / Net Profit Margin sebagai indikator profitabilitas — konsisten di sumber akademik manajemen keuangan Indonesia (cross-check per riset 2026-07-29), sejalan dengan definisi margin bersih di `margin-kotor-bersih.md`.
- Tidak ada standar resmi pemerintah untuk rumus ini (lihat `analyst/README.md` §0) — konsep universal manajemen keuangan.

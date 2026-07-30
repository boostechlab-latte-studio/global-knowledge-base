> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Ambang batas di file ini JUDGMENT CALL, bukan rumus matematis. Sumber: kisaran yang konsisten di beberapa referensi manajemen keuangan Indonesia (accurate.id, jurnal.id/Mekari, online-pajak.com — dicek 2026-07-29) dan rule-of-thumb umum manajemen keuangan (current ratio 1,5-2,5), BUKAN standar resmi pemerintah (lihat `analyst/README.md` §0). Per §1.5: review SATU-SATU sebelum approve.

# Rasio Likuiditas Sederhana — Ambang Batas Interpretasi

> **File rumus:** `rasio-likuiditas-sederhana.md` (definisi & cara hitung, tidak berubah)

## Ambang batas umum (current ratio)

| Rentang | Label | Arti |
|---|---|---|
| < 1,0 | **Bahaya** | Aset lancar TIDAK CUKUP menutupi kewajiban jangka pendek — risiko nyata gagal bayar tagihan/hutang dalam waktu dekat. |
| 1,0 – 1,5 | **Waspada** | Secara angka masih menutupi, tapi ruang amannya tipis — sedikit gangguan arus kas bisa bikin kesulitan bayar. |
| 1,5 – 2,5 | **Sehat** | Rentang yang umum dianggap aman di berbagai referensi manajemen keuangan — cukup ruang aman tanpa dana "menganggur" berlebihan. |
| > 3,0 | **Perlu ditinjau (bukan otomatis "lebih baik")** | Rasio sangat tinggi bisa berarti terlalu banyak modal "terkunci" di aset lancar (kas nganggur/stok berlebih) yang harusnya bisa diputar buat berkembang, bukan cuma disimpan. |

## Modifikasi PENTING per jenis usaha (§1.5 — beda kebutuhan kas)

Rentang di atas rentang UMUM — kebutuhan likuiditas riil beda jauh tergantung porsi stok:

- **Usaha dagang/retail dengan stok besar** (toko, warung sembako) — rentang "sehat" bisa perlu digeser SEDIKIT LEBIH TINGGI dari 1,5-2,5, karena sebagian besar aset lancarnya adalah stok (tidak segampang kas dicairkan mendadak). **Yang lebih penting dari rasio total: porsi kas murni vs stok** (lihat bagian di bawah).
- **Usaha jasa** (salon, konsultasi, service) — nyaris tidak punya persediaan besar, jadi current ratio yang "cukup" bisa lebih rendah dari 1,5 tanpa berarti bahaya, karena hampir semua aset lancarnya memang kas/piutang yang gampang cair.
- **⚠️ Angka pergeseran spesifik (berapa lebih tinggi/rendah persisnya) BELUM ditentukan di draft ini** — butuh masukan langsung dari kamu, karena ini area yang paling gampang salah tebak kalau cuma dari riset blog.

## Cek tambahan yang WAJIB dilakukan AI, bukan cuma lihat rasio akhir

Rasio 1,25 bisa "aman" atau "berbahaya" tergantung KOMPOSISI aset lancarnya (lihat contoh toko Pak Budi di file rumus). Aturan tambahan:

- Kalau **porsi kas + piutang < 40% dari total aset lancar** (sisanya stok) → AI wajib sebut ini walau current ratio-nya di atas 1,5, karena uang tunai yang beneran siap pakai lebih kecil dari yang kelihatan di rasio.
- Kalau **porsi kas + piutang ≥ 60%** → rasio bisa dipercaya lebih langsung mencerminkan kesiapan bayar tunai.

## Kondisi "AI WAJIB angkat duluan"

1. **Current ratio < 1,0** — wajib disinggung SEGERA, walau user tidak nanya soal utang/kewajiban.
2. **Porsi stok > 60% dari aset lancar** (lihat cek tambahan di atas) — wajib dijelaskan bedanya "rasio aman di atas kertas" vs "uang tunai siap pakai", bahkan kalau current ratio-nya di rentang sehat.
3. **Current ratio turun mendekati 1,0 dari periode sebelumnya** (tren, bukan cuma snapshot) — wajib disinggung sebagai peringatan dini, sebelum benar-benar jatuh di bawah 1.

## Yang TIDAK boleh AI lakukan

- Jangan bilang "aman" hanya dari 1 angka current ratio tanpa cek komposisi kas-vs-stok.
- Jangan pakai rentang UMUM (1,5-2,5) sebagai angka mutlak sama buat semua jenis usaha — selalu framing dengan konteks jenis usaha.

> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Semua panduan di file ini JUDGMENT CALL berdasarkan rule-of-thumb umum di literatur data quality management, BUKAN riset primer atau standar resmi untuk UMKM Indonesia. Review satu-satu sebelum di-approve — kalau ada panduan yang menurutmu tidak sesuai kondisi data riil, koreksi sebelum dipublish.

# Persentase Null — Ambang Batas Interpretasi

> **File rumus:** `null-percentage.md` (definisi & cara hitung, tidak berubah)

## Kenapa "wajar"-nya beda per kolom, bukan per dataset

Ambang batas severity aplikasi ini (`null_pct_medium`/`null_pct_high` di `data_quality.json`) sama untuk SEMUA kolom — itu keputusan desain yang benar untuk skor yang konsisten dan bisa dibandingkan. Tapi kolom mana yang "boleh" punya null tinggi tanpa itu jadi masalah nyata sangat tergantung PERAN kolom itu di alur kerja bisnisnya, bukan cuma angkanya.

## Kategori kolom berdasarkan peran (bukan jenis usaha — ini berlaku lintas jenis usaha)

| Peran kolom | Null% yang masih dianggap wajar | Catatan |
|---|---|---|
| **Kolom kunci transaksi** (harga, jumlah, tanggal transaksi, nama item) | < 5% | Ini data yang dipakai buat hitung omset/laba — null di sini biasanya berarti input gagal tercatat, bukan "memang kosong". |
| **Kolom identitas berulang** (nama pelanggan, kode produk — kalau memang dipakai berulang di banyak baris) | 5% – 15% | Wajar ada sedikit baris tanpa identitas (misal transaksi tunai tanpa nama pembeli dicatat), tapi kalau tinggi berarti proses pencatatan identitas belum konsisten. |
| **Kolom opsional/kontekstual** (catatan, keterangan tambahan, alasan diskon) | Bisa sangat tinggi (50%+) dan tetap wajar | Kolom ini SECARA DESAIN cuma diisi kalau ada sesuatu yang perlu dicatat — null tinggi di sini adalah tanda proses berjalan normal, bukan tanda masalah. |

**⚠️ Perlu direview:** kategori "peran kolom" di atas itu heuristik nama-kolom + konteks pemakaian, bukan aturan otomatis yang bisa dideteksi program — AI perlu membaca nama kolom dan tipe datanya dulu sebelum menyimpulkan kolom itu masuk kategori mana.

## Yang TIDAK boleh AI lakukan

- Jangan bilang "data kamu banyak yang kosong, kualitasnya jelek" tanpa melihat dulu apakah kolom yang null itu memang kolom inti atau kolom opsional — 90% null di kolom catatan itu BUKAN masalah kualitas data.
- Jangan samakan ambang batas "wajar" di tabel ini dengan skor severity resmi aplikasi (`baik`/`sedang`/`tinggi`) — skor resmi tetap dihitung generik oleh backend dan TIDAK berubah oleh konteks di file ini; tabel ini cuma membantu framing NARASI-nya.
- Jangan asumsikan null tinggi di kolom kunci selalu berarti kesalahan input user — kadang itu tanda sumber data (misal hasil export sistem lama) yang memang tidak lengkap; sebutkan kemungkinan itu di narasi, bukan menuduh langsung.

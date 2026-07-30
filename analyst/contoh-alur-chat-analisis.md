# Contoh Alur Chat — Analisis Proaktif

> **Kategori:** analyst — Fase 1: Rasio Keuangan Dasar
> **Fungsi file ini:** paling penting buat §1.5 poin 1 dari `analyst/README.md` — nunjukin BENTUK percakapan yang diharapkan dari AI, bukan sekadar rumus. AI dilatih (lewat retrieval konten ini) buat NGOBROL, gali balik, dan PROAKTIF ngangkat insight — bukan cuma jawab 1 pertanyaan lalu diam.
> **Cara pakai:** ini contoh pola, bukan skrip yang dihafal persis. Angka & detail usaha di tiap contoh cuma ilustrasi.

## Pola umum yang dipakai di semua contoh

1. User nanya sesuatu yang SAMAR (tidak spesifik rumus/rasio apa).
2. AI gali balik SATU pertanyaan klarifikasi singkat (bukan langsung nge-dump semua rasio sekaligus).
3. AI jawab pakai data yang ada, DAN proaktif menyinggung 1 insight relevan yang tidak ditanya langsung — kalau kondisinya memang memenuhi salah satu pemicu "WAJIB diangkat AI duluan" dari file rumus terkait.

---

## Contoh 1 — Pertanyaan samar soal "untung"

**User:** "usaha saya bulan ini gimana ya, untung nggak sih?"

**AI:** "Boleh, saya bantu lihat. Mau saya lihatkan dari sisi margin keuntungan jualan, atau dari sisi kas/likuiditas dulu? Atau saya cek dua-duanya sekalian dari laporan bulan ini?"

**User:** "dua-duanya aja"

**AI:** "Oke. Dari Laporan Laba Rugi bulan ini: penjualan Rp 15.000.000, margin bersih kamu 12% — artinya dari tiap Rp 1.000 jualan, Rp 120 jadi untung bersih. Itu turun dari bulan lalu yang 15%. Satu hal yang perlu saya singgung: penurunan ini kelihatannya bukan dari jualan turun (omset malah naik), tapi dari biaya operasional yang naik lebih cepat. Mau saya bantu rinci biaya mana yang naik paling banyak?"

*(Insight proaktif: margin turun disinggung walau user cuma nanya "untung nggak", sesuai pemicu di `margin-kotor-bersih.md`.)*

---

## Contoh 2 — Pertanyaan spesifik tapi ada insight tersembunyi

**User:** "aset lancar saya berapa sekarang?"

**AI:** "Aset lancar kamu Rp 10.000.000 (kas + piutang + stok). Dibanding kewajiban jangka pendek Rp 8.000.000, rasio likuiditasnya 1,25 — di atas 1 jadi kelihatan aman. Tapi ada yang perlu saya kasih tau: dari Rp 10 juta itu, Rp 6 juta-nya ada di stok barang, bukan uang tunai. Kalau ada tagihan mendadak, uang tunai yang beneran siap kamu pakai cuma sekitar Rp 4 juta. Mau saya bantu lihat gimana caranya stok itu bisa lebih cepat cair jadi kas?"

*(Insight proaktif: user cuma nanya angka aset lancar, tapi AI menyinggung komposisi stok-vs-kas — pemicu dari `rasio-likuiditas-sederhana.md`.)*

---

## Contoh 3 — User bandingkan diri dengan usaha lain (AI tidak menebak, gali balik)

**User:** "margin usaha kuliner itu normalnya berapa sih?"

**AI:** "Itu tergantung jenis usaha kulinernya — warung makan, kafe, dan katering biasanya beda kisaran wajarnya. Usaha kamu sendiri jenis apa? Kalau kamu kasih tau, saya bisa bandingkan margin kamu sekarang (12%) sama kisaran yang biasa buat jenis usaha itu."

*(Bukan insight proaktif, tapi contoh AI TIDAK menjawab dengan angka yang belum divalidasi/ditebak — nunggu konteks lebih spesifik dulu sebelum kasih pembanding, karena ambang batas itu ada di file `-insight.md` yang per-jenis-usaha, bukan angka tunggal.)*

---

## Contoh 4 — Dua bulan berturut-turut margin turun (pemicu wajib)

**User:** "cek dong laporan bulan ini"

**AI:** "Laporan bulan ini: omset Rp 18.000.000, laba bersih Rp 1.800.000 (margin bersih 10%). Ada hal yang perlu saya angkat: ini bulan KEDUA berturut-turut margin bersih kamu turun (bulan lalu 12%, sebelumnya 15%). Saya belum tau penyebabnya dari data laporan aja — mau saya bantu telusuri, apa dari harga bahan baku naik, atau ada biaya baru yang masuk?"

*(Insight proaktif WAJIB — user cuma minta "cek laporan", bukan minta analisis tren, tapi pemicu 2-bulan-berturut-turut dari `margin-kotor-bersih.md` mengharuskan AI mengangkat ini duluan.)*

---

## Contoh 5 — User baru pertama kali punya data lengkap

**User:** "oke laporan laba rugi sama neraca bulan ini udah saya isi semua"

**AI:** "Bagus, datanya udah lengkap. Ini pertama kalinya saya bisa hitung gambaran kesehatan usaha kamu dari 3 sisi: margin keuntungan, likuiditas (kemampuan bayar tagihan jangka pendek), dan profitabilitas keseluruhan. Mau saya jelasin ketiganya sekarang, atau ada yang paling penasaran duluan?"

*(Insight proaktif — user tidak eksplisit minta analisis, cuma bilang data sudah lengkap, tapi ini pemicu "data cukup pertama kali" dari ketiga file rumus.)*

---

## Yang TIDAK boleh terjadi (anti-pola)

- AI langsung nge-dump semua rumus/rasio sekaligus tanpa digali dulu apa yang user butuhkan (Contoh 1 salah: langsung jawab margin+likuiditas+profitabilitas semua tanpa nanya balik).
- AI kasih label "bagus/jelek/sehat" tanpa tau jenis usahanya (Contoh 3 salah: langsung bilang "margin kamu jelek" padahal ambang batasnya beda per jenis usaha).
- AI menyinggung insight proaktif tanpa penanda bahwa ini arahan umum, bukan vonis final (lihat disclaimer di `analyst/README.md` §6) — semua contoh di atas WAJIB tetap disertai nada "arahan umum", bukan "putusan pasti benar".

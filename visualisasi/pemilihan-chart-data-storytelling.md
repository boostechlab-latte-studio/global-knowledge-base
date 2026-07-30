# Memilih Visualisasi yang Tepat untuk Cerita Data

> **Kategori:** visualisasi — memilih & menyusun chart yang tepat, plus cara menceritakan insight dari data
> **Target pembaca:** siapa aja yang punya data (gak terbatas ke data keuangan) dan mau tau visualisasi apa yang paling pas buat nunjukin cerita di balik datanya.

## Kenapa pemilihan chart itu penting

Chart yang salah bikin data BENAR tapi kesannya SALAH. Contoh: pakai pie chart buat 15 kategori — mata gak bisa bandingin 15 potongan warna beda, padahal kalau dibikin bar chart urut dari terbesar, langsung kelihatan mana yang dominan. Chart bukan hiasan — chart itu cara nerjemahin angka jadi keputusan yang gampang diambil.

Prinsip dasar: **tanya dulu "pertanyaan apa yang mau dijawab chart ini?" sebelum milih tipenya.** Tipe chart itu jawaban dari pertanyaan itu, bukan sebaliknya.

## Peta cepat: pertanyaan → tipe chart

| Pertanyaan yang mau dijawab | Chart yang cocok | Kenapa |
|---|---|---|
| "Mana yang paling gede/kecil di antara kategori-kategori ini?" | **Bar chart** | Mata manusia paling akurat bandingin PANJANG batang, bukan bandingin warna/sudut |
| "Gimana trennya dari waktu ke waktu?" | **Line/Area chart** | Garis nunjukin ARAH perubahan — naik/turun/stabil — yang gak kelihatan dari angka mentah |
| "Berapa persen bagian ini dari keseluruhan?" | **Pie/Donut chart** (kalau kategorinya SEDIKIT, maks ~8) | Proporsi paling natural dibaca sebagai "potongan dari 1 lingkaran" — tapi cuma kalau kategorinya dikit, kalau banyak malah bikin bingung, pindah ke bar |
| "Ada hubungan antara 2 hal ini gak?" | **Scatter plot** | Nunjukin pola sebaran 2 variabel numerik — kalau titik-titiknya naik bareng, ada korelasi positif |
| "Datanya nyebar gimana, ada yang aneh/outlier gak?" | **Histogram** (buat liat sebaran) atau **Boxplot** (buat liat outlier) | Histogram nunjukin bentuk distribusi (normal/miring/dobel puncak), boxplot langsung nandain titik yang "gak wajar" |
| "Ini terjadi di mana secara geografis?" | **Map** | Kalau ada data lokasi (kota, alamat, koordinat), peta jauh lebih intuitif daripada tabel nama kota |
| "Gimana pola 2 kategori yang saling silang?" (misal region vs bulan, produk vs status) | **Heatmap** | Warna gelap-terang lebih cepet ke-scan mata daripada baca tabel angka silang |
| "Berapa angka intinya, langsung aja?" | **KPI card** | Kadang jawaban terbaik BUKAN chart — cukup 1 angka besar yang jelas |
| "Ini progress-nya udah sampe mana dari target?" | **Gauge** | Cocok kalau ada batas jelas (0-100%, target SLA) — bukan buat angka yang bisa naik tanpa batas |
| "Gimana profil beberapa hal ini dibandingin sekaligus?" (bukan cuma 1 angka, tapi beberapa dimensi bareng) | **Radar chart** | Nunjukin "bentuk" keseluruhan beberapa metrik dalam 1 gambar — misal bandingin toko A vs toko B dari 5 aspek sekaligus (omset, margin, retensi pelanggan, dst) dalam 1 chart, bukan 5 chart terpisah |
| "Datanya kebanyakan buat divisualisasikan langsung, tapi masih perlu dilihat detailnya" | **Pivot table** | Lihat bagian khusus di bawah — bukan chart visual, tapi cara ringkas nampilin data besar tetap bisa di-scan |

## Kapan pakai KPI vs Gauge (sering ketuker)

Dua-duanya nampilin 1 angka, tapi tujuannya beda:

- **KPI card** — buat angka yang gak punya batas atas jelas dan yang penting cuma BESARANNYA (total penjualan, jumlah transaksi, total pelanggan baru). Gak ada "target 100%" yang masuk akal — omset boleh terus naik tanpa batas.
- **Gauge** — buat angka yang punya SKALA/BATAS jelas dan yang penting seberapa DEKAT ke target/batas itu (tingkat keberhasilan pengiriman 87% dari target 95%, skor kepuasan 4,2 dari 5, kapasitas gudang terpakai 78%). Kalau angkanya bisa naik terus tanpa ada "penuh"/"maksimal" yang masuk akal, itu tandanya harusnya KPI, bukan gauge.

Aturan cepat: ada kata "dari" yang implisit (87% **dari** target, 4,2 **dari** 5) → gauge. Angka berdiri sendiri (total omset bulan ini) → KPI.

## Chart buat audit / pemeriksaan data (nyari yang aneh)

Beda tujuan dari chart "cerita data" biasa — di sini tujuannya nyari ANOMALI, bukan nunjukin tren:

- **Boxplot** — chart paling langsung buat nemuin outlier numerik (transaksi yang nilainya jauh di luar kewajaran, misal 1 transaksi Rp 50 juta di antara rata-rata Rp 200 ribu). Titik di luar "kotak" itu yang perlu dicek manual.
- **Table dengan sorting** — buat audit detail per baris (urutkan dari nilai terbesar/terkecil/paling baru, baru scroll cari yang janggal) — kadang lebih efektif dari chart apa pun buat audit granular.
- **Heatmap** — buat nemuin pola aneh di data 2 dimensi (misal: transaksi jam 3 pagi yang harusnya sepi tapi rame — kelihatan sebagai kotak gelap di posisi yang gak biasa di heatmap jam×hari).
- **Histogram** — buat lihat apa distribusi datanya "wajar" (bentuk normal) atau mencurigakan (ada 2 puncak/dobel populasi yang harusnya 1 kelompok — bisa nandain 2 sumber data yang ketuker).

## Legend — kenapa penting dan kapan wajib ada

Legend itu "kunci warna" — tanpa itu, chart yang pakai lebih dari 1 warna/kategori jadi gak bisa dibaca sama sekali (pembaca gak tau warna biru itu apa, warna oranye itu apa).

- **Wajib ada**: pie/donut chart (warna itu SATU-SATUNYA cara bedain slice), chart apa pun yang punya lebih dari 1 series/garis/kelompok warna (misal line chart yang bandingin 3 produk sekaligus, tiap produk beda warna).
- **Gak perlu**: chart yang cuma 1 warna/1 series (misal bar chart 1 metrik doang, KPI card, gauge tunggal) — nambah legend di situ cuma nambah elemen visual tanpa nambah informasi.
- **Posisi yang enak dibaca**: di atas atau di kanan chart, bukan di bawah kalau chart-nya lebar (mata harus balik ke atas buat cocokin warna, jadi capek).
- **Interaktif itu bonus, bukan wajib**: kalau legend-nya bisa diklik buat nyembunyiin/nunjukin 1 kategori doang, itu nambah kegunaan — tapi legend yang statis (gak bisa diklik) tetap sah, yang penting warnanya jelas.

## Data kebanyakan buat 1 chart? Coba pivot table

Kadang jumlah kategori/dimensi yang mau dibandingin kebanyakan buat 1 chart visual (misal: 50 produk × 12 bulan × 3 region — gak ada chart yang bisa nampilin itu semua sekaligus dengan jelas). Di sini pivot table lebih berguna daripada maksain bikin chart:

- **Konsepnya**: tabel yang barisnya 1 kategori (misal produk), kolomnya kategori lain (misal bulan), dan isinya angka teragregasi (misal total penjualan) — jadi bisa scan cepat "produk mana paling laku bulan mana" tanpa harus baca 50 chart terpisah.
- **Kapan pilih pivot table dibanding chart**: kalau kombinasi kategori yang mau dibandingin lebih dari 2 dimensi, atau jumlah kategorinya banyak (>15-20) sehingga chart visual (bar/line) bakal terlalu penuh buat dibaca.
- **Tetap kasih ringkasan visual di sampingnya**: pivot table bagus buat detail, tapi tambahkan 1 KPI atau bar chart kecil di sampingnya buat highlight "yang paling penting" (misal produk #1 terlaris) — jangan cuma kasih tabel mentah tanpa ada angka yang di-highlight duluan.
- **Urutan & highlight**: sort kolom/baris dari yang paling besar, dan kasih warna latar (heatmap-style di dalam tabel, bukan chart terpisah) buat sel dengan nilai tinggi/rendah — biar pola masih kebaca sekilas walau bentuknya tabel.

## Kesalahan umum yang sering kejadian

1. **Pie chart buat >8 kategori** — jadi tumpukan warna yang gak kebaca. Ganti ke bar chart, urutkan dari terbesar.
2. **Line chart buat data yang bukan urutan waktu/urutan alami** — garis nyiratin "perjalanan dari A ke B" padahal datanya kategori lepas-lepas. Pakai bar.
3. **3D chart atau efek visual berlebihan** — kelihatan keren tapi bikin susah baca angka SEBENARNYA (perspektif 3D bikin batang belakang kelihatan lebih kecil dari batang depan walau nilainya sama).
4. **Nampilin terlalu banyak chart sekaligus tanpa hierarki** — user gak tau harus liat yang mana duluan. Selalu mulai dari angka paling penting (KPI), baru breakdown-nya.
5. **Warna random tanpa makna** — kalau ada kategori yang konsisten (misal "Berhasil"/"Gagal"), pakai warna yang konsisten juga tiap kali muncul (hijau buat berhasil, merah buat gagal) — jangan random tiap chart beda.

## Cara nyeritain insight dari chart (bukan cuma nunjukin chart)

Chart doang belum cerita — angka butuh KONTEKS biar jadi insight yang berguna. Pola yang bagus:

1. **Sebutkan angka spesifik** — bukan "penjualan lumayan bagus" tapi "penjualan naik 23% dibanding bulan lalu".
2. **Bandingkan dengan sesuatu** — angka tunggal gak ada artinya tanpa pembanding (bulan lalu, target, rata-rata industri, kategori lain).
3. **Jelaskan KENAPA itu penting** — "naik 23%" doang belum cukup, lanjutkan dengan dampaknya ("ini bagus, tapi stok mungkin perlu ditambah minggu depan kalau tren ini lanjut").
4. **Kasih 1 langkah lanjutan yang konkret** — bukan "perlu dianalisis lebih lanjut" (itu bukan jawaban), tapi rekomendasi yang bisa langsung dikerjakan.

Contoh perbedaan cerita data yang lemah vs kuat:

> ❌ Lemah: "Grafik menunjukkan penjualan bervariasi tiap bulan."
>
> ✅ Kuat: "Penjualan Maret (Rp 45 juta) itu 30% lebih tinggi dari rata-rata 5 bulan terakhir (Rp 34,6 juta) — kemungkinan besar karena promo Ramadan yang mulai bulan itu. Kalau polanya berulang, siapkan stok lebih banyak mulai H-2 minggu sebelum Ramadan tahun depan."

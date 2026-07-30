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
| "Gimana profil beberapa metrik sekaligus buat 1 entity?" | **Radar chart** | Nunjukin "bentuk" keseluruhan performa dalam 1 gambar, cocok buat bandingin beberapa entity punya kekuatan di mana |
| "Berapa angka intinya, langsung aja?" | **KPI card** | Kadang jawaban terbaik BUKAN chart — cukup 1 angka besar yang jelas |
| "Ini progress-nya udah sampe mana dari target?" | **Gauge** | Cocok kalau ada batas jelas (0-100%, target SLA) — bukan buat angka yang bisa naik tanpa batas |

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

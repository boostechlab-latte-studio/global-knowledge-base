# Changelog

Semua versi yang pernah dipublish, urut dari terbaru. Format versi: `MAJOR.MINOR.PATCH` (semver) — client menolak versi yang sama atau lebih kecil dari yang sudah terpasang, jadi versi WAJIB selalu naik tiap publish.

## v1.5.0 — 2026-08-07

- Kategori baru: **kualitas-data** — interpretasi null%/baris duplikat/persentase outlier per konteks bisnis (peran kolom, pola data), melengkapi ambang batas severity generik yang dihitung aplikasi konsumen. 3 topik (null%, baris duplikat, outlier%), masing-masing file rumus netral + file ambang batas interpretasi. **⚠️ Ambang batas di file `*-insight.md` masih DRAFT — rule-of-thumb umum di literatur data quality management, BUKAN riset primer/survei resmi — perlu direview manual lebih lanjut.**

## v1.4.0 — 2026-07-30

- **visualisasi**: tambah section "Alur dari data mentah sampai ke chart yang tepat" — peta proses yang nyambungin pemilihan chart, legend, audit/anomali, dan cara nyeritain insight jadi satu alur runtut (bukan topik lepas-lepas).

## v1.3.0 — 2026-07-30

- **analyst**: audience diperluas — dari fokus UMKM doang jadi juga mencakup individu/personal, jasa, dan toko. 3 file rumus (`margin-kotor-bersih.md`, `rasio-likuiditas-sederhana.md`, `rasio-profitabilitas.md`) masing-masing dapat 1 contoh personal tambahan (freelancer, tabungan pribadi, gig-work) di samping contoh usaha yang sudah ada.

## v1.2.0 — 2026-07-30

- **visualisasi**: konten diperluas — tambah baris radar chart di peta cepat (sebelumnya kelewat), section "Kapan pakai KPI vs Gauge", section "Chart buat audit/pemeriksaan data" (boxplot/table/heatmap/histogram buat nyari anomali), section "Legend — kenapa penting dan kapan wajib ada", section "Data kebanyakan buat 1 chart? Coba pivot table".

## v1.1.0 — 2026-07-30

- Kategori baru: **visualisasi** — `pemilihan-chart-data-storytelling.md` (cara memilih tipe chart yang tepat + cara menceritakan insight dari data). Kategori terpisah dari `analyst` karena topiknya general-purpose, gak terbatas ke data finansial.

## v1.0.0 — 2026-07-30

- Rilis pertama. Kategori **analyst** (7 file): `margin-kotor-bersih.md` + insight, `rasio-likuiditas-sederhana.md` + insight, `rasio-profitabilitas.md` + insight, `contoh-alur-chat-analisis.md`.

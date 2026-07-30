> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Ambang batas di file ini SAMA PERSIS dengan `margin-kotor-bersih-insight.md` bagian margin bersih — sengaja, karena ROS secara matematis = margin bersih (lihat catatan di `rasio-profitabilitas.md`). File ini cuma reframe cara bicaranya, bukan angka baru. Tetap butuh direview per §1.5 karena dipakai di konteks pertanyaan yang beda (lihat di bawah).

# Rasio Profitabilitas (ROS) — Ambang Batas Interpretasi

> **File rumus:** `rasio-profitabilitas.md` (definisi & cara hitung, tidak berubah)
> **File acuan angka:** `margin-kotor-bersih-insight.md` — tabel ambang batas margin bersih DIPAKAI ULANG di sini, tidak diduplikasi supaya kalau ada koreksi angka, cukup diperbaiki di 1 tempat (`margin-kotor-bersih-insight.md`).

## Cara pakai tabel ambang batas

Rujuk tabel "Ambang batas per jenis usaha" di `margin-kotor-bersih-insight.md`, kolom **Margin Bersih wajar** — itu angka yang sama dipakai buat menilai ROS (kuliner 10-15%, retail 5-20%, jasa 20-30%).

**Bedanya cuma cara AI membingkai kalimatnya:**
- Konteks "margin bersih" → user biasanya nanya soal PERSENTASE keuntungan ("margin saya berapa persen").
- Konteks "ROS/per-Rp1000" → user biasanya nanya SECARA UMUM soal "untung nggak" tanpa sebut kata margin/rasio — di sini AI pakai framing "dari tiap Rp 1.000 jualan, sisa Rp X jadi untung" (lihat `rasio-profitabilitas.md` bagian "Cara sampaikan ke user").

## Kondisi "AI WAJIB angkat duluan"

Sama seperti margin bersih (`margin-kotor-bersih-insight.md`) — pemicunya identik karena angkanya sama:

1. ROS turun 2 periode berturut-turut.
2. ROS di bawah batas bawah rentang wajar jenis usaha.
3. Khusus untuk file ini — **ROS dipakai sebagai jembatan ke Fase 2 (BEP & harga)**: kalau ROS rendah DAN user belum pernah diajak bahas strategi harga, AI proaktif menawarkan lanjut ke `strategi-penetapan-harga.md` (Fase 2) sebagai langkah konkret berikutnya, bukan cuma berhenti di "ROS kamu rendah".

## Yang TIDAK boleh AI lakukan

- Jangan hitung ulang/tentukan ambang batas baru yang beda dari `margin-kotor-bersih-insight.md` — kalau butuh koreksi angka, koreksi di file itu (single source of truth angkanya), bukan di sini.

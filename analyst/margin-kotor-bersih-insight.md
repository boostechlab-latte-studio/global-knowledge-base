> # ⚠️ DRAFT — BUTUH REVIEW MANUAL SEBELUM APPROVE
> Semua ambang batas di file ini JUDGMENT CALL, bukan rumus matematis (beda dari `margin-kotor-bersih.md`). Sumber: kisaran yang konsisten muncul di beberapa blog vendor software UMKM Indonesia (accountingplus.id, majoo.id, tuwaga.id, ismesoft.com — dicek 2026-07-29), BUKAN standar resmi pemerintah/lembaga (lihat `analyst/README.md` §0). Per §1.5: review angka di tabel di bawah SATU-SATU sebelum di-approve — kalau ada angka yang menurutmu tidak sesuai kondisi UMKM Indonesia riil, koreksi sebelum dipublish.

# Margin Kotor & Margin Bersih — Ambang Batas Interpretasi

> **File rumus:** `margin-kotor-bersih.md` (definisi & cara hitung, tidak berubah)

## Ambang batas per jenis usaha

| Jenis usaha | Margin Kotor wajar | Margin Bersih wajar | Catatan |
|---|---|---|---|
| **Kuliner (warung, resto, kafe)** | 30% – 50% | 10% – 15% | Margin kotor kuliner sering TINGGI (bahan baku relatif murah dibanding harga jual), tapi biaya operasional (sewa, gas, listrik, tenaga kerja) menekan margin bersih jadi jauh lebih kecil — gap besar antara margin kotor & bersih itu NORMAL buat kuliner, bukan otomatis tanda masalah. |
| **Retail/dagang (toko, online shop)** | 30% – 50% | 5% – 20% | Rentang margin bersih retail PALING LEBAR dari semua jenis usaha — sangat tergantung volume jualan & efisiensi stok. Retail dengan volume tinggi bisa sehat di margin bersih 5-8%, bukan berarti bermasalah. |
| **Jasa (salon, service, konsultasi kecil)** | 40% – 60% | 20% – 30% | Usaha jasa biasanya margin PALING TINGGI dari 3 kategori ini — karena tidak ada HPP barang fisik (cuma waktu & keahlian), jadi bagian terbesar biaya adalah operasional, bukan bahan baku. |

**⚠️ Perlu direview:** angka di atas dari rangkuman blog vendor (bukan riset primer/survei resmi ke pelaku UMKM Indonesia) — cocokkan sama pengalaman bisnis nyata sebelum jadi acuan interpretasi yang AI sampaikan ke user.

## Label interpretasi (tipis / wajar / sehat)

Dipakai untuk margin BERSIH (bukan margin kotor — margin kotor cuma langkah antara, tidak perlu dilabeli):

- **Tipis** — margin bersih di bawah batas bawah rentang wajar jenis usaha (misal kuliner < 10%, retail < 5%, jasa < 20%)
- **Wajar** — berada di dalam rentang tabel di atas
- **Sehat** — di atas batas atas rentang, DAN stabil/naik 2 periode berturut-turut (bukan cuma 1 bulan kebetulan bagus)

> **Kalimat contoh buat AI (bukan skrip kaku, contoh nada):** *"Margin bersih kamu 8% untuk usaha kuliner — itu di bawah kisaran wajar (biasanya 10-15% buat warung/resto sejenis). Ini bukan berarti usaha kamu gagal, tapi ada ruang buat dicek lagi apa yang bikin tipis — mau saya bantu telusuri biaya operasionalnya?"*
>
> Perhatikan nadanya: **arahan, bukan vonis** — sesuai disclaimer wajib di `analyst/README.md` §6.

## Kondisi "AI WAJIB angkat duluan" (detail dari pemicu di file rumus)

1. **Margin bersih turun 2 periode berturut-turut** — walau masih di dalam rentang "wajar", tren turun tetap wajib disinggung (tren lebih penting dari angka snapshot).
2. **Margin bersih di bawah batas bawah rentang wajar** untuk jenis usahanya — wajib diangkat, tapi dengan nada "ada ruang ditelusuri", bukan "usaha kamu buruk".
3. **Gap besar antara margin kotor dan margin bersih** (selisih > 25 poin persentase) — sinyal biaya operasional berat, TAPI untuk kuliner ini kadang NORMAL (lihat catatan tabel) — AI perlu cek jenis usaha dulu sebelum menyimpulkan ini masalah.

## Yang TIDAK boleh AI lakukan

- Jangan bilang "margin kamu jelek" tanpa tau jenis usahanya dulu (retail 8% itu wajar, kuliner 8% itu tipis — bedanya besar).
- Jangan bandingkan margin user dengan angka di tabel ini seolah itu "standar resmi" — selalu framing sebagai "kisaran umum yang biasa dipakai", bukan aturan baku.

# Agent Guide — global-knowledge-base (content repo)

Repo ini **bukan kode aplikasi** — isinya konten pengetahuan (`.md`) yang dipublish ke GitHub Releases dan dikonsumsi oleh aplikasi eksternal lewat `manifest.json`. Panduan operasional LENGKAP (konsep, cara hosting, SOP publish detail) ada di repo terpisah, **BUKAN di sini** — lihat `documents/global-knowledge-base/README.md` di working directory produk yang konsumsi repo ini. File ini cuma aturan kerja SPESIFIK buat repo ini sendiri.

## Aturan Mutlak

1. **Setiap kali kerjaan di repo ini selesai (nambah/ubah file `.md`), WAJIB langsung `git push` ke `origin main`.** Jangan pernah biarin commit numpuk cuma di lokal — repo ini gunanya buat DIKONSUMSI publik, kalau gak di-push, gunanya nol. Ini beda dari repo produk pemakainya (working directory terpisah, kelolaannya sendiri) yang punya aturan "push cuma kalau diminta eksplisit" — repo ini SEBALIKNYA: push itu DEFAULT tiap kali ada perubahan, karena isinya emang buat dipublish.
2. **Setiap ada perubahan konten (nambah file baru, edit file lama), WAJIB publish versi baru** — jangan biarin `main` branch punya konten yang beda dari versi yang tercatat di `manifest.json`. Urutannya:
   1. Commit + push perubahan `.md`-nya dulu ke `main`.
   2. `zip -r knowledge-X.Y.Z.zip <semua folder kategori>` (folder kategori aja, bukan `README.md`/`AGENTS.md`/`CHANGELOG.md`).
   3. `shasum -a 256 knowledge-X.Y.Z.zip` — catat hasilnya.
   4. `git tag knowledge-vX.Y.Z && git push origin knowledge-vX.Y.Z`
   5. `gh release create knowledge-vX.Y.Z knowledge-X.Y.Z.zip --repo boostechlab-latte-studio/global-knowledge-base --title "Knowledge vX.Y.Z" --notes "..."`
   6. Update `manifest.json` (`version`, `released_at`, `package_url` dari asset release, `sha256` dari langkah 3).
   7. Commit + push `manifest.json`.
   8. Hapus zip lokal (`rm knowledge-X.Y.Z.zip`) — jangan biarin nyangkut di working directory.
   9. **Update `CHANGELOG.md`** — 1 entry baru paling atas, isi ringkas apa yang berubah versi ini.
3. **Versi WAJIB naik tiap publish** — semver `MAJOR.MINOR.PATCH`. Perubahan konten (nambah/edit topik) → naikin MINOR. Perbaikan typo/kecil → naikin PATCH. Jangan pernah nurunin/nyamain versi — client (`GlobalKnowledgeService` di produk) nolak versi yang sama atau lebih kecil dari yang udah terpasang.
4. **README.md dan seluruh konten di sini TIDAK BOLEH menyebut nama produk pemakainya apa pun** — repo ini publik dan berdiri sendiri secara konsep ("basis pengetahuan umum"), bukan didokumentasikan sebagai bagian dari produk tertentu. Sebelum commit, cek dulu isinya bersih dari nama produk pemakai (grep nama produk itu ke seluruh file di repo ini) kalau ragu.
5. **Setiap tambah kategori baru** (folder baru di root), update daftar struktur folder di `README.md` juga — jangan biarin README ketinggalan dari struktur folder yang sebenarnya.
6. **Ownership dokumen:**
   - `README.md` — deskripsi + struktur folder, buat pembaca publik.
   - `CHANGELOG.md` — riwayat versi, WAJIB di-update tiap publish (aturan #2 poin 9).
   - `manifest.json` — SATU-SATUNYA sumber kebenaran versi terpasang buat client, JANGAN diedit manual di luar alur publish di atas.
   - `AGENTS.md` (file ini) — aturan kerja repo ini sendiri.

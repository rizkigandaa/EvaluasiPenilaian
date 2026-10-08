# Asisten Penilai LKPD (tanpa API)

Situs statis satu file (`index.html`). Tidak memakai API, kunci, atau server: semua perhitungan berjalan di browser dan data tersimpan di browser pengguna (localStorage).

## Deploy ke Vercel
1. Ekstrak ZIP, unggah folder ke GitHub, atau jalankan `vercel` di folder ini.
2. Di Vercel: Add New > Project, pilih repositori. Framework Preset: **Other**. Kosongkan build command dan output directory.
3. Klik Deploy. Tidak ada environment variable yang perlu diatur.

## Cara pakai
1. Isi data LKPD. Untuk tiap soal isi **kata kunci** (pisahkan koma; sinonim dengan `|`, mis. `karbon dioksida|co2`) dan/atau **kunci jawaban**, lalu **jawaban siswa**.
2. Di panel asisten ketik atau klik: `nilai`, `umpan balik`, `evaluasi`, `rubrik`, `simpan`, `rekap`.

## Cara kerja dan batasannya
- Skor = kecocokan kata kunci (dengan toleransi imbuhan dan salah ketik ringan), digabung dengan kemiripan terhadap kunci jawaban bila diisi.
- Evaluasi LKPD mendeteksi jenjang berpikir C1-C6 dari kata kerja perintah, kejelasan soal, dan kesesuaian dengan tujuan pembelajaran.
- Ini mesin berbasis aturan, bukan AI generatif. Ia tidak memahami makna: jawaban benar yang memakai kata berbeda dari kata kunci bisa terlewat, dan jawaban uraian panjang atau opini kurang cocok dinilai otomatis. Skor adalah rekomendasi; guru menentukan nilai akhir.

## Menyatukan dengan situs lain
Deploy sebagai proyek terpisah lalu tautkan, atau sematkan:
`<iframe src="https://NAMA-PROYEK.vercel.app" style="width:100%;height:80vh;border:0"></iframe>`

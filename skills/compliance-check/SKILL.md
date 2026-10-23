---
name: compliance-check
description: Memeriksa draf tweet, thread, caption, dan naskah TikTok sebelum dikirim, untuk mendeteksi disclosure affiliate yang hilang, klaim berlebihan, klaim terlarang, dan risiko kebijakan platform. Pakai sebagai langkah terakhir untuk semua output Racik.
allowed-tools: Read, Write
---

# Compliance Check

Jalankan pada SETIAP konten sebelum masuk kalender/Telegram. Output: tabel per item
`[LOLOS] / [REVISI] / [BLOKIR]`, alasan, dan saran perbaikan. Jangan pernah posting otomatis;
user yang memutuskan.

## 1. Disclosure (wajib bila ada link/komisi)
- [ ] Ada "#ad", "(link affiliate)", atau kalimat jelas "aku dapet komisi" di tweet/caption yang membawa link atau CTA beli.
- [ ] Thread: disclosure ada di tweet CTA (bukan cuma di reply link).
- [ ] TikTok: caption berisi disclosure dan diingatkan untuk menyalakan label konten berbayar/affiliate di aplikasi.
- [ ] Tidak ada penyamaran ("bukan endorse", "gak dibayar") jika sebenarnya affiliate.

## 2. Overclaim -> [REVISI]
Kata/frasa absolut: paling, terbaik, nomor 1, 100%, dijamin, pasti, gak ada saingan, termurah se-Indonesia,
"semua orang pakai", angka penjualan/rating yang tidak ada di brief, testimoni yang tidak berasal dari user.
Harga/promo harus sesuai brief dan ditambah "harga bisa berubah".

## 3. Klaim terlarang -> [BLOKIR]
- Kesehatan/medis: menyembuhkan, mengobati, menurunkan berat badan X kg, aman untuk ibu hamil (tanpa izin/BPOM), menggantikan obat.
- Keuangan: cuan pasti, balik modal dijamin, pendapatan pasti, skema investasi.
- Produk ilegal/berisiko: obat keras, rokok/vape ke audiens muda, judi/slot, pinjol ilegal, barang bajakan.
- Akun berbagi/reseller langganan premium yang melanggar ketentuan layanan (mis. sharing akun Netflix/Spotify) -> tandai risiko ToS.
- Jasa akademik: menawarkan "joki"/pengerjaan skripsi atas nama mahasiswa -> tandai risiko integritas akademik; sarankan framing "bimbingan/tutor".
- SARA, ujaran kebencian, konten menyesatkan tentang tokoh nyata.

## 4. Platform & teknis
- [ ] Setiap tweet <= 280 karakter; hashtag <= 3 per tweet.
- [ ] Link affiliate tidak di tweet pertama thread.
- [ ] Tidak ada ajakan spam (follow-for-follow massal) di konten affiliate.
- [ ] Klip gaming/musik: milik sendiri atau berlisensi.

## Format output
| # | Konten | Status | Masalah | Saran |
|---|---|---|---|---|

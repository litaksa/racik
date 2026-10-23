---
name: racik
description: Orkestrator Racik. Dari satu link/brief produk affiliate, hasilkan 10 tweet, 3 thread storytelling soft-sell, 4 naskah TikTok, kalender konten Excel, dan laporan compliance. Pakai saat user bilang "racik", kirim link/brief produk, atau minta konten harian.
allowed-tools: Read, Write, Bash, WebFetch
---

# Racik: pipeline konten harian

1. **Brief**: baca brief dari `produk/<nama>.md` atau link yang diberikan (WebFetch). Ekstrak: nama, harga, harga promo, 3-5 fakta, link affiliate. Fakta yang tidak ada -> `[CEK: ...]`. Simpan ke `output/<tanggal>/brief.md`.
2. **Voice**: muat `brand-voice` dan contohnya.
3. **10 tweet**: tweet tunggal beragam (4 nilai/tips, 3 obrolan relatable, 3 soft promo). Hanya soft promo yang memuat CTA + disclosure.
4. **3 thread**: jalankan `storytelling-softsell`, 3 sudut berbeda.
5. **4 naskah TikTok**: jalankan `tiktok-script` (EDU, FOOD, TREN, GAME).
6. **Compliance**: jalankan `compliance-check` atas semua item; perbaiki item [REVISI] sekali, item [BLOKIR] dikeluarkan.
7. **Kalender Excel**: buat `output/<tanggal>/kalender.xlsx` dengan kolom: Tanggal, Jam, Platform, Akun, Jenis, Konten, Disclosure, Status Compliance, Link. Jadwal default tweet 07:00-22:00 tersebar, TikTok 1 per akun tiap 2 hari.
8. **Ringkasan**: tulis `output/<tanggal>/ringkasan.md` (jumlah item, item yang diblokir, waktu proses). Ringkasan ini yang dikirim ke Telegram via Assistant.

Jangan pernah posting otomatis ke X/TikTok; semua output adalah draf untuk ditinjau user.

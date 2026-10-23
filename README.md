![Racik](cover.jpg)

# Racik: Creator Agent untuk affiliate (Tencent Cloud Hackathon Indonesia 2026)

Racik turns one product brief into 10 X posts, 3 soft-sell storytelling threads, 4 TikTok scripts, an Excel posting calendar and a compliance report. Drafts only, no auto-posting. Built on Tencent WorkBuddy skills.

Satu link/brief produk affiliate menghasilkan **10 tweet + 3 thread storytelling soft-sell + 4 naskah TikTok + kalender Excel + laporan compliance**, dikirim tiap pagi ke Telegram. Dibangun di atas **Tencent WorkBuddy** skills.

Contoh brief produk ada di [`examples/termos-kunci-lulus.md`](examples/termos-kunci-lulus.md).

## Isi
```
skills/
  racik/SKILL.md                         # orkestrator (merangkai skill lain)
  brand-voice/SKILL.md                   # gaya bahasa akun @sawitgundul
  brand-voice/references/examples.md     # contoh kalimat asli + engagement
  storytelling-softsell/SKILL.md         # framework thread soft-selling
  storytelling-softsell/references/example-threads.md
  tiktok-script/SKILL.md                 # 4 persona: EDU, FOOD, TREN, GAME
  compliance-check/SKILL.md              # disclosure, overclaim, klaim terlarang
```

## Instalasi ke WorkBuddy
Format mengikuti dokumentasi skills (SKILL.md + YAML frontmatter `name`, `description`, `allowed-tools`): https://www.workbuddy.ai/docs/cli/skills

**Opsi A: level user (aktif di semua project)**
```bash
mkdir -p ~/.codebuddy/skills
cp -r skills/* ~/.codebuddy/skills/
```
Windows: salin ke `%USERPROFILE%\.codebuddy\skills\`.

**Opsi B: level project (hanya di folder kerja ini)**
```bash
mkdir -p <folder-kerja>/.codebuddy/skills
cp -r skills/* <folder-kerja>/.codebuddy/skills/
```
Lalu buka WorkBuddy, beri izin akses ke `<folder-kerja>`, buat task baru. Skill bisa dipanggil otomatis lewat deskripsinya atau manual dengan `/racik`, `/brand-voice`, dst.

> Catatan: halaman praktik WorkBuddy (https://www.workbuddy.ai/docs/workbuddy/From-Beginner-to-Expert-Guide/Practice-Cases/Create-Skills) juga menyebut skill.yml. Jika versi desktop yang kamu pakai tidak mendeteksi SKILL.md, minta WorkBuddy: "Install skill dari folder ini" agar dia membuat konfigurasi yang dibutuhkan.

## Struktur folder kerja yang disarankan
```
racik-kerja/
  .codebuddy/skills/...      # (opsi B)
  produk/tumbler.md          # brief produk: nama, harga, fakta, link affiliate
  output/2026-10-24/...      # hasil harian (otomatis)
```

## Cara skill dirangkai
```
brief/link produk
   -> racik (orkestrator)
        -> brand-voice (gaya bahasa, dipakai semua langkah)
        -> 10 tweet
        -> storytelling-softsell  x3 thread
        -> tiktok-script          x4 naskah
        -> compliance-check       (revisi/blokir)
        -> kalender.xlsx + ringkasan.md
   -> Automation harian 07:00 -> Assistant -> Telegram
```

## Otomasi harian + Telegram
1. Hubungkan Telegram: buat bot di BotFather, tempel token di Assistant Settings -> Channels -> Telegram (https://www.workbuddy.ai/docs/workbuddy/Platform-Integration/Telegram-Guide).
2. Automation -> New Automation -> "Jalankan /racik untuk produk di folder produk/ yang belum diproses, kirim ringkasan" -> Daily 07:00 -> pilih workspace `racik-kerja` (https://www.workbuddy.ai/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide).
3. PC harus menyala dan WorkBuddy berjalan agar automation jalan.

## Prinsip keamanan
Racik hanya membuat draf. Tidak ada posting otomatis ke X/TikTok; user meninjau dan memposting sendiri. Semua konten berlink affiliate wajib lolos `compliance-check`.

#WorkBuddy #TencentCloudHackathon

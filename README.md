# 🤖 Bot WhatsApp dengan Website Generator & Vercel Deploy

Bot WhatsApp yang bisa generate website otomatis dari AI (Groq API) dan langsung deploy ke Vercel.

## ✨ Fitur Utama

- 💬 **ChatBot AI** - Reply dengan `.ai <pertanyaan>`
- 📥 **Download Media** - TikTok, YouTube, Instagram
- 🎨 **Sticker Maker** - Reply gambar/video dengan `.s`
- 💤 **Sleep Tracker** - Track durasi tidur (`.tidur`, `.bangun`, `.laporan tidur`)
- 🌐 **Website Generator** - Generate & deploy website otomatis ke Vercel dengan `.web <deskripsi>`

## 🛠️ Instalasi

### Prerequisite
- Node.js v16+ ([Download](https://nodejs.org/))
- Vercel CLI (`npm install -g vercel`)
- Git

### Steps
```bash
# 1. Clone repo
git clone https://github.com/[username]/botwa.git
cd botwa

# 2. Install dependencies
npm install

# 3. Setup environment
cp .env.example .env
# Edit .env dan tambahkan Groq API Key

# 4. Login ke Vercel (untuk auto-deploy)
vercel login

# 5. Jalankan bot
node index.js

# 6. Scan QR Code dengan WhatsApp untuk autentikasi
```

## 🔑 Environment Variables

Buat file `.env`:
```
GROK_API_KEY=your_groq_api_key_here
```

**Dapatkan Groq API Key:**
1. Buka https://console.groq.com
2. Create API Key
3. Copy ke `.env`

## 📱 Cara Pakai Bot

| Command | Fungsi |
|---------|--------|
| `.ai [pertanyaan]` | Tanya AI (Groq) |
| `.tiktokaudio [URL]` | Download audio TikTok |
| `.s` | Convert gambar/video jadi stiker |
| `.tidur` | Catat waktu tidur mulai |
| `.bangun` | Catat waktu bangun |
| `.laporan tidur` | Lihat analisis tidur |
| `.web [deskripsi]` | Generate + deploy website |

## 🌐 Deploy Website via WhatsApp

Bot bisa auto-generate dan deploy website:
```
User: .web saya mau website jasa travel ke seluruh Indonesia
Bot: [Generate HTML dengan AI] → Deploy ke Vercel → Kirim URL
```

**Requirement:** Vercel account sudah login di local machine

```bash
vercel login  # Run sekali di awal
```

## 📛 Deploy Bot

### Opsi 1: Railway (Recommended)
```bash
# Push ke GitHub, connect Railway dengan repo
# Railway akan auto-run `npm start`
```

### Opsi 2: Heroku (Vercel Alternative untuk Bot)
```bash
heroku login
heroku create bot-wa-kamu
git push heroku main
```

### Opsi 3: VPS/Lokal dengan PM2
```bash
npm install -g pm2
pm2 start index.js --name "botwa"
pm2 startup
pm2 save
```

## 📝 Package Dependencies

- `@whiskeysockets/baileys` - WhatsApp Web Automation
- `axios` - HTTP Client
- `ffmpeg-static` - Video Processing
- `tesseract.js` - OCR (Optical Character Recognition)
- `ytdl-core` & `@tobyg74/tiktok-api-dl` - Media Download
- `wa-sticker-formatter` - Sticker Processor

## ⚠️ Penting

- **Jangan share `.env` dan folder `session/`**
- **Groq API free tier:** 30+ request/min
- **Vercel:** Free tier support 1 project
- **Bot perlu running 24/7** - gunakan Railway atau VPS

## 🐛 Troubleshooting

**QR Code tidak muncul?**
- Pastikan terminal support UTF-8
- Update baileys: `npm install @whiskeysockets/baileys@latest`

**Deploy Vercel gagal?**
- Run `vercel login` terlebih dahulu
- Pastikan folder `site/` bisa diakses

**Groq API error?**
- Cek API key di `.env`
- Cek credit limit di dashboard Groq

## 📄 License

ISC

## 👨‍💻 Author

Made with ❤️ 

## Pembuat
([yanzyuyu](https://github.com/yanzyuyu))







# Sikobokan — Web Undangan Digital

> Platform undangan digital modern untuk pernikahan, khitanan, dan ulang tahun. Dibuat dengan cinta oleh tim **Ucil, Burat, dan Kanjut**.

---

## Tim Pengembang

| Nama   | Peran                          |
|--------|--------------------------------|
| Ucil   | Lead Developer & Architect     |
| Burat  | Frontend & UI/UX Designer      |
| Kanjut | Backend, Config & Monetisasi   |

---

## Tech Stack

| Layer      | Teknologi                                        |
|------------|--------------------------------------------------|
| Frontend   | HTML5, CSS3 (Vanilla), Vanilla JavaScript ES6+   |
| Fonts      | Google Fonts (Playfair Display, Poppins)         |
| Icons      | Inline SVG / Unicode ornaments                  |
| Maps       | Google Maps Embed API (iframe)                  |
| Music      | HTML5 `<audio>` API                             |
| Deployment | Static hosting: Netlify / Vercel / GitHub Pages |
| Config     | URL Parameters + `config.json` per undangan     |
| Storage    | Google Sheets API (RSVP submissions)            |

---

## Struktur File

```
web-undangan/
├── style-base.css              # Base styles (shared semua template)
├── README.md                   # Dokumentasi ini
│
├── templates/
│   ├── pernikahan/
│   │   ├── index.html          # Template pernikahan
│   │   ├── style.css           # Override styles pernikahan
│   │   └── script.js           # Logic pernikahan
│   │
│   ├── ultah/
│   │   ├── index.html          # Template ulang tahun
│   │   ├── style.css           # Override styles ultah
│   │   └── script.js           # Logic ultah
│   │
│   └── khitanan/
│       ├── index.html          # Template khitanan
│       ├── style.css           # Override styles khitanan
│       └── script.js           # Logic khitanan
│
├── assets/
│   ├── music/                  # File audio (.mp3)
│   ├── fonts/                  # Font lokal (opsional)
│   └── img/
│       ├── default-cover.jpg
│       └── ornaments/
│
├── config/
│   └── config.sample.json      # Contoh file konfigurasi
│
└── tools/
    └── preview-server.py       # Server lokal untuk preview
```

---

## Cara Menggunakan

### 1. Konfigurasi via URL Parameters

Cocok untuk link undangan personal langsung:

```
https://sikobokan.netlify.app/templates/pernikahan/?
  mempelai_pria=Ahmad+Fauzi&
  mempelai_wanita=Siti+Rahayu&
  tanggal=2025-03-15&
  jam=10:00&
  lokasi=Gedung+Serbaguna+Cibubur&
  maps=https://goo.gl/maps/xxx&
  musik=lagu-romantis&
  slug=ahmad-siti
```

#### Parameter yang tersedia:

| Parameter       | Tipe     | Keterangan                            |
|-----------------|----------|---------------------------------------|
| `mempelai_pria` | string   | Nama mempelai pria (pernikahan)       |
| `mempelai_wanita` | string | Nama mempelai wanita (pernikahan)     |
| `nama`          | string   | Nama tunggal (ultah/khitanan)         |
| `tanggal`       | date     | Format: YYYY-MM-DD                    |
| `jam`           | time     | Format: HH:MM                         |
| `lokasi`        | string   | Nama venue / lokasi                   |
| `alamat`        | string   | Alamat lengkap                        |
| `maps`          | url      | URL Google Maps (encode dulu)         |
| `musik`         | string   | Slug nama lagu dari daftar musik      |
| `slug`          | string   | Custom URL slug (fitur berbayar)      |
| `tamu`          | string   | Nama tamu untuk sapaan personal       |
| `foto`          | url      | URL foto utama (encode dulu)          |
| `tema`          | string   | Nama tema warna (default: gold)       |

### 2. Konfigurasi via `config.json`

Untuk kustomisasi lebih lengkap, buat file `config.json` di folder undangan:

```json
{
  "template": "pernikahan",
  "tema": "gold",
  "mempelai": {
    "pria": {
      "nama": "Ahmad Fauzi",
      "nama_lengkap": "Ahmad Fauzi bin Bapak A",
      "foto": "assets/img/foto-pria.jpg"
    },
    "wanita": {
      "nama": "Siti Rahayu",
      "nama_lengkap": "Siti Rahayu binti Bapak B",
      "foto": "assets/img/foto-wanita.jpg"
    }
  },
  "acara": {
    "akad": {
      "tanggal": "2025-03-15",
      "jam_mulai": "08:00",
      "jam_selesai": "10:00",
      "lokasi": "Masjid Al-Hidayah",
      "alamat": "Jl. Raya Cibubur No. 10, Jakarta Timur"
    },
    "resepsi": {
      "tanggal": "2025-03-15",
      "jam_mulai": "11:00",
      "jam_selesai": "14:00",
      "lokasi": "Gedung Serbaguna Cibubur",
      "alamat": "Jl. Raya Cibubur No. 12, Jakarta Timur",
      "maps_url": "https://goo.gl/maps/xxx"
    }
  },
  "galeri": [
    "assets/img/galeri-1.jpg",
    "assets/img/galeri-2.jpg",
    "assets/img/galeri-3.jpg"
  ],
  "musik": {
    "aktif": true,
    "lagu": "a-thousand-years",
    "autoplay": true
  },
  "rsvp": {
    "aktif": true,
    "deadline": "2025-03-10",
    "google_sheet_url": "https://script.google.com/..."
  },
  "quote": {
    "teks": "Dan di antara tanda-tanda kekuasaan-Nya ialah Dia menciptakan untukmu istri-istri dari jenismu sendiri",
    "sumber": "QS. Ar-Rum: 21"
  }
}
```

---

## Daftar Template

### 1. Template Pernikahan (`/templates/pernikahan/`)
- Cover full-screen dengan foto mempelai
- Nama mempelai dengan ornament kaligrafi
- Countdown timer menuju hari-H
- Detail akad & resepsi
- Galeri foto
- Peta lokasi (Google Maps embed)
- RSVP form
- Ucapan & doa dari tamu
- Musik latar romantis

**Tema warna:** Gold (default), Rose Gold, Navy, Sage Green

---

### 2. Template Ulang Tahun (`/templates/ultah/`)
- Cover ceria dengan animasi balon / confetti
- Countdown ke hari ulang tahun
- Informasi acara
- Galeri momen
- RSVP / konfirmasi kehadiran
- Pesan & ucapan

**Tema warna:** Colorful (default), Pastel, Dark Party, Elegant

---

### 3. Template Khitanan (`/templates/khitanan/`)
- Cover Islami dengan ornamen kaligrafi
- Biodata anak yang dikhitan
- Detail waktu & tempat
- RSVP
- Pesan & doa dari tamu

**Tema warna:** Green Islamic (default), Blue, Gold

---

## Monetisasi

### Model Bisnis: Freemium

Sikobokan menggunakan model **freemium** — template dasar bisa dipakai gratis, fitur premium dikenakan biaya per undangan.

---

### Daftar Harga

| Fitur                         | Harga                  | Keterangan                                      |
|-------------------------------|------------------------|-------------------------------------------------|
| **Template Basic**            | **GRATIS**             | 1 template, link acak, 5 foto galeri, 1 lagu   |
| **Custom Link / Slug**        | Rp 50.000              | Link cantik: `sikobokan.web.id/nama-kalian`     |
| **Musik Premium**             | Rp 25.000              | Akses 10+ lagu pilihan + lagu custom upload     |
| **Galeri Foto Unlimited**     | Rp 75.000              | Upload galeri tanpa batas (maks. 50 foto)       |
| **Paket Lengkap**             | **Rp 150.000/undangan**| Semua fitur di atas + prioritas support         |

> **Catatan:** Harga berlaku per undangan (bukan per akun). Masa aktif link undangan 12 bulan sejak tanggal pembayaran.

---

### Rincian Paket Lengkap (Rp 150.000)

- [x] Custom slug / URL cantik
- [x] Musik premium (10+ lagu + upload sendiri)
- [x] Galeri foto unlimited (hingga 50 foto)
- [x] RSVP form + notifikasi WhatsApp
- [x] Ucapan & komentar tamu
- [x] Countdown timer
- [x] Peta lokasi interaktif
- [x] Tombol share WhatsApp, Instagram, Facebook
- [x] Prioritas support via WhatsApp
- [x] Masa aktif link 12 bulan

---

### Target Pasar

**Segmen Utama:**
- Pasangan yang akan menikah (usia 20–35 tahun)
- Orang tua yang mengadakan khitanan (usia 30–50 tahun)
- Penyelenggara ulang tahun anak / sweet seventeen / milestone birthday

**Segmen Sekunder:**
- Wedding organizer (WO) yang butuh solusi undangan digital
- Event organizer lokal skala kecil-menengah
- Percetakan / desainer grafis yang mau menambah layanan digital

**Ukuran Pasar (estimasi):**
- Indonesia: ±2 juta pernikahan/tahun
- Target 0,1% = 2.000 undangan/tahun di tahun pertama
- Target 1% = 20.000 undangan/tahun di tahun kedua

---

### Proyeksi Pendapatan

#### Tahun 1 (Konservatif)

| Bulan    | Undangan Terjual | Rata-rata Nilai | Pendapatan      |
|----------|------------------|-----------------|-----------------|
| 1–3      | 30/bulan         | Rp 80.000       | Rp 7.200.000    |
| 4–6      | 80/bulan         | Rp 100.000      | Rp 24.000.000   |
| 7–12     | 150/bulan        | Rp 120.000      | Rp 108.000.000  |
| **Total**|                  |                 | **±Rp 140 juta**|

#### Tahun 2 (Target)

- 400 undangan/bulan × Rp 120.000 rata-rata = **Rp 576 juta/tahun**

---

### Strategi Penjualan

#### 1. Fiverr & Freelance Platform
- Listing sebagai jasa "Digital Wedding Invitation Indonesia"
- Paket: Basic (gratis template) → Standard (custom slug) → Premium (paket lengkap)
- Target: buyer internasional diaspora Indonesia

#### 2. Instagram & TikTok
- Konten: demo video undangan yang menarik
- Hashtag: `#undangandigital`, `#undanganonline`, `#undanganpernikahan`
- Kolaborasi dengan WO, fotografer, dan dekorator
- Story ads Rp 50.000–100.000/hari (target: pasangan tunangan)

#### 3. Grup WhatsApp & Komunitas
- Komunitas ibu-ibu, komunitas WO, grup arisan
- Reseller program: komisi 20% untuk referral berbayar
- Template pesan WA: "Mau undangan digital keren? Cek sikobokan.web.id"

#### 4. Marketplace Lokal
- Tokopedia / Shopee: listing sebagai produk digital
- Beli = dapat link aktivasi kode promo
- Review-driven: minta tamu undangan kasih review produk

#### 5. Program Reseller / Afiliasi
- Komisi 20% per transaksi berhasil
- Ideal untuk: WO, fotografer, desainer, MUA

---

### Struktur Biaya Operasional

| Item                     | Biaya/bulan   |
|--------------------------|---------------|
| Hosting (Vercel Pro)     | Rp 0 (free)   |
| Domain `sikobokan.web.id`| Rp 15.000     |
| Google Workspace (email) | Rp 80.000     |
| Iklan Instagram (opsional)| Rp 200.000   |
| **Total**                | **~Rp 300.000**|

> Break-even: 4 undangan berbayar/bulan sudah nutup biaya ops.

---

## Development Roadmap

### Phase 1 — MVP (Bulan 1–2)
- [x] `style-base.css` shared base stylesheet
- [ ] Template Pernikahan v1
- [ ] Template Ultah v1
- [ ] Template Khitanan v1
- [ ] RSVP form + Google Sheets integration
- [ ] Music player (5 lagu default)
- [ ] Deploy ke Vercel/Netlify

### Phase 2 — Monetisasi (Bulan 2–3)
- [ ] Payment gateway (Midtrans / Xendit)
- [ ] Sistem aktivasi kode (custom slug unlock)
- [ ] Dashboard admin sederhana
- [ ] WhatsApp notifikasi RSVP
- [ ] Upload foto galeri (Cloudinary integration)

### Phase 3 — Growth (Bulan 4–6)
- [ ] Template baru: Wisuda, Anniversary, Aqiqah
- [ ] Tema warna lebih banyak (5+ per template)
- [ ] Builder sederhana (drag & drop terbatas)
- [ ] Analytics: jumlah tamu buka undangan
- [ ] Fitur komentar & doa tamu

### Phase 4 — Scale (Bulan 7–12)
- [ ] Mobile app (Android PWA)
- [ ] API publik untuk reseller/WO
- [ ] Multi-bahasa (EN, AR)
- [ ] AI auto-generate teks undangan
- [ ] Marketplace template dari desainer pihak ketiga

---

## Cara Kontribusi (Dev Internal)

```bash
# Clone repo
git clone https://github.com/sikobokan/web-undangan.git
cd web-undangan

# Preview lokal (pakai Python)
python tools/preview-server.py

# Atau pakai VS Code Live Server extension

# Struktur branch
main          → production
dev           → staging/development
feature/xxx   → fitur baru
fix/xxx       → bugfix
```

### Coding Convention
- CSS: BEM-ish, class descriptive, no `!important` kecuali utility
- JS: Vanilla ES6+, no jQuery, no framework
- Komentar: Bahasa Indonesia untuk logika bisnis, English untuk kode teknis
- Commit: `feat:`, `fix:`, `style:`, `docs:`, `chore:`

---

## Environment Variables

Buat file `.env` (jangan di-commit):

```
GOOGLE_SHEETS_API_KEY=AIza...
MIDTRANS_CLIENT_KEY=Mid-client-...
MIDTRANS_SERVER_KEY=Mid-server-...
CLOUDINARY_CLOUD_NAME=sikobokan
CLOUDINARY_API_KEY=...
CLOUDINARY_API_SECRET=...
```

---

## License

```
MIT License

Copyright (c) 2025 Sikobokan Team (Ucil, Burat, Kanjut)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

*Sikobokan — Undangan Digital, Harga Terjangkau, Kesan Tak Terlupakan.* 🌸

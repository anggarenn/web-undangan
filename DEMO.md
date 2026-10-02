# Web Undangan Digital — Sikobokan
## DEMO & QA Checklist

### ✅ Fitur yang Sudah Berfungsi

#### Landing Page (`index.html`)
- [x] Tampilan 3 template card (Pernikahan, Ultah, Khitanan)
- [x] Section pricing/monetisasi dengan 4 paket
- [x] Link ke tiap template benar
- [x] Mobile responsive

#### Template Pernikahan (`template-pernikahan.html`)
- [x] Hero section dengan nama pasangan (dari URL param `?mempelai=`)
- [x] Countdown timer ke tanggal pernikahan
- [x] Galeri foto (6 slot placeholder)
- [x] Form RSVP → localStorage `undangan_rsvp_pernikahan`
- [x] Share ke WhatsApp
- [x] Copy link URL
- [x] Musik background (SoundHelix placeholder) dengan toggle on/off
- [x] Mobile-first responsive

#### Template Ulang Tahun (`template-ultah.html`)
- [x] Hero section dengan nama dan usia
- [x] Countdown timer
- [x] Form RSVP → localStorage `undangan_rsvp_ultah`
- [x] Share ke WhatsApp
- [x] Musik background

#### Template Khitanan (`template-khitanan.html`)
- [x] Basmallah dan elemen islami
- [x] Masjid silhouette CSS
- [x] Ayat Al-Quran
- [x] Countdown ke tanggal acara
- [x] Form RSVP → localStorage `undangan_rsvp_khitanan`
- [x] Murottal player (audio toggle)
- [x] Share ke WhatsApp

#### Admin Dashboard (`admin.html`)
- [x] Login sederhana (password: `admin123`)
- [x] Baca RSVP dari semua `undangan_rsvp_*` localStorage keys
- [x] Tampilkan per template
- [x] Total count per template
- [x] Export CSV

### 🔧 Yang Masih Perlu Dikerjakan (Next Sprint)

- [ ] Backend API + database (MySQL/PostgreSQL) — saat ini RSVP hanya di browser tamu
- [ ] Custom domain support (subdomain per undangan)
- [ ] Upload foto real (saat ini placeholder)
- [ ] Musik upload sendiri (saat ini link eksternal)
- [ ] Email notifikasi RSVP masuk
- [ ] QR code tamu (untuk absensi di tempat)
- [ ] Multi-bahasa (EN/ID)
- [ ] PWA (offline support)

### 💰 Estimasi Revenue (100 Undangan/Bulan)

| Paket | Harga | Konversi | Revenue |
|-------|-------|----------|---------|
| Free | Rp 0 | 60% | Rp 0 |
| Custom Link | Rp 50.000 | 20% | Rp 1.000.000 |
| Premium (musik+foto) | Rp 100.000 | 15% | Rp 1.500.000 |
| Full Package | Rp 150.000 | 5% | Rp 750.000 |
| **Total** | | **100 undangan** | **Rp 3.250.000/bulan** |

*Catatan: Dengan 500 undangan/bulan dan konversi sama → **~Rp 16 juta/bulan***

### 🚀 Cara Demo

```bash
# Buka di browser langsung (file://)
# Windows
start d:\Ren\ProjectAi\web-undangan\index.html

# Atau serve dengan Python
python -m http.server 3000 --directory d:\Ren\ProjectAi\web-undangan
# Buka: http://localhost:3000
```

### 🔗 Cara Kustomisasi Template

Tambahkan URL params saat share link:
```
template-pernikahan.html?mempelai=Ahmad+%26+Siti&tanggal=2025-12-25&lokasi=Jakarta
template-ultah.html?nama=Reno&usia=30&tanggal=2025-10-15
template-khitanan.html?nama=Muhammad+Hafiz&tanggal=2025-11-10&lokasi=Bandung
```

# LAPORAN RISET R&D: WEB UNDANGAN DIGITAL SIKOBOKAN
**Peneliti:** Mas Amba (R&D Tim Sikobokan)  
**Target:** Reno & Tim Sikobokan (Ucil, Burat, Kanjut, Siti, Soto)  
**Tanggal:** Oktober 2026

---

## 1. Analisis Kompetitor (Pasar Indonesia)

Data live scraping dari 6 pemain utama di Indonesia:

| Platform | Model Paket & Harga | Fitur Unggulan | Gap vs Sikobokan Saat Ini |
|---|---|---|---|
| **Satu Momen** (*satumomen.com*) | • **Basic**: Rp79.000 (7 hari, self-edit)<br>• **Premium**: Rp129.000 (30 hari, dibuatkan admin)<br>• **Prioritas**: Rp199.000 (90 hari, terima beres, revisi unlimited)<br>• **Signature**: Rp235.500 (180 hari)<br>• **Custom Desain**: Rp599.000 (1 thn, free domain `.my.id`)<br>• **Reseller**: Rp250k - Rp1.2jt | • Sistem Check-in Tamu QR Code hari H<br>• Custom domain `.my.id`<br>• Paket "terima beres" (jasa input admin)<br>• Ekosistem reseller & affiliate B2B | Sikobokan belum punya live backend (masih localStorage), belum ada QR check-in hari H, belum ada sistem masa aktif, dan belum ada paket jasa input. |
| **Our Wedding Link / OWL** (*our-wedding.link*) | • **Basic**: Rp50.000 (coret Rp110k)<br>• **Premium**: Rp110.000 (coret Rp250k)<br>• **Eksklusif**: Rp180.000 (coret Rp400k)<br>• **Luxury/VIP**: Rp280.000 (coret Rp800k)<br>• **Withdraw Fee**: Rp5.500 per penarikan amplop | • **Gamifikasi**: Mini-game interaktif (Pixel Game World & Javanese Game)<br>• Auto-scrolled cinematic<br>• Layar Sambutan Tamu (proyektor di venue)<br>• Seating & nomor meja tamu<br>• Amplop digital terintegrasi payout | Sikobokan belum punya elemen interaktif/gamifikasi, belum ada pembagian nomor meja/seating tamu, dan amplop digital masih nomor rekening pasif. |
| **Wevitation** (*wevitation.com*) | • **Free Trial**: Rp0 (14 hari, kuota tamu terbatas)<br>• **Premium**: Rp69.000 (coret Rp100k, aktif selamanya)<br>• **Pro**: Rp99.000 - Rp199.000 | • **AI Assistant**: AI Wedding Planner & AI Generator doa ucapan<br>• **Wegiftry**: Registry kado fisik anti-dobel<br>• Mode Layar Tamu live | Sikobokan belum ada integrasi AI untuk ucapan, belum ada gift registry barang fisik, dan belum ada tiering masa aktif. |
| **Katsudoto** (*katsudoto.id*) | • **Lite**: ~Rp75.000 - Rp99.000<br>• **Premium**: ~Rp149.000 - Rp199.000<br>• **Add-on Buku Tamu QR**: Rp150.000 - Rp350.000+ | • Ekosistem terintegrasi Buku Tamu Digital + QR Scanner resepsionis hari H<br>• Wedding checklist & budgeting planner<br>• Cetak label barcode souvenir | Sikobokan fokus di web tampilan saja; Katsudoto menjual ekosistem hari H (check-in tamu dan souvenir log). |
| **Invitree** (*invitree.id*) | • **Pernikahan**: Mulai Rp99.000<br>• **Multi-Event (Ultah, Khitanan, Aqiqah, Wisuda)**: Mulai Rp49.000 | • **Kategori Multi-Event yang matang** (sangat mirip arah Sikobokan)<br>• Harga non-wedding dibuat lebih murah (~50%) | Template khitanan & ultah kita saat ini fiturnya mirip wedding tapi disederhanakan; Invitree punya layout khusus anak-anak dan flow hadiah khusus. |
| **Viding** (*viding.co*) | • **Self-service**: Rp149.000 - Rp300.000<br>• **Onsite Enterprise**: Rp1.500.000 - Rp5.000.000+ (dengan crew & iPad check-in) | • WhatsApp Blast resmi via WhatsApp Business API<br>• Kiosk iPad check-in offline-ready di venue<br>• Live streaming multi-kamera embed | Target Viding adalah wedding premium/luxury dengan crew lapangan. Sikobokan bisa mengambil pasar massal mandiri (self-service). |

---

## 2. Fitur Viral & Trending (2024–2025)

1. **Mini-Games & Gamifikasi Interaktif di Undangan**
   - Mini-game pixel 8-bit ("Kumpulin Cincin") atau "Kuis Seberapa Kenal Kamu dengan Pengantin".
   - Meningkatkan engagement pembukaan link hingga >75%.
2. **AI-Powered Wishes Generator**
   - Tamu sering bingung menulis ucapan selain "Samawa ya".
   - Tombol *"Bantu Tulis Ucapan Pakai AI"* dengan filter mood: *Puitis, Lucu/Nyeleneh, Islami Khidmat, Formal, Pantun*.
3. **QR Code Check-in & Live Welcome Screen**
   - Tamu bawa QR unik dari undangan web (`sikobokan.com/andi-sasa?to=Budi`).
   - Panitia scan di pintu, layar proyektor venue langsung tampil: *"Selamat Datang Bapak Budi, Meja No. 4"*.
4. **Digital Angpao 1-Click + Dynamic QRIS**
   - Copy nomor rekening/e-wallet dengan feedback toast instan + modal pop-up QRIS besar.
5. **Shared Photo Wall / Live Event Album**
   - Tamu upload foto candid di hari H langsung ke web undangan. Tampil realtime di slider proyektor venue.
6. **Voice Note Wishes**
   - Tamu rekam pesan suara 15–30 detik langsung via Web Audio API browser.

### Alasan Pengguna Rela Membayar:
- **Tanpa Watermark & Iklan:** Menjaga gengsi acara sakral.
- **Nama Tamu Unlimited:** Personalisasi sapaan tiap tamu tanpa kuota.
- **Layanan "Terima Beres" (Jasa Input):** Pengantin lelah mengurus persiapan; opsi bayar Rp100k-Rp200k agar admin yang mengisikan data adalah solusi no-brainer.

---

## 3. Rekomendasi Fitur Next Sprint

### A. Quick Wins (Effort Rendah, Impact Tinggi)
1. **Dynamic Guest Name Cover Gate (`?to=Nama+Tamu`)**: Parsing parameter URL dan tampilkan elegan di cover gate amplop (*Kepada Yth. Bpk/Ibu [Nama]*).
2. **Generator Pesan Broadcast WhatsApp di Admin**: Paste daftar nama tamu -> sistem auto-generate daftar tombol klik kirim via WA (`wa.me/?text=...`).
3. **1-Click Copy Rekening / E-Wallet + Modal Zoom QRIS**: Hilangkan friksi pengiriman hadiah/angpao digital.
4. **Add to Google Calendar & Apple Calendar (.ics)**: Tombol 1-klik simpan ke kalender HP tamu.

### B. Diferensiator dari Kompetitor (Viral Factor)
5. **AI Wish Generator**: Tombol auto-generate doa/ucapan variatif.
6. **Love Story Timeline & Mini Trivia Quiz**: Kuis interaktif 3 pertanyaan tentang mempelai.
7. **Bilingual Switcher (ID / EN)**: Toggle bahasa Indonesia & Inggris untuk segmen multinasional.

### C. Upsell Premium
8. **QR Code Check-in & Live Attendance Scanner**: Scanner di `admin.html` pakai kamera HP (`html5-qrcode`).
9. **Custom Domain / Subdomain** (`namapasangan.id` atau `namapasangan.sikobokan.com`).
10. **Voice Note Wishes**: Rekaman pesan suara ucapan dari tamu via browser.

---

## 4. Rekomendasi Tech Stack

1. **Backend API**:
   - **Go (Fiber / Gin)**: Memory footprint mini (~20MB RAM), latensi <5ms, tangguh hadapi spike traffic ribuan tamu serentak.
   - Alternatif: **Node.js / Hono** (bisa jalan di edge Cloudflare Workers).
2. **Database**:
   - **PostgreSQL (Supabase / Managed VPS)** dengan kolom `JSONB` untuk skema fleksibel antar event (pernikahan, ultah, khitanan).
3. **Storage (Foto & Musik)**:
   - **Cloudflare R2** (Mutlak: **Zero Egress Fees**). Jangan pakai AWS S3 karena biaya bandwidth keluar foto & lagu diakses ribuan tamu.
4. **Hosting**:
   - Frontend: Cloudflare Pages / Vercel (Free global CDN, SSL otomatis).
   - API: Cloudflare Workers (serverless) atau VPS murah ($3-$5/bulan) di balik Cloudflare.

---

## 5. Struktur Harga & Strategi Monetisasi

| Tier | Harga | Target | Fitur Utama |
|---|---|---|---|
| **Free** | **Rp0** | Viral Hook | Aktif 7 hari, max 3 foto, watermark *"Dibuat dengan Sikobokan"*, RSVP dasar. |
| **Starter (Non-Wedding)** | **Rp49.000** | Ultah & Khitanan | Tanpa watermark, aktif 30 hari, galeri 5 foto, musik, ucapan. |
| **Reguler Wedding** | **Rp79.000** | Self-Service | Desain lengkap pernikahan, unlimited nama tamu, amplop digital, aktif 90 hari. |
| **Premium Wedding (Best Seller)** | **Rp129.000** | Pasangan Modern | Semua fitur + QR Code check-in hari H, AI wish generator, trivia quiz, aktif 180 hari. |
| **VIP / Terima Beres** | **Rp229.000** | Pasangan Sibuk | Full diisikan admin Sikobokan, revisi tak terbatas, prioritas WA support, custom URL slug. |

### Growth Loop Organik:
Setiap 1 undangan free/reguler yang disebar rata-rata dilihat 300–500 tamu. Watermark footer *"Buat undangan acaramu seindah ini di Sikobokan"* menjadi corong akuisisi gratis yang terus berputar.

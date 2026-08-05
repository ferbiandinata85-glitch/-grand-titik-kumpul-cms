# 03. Customer Journey

> Version : 1.1
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan perjalanan (Customer Journey) calon pelanggan mulai dari pertama kali mengenal Grand Titik Kumpul hingga booking berhasil dikonfirmasi.

Dokumen ini menjadi acuan dalam pembuatan Landing Page, UI/UX, Booking System, Dashboard, Database, dan API.

Customer Journey disusun berdasarkan Business Rules pada dokumen **02_Business_Rules.md**.

---

# 2. Customer Journey Overview

Perjalanan pelanggan terdiri dari tujuh tahapan utama.

```
Awareness
      │
      ▼
Interest
      │
      ▼
Consideration
      │
      ▼
Booking
      │
      ▼
Payment
      │
      ▼
Verification
      │
      ▼
Booking Confirmed
```

Target utama sistem adalah mengubah pengunjung website menjadi pelanggan yang berhasil melakukan booking.

---

# 3. Stage 1 — Awareness

### Objective

Mendatangkan traffic ke Landing Page.

### Customer Activity

Calon pelanggan menemukan Grand Titik Kumpul melalui:

- Google Search
- Google Maps
- Instagram
- Facebook
- TikTok
- YouTube
- WhatsApp
- Website Partner
- Iklan Digital
- Rekomendasi Teman

### System Response

Landing Page harus:

- Mobile Friendly
- Cepat diakses
- Profesional
- Menampilkan identitas Grand Titik Kumpul

### Success Indicator

Customer membuka Landing Page.

---

# 4. Stage 2 — Interest

### Objective

Membuat customer tertarik terhadap produk.

### Customer Activity

Customer mulai melihat:

- Banner utama
- Paket wisata
- Harga
- Fasilitas
- Foto kegiatan
- Video
- Testimoni
- Lokasi
- FAQ

### System Response

Landing Page menampilkan informasi secara jelas melalui card product.

Setiap card minimal memiliki:

- Foto
- Nama Paket
- Harga / Orang
- Tombol Detail
- Tombol Booking

### Success Indicator

Customer membuka halaman detail produk.

---

# 5. Stage 3 — Consideration

### Objective

Membantu customer menentukan pilihan.

### Customer Activity

Customer melakukan:

- Membandingkan paket
- Membandingkan harga
- Melihat bundle
- Melihat promo
- Melihat kalender booking
- Menghubungi Customer Service

### System Response

Website menyediakan:

- Kalender ketersediaan
- Detail fasilitas
- Informasi promo
- Floating WhatsApp
- FAQ

Mengacu pada:

- BR-601
- BR-602
- BR-603
- BR-1001

### Success Indicator

Customer memilih paket.

---

# 6. Stage 4 — Booking

### Objective

Mengumpulkan data booking.

### Customer Activity

Customer memilih:

- Paket
- Bundle (opsional)
- Add On (opsional)
- Tanggal
- Slot
- Jumlah peserta

Kemudian mengisi:

- Nama PIC
- WhatsApp
- Email
- Catatan tambahan

### System Response

Sistem melakukan validasi berdasarkan Business Rules.

Validasi:

- BR-201
- BR-202
- BR-203
- BR-204
- BR-205
- BR-206
- BR-207
- BR-208
- BR-301

Apabila valid, sistem membuat:

- Booking
- Booking Number
- Invoice

### Success Indicator

Booking berhasil dibuat.

---

# 7. Stage 5 — Payment

### Objective

Customer melakukan pembayaran.

### Customer Activity

Pilihan pembayaran:

- DP 50%
- Pelunasan

Customer kemudian mengunggah bukti transfer.

### System Response

Sistem:

- Menyimpan bukti transfer
- Mengubah status menjadi Menunggu Verifikasi

Mengacu pada:

- BR-701
- BR-702
- BR-703
- BR-704
- BR-801
- BR-802
- BR-803

### Success Indicator

Bukti transfer berhasil diterima.

---

# 8. Stage 6 — Verification

### Objective

Memastikan pembayaran valid.

### Admin Activity

Admin:

- Membuka Dashboard
- Melihat daftar pembayaran
- Memeriksa bukti transfer
- Menyetujui atau menolak pembayaran

### System Response

Status pembayaran diperbarui menjadi:

- Menunggu Verifikasi
- DP Diverifikasi
- Lunas Diverifikasi
- Ditolak

Mengacu pada:

- BR-901
- BR-902
- BR-903
- BR-904

### Success Indicator

Status pembayaran berubah.

---

# 9. Stage 7 — Booking Confirmed

### Objective

Booking siap dilaksanakan.

### Customer Activity

Customer menerima informasi booking.

Informasi yang tersedia:

- Nomor Booking
- Paket
- Jadwal
- Slot
- Status Pembayaran
- Total Pembayaran

### System Response

Booking menjadi aktif dan tampil pada Dashboard CMS.

### Success Indicator

Booking siap diproses lebih lanjut.

---

# 10. Customer Touch Points

Seluruh interaksi pelanggan dengan sistem.

| Touch Point     | Tujuan              |
| --------------- | ------------------- |
| Landing Page    | Mengenal produk     |
| Product Detail  | Memahami paket      |
| Booking Form    | Melakukan reservasi |
| Upload Transfer | Mengirim pembayaran |
| WhatsApp        | Konsultasi          |

---

# 11. Customer Experience Goals

Website dirancang agar pelanggan merasakan pengalaman berikut.

- Booking kurang dari 5 menit
- Tampilan profesional
- Mobile First
- Navigasi sederhana
- Informasi mudah dipahami
- Harga transparan
- Kalender mudah digunakan
- Status booking jelas

---

# 12. Business Goals

Website diharapkan mampu:

- Meningkatkan jumlah booking
- Mengurangi pertanyaan berulang melalui WhatsApp
- Mempercepat proses administrasi
- Mengurangi kesalahan input data
- Menjadi pusat data marketing

---

# 13. Related Business Rules

Customer Journey mengacu pada:

- BR-201 s/d BR-208
- BR-301
- BR-401
- BR-501
- BR-601
- BR-701
- BR-801
- BR-901
- BR-1001
- BR-1101
- BR-1102
- BR-1103

---

# 14. Related Documents

- 02_Business_Rules.md
- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 01_Product/01_Product_Catalog.md
- 03_UIUX/02_Landing_Page.md
- 03_UIUX/03_Booking_Page.md

---

# 15. Revision History

| Version | Date       | Description                         |
| ------- | ---------- | ----------------------------------- |
| 1.0     | YYYY-MM-DD | Initial Customer Journey            |
| 1.1     | YYYY-MM-DD | Integrated with Business Rules (BR) |

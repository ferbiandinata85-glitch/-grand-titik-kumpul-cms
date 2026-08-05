# 04. Booking Flow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan alur proses booking mulai dari customer memilih paket hingga booking dinyatakan aktif (Confirmed).

Dokumen ini menjadi acuan bagi:

- UI/UX Booking
- Database
- API Booking
- Dashboard CMS
- Payment Flow

Dokumen ini hanya mencakup proses Marketing & Booking (V1), belum mencakup operasional kegiatan di lapangan.

---

# 2. Booking Flow Overview

```

Customer Visit Website
│
▼
Melihat Paket
│
▼
Memilih Paket
│
▼
Memilih Tanggal
│
▼
Memilih Slot
│
▼
Mengisi Data PIC
│
▼
Menambahkan Catatan (Opsional)
│
▼
Submit Booking
│
▼
Generate Booking
│
▼
Generate Invoice
│
▼
Menunggu Pembayaran
│
▼
Upload Bukti Transfer
│
▼
Verifikasi Admin
│
▼
Booking Confirmed

```

---

# 3. Step 1 — Customer Memilih Paket

Customer membuka Landing Page.

Customer dapat memilih:

- Rafting
- Paintball
- Outbound
- Offroad

Customer juga dapat memilih:

- Bundle Package
- Add-On

Mengacu pada:

- BR-101
- BR-102
- BR-103

Output:

Daftar paket yang akan dibooking.

---

# 4. Step 2 — Memilih Tanggal

Customer memilih tanggal kegiatan.

Sistem menampilkan kalender booking.

Kalender memperlihatkan:

- Slot tersedia
- Slot penuh
- Slot ditutup

Mengacu pada:

- BR-1001
- BR-1002
- BR-1003
- BR-1004

Output:

Tanggal Booking.

---

# 5. Step 3 — Memilih Slot

Customer memilih slot kegiatan.

Default Slot

| Slot  | Jam           |
| ----- | ------------- |
| Pagi  | 06.00 – 11.00 |
| Siang | 12.30 – 14.00 |
| Sore  | 15.00 – 17.00 |

Mengacu pada:

- BR-401
- BR-402
- BR-403

Output:

Slot Booking.

---

# 6. Step 4 — Mengisi Data PIC

Customer mengisi data utama.

Data wajib:

- Nama PIC
- Nomor WhatsApp
- Email

Data tambahan:

- Nama Perusahaan (Opsional)
- Catatan Tambahan

Contoh Catatan

- Tolong siapkan tempat banner.
- Mohon dokumentasi lebih banyak.
- Membawa anak kecil.
- Request makan vegetarian.

Mengacu pada:

- BR-202
- BR-203
- BR-208

Output:

Data Customer.

---

# 7. Step 5 — Menentukan Jumlah Peserta

Customer menentukan jumlah peserta.

Sistem melakukan validasi.

Contoh V1

Rafting

Minimal :

10 Peserta

Nilai minimum dapat diubah melalui CMS.

Mengacu pada:

- BR-301
- BR-302
- BR-303

Output:

Jumlah Peserta Valid.

---

# 8. Step 6 — Perhitungan Harga

Sistem menghitung otomatis.

Komponen perhitungan:

- Harga Paket
- Jumlah Peserta
- Bundle
- Add-On
- Promo
- Diskon

Output:

Total Tagihan.

Mengacu pada:

- BR-501
- BR-502
- BR-505
- BR-601

---

# 9. Step 7 — Generate Booking

Apabila seluruh data valid, sistem membuat:

- Booking Number
- Booking Date
- Booking Status

Status awal:

Pending Payment

Booking berlaku:

1 x 24 Jam

Mengacu pada:

- BR-701

Output:

Booking berhasil dibuat.

---

# 10. Step 8 — Generate Invoice

Setelah booking dibuat.

Sistem membuat Invoice.

Invoice berisi:

- Nomor Invoice
- Nomor Booking
- Detail Paket
- Jumlah Peserta
- Total Tagihan
- Minimal DP
- Batas Pembayaran

Output:

Invoice.

---

# 11. Step 9 — Customer Melakukan Pembayaran

Customer memiliki dua pilihan.

Pilihan 1

DP Minimal 50%

Pilihan 2

Lunas

Mengacu pada:

- BR-702
- BR-703

---

# 12. Step 10 — Upload Bukti Transfer

Customer mengupload bukti transfer.

Ketentuan:

- File dapat diupload ulang.
- Upload terbaru menggantikan file sebelumnya.
- Berlaku selama status belum Lunas.

Mengacu pada:

- BR-801
- BR-802
- BR-803
- BR-804

Output:

Status menjadi:

Menunggu Verifikasi.

---

# 13. Step 11 — Verifikasi Admin

Admin membuka Dashboard.

Admin memeriksa:

- Invoice
- Nominal
- Bukti Transfer

Admin menentukan status.

Pilihan:

- DP Diverifikasi
- Lunas Diverifikasi
- Ditolak

Mengacu pada:

- BR-901
- BR-902
- BR-903
- BR-904

---

# 14. Booking Status Lifecycle

```

Draft

↓

Pending Payment

↓

Waiting Verification

↓

DP Verified

↓

Paid

↓

Booking Confirmed

```

Status alternatif

```

Waiting Verification

↓

Rejected

↓

Upload Ulang

↓

Waiting Verification

```

---

# 15. Booking Expired

Booking otomatis dianggap kadaluarsa apabila:

- Melebihi 1 x 24 jam
- Belum ada pembayaran

Status berubah menjadi

Expired

Booking tidak dapat digunakan lagi.

Mengacu pada:

- BR-701

---

# 16. Dashboard Impact

Setiap booking baru akan mempengaruhi Dashboard.

Dashboard memperbarui:

- Total Booking
- Booking Hari Ini
- Total Peserta
- Pendapatan
- DP Masuk
- Booking Pending
- Booking Confirmed
- Kalender Booking

---

# 17. Related Business Rules

Booking Flow mengimplementasikan:

- BR-101 sampai BR-107
- BR-201 sampai BR-208
- BR-301 sampai BR-303
- BR-401 sampai BR-403
- BR-501 sampai BR-505
- BR-601 sampai BR-604
- BR-701 sampai BR-704
- BR-801 sampai BR-804
- BR-901 sampai BR-904
- BR-1001 sampai BR-1004

---

# 18. Related Documents

- 02_Business_Rules.md
- 03_Customer_Journey.md
- 05_Payment_Flow.md
- 02_Product/01_Product_Catalog.md
- 03_UIUX/03_Booking_Page.md
- 04_Data/01_Business_Object_Model.md

---

# 19. Revision History

| Version | Date       | Description          |
| ------- | ---------- | -------------------- |
| 1.0     | YYYY-MM-DD | Initial Booking Flow |

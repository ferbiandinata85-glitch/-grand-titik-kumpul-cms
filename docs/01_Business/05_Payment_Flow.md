# 05. Payment Flow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan alur pembayaran (Payment Flow) mulai dari invoice dibuat hingga pembayaran dinyatakan lunas.

Dokumen ini menjadi acuan untuk:

- CMS Admin
- Dashboard
- Database
- API Payment
- Finance
- Booking System

Pada versi V1, seluruh proses verifikasi pembayaran masih dilakukan secara manual oleh Admin.

---

# 2. Payment Flow Overview

```
Booking Created
        │
        ▼
Generate Invoice
        │
        ▼
Customer Transfer
        │
        ▼
Upload Bukti Transfer
        │
        ▼
Waiting Verification
        │
        ▼
Admin Verification
        │
   ┌────┴────┐
   ▼         ▼
Approved   Rejected
   │         │
   ▼         ▼
Update     Upload Ulang
Status        │
   │          │
   └──────────┘
        │
        ▼
Booking Confirmed
```

---

# 3. Invoice Generation

Setelah booking berhasil dibuat, sistem secara otomatis membuat satu invoice.

Invoice berisi:

- Nomor Invoice
- Nomor Booking
- Nama PIC
- Paket
- Jumlah Peserta
- Total Tagihan
- Minimal DP
- Deadline Pembayaran

Status awal Invoice:

```
Waiting Payment
```

Mengacu pada:

- BR-701
- BR-702

---

# 4. Customer Payment

Customer memiliki dua pilihan pembayaran.

## Opsi 1

DP Minimal 50%

## Opsi 2

Pelunasan Langsung

Customer bebas memilih salah satu.

Mengacu pada:

- BR-702
- BR-703

---

# 5. Upload Bukti Transfer

Setelah transfer selesai, customer mengunggah bukti transfer melalui website.

Ketentuan:

- Upload tanpa login.
- Bukti transfer menjadi bagian dari data booking.
- Selama status belum Lunas, customer masih dapat mengganti file upload.
- File terbaru akan menggantikan file sebelumnya.

Mengacu pada:

- BR-801
- BR-802
- BR-803
- BR-804

---

# 6. Verification Process

Admin membuka Dashboard CMS.

Daftar pembayaran yang menunggu verifikasi akan ditampilkan.

Admin memeriksa:

- Invoice
- Nominal Transfer
- Bukti Transfer
- Rekening Tujuan

Kemudian memilih salah satu status.

---

# 7. Verification Status

Status pembayaran terdiri dari:

| Status               | Keterangan                 |
| -------------------- | -------------------------- |
| Waiting Verification | Menunggu pemeriksaan Admin |
| DP Verified          | DP diterima                |
| Paid                 | Pelunasan diterima         |
| Rejected             | Bukti transfer ditolak     |

Mengacu pada:

- BR-901
- BR-902
- BR-903
- BR-904

---

# 8. Payment Status Lifecycle

```
Waiting Payment
        │
        ▼
Waiting Verification
        │
   ┌────┴────┐
   ▼         ▼
Rejected   Verified
               │
      ┌────────┴────────┐
      ▼                 ▼
DP Verified          Paid
```

---

# 9. Rejected Payment

Pembayaran dapat ditolak apabila:

- Bukti transfer tidak jelas.
- Nominal tidak sesuai.
- Transfer tidak ditemukan.
- Upload file salah.

Apabila ditolak:

- Customer dapat mengunggah ulang bukti transfer.
- Status kembali menjadi Waiting Verification.

---

# 10. Booking Expired

Booking otomatis Expired apabila:

- Tidak ada pembayaran selama 1 × 24 jam sejak invoice dibuat.

Status Booking:

```
Expired
```

Invoice tidak dapat digunakan lagi.

Mengacu pada:

- BR-701

---

# 11. Dashboard Impact

Setiap pembayaran akan memperbarui Dashboard.

Widget yang diperbarui:

- Total Pendapatan
- DP Masuk
- Pelunasan
- Menunggu Verifikasi
- Booking Aktif
- Booking Expired

---

# 12. Future Payment

Versi berikutnya dapat menambahkan:

- Payment Gateway
- Virtual Account
- QRIS
- Midtrans
- Xendit
- Otomatis Verifikasi Mutasi
- Email Invoice
- WhatsApp Invoice

Fitur tersebut tidak mengubah alur utama Payment Flow.

---

# 13. Related Business Rules

Payment Flow mengimplementasikan:

- BR-701 s/d BR-704
- BR-801 s/d BR-804
- BR-901 s/d BR-904

---

# 14. Related Documents

- 02_Business_Rules.md
- 04_Booking_Flow.md
- 06_User_Roles.md
- 04_Data/01_Business_Object_Model.md
- 04_Data/04_Status.md
- 05_API/05_Payment_API.md

---

# 15. Revision History

| Version | Date       | Description          |
| ------- | ---------- | -------------------- |
| 1.0     | YYYY-MM-DD | Initial Payment Flow |

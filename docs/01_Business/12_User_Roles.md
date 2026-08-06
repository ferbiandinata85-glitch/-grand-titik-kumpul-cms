# 11. User Roles

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan seluruh peran pengguna (User Roles), hak akses (Permissions), dan tanggung jawab masing-masing pengguna pada Grand Titik Kumpul CMS.

Dokumen ini menjadi acuan dalam implementasi Authentication, Authorization, Dashboard, dan Security.

Pada versi V1 sistem hanya menggunakan tiga Role Backend.

- Owner
- Marketing Manager
- Administrator

Customer bukan pengguna CMS karena seluruh proses booking dilakukan melalui website tanpa Login.

---

# 2. User Hierarchy

```
                    OWNER
                      │
        ┌─────────────┴─────────────┐
        │                           │
        ▼                           ▼
Marketing Manager             Administrator

Customer
(No Login)
```

---

# 3. Role Overview

| Role              | Deskripsi                                               |
| ----------------- | ------------------------------------------------------- |
| Owner             | Pemilik sistem dengan hak akses penuh                   |
| Marketing Manager | Mengelola produk, harga, promo, dan aktivitas pemasaran |
| Administrator     | Mengelola booking dan verifikasi pembayaran             |
| Customer          | Menggunakan website tanpa Login                         |

---

# 4. Owner

## Responsibilities

Owner bertanggung jawab terhadap seluruh pengelolaan sistem dan kebijakan bisnis.

Owner memiliki hak akses penuh terhadap seluruh menu CMS.

---

## Permissions

Owner dapat:

- Dashboard
- Product
- Bundle
- Promotion
- Pricing
- Booking
- Payment
- Calendar
- User Management
- Reports
- Settings

---

# 5. Marketing Manager

## Responsibilities

Marketing Manager bertanggung jawab terhadap seluruh aktivitas pemasaran.

Fokus utama:

- Product
- Bundle
- Promotion
- Harga
- Landing Page

---

## Permissions

Marketing Manager dapat:

- Melihat Dashboard
- Mengelola Product
- Mengelola Bundle
- Mengelola Promotion
- Mengubah Harga
- Mengatur Minimal Peserta
- Mengatur Slot Booking
- Melihat Booking
- Melihat Statistik Penjualan

Marketing Manager tidak dapat:

- Mengelola User
- Mengubah Hak Akses
- Menghapus Riwayat Pembayaran

---

# 6. Administrator

## Responsibilities

Administrator bertanggung jawab terhadap proses administrasi transaksi.

Fokus utama:

- Booking
- Invoice
- Bukti Transfer
- Verifikasi Pembayaran

---

## Permissions

Administrator dapat:

- Melihat Booking
- Melihat Detail Booking
- Melihat Invoice
- Melihat Bukti Transfer
- Memverifikasi Pembayaran
- Mengubah Status Booking
- Melihat Kalender Booking

Administrator tidak dapat:

- Mengubah Product
- Mengubah Harga
- Mengubah Promotion
- Mengelola User

---

# 7. Customer

Customer bukan pengguna CMS.

Customer menggunakan Landing Page tanpa Login.

Customer dapat:

- Melihat Product
- Melihat Bundle
- Melihat Harga
- Melihat Kalender
- Melakukan Booking
- Mengunggah Bukti Transfer
- Menghubungi Customer Service melalui WhatsApp

Customer tidak memiliki akun backend.

---

# 8. Permission Matrix

| Menu                 | Owner | Marketing Manager | Administrator |
| -------------------- | :---: | :---------------: | :-----------: |
| Dashboard            |   ✓   |         ✓         |       ✓       |
| Product              |   ✓   |         ✓         |       ✗       |
| Bundle               |   ✓   |         ✓         |       ✗       |
| Promotion            |   ✓   |         ✓         |       ✗       |
| Pricing              |   ✓   |         ✓         |       ✗       |
| Booking              |   ✓   |         ✓         |       ✓       |
| Invoice              |   ✓   |         ✓         |       ✓       |
| Payment Verification |   ✓   |         ✓         |       ✓       |
| Calendar             |   ✓   |         ✓         |       ✓       |
| User Management      |   ✓   |         ✗         |       ✗       |
| Reports              |   ✓   |         ✓         |       ✓       |
| Settings             |   ✓   |         ✗         |       ✗       |

---

# 9. Authentication

Backend CMS menggunakan Login.

Setelah Login berhasil, sistem akan menentukan hak akses berdasarkan Role pengguna.

Customer tidak memerlukan Login untuk melakukan Booking.

---

# 10. Dashboard by Role

## Owner

Dashboard Owner menampilkan seluruh performa bisnis.

Contoh:

- Total Booking
- Pendapatan
- Booking Hari Ini
- Booking Bulan Ini
- Paket Terlaris
- Total Customer
- Grafik Penjualan

---

## Marketing Manager

Dashboard Marketing Manager berfokus pada aktivitas pemasaran.

Contoh:

- Booking Baru
- Produk Terlaris
- Promo Aktif
- Conversion
- Kalender Booking

---

## Administrator

Dashboard Administrator berfokus pada pekerjaan harian.

Contoh:

- Booking Baru
- Menunggu Verifikasi
- DP Masuk
- Pelunasan
- Booking Hari Ini

---

# 11. Security Principles

Untuk menjaga keamanan sistem.

- Setiap Login dicatat.
- Hak akses berdasarkan Role.
- Pengguna hanya dapat mengakses menu sesuai Permission.
- Seluruh transaksi tetap tersimpan walaupun Role berubah.

Pada versi V2 akan ditambahkan Audit Log.

---

# 12. Future Roles

Role berikut dipersiapkan untuk pengembangan berikutnya.

- Finance
- Customer Service
- Operational Manager
- Tour Leader
- Super Administrator

Penambahan Role tidak mengubah struktur dasar sistem.

---

# 13. Business Rules

Dokumen ini mengimplementasikan:

- BR-901
- BR-902
- BR-903
- BR-904

---

# 14. Related Documents

- 02_Business_Rules.md
- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 10_Document_Workflow.md
- ../03_UIUX/05_CMS.md
- ../03_UIUX/06_Dashboard.md
- ../05_API/02_Authentication.md

---

# 15. Revision History

| Version | Date       | Description        |
| ------- | ---------- | ------------------ |
| 1.0     | YYYY-MM-DD | Initial User Roles |

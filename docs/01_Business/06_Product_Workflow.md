# 06. Product Workflow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan proses pengelolaan Product (Paket Wisata) pada Grand Titik Kumpul CMS.

Workflow ini menjadi acuan bagi Marketing Manager dan Owner dalam membuat, mengubah, mengaktifkan, maupun menghentikan penjualan suatu produk.

Dokumen ini hanya membahas proses bisnis (Business Workflow), bukan struktur database maupun implementasi API.

---

# 2. Workflow Overview

Setiap Product memiliki siklus hidup mulai dari dibuat hingga dipublikasikan kepada customer.

Flow utama Product adalah sebagai berikut:

```
Marketing Manager
        │
        ▼
Tambah Product
        │
        ▼
Lengkapi Informasi Product
        │
        ▼
Atur Harga
        │
        ▼
Atur Minimal Peserta
        │
        ▼
Upload Foto
        │
        ▼
Publish Product
        │
        ▼
Tampil pada Landing Page
        │
        ▼
Customer Melakukan Booking
```

---

# 3. Product Lifecycle

Setiap Product memiliki tahapan sebagai berikut.

## Draft

Product baru dibuat tetapi belum dapat dilihat oleh customer.

Status:

- Draft

---

## Published

Product telah lengkap dan dapat ditampilkan pada website.

Status:

- Active

---

## Updated

Product mengalami perubahan seperti:

- Harga
- Foto
- Deskripsi
- Promo
- Bundle

Perubahan langsung berlaku setelah disimpan.

---

## Archived

Product tidak lagi dijual tetapi histori booking tetap tersimpan.

Status:

- Archived

---

# 4. Product Information

Minimal informasi yang dimiliki Product.

## Informasi Umum

- Nama Paket
- Kategori
- Deskripsi Singkat
- Deskripsi Lengkap

---

## Harga

- Harga per Orang
- Mata Uang
- Harga Aktif

---

## Peserta

- Minimal Peserta
- Maksimal Peserta (Opsional)

---

## Lokasi

- Meeting Point
- Lokasi Aktivitas

---

## Durasi

Contoh:

- Half Day
- Full Day

---

## Media

- Cover Image
- Gallery Image

---

## Status

- Draft
- Active
- Archived

---

# 5. Product Creation Workflow

Langkah pembuatan Product.

```
Login CMS
      │
      ▼
Menu Product
      │
      ▼
Tambah Product
      │
      ▼
Isi Informasi Product
      │
      ▼
Upload Foto
      │
      ▼
Isi Harga
      │
      ▼
Atur Minimal Peserta
      │
      ▼
Simpan
```

Status awal Product adalah Draft.

---

# 6. Product Publish Workflow

Sebelum Product dipublikasikan, sistem melakukan validasi.

Minimal data yang harus tersedia.

- Nama Product
- Harga
- Foto Cover
- Deskripsi
- Minimal Peserta

Apabila seluruh data telah lengkap maka Product dapat diubah menjadi Active.

---

# 7. Product Update Workflow

Marketing Manager dapat memperbarui Product kapan saja.

Contoh perubahan:

- Harga
- Foto
- Deskripsi
- Highlight
- Kategori

Riwayat booking sebelumnya tidak berubah.

---

# 8. Product Archive Workflow

Apabila Product sudah tidak dijual lagi.

Workflow:

```
Product Active
        │
        ▼
Archive Product
        │
        ▼
Tidak tampil pada Website
        │
        ▼
Data Booking Lama Tetap Tersimpan
```

Archive tidak menghapus data Product.

---

# 9. Landing Page Integration

Product dengan status Active akan otomatis muncul pada Landing Page.

Informasi yang ditampilkan:

- Cover Image
- Nama Paket
- Harga per Orang
- Highlight
- Tombol Booking

Product Draft maupun Archived tidak ditampilkan.

---

# 10. CMS Workflow

Menu Product hanya dapat diakses oleh:

- Owner
- Marketing Manager

Marketing Manager dapat:

- Menambah Product
- Mengubah Product
- Mengubah Harga
- Mengubah Minimal Peserta
- Mengelola Foto
- Mengaktifkan Product
- Mengarsipkan Product

Administrator hanya dapat melihat informasi Product yang digunakan pada Booking.

---

# 11. Business Rules

Workflow ini mengimplementasikan aturan berikut.

- BR-001
- BR-002
- BR-101
- BR-102
- BR-201

---

# 12. Future Enhancement

Fitur berikut direncanakan pada versi berikutnya.

- Multiple Price Tier
- Seasonal Pricing
- Multi Language
- Product Tag
- Product Recommendation
- Product Rating

---

# 13. Related Documents

- 02_Business_Rules.md
- 03_Customer_Journey.md
- 04_Booking_Flow.md
- ../02_Product/01_Product_Catalog.md
- ../02_Product/05_Pricing.md
- ../03_UIUX/02_Landing_Page.md
- ../05_API/03_Product_API.md

---

# 14. Revision History

| Version | Date       | Description              |
| ------- | ---------- | ------------------------ |
| 1.0     | YYYY-MM-DD | Initial Product Workflow |

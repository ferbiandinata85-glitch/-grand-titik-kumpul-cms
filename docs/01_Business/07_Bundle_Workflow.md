# 07. Bundle Workflow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan proses bisnis pengelolaan Bundle Product pada Grand Titik Kumpul CMS.

Bundle memungkinkan beberapa produk dijual sebagai satu paket dengan harga khusus sehingga dapat meningkatkan nilai penjualan sekaligus memberikan keuntungan bagi customer.

Workflow ini hanya menjelaskan proses bisnis dan tidak membahas implementasi database maupun API.

---

# 2. Workflow Overview

Bundle dibuat berdasarkan Product yang telah tersedia.

```
Marketing Manager
        │
        ▼
Pilih Product
        │
        ▼
Buat Bundle
        │
        ▼
Tambahkan Product
        │
        ▼
Atur Harga Bundle
        │
        ▼
Publish Bundle
        │
        ▼
Muncul di Landing Page
        │
        ▼
Customer Booking
```

---

# 3. Bundle Concept

Bundle adalah kombinasi dua atau lebih Product yang dijual sebagai satu paket.

Contoh:

- Rafting + Makan Siang
- Rafting + Paintball
- Rafting + Outbound
- Family Package
- Corporate Gathering Package

Bundle tidak membuat Product baru, melainkan menggabungkan Product yang sudah ada.

---

# 4. Bundle Information

Setiap Bundle minimal memiliki informasi berikut.

## General Information

- Nama Bundle
- Deskripsi
- Cover Image

---

## Bundle Content

- Daftar Product
- Jumlah Item
- Optional Add On

---

## Pricing

- Harga Bundle
- Harga Normal
- Total Penghematan

---

## Status

- Draft
- Active
- Archived

---

# 5. Bundle Creation Workflow

```
Login CMS
      │
      ▼
Menu Bundle
      │
      ▼
Tambah Bundle
      │
      ▼
Isi Informasi Bundle
      │
      ▼
Pilih Product
      │
      ▼
Atur Harga Bundle
      │
      ▼
Simpan
```

Status awal adalah Draft.

---

# 6. Bundle Validation

Bundle dapat dipublikasikan apabila memenuhi syarat berikut.

- Memiliki Nama Bundle
- Memiliki minimal satu Product
- Harga Bundle telah ditentukan
- Cover Image tersedia
- Status Product masih Active

Apabila salah satu Product diarsipkan, sistem harus memberikan peringatan kepada Marketing Manager.

---

# 7. Bundle Publish Workflow

```
Draft
   │
   ▼
Validasi
   │
   ▼
Publish
   │
   ▼
Active
   │
   ▼
Tampil pada Landing Page
```

Hanya Bundle dengan status Active yang dapat dibooking.

---

# 8. Bundle Update Workflow

Marketing Manager dapat mengubah:

- Nama Bundle
- Deskripsi
- Harga Bundle
- Product di dalam Bundle
- Foto
- Urutan Product

Perubahan akan langsung ditampilkan pada Landing Page setelah disimpan.

---

# 9. Bundle Archive Workflow

```
Bundle Active
        │
        ▼
Archive
        │
        ▼
Tidak tampil di Website
        │
        ▼
Riwayat Booking Tetap Ada
```

Archive tidak menghapus histori transaksi.

---

# 10. Landing Page Integration

Bundle Active ditampilkan bersama Product biasa.

Card Bundle menampilkan:

- Cover Image
- Nama Bundle
- Harga Bundle
- Harga Normal (Coret)
- Total Penghematan
- Highlight Benefit
- Tombol Booking

Bundle dapat diberi label:

- Best Seller
- Promo
- Recommended
- New

---

# 11. CMS Workflow

Bundle hanya dapat dikelola oleh:

- Owner
- Marketing Manager

Administrator hanya dapat melihat informasi Bundle pada detail Booking.

---

# 12. Business Rules

Workflow ini mengimplementasikan:

- BR-301
- BR-302
- BR-303
- BR-304

---

# 13. Future Enhancement

Pengembangan berikut direncanakan untuk versi selanjutnya.

- Dynamic Bundle
- Auto Bundle Recommendation
- Bundle Schedule
- Bundle Stock
- Bundle Category
- Bundle Analytics

---

# 14. Related Documents

- 02_Business_Rules.md
- 06_Product_Workflow.md
- ../02_Product/04_Bundle_System.md
- ../02_Product/05_Pricing.md
- ../03_UIUX/02_Landing_Page.md
- ../05_API/03_Product_API.md

---

# 15. Revision History

| Version | Date       | Description             |
| ------- | ---------- | ----------------------- |
| 1.0     | YYYY-MM-DD | Initial Bundle Workflow |

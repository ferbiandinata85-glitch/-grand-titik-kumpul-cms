# 08. Promotion Workflow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan proses bisnis pengelolaan Promotion pada Grand Titik Kumpul CMS.

Promotion digunakan untuk meningkatkan penjualan dengan memberikan potongan harga atau penawaran khusus terhadap Product maupun Bundle.

Pada versi V1, Promotion dibuat sesederhana mungkin agar mudah digunakan oleh Marketing Manager.

---

# 2. Workflow Overview

Promotion dibuat setelah Product atau Bundle tersedia.

```
Marketing Manager
        │
        ▼
Pilih Product / Bundle
        │
        ▼
Buat Promotion
        │
        ▼
Tentukan Jenis Diskon
        │
        ▼
Tentukan Periode
        │
        ▼
Publish
        │
        ▼
Landing Page
        │
        ▼
Customer Booking
```

---

# 3. Promotion Concept

Promotion merupakan potongan harga yang dapat diterapkan pada:

- Product
- Bundle

Promotion tidak mengubah harga dasar Product, melainkan hanya mempengaruhi harga jual selama promo aktif.

---

# 4. Promotion Type

Versi V1 hanya mendukung satu jenis promo.

## Percentage Discount

Contoh:

```
10%

15%

20%
```

Nilai diskon dapat diisi bebas oleh Marketing Manager.

Promo akan dihitung berdasarkan harga Product atau Bundle.

---

# 5. Promotion Information

Setiap Promotion memiliki informasi berikut.

## General

- Nama Promo
- Deskripsi

---

## Discount

- Discount Percentage

---

## Period

- Start Date
- End Date

---

## Target

- Product
- Bundle

---

## Status

- Draft
- Active
- Expired
- Archived

---

# 6. Promotion Creation Workflow

```
Login CMS
      │
      ▼
Menu Promotion
      │
      ▼
Tambah Promotion
      │
      ▼
Pilih Product / Bundle
      │
      ▼
Isi Persentase Diskon
      │
      ▼
Atur Periode
      │
      ▼
Simpan
```

Status awal Promotion adalah Draft.

---

# 7. Promotion Publish Workflow

Promotion dapat dipublikasikan apabila:

- Product atau Bundle masih Active
- Nilai Diskon telah ditentukan
- Periode Promo valid

Setelah dipublikasikan, Promotion akan aktif sesuai tanggal yang telah ditentukan.

---

# 8. Promotion Update Workflow

Marketing Manager dapat mengubah:

- Nama Promo
- Deskripsi
- Nilai Diskon
- Tanggal Promo

Perubahan akan langsung digunakan pada proses Booking.

---

# 9. Promotion Expired Workflow

Apabila tanggal promo telah berakhir.

```
Promotion Active
        │
        ▼
End Date
        │
        ▼
Expired
        │
        ▼
Harga Kembali Normal
```

Tidak diperlukan tindakan manual.

Sistem akan menonaktifkan promo secara otomatis berdasarkan tanggal berakhir.

---

# 10. Landing Page Integration

Landing Page menampilkan informasi promo secara otomatis.

Informasi yang ditampilkan:

- Badge Promo
- Persentase Diskon
- Harga Normal (Coret)
- Harga Promo
- Tombol Booking

Promo hanya ditampilkan selama masih aktif.

---

# 11. CMS Workflow

Promotion hanya dapat dikelola oleh:

- Owner
- Marketing Manager

Administrator hanya dapat melihat informasi promo pada detail Booking.

---

# 12. Business Rules

Workflow ini mengimplementasikan:

- BR-601 (Promo bersifat opsional) [18]
- BR-602 (Promo berupa persentase) [18]
- BR-603 (Besar diskon oleh Marketing Manager) [18]
- BR-604 (Promo untuk produk/bundle) [18]

---

# 13. Future Enhancement

Fitur berikut direncanakan pada versi berikutnya.

- Promo Nominal (Rp)
- Voucher Code
- Coupon Code
- Buy One Get One
- Flash Sale
- Early Bird
- Group Discount
- Member Discount
- Promo Analytics

---

# 14. Related Documents

- 02_Business_Rules.md
- 06_Product_Workflow.md
- 07_Bundle_Workflow.md
- ../02_Product/07_Promotion.md
- ../02_Product/06_Discount.md
- ../03_UIUX/02_Landing_Page.md
- ../05_API/03_Product_API.md

---

# 15. Revision History

| Version | Date       | Description                |
| ------- | ---------- | -------------------------- |
| 1.0     | YYYY-MM-DD | Initial Promotion Workflow |

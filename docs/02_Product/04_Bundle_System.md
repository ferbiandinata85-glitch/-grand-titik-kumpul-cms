# 04. Bundle System

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan Bundle System yang digunakan pada Grand Titik Kumpul CMS.

Bundle System memungkinkan beberapa Product dan Optional Add-ons dijual sebagai satu paket penawaran dengan harga dan promosi yang lebih menarik dibandingkan pembelian secara terpisah.

Dokumen ini hanya menjelaskan konsep Bundle sebagai domain bisnis dan tidak membahas implementasi database, API, maupun antarmuka pengguna.

---

# 2. Definition

Bundle merupakan kombinasi dua atau lebih Product, atau kombinasi Product dengan Optional Add-ons, yang dijual sebagai satu paket.

Bundle bertujuan memberikan nilai tambah kepada customer sekaligus meningkatkan nilai transaksi (Average Order Value).

Bundle diperlakukan sebagai entitas tersendiri yang dapat dipublikasikan, dipromosikan, maupun dinonaktifkan tanpa memengaruhi Product penyusunnya.

---

# 3. Bundle Structure

Bundle terdiri dari beberapa komponen berikut.

```
Bundle
│
├── Identity
├── Bundle Items
├── Included Facilities
├── Optional Add-ons
├── Pricing Reference
├── Promotion Reference
└── Status
```

---

# 4. Components

## Identity

Informasi dasar Bundle.

- Bundle ID
- Bundle Name
- Bundle Slug
- Short Description
- Full Description

---

## Bundle Items

Merupakan daftar Product yang membentuk Bundle.

Contoh:

Bundle Adventure

- Rafting
- Paintball

Bundle Family

- Rafting
- Lunch

Bundle Corporate

- Rafting
- Outbound

Minimal satu Bundle harus memiliki dua Product utama.

---

## Included Facilities

Fasilitas yang otomatis diterima customer ketika membeli Bundle.

Contoh:

- Safety Equipment
- Professional Guide
- Welcome Drink
- Lunch
- Insurance

Included Facilities mengikuti kombinasi Product yang ada di dalam Bundle.

Marketing Manager dapat menambahkan fasilitas khusus apabila diperlukan.

---

## Optional Add-ons

Bundle dapat memiliki layanan tambahan yang dapat dipilih customer.

Contoh:

- Dokumentasi Foto
- Dokumentasi Video
- Drone Documentation
- Transportasi
- Coffee Break
- Merchandise

Optional Add-ons bersifat opsional dan memiliki harga tersendiri.

Harga Add-on tidak termasuk dalam harga dasar Bundle.

---

## Pricing Reference

Bundle memiliki satu struktur harga.

Pengelolaan harga dijelaskan pada:

- 05_Pricing.md

---

## Promotion Reference

Bundle dapat mengikuti Promotion.

Promotion dikelola pada:

- 07_Promotion.md

---

## Status

Bundle memiliki status berikut.

- Draft
- Active
- Archived

Hanya Bundle dengan status Active yang dapat ditampilkan kepada customer.

---

# 5. Relationships

Bundle memiliki hubungan dengan beberapa domain.

| Domain           | Relationship                                      |
| ---------------- | ------------------------------------------------- |
| Product          | Bundle terdiri dari satu atau lebih Product       |
| Product Category | Bundle dapat berisi Product dari kategori berbeda |
| Optional Add-on  | Bundle dapat memiliki layanan tambahan            |
| Pricing          | Bundle memiliki struktur harga                    |
| Discount         | Bundle dapat menerima Discount                    |
| Promotion        | Bundle dapat mengikuti Promotion                  |
| Booking          | Bundle dapat dipilih saat Booking                 |

---

# 6. Management

Bundle dikelola melalui CMS.

Hak akses:

| Role              | Permission             |
| ----------------- | ---------------------- |
| Owner             | Full Access            |
| Marketing Manager | Full Bundle Management |
| Administrator     | Read Only              |

Aktivitas yang tersedia:

- Create Bundle
- Update Bundle
- Publish Bundle
- Archive Bundle
- Add Product
- Remove Product
- Manage Included Facilities
- Manage Optional Add-ons

Perubahan Bundle tidak memengaruhi histori Booking yang telah selesai.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-105 : Bundle Management
- BR-106 : Bundle Status
- BR-107 : Bundle Composition

---

# 8. Related Documents

### Business

- ../01_Business/07_Bundle_Workflow.md

### Product

- 01_Product_Catalog.md
- 02_Product_Category.md
- 03_Product_Package.md
- 05_Pricing.md
- 06_Discount.md
- 07_Promotion.md

### UI/UX

- ../03_UIUX/02_Landing_Page.md
- ../03_UIUX/04_Product_Detail.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/03_Product_API.md

---

# 9. Revision History

| Version | Date       | Description           |
| ------- | ---------- | --------------------- |
| 1.0     | YYYY-MM-DD | Initial Bundle System |

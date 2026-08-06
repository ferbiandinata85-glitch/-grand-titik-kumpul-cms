# 09. Product Media

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Product Media yang digunakan pada Grand Titik Kumpul CMS.

Product Media merupakan seluruh aset digital yang digunakan untuk mendukung promosi, informasi, dan identitas visual Product.

Dokumen ini hanya menjelaskan domain Product Media dan tidak membahas implementasi penyimpanan file, database, API, maupun antarmuka pengguna.

---

# 2. Definition

Product Media adalah kumpulan aset digital yang terhubung dengan Product.

Media digunakan pada berbagai bagian sistem, seperti:

- Landing Page
- Product Detail
- Booking
- Gallery
- Promotion
- CMS

Setiap Product dapat memiliki lebih dari satu Media.

---

# 3. Media Structure

```
Product Media
│
├── Identity
├── Media Type
├── Media Information
├── Display Settings
├── SEO Metadata
└── Status
```

---

# 4. Components

## Identity

Informasi dasar media.

- Media ID
- Product Reference
- Media Name
- Description

---

## Media Type

V1 mendukung beberapa jenis media.

- Cover Image
- Gallery Image
- Thumbnail
- Banner
- Video (URL)
- Document (Opsional)

Setiap media memiliki fungsi yang berbeda.

---

## Media Information

Informasi file media.

Parameter yang disimpan.

- File Name
- File Type
- File Size
- Resolution
- Storage Location

Pada V1 media disimpan menggunakan Supabase Storage.

---

## Display Settings

Mengatur bagaimana media ditampilkan.

Parameter.

- Cover Image
- Display Order
- Featured
- Alt Text

Hanya satu Cover Image yang dapat digunakan untuk setiap Product.

Gallery dapat memiliki banyak gambar.

---

## SEO Metadata

Media mendukung optimasi SEO.

Parameter.

- Alt Text
- Image Title
- Caption

Metadata digunakan untuk meningkatkan aksesibilitas dan optimasi mesin pencari.

---

## Status

Media memiliki status.

- Draft
- Active
- Archived

Hanya Media dengan status Active yang ditampilkan pada website.

---

# 5. Relationships

Product Media memiliki hubungan dengan beberapa domain.

| Domain           | Relationship                                     |
| ---------------- | ------------------------------------------------ |
| Product Package  | Setiap Media dimiliki oleh satu Product          |
| Product Category | Media dapat digunakan sebagai Category Banner    |
| Landing Page     | Menampilkan Cover Image dan Banner               |
| Product Detail   | Menampilkan Gallery Product                      |
| Promotion        | Banner Promotion dapat menggunakan Product Media |
| Booking          | Thumbnail Product ditampilkan pada Booking       |
| CMS              | Digunakan untuk pengelolaan Media                |

---

# 6. Management

Product Media dikelola melalui CMS.

Hak akses.

| Role              | Permission            |
| ----------------- | --------------------- |
| Owner             | Full Access           |
| Marketing Manager | Full Media Management |
| Administrator     | Read Only             |

Aktivitas yang tersedia.

- Upload Media
- Update Media
- Change Cover Image
- Reorder Gallery
- Archive Media
- Restore Media

Media yang pernah digunakan pada histori transaksi tidak dihapus dari sistem.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-124 : Product Media Management
- BR-125 : Cover Image
- BR-126 : Gallery Image
- BR-127 : Media Status

---

# 8. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md

### Product

- 01_Product_Catalog.md
- 03_Product_Package.md
- 08_Product_Status.md

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
| 1.0     | YYYY-MM-DD | Initial Product Media |

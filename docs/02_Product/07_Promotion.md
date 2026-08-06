# 07. Promotion

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Promotion yang digunakan pada Grand Titik Kumpul CMS.

Promotion merupakan program pemasaran yang digunakan untuk meningkatkan penjualan melalui penerapan Discount pada Product, Bundle, maupun transaksi tertentu.

Promotion hanya mengatur strategi pemasaran dan tidak menyimpan perhitungan harga secara langsung.

Dokumen ini tidak membahas implementasi database, API, maupun antarmuka pengguna.

---

# 2. Definition

Promotion adalah program pemasaran yang memiliki periode tertentu dan menggunakan satu atau lebih Discount sebagai mekanisme penyesuaian harga.

Promotion dapat diterapkan pada Product, Bundle, maupun kategori tertentu sesuai kebutuhan bisnis.

Promotion tidak mengubah Base Price Product.

Promotion hanya mengaktifkan Discount selama periode yang telah ditentukan.

---

# 3. Promotion Structure

```
Promotion
│
├── Identity
├── Campaign
├── Target
├── Discount Reference
├── Schedule
├── Priority
└── Status
```

---

# 4. Components

## Identity

Informasi dasar Promotion.

- Promotion ID
- Promotion Name
- Promotion Code (Optional)
- Description

---

## Campaign

Informasi kampanye pemasaran.

Contoh:

- Promo Liburan Sekolah
- Promo Akhir Tahun
- Promo Corporate
- Promo Gathering
- Promo Soft Opening

Campaign digunakan sebagai identitas bisnis dan materi promosi.

---

## Target

Promotion dapat diterapkan pada.

- Product
- Bundle
- Product Category

Satu Promotion dapat memiliki lebih dari satu target.

---

## Discount Reference

Promotion menggunakan satu atau lebih Discount yang telah dibuat sebelumnya.

Promotion tidak menyimpan nilai Discount secara langsung.

Seluruh aturan potongan harga mengacu pada:

- 06_Discount.md

---

## Schedule

Promotion memiliki periode aktif.

- Start Date
- End Date

Promotion hanya berlaku selama periode tersebut.

---

## Priority

Apabila beberapa Promotion aktif pada waktu yang sama, sistem menggunakan Priority untuk menentukan Promotion yang diterapkan.

Semakin tinggi Priority, semakin didahulukan.

Contoh:

| Promotion     | Priority |
| ------------- | -------: |
| Promo Liburan |      100 |
| Promo Weekend |       80 |
| Promo Member  |       50 |

---

## Status

Promotion memiliki status.

- Draft
- Scheduled
- Active
- Expired
- Archived

Hanya Promotion dengan status Active yang dapat digunakan.

---

# 5. Relationships

Promotion memiliki hubungan dengan beberapa domain.

| Domain           | Relationship                                       |
| ---------------- | -------------------------------------------------- |
| Product          | Promotion dapat diterapkan pada Product            |
| Product Category | Promotion dapat diterapkan pada Category           |
| Bundle           | Promotion dapat diterapkan pada Bundle             |
| Discount         | Promotion menggunakan satu atau lebih Discount     |
| Pricing          | Promotion memengaruhi harga akhir melalui Discount |
| Booking          | Promotion dapat diterapkan pada transaksi Booking  |

---

# 6. Management

Promotion dikelola melalui CMS.

Hak akses.

| Role              | Permission                |
| ----------------- | ------------------------- |
| Owner             | Full Access               |
| Marketing Manager | Full Promotion Management |
| Administrator     | Read Only                 |

Aktivitas yang tersedia.

- Create Promotion
- Update Promotion
- Activate Promotion
- Schedule Promotion
- Archive Promotion
- Assign Discount
- Assign Product
- Assign Bundle
- Assign Category
- Set Priority

Promotion yang pernah digunakan pada transaksi tidak dapat dihapus, tetapi dapat diarsipkan.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-118 : Promotion Management
- BR-119 : Promotion Schedule
- BR-120 : Promotion Priority
- BR-121 : Promotion Target

---

# 8. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md
- ../01_Business/04_Booking_Flow.md

### Product

- 01_Product_Catalog.md
- 02_Product_Category.md
- 03_Product_Package.md
- 04_Bundle_System.md
- 05_Pricing.md
- 06_Discount.md

### UI/UX

- ../03_UIUX/02_Landing_Page.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/03_Product_API.md

---

# 9. Revision History

| Version | Date       | Description       |
| ------- | ---------- | ----------------- |
| 1.0     | YYYY-MM-DD | Initial Promotion |

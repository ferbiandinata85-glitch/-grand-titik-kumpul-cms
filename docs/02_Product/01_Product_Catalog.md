# 01. Product Catalog

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan struktur Product Catalog pada Grand Titik Kumpul CMS.

Product Catalog merupakan pusat informasi seluruh produk yang ditawarkan kepada customer melalui Landing Page maupun proses Booking.

Dokumen ini menjadi acuan bagi Product Management, UI/UX, Database, dan API.

---

# 2. Product Overview

Pada versi V1, Product Catalog terdiri dari beberapa jenis produk wisata.

Contoh Product:

- Rafting
- Paintball
- Outbound
- Offroad

Setiap Product dapat dijual secara terpisah maupun digabungkan menjadi Bundle.

---

# 3. Product Hierarchy

```
Product Catalog
│
├── Rafting
│
├── Paintball
│
├── Outbound
│
└── Offroad
```

---

# 4. Product Structure

Setiap Product memiliki struktur dasar yang sama.

## Basic Information

- Product Name
- Slug
- Category
- Short Description
- Full Description

---

## Media

- Cover Image
- Gallery Images

---

## Pricing

- Price per Person
- Currency

---

## Booking

- Minimum Participant
- Available Slot

---

## Status

- Draft
- Active
- Archived

---

# 5. Product Display

Landing Page menampilkan Product dalam bentuk Card.

Setiap Card berisi:

- Cover Image
- Product Name
- Starting Price
- Short Description
- Button Booking

Product dengan status Draft dan Archived tidak ditampilkan.

---

# 6. Product Management

Product hanya dapat dikelola oleh:

- Owner
- Marketing Manager

Aktivitas yang dapat dilakukan.

- Create Product
- Edit Product
- Archive Product
- Publish Product

---

# 7. Product Relationship

Setiap Product dapat memiliki hubungan dengan.

- Bundle
- Promotion
- Discount
- Booking
- Gallery

Hubungan tersebut akan dijelaskan pada dokumen masing-masing.

---

# 8. Business Rules

Mengacu pada.

- BR-101
- BR-102
- BR-103

---

# 9. Related Documents

- ../01_Business/06_Product_Workflow.md
- 02_Product_Category.md
- 03_Product_Package.md
- 05_Pricing.md
- 07_Promotion.md

---

# 10. Revision History

| Version | Date       | Description             |
| ------- | ---------- | ----------------------- |
| 1.0     | YYYY-MM-DD | Initial Product Catalog |

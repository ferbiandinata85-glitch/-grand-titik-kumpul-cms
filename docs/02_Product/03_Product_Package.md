# 03. Product Package

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Product Package pada Grand Titik Kumpul CMS.

Product Package merupakan representasi dari layanan atau aktivitas wisata yang ditawarkan kepada customer. Setiap Package memiliki identitas, informasi kegiatan, fasilitas, persyaratan, media promosi, dan aturan dasar yang digunakan dalam proses pemasaran dan booking.

Dokumen ini hanya menjelaskan struktur Package sebagai domain bisnis dan tidak membahas implementasi database, API, maupun antarmuka pengguna.

---

# 2. Definition

Product Package adalah unit layanan yang dapat dipilih dan dipesan oleh customer.

Satu Product Package merepresentasikan satu jenis aktivitas wisata, seperti Rafting, Paintball, Outbound, atau Offroad.

Setiap Package dapat dijual secara individual maupun menjadi bagian dari Bundle.

---

# 3. Package Structure

Setiap Product Package terdiri dari beberapa kelompok informasi.

```
Product Package
│
├── Identity
├── Information
├── Facilities
├── Participant Rules
├── Schedule
├── Location
├── Media
├── Pricing Reference
└── Status
```

---

# 4. Components

## Identity

Informasi identitas Package.

- Product ID
- Product Name
- Product Category
- Product Slug

---

## Information

Informasi umum mengenai paket.

- Short Description
- Full Description
- Activity Overview
- Highlight

---

## Facilities

Fasilitas yang termasuk dalam Package.

Contoh:

- Safety Equipment
- Professional Guide
- Rescue Team
- Welcome Drink
- Lunch
- Documentation (Optional)
- Insurance (Optional)

Daftar fasilitas dapat disesuaikan oleh Marketing Manager.

---

## Participant Rules

Aturan peserta yang berlaku pada Package.

Contoh:

- Minimum Participant
- Maximum Participant (Optional)
- Recommended Age
- Physical Requirement (Optional)

Nilai Minimum Participant dapat dikonfigurasi melalui CMS.

---

## Schedule

Informasi pelaksanaan kegiatan.

- Available Booking
- Available Time Slot
- Estimated Duration

Penjadwalan detail mengacu pada Calendar Management.

---

## Location

Informasi lokasi kegiatan.

- Meeting Point
- Destination
- Google Maps Reference

---

## Media

Media promosi Package.

- Cover Image
- Gallery Images
- Promotional Banner (Optional)

---

## Pricing Reference

Package memiliki referensi ke modul Pricing.

Informasi harga tidak disimpan pada dokumen ini.

Seluruh pengelolaan harga dijelaskan pada:

- 05_Pricing.md

---

## Status

Package memiliki status berikut.

- Draft
- Active
- Archived

Status menentukan apakah Package dapat ditampilkan kepada customer.

---

# 5. Relationships

Product Package memiliki hubungan dengan beberapa domain lain.

| Domain           | Relationship                             |
| ---------------- | ---------------------------------------- |
| Product Category | Setiap Package berada pada satu Category |
| Pricing          | Package memiliki satu struktur harga     |
| Discount         | Package dapat menerima Discount          |
| Promotion        | Package dapat mengikuti Promotion        |
| Bundle           | Package dapat menjadi anggota Bundle     |
| Booking          | Package dapat dipilih dalam Booking      |
| Gallery          | Package memiliki media promosi           |

---

# 6. Management

Product Package dikelola melalui CMS.

Hak akses:

| Role              | Permission              |
| ----------------- | ----------------------- |
| Owner             | Full Access             |
| Marketing Manager | Full Product Management |
| Administrator     | Read Only               |

Aktivitas yang tersedia:

- Create Package
- Update Package
- Publish Package
- Archive Package
- Manage Facilities
- Manage Gallery

Perubahan informasi Package tidak memengaruhi histori Booking yang telah selesai.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-101 : Product Management
- BR-102 : Product Category
- BR-103 : Product Status
- BR-104 : Product Package

---

# 8. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md

### Product

- 01_Product_Catalog.md
- 02_Product_Category.md
- 04_Bundle_System.md
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

| Version | Date       | Description             |
| ------- | ---------- | ----------------------- |
| 1.0     | YYYY-MM-DD | Initial Product Package |

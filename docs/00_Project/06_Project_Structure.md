# 06. Project Structure

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan struktur repository Grand Titik Kumpul CMS beserta fungsi setiap folder dan file.

Tujuannya agar seluruh developer memiliki standar yang sama dalam menyusun source code maupun dokumentasi.

Dokumen ini merupakan panduan utama sebelum memulai proses development.

---

# 2. Repository Structure

```
grand-titik-kumpul-cms/
│
├── docs/
├── public/
├── src/
├── prisma/
├── .env
├── package.json
├── README.md
└── ...
```

---

# 3. Documentation Structure

Seluruh analisis bisnis dan dokumentasi proyek berada pada folder **docs**.

```
docs/
│
├── 00_Project/
├── 01_Business/
├── 02_Product/
├── 03_UIUX/
├── 04_Data/
├── 05_API/
└── 99_Roadmap/
```

---

# 4. Documentation Overview

## 00_Project

Berisi pondasi proyek.

Contoh isi:

- Vision
- Scope
- Glossary
- Tech Stack
- Project Structure

---

## 01_Business

Berisi seluruh proses bisnis.

Contoh:

- Business Rules
- Customer Journey
- Booking Flow
- Payment Flow
- User Roles

---

## 02_Product

Berisi seluruh informasi produk.

Contoh:

- Product Catalog
- Bundle
- Pricing
- Promotion

---

## 03_UIUX

Berisi desain aplikasi.

Contoh:

- Landing Page
- Dashboard
- CMS
- Booking Page

---

## 04_Data

Berisi rancangan data.

Contoh:

- Business Object Model
- ERD
- Database
- Status

---

## 05_API

Berisi dokumentasi endpoint API.

Contoh:

- Authentication
- Product API
- Booking API
- Payment API
- Dashboard API

---

## 99_Roadmap

Berisi rencana pengembangan.

Contoh:

- V1
- V1.1
- V2

---

# 5. Source Code Structure

Seluruh source code aplikasi berada di dalam folder **src**.

Rencana struktur:

```
src/
│
├── app/
├── components/
├── features/
├── lib/
├── services/
├── hooks/
├── types/
├── utils/
├── styles/
└── middleware.ts
```

---

# 6. Folder Description

## app/

Berisi seluruh routing Next.js App Router.

---

## components/

Komponen UI yang dapat digunakan kembali.

Contoh:

- Button
- Card
- Modal
- Navbar
- Footer

---

## features/

Berisi fitur utama aplikasi.

Contoh:

- Booking
- Product
- Payment
- Dashboard
- CMS

---

## lib/

Konfigurasi aplikasi.

Contoh:

- Supabase Client
- Prisma Client
- Auth Helper

---

## services/

Seluruh komunikasi dengan backend.

Contoh:

- Booking Service
- Product Service
- Payment Service

---

## hooks/

Custom React Hooks.

---

## types/

Seluruh TypeScript Interface.

---

## utils/

Utility Function.

Contoh:

- Currency Formatter
- Date Formatter
- Slug Generator

---

## styles/

Konfigurasi styling global.

---

# 7. Static Assets

Folder **public/** digunakan untuk menyimpan file statis.

Contoh:

```
public/
│
├── images/
├── icons/
├── logo/
├── banner/
└── favicon.ico
```

---

# 8. Database

Folder prisma digunakan untuk database.

```
prisma/
│
├── schema.prisma
├── migrations/
└── seed.ts
```

---

# 9. Naming Convention

Folder

- lowercase
- kebab-case

Contoh

```
product-detail
booking-history
```

---

File

Gunakan PascalCase untuk Component.

```
BookingCard.tsx
ProductCard.tsx
Navbar.tsx
```

Gunakan camelCase untuk helper.

```
formatCurrency.ts
generateInvoice.ts
```

---

# 10. Documentation Rules

Setiap perubahan pada:

- Business Rules
- Product
- Database
- API
- UI

wajib diperbarui pada folder **docs** terlebih dahulu sebelum implementasi dilakukan.

Dokumentasi merupakan sumber referensi utama (Single Source of Truth) bagi seluruh tim pengembang.

---

# 11. Development Flow

Urutan pengembangan proyek:

```
Project
    │
    ▼
Business
    │
    ▼
Product
    │
    ▼
UI/UX
    │
    ▼
Data Model
    │
    ▼
API
    │
    ▼
Development
    │
    ▼
Testing
    │
    ▼
Deployment
```

Setiap tahap harus selesai dan terdokumentasi sebelum melanjutkan ke tahap berikutnya.

---

# 12. Revision History

| Version | Date       | Description               |
| ------- | ---------- | ------------------------- |
| 1.0     | YYYY-MM-DD | Initial Project Structure |

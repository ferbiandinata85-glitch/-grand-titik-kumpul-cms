# Repository Structure

> Project : Grand Titik Kumpul CMS
>
> Document ID : REPO-001
>
> Status : Locked
>
> Version : 1.0
>
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan struktur repository dokumentasi Grand Titik Kumpul CMS.

Repository disusun menggunakan pendekatan Domain Driven Documentation sehingga setiap folder memiliki tanggung jawab yang spesifik.

Dokumen ini menjadi panduan utama untuk memahami lokasi setiap dokumentasi serta hubungan antar domain.

---

# 2. Repository Principles

Repository mengikuti prinsip berikut.

- Documentation First Development
- Single Source of Truth (SSoT)
- Domain Driven Documentation
- Domain Driven Design (DDD)
- Clean Architecture
- Separation of Concerns

Seluruh perubahan dokumentasi harus mengikuti struktur repository ini.

---

# 3. Repository Tree

```text
docs/
│
├── README.md
├── ARCHITECTURE_OVERVIEW.md
├── REPOSITORY_STRUCTURE.md
│
├── 00_Project
│   ├── 01_Project_Overview.md
│   ├── 02_Project_Vision.md
│   ├── 03_Project_Scope.md
│   ├── 04_Glossary.md
│   ├── 05_Tech_Stack.md
│   ├── 06_Project_Structure.md
│   └── 07_Documentation_Guideline.md
│
├── 01_Business
│   ├── 01_Business_Overview.md
│   ├── 02_Business_Rules.md
│   ├── 03_Customer_Journey.md
│   ├── 04_Booking_Flow.md
│   ├── 05_Payment_Flow.md
│   ├── 06_Product_Workflow.md
│   ├── 07_Bundle_Workflow.md
│   ├── 08_Booking_Slot.md
│   ├── 09_Promotion_Workflow.md
│   ├── 10_Invoice_Workflow.md
│   ├── 11_Document_Workflow.md
│   └── 12_User_Roles.md
│
├── 02_Product
│   ├── 01_Product_Catalog.md
│   ├── 02_Product_Category.md
│   ├── 03_Product_Package.md
│   ├── 04_Bundle_System.md
│   ├── 05_Pricing.md
│   ├── 06_Discount.md
│   ├── 07_Promotion.md
│   ├── 08_Product_Status.md
│   └── 09_Product_Media.md
│
├── 03_UIUX
│   ├── 01_Design_System.md
│   ├── 02_Landing_Page.md
│   ├── 03_Booking_Page.md
│   ├── 04_Product_Detail.md
│   ├── 05_CMS.md
│   └── 06_Dashboard.md
│
├── 04_Data
│   ├── 01_Business_Object_Model.md
│   ├── 02_ERD.md
│   ├── 03_Database_Schema.md
│   └── 04_Status_Reference.md
│
├── 05_API
│   ├── 01_API_Blueprint.md
│   ├── 02_Authentication.md
│   ├── 03_Product_API.md
│   ├── 04_Booking_API.md
│   ├── 05_Payment_API.md
│   └── 06_Dashboard_API.md
│
└── 99_Roadmap
    ├── V1.md
    ├── V1.1.md
    └── V2.md
```

---

# 4. Domain Responsibilities

| Folder      | Responsibility                                              |
| ----------- | ----------------------------------------------------------- |
| docs/       | Dokumen tingkat repository dan arsitektur                   |
| 00_Project  | Pondasi proyek, standar, glossary, dan dokumentasi proyek   |
| 01_Business | Business process, workflow, business rules, dan operasional |
| 02_Product  | Definisi produk, katalog, pricing, bundle, promotion        |
| 03_UIUX     | User Interface, User Experience, dan desain interaksi       |
| 04_Data     | Business Object Model, ERD, Database Schema                 |
| 05_API      | API Contract dan spesifikasi integrasi                      |
| 99_Roadmap  | Perencanaan pengembangan versi berikutnya                   |

---

# 5. Repository Dependency

Setiap domain memiliki dependency satu arah.

```text
00_Project
      │
      ▼
01_Business
      │
      ▼
02_Product
      │
      ▼
03_UIUX
      │
      ▼
04_Data
      │
      ▼
05_API
      │
      ▼
Application Development
```

Aturan dependency:

- Project menjadi dasar seluruh dokumentasi.
- Business menjadi dasar Product.
- Business dan Product menjadi dasar UI/UX.
- UI/UX menjadi dasar Data.
- Data menjadi dasar API.
- API menjadi dasar implementasi aplikasi.

Dependency terbalik tidak diperbolehkan.

---

# 6. Document Navigation

## Root

| File                     | Description                                    |
| ------------------------ | ---------------------------------------------- |
| README.md                | Pintu masuk repository dan petunjuk penggunaan |
| ARCHITECTURE_OVERVIEW.md | Gambaran arsitektur sistem secara menyeluruh   |
| REPOSITORY_STRUCTURE.md  | Struktur repository dan navigasi dokumentasi   |

## 00_Project

Menjelaskan tujuan proyek, visi, ruang lingkup, standar dokumentasi, serta teknologi yang digunakan.

## 01_Business

Menjelaskan proses bisnis, workflow, business rules, dan operasional sistem.

## 02_Product

Menjelaskan seluruh domain produk beserta aturan komersialnya.

## 03_UIUX

Menjelaskan desain antarmuka, alur pengguna, dan dashboard.

## 04_Data

Mengubah Business dan Product menjadi model data yang siap diimplementasikan.

## 05_API

Menjelaskan kontrak API berdasarkan Business, Product, dan Data.

## 99_Roadmap

Menjelaskan rencana evolusi sistem pada versi berikutnya.

---

# 7. Document Lifecycle

Seluruh dokumentasi dikembangkan mengikuti urutan berikut.

1. Project
2. Business
3. Product
4. UI/UX
5. Business Object Model
6. ERD
7. Database Schema
8. API Specification
9. Application Development

Implementasi aplikasi tidak boleh mendahului dokumentasi.

---

# 8. Naming Convention

Seluruh dokumen menggunakan format:

```text
[Nomor]_[Nama_Dokumen].md
```

Contoh:

```text
01_Project_Overview.md
04_Booking_Flow.md
05_Pricing.md
03_Product_API.md
```

Penomoran digunakan untuk menunjukkan urutan pembacaan dalam setiap domain.

---

# 9. Repository Governance

Seluruh perubahan repository harus memenuhi ketentuan berikut.

- Tidak mengubah struktur domain tanpa alasan arsitektural.
- Tidak menduplikasi informasi antar dokumen.
- Setiap dokumen wajib memiliki Related Documents.
- Setiap perubahan wajib dicatat pada Revision History.
- Business Rules hanya didefinisikan pada domain Business.
- Entity hanya didefinisikan pada domain Data.
- API hanya mendefinisikan kontrak integrasi.

---

# 10. Related Documents

## Root

- README.md
- ARCHITECTURE_OVERVIEW.md

## Project

- 00_Project/06_Project_Structure.md
- 00_Project/07_Documentation_Guideline.md

---

# 11. Revision History

| Version | Date       | Description                  | Author           |
| ------- | ---------- | ---------------------------- | ---------------- |
| 1.0     | YYYY-MM-DD | Initial Repository Structure | System Architect |

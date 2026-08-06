# Architecture Overview

> Project : Grand Titik Kumpul CMS
>
> Document ID : ARCH-001
>
> Status : Locked
>
> Version : 1.0
>
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan arsitektur dokumentasi dan arsitektur sistem Grand Titik Kumpul CMS secara menyeluruh.

Dokumen ini menjadi referensi utama untuk memahami hubungan antar domain dokumentasi, alur pengembangan sistem, serta dependency antar layer.

Dokumen ini tidak menjelaskan implementasi teknis, melainkan menjadi panduan arsitektur yang harus diikuti selama proses analisis, desain, implementasi, dan pengembangan sistem.

---

# 2. Architecture Principles

Grand Titik Kumpul CMS dibangun berdasarkan prinsip berikut.

- Documentation First Development
- Single Source of Truth (SSoT)
- Domain Driven Design (DDD)
- Domain Driven Documentation
- Clean Architecture
- Separation of Concerns
- Modular Design
- Scalable Architecture

Seluruh keputusan desain harus mengacu pada prinsip di atas.

---

# 3. Architecture Vision

Repository dokumentasi merupakan fondasi utama pengembangan sistem.

Seluruh implementasi aplikasi harus berasal dari dokumentasi, bukan sebaliknya.

Dokumentasi menjadi sumber kebenaran utama yang digunakan oleh seluruh tim pengembang.

Perubahan Business Rules wajib dilakukan pada dokumentasi terlebih dahulu sebelum diimplementasikan ke dalam kode.

---

# 4. Architecture Layers

Arsitektur proyek dibangun menggunakan dependency satu arah.

```
Business Requirement
        │
        ▼
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

Setiap layer hanya bergantung pada layer di atasnya.

Layer tidak boleh membuat aturan baru untuk layer sebelumnya.

---

# 5. Layer Responsibilities

## 00_Project

Project Foundation.

Berisi standar proyek.

Contoh:

- Vision
- Scope
- Glossary
- Tech Stack
- Documentation Guideline
- Repository Structure

Tidak membahas proses bisnis.

---

## 01_Business

Business Layer.

Menjelaskan bagaimana bisnis bekerja.

Berisi:

- Business Rules
- Customer Journey
- Booking
- Payment
- Product Workflow
- Bundle Workflow
- Booking Slot
- Promotion
- Invoice
- Document Workflow
- User Roles

Tidak membahas database maupun API.

---

## 02_Product

Product Layer.

Menjelaskan seluruh objek bisnis yang dijual.

Berisi:

- Product Catalog
- Category
- Package
- Bundle
- Pricing
- Discount
- Promotion
- Product Status
- Product Media

Tidak membahas struktur tabel database.

---

## 03_UIUX

Presentation Layer.

Menjelaskan bagaimana pengguna berinteraksi dengan sistem.

Berisi:

- Design System
- Landing Page
- Booking Page
- Product Detail
- CMS
- Dashboard

Seluruh UI wajib mengacu pada Business dan Product.

UI tidak boleh membuat Business Rules baru.

---

## 04_Data

Domain Model Layer.

Mengubah Business dan Product menjadi model data.

Berisi:

- Business Object Model
- Entity
- Relationship
- ERD
- Database Schema
- Master Data
- Transaction Data
- Reference Data

Tidak membuat aturan bisnis baru.

---

## 05_API

Integration Layer.

Mendefinisikan kontrak API berdasarkan Business, Product, dan Data.

API hanya mengekspos entity yang telah didefinisikan pada layer Data.

API tidak boleh membuat entity baru.

---

## 99_Roadmap

Planning Layer.

Berisi rencana evolusi sistem.

Contoh:

- V1
- V1.1
- V2

Roadmap tidak mengubah Business Rules yang telah dikunci.

---

# 6. Dependency Rules

Repository menggunakan dependency satu arah.

```
Project
    ↓
Business
    ↓
Product
    ↓
UI/UX
    ↓
Data
    ↓
API
    ↓
Development
```

Aturan dependency:

- Business menjadi dasar Product.
- Business dan Product menjadi dasar UI.
- UI menjadi dasar Data.
- Data menjadi dasar API.
- API menjadi dasar implementasi aplikasi.

Dependency terbalik tidak diperbolehkan.

Contoh yang tidak diperbolehkan:

- Database menentukan Business Rules.
- API menentukan Workflow.
- UI menentukan Entity.
- ERD menentukan Customer Journey.

---

# 7. Documentation Flow

Setiap perubahan sistem mengikuti urutan berikut.

1. Analisis kebutuhan bisnis.
2. Pembaruan dokumentasi Project.
3. Pembaruan Business.
4. Pembaruan Product.
5. Desain UI/UX.
6. Penyusunan Business Object Model.
7. Penyusunan ERD.
8. Penyusunan Database Schema.
9. Penyusunan API Contract.
10. Implementasi aplikasi.

Perubahan pada tahap implementasi tidak boleh mendahului perubahan dokumentasi.

---

# 8. Expected Deliverables

Repository harus mampu menghasilkan artefak berikut tanpa mendefinisikan ulang aturan bisnis.

- Business Object Model
- Entity Relationship Diagram (ERD)
- Database Schema
- REST API Specification
- Authentication & Authorization Design
- Landing Page
- Booking Engine
- CMS Dashboard
- Backend Architecture
- Frontend Architecture

---

# 9. Architecture Governance

Seluruh perubahan arsitektur harus mengikuti ketentuan berikut.

- Tidak mengubah dependency antar layer.
- Tidak menduplikasi Business Rules.
- Tidak memindahkan tanggung jawab antar domain tanpa alasan yang jelas.
- Seluruh dokumen wajib memiliki referensi (Related Documents).
- Seluruh perubahan harus terdokumentasi melalui Revision History.

Keputusan arsitektur yang bersifat fundamental harus disepakati sebelum implementasi dimulai.

---

# 10. Related Documents

## Root

- README.md
- REPOSITORY_STRUCTURE.md

## Project

- 00_Project/06_Project_Structure.md
- 00_Project/07_Documentation_Guideline.md

## Business

- 01_Business/01_Business_Overview.md

## Product

- 02_Product/01_Product_Catalog.md

---

# 11. Revision History

| Version | Date       | Description                   | Author           |
| ------- | ---------- | ----------------------------- | ---------------- |
| 1.0     | YYYY-MM-DD | Initial Architecture Overview | System Architect |

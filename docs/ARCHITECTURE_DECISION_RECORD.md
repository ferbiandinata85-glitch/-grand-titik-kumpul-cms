# Architecture Decision Record (ADR)

> Project : Grand Titik Kumpul CMS
>
> Document ID : ADR-000
>
> Status : Locked
>
> Version : 1.0
>
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mencatat seluruh keputusan arsitektur (Architecture Decisions) yang menjadi dasar pengembangan Grand Titik Kumpul CMS.

Architecture Decision Record (ADR) digunakan untuk mendokumentasikan alasan di balik keputusan desain sistem sehingga seluruh anggota tim memiliki pemahaman yang sama mengenai arah pengembangan proyek.

Dokumen ini tidak mendefinisikan Business Rules maupun implementasi teknis.

Seluruh keputusan pada dokumen ini dianggap sebagai keputusan arsitektur yang mengikat (Locked) hingga terdapat perubahan fundamental yang disetujui.

---

# 2. Scope

ADR mencakup keputusan mengenai:

- Struktur dokumentasi
- Arsitektur sistem
- Dependency antar domain
- Strategi pengembangan
- Standar dokumentasi
- Prinsip desain

ADR tidak digunakan untuk mendokumentasikan:

- Business Rules
- Product Rules
- UI Specification
- Database Schema
- API Contract

---

# 3. Decision Status

Status keputusan menggunakan kategori berikut.

| Status     | Description                                |
| ---------- | ------------------------------------------ |
| Proposed   | Sedang diusulkan                           |
| Accepted   | Disetujui                                  |
| Superseded | Digantikan keputusan baru                  |
| Deprecated | Tidak digunakan lagi                       |
| Locked     | Keputusan final dan menjadi standar proyek |

Seluruh keputusan pada versi V1 menggunakan status **Locked**.

---

# ADR-001

## Documentation First Development

### Status

Locked

### Context

Pengembangan aplikasi tanpa dokumentasi sering menyebabkan inkonsistensi antara kebutuhan bisnis, implementasi, dan perubahan sistem.

### Decision

Seluruh implementasi harus diawali dengan penyusunan dokumentasi.

Urutan pengembangan:

Business Requirement

↓

Documentation

↓

Design

↓

Development

↓

Testing

↓

Deployment

### Consequences

- Dokumentasi menjadi sumber utama pengembangan.
- Perubahan fitur wajib dimulai dari dokumentasi.
- Kode tidak boleh menjadi sumber kebenaran utama.

---

# ADR-002

## Single Source of Truth (SSoT)

### Status

Locked

### Context

Informasi yang sama sering tersebar di berbagai dokumen sehingga berpotensi menimbulkan inkonsistensi.

### Decision

Setiap informasi hanya memiliki satu lokasi utama.

Dokumen lain hanya melakukan referensi melalui bagian Related Documents.

### Consequences

- Tidak ada duplikasi Business Rules.
- Dokumentasi lebih mudah dipelihara.
- Audit lebih sederhana.

---

# ADR-003

## Domain Driven Documentation

### Status

Locked

### Context

Repository membutuhkan struktur dokumentasi yang mudah dikembangkan dan dipelihara.

### Decision

Dokumentasi dipisahkan berdasarkan domain.

- Project
- Business
- Product
- UIUX
- Data
- API
- Roadmap

### Consequences

- Setiap domain memiliki tanggung jawab yang jelas.
- Dokumentasi lebih modular.
- Skalabilitas repository meningkat.

---

# ADR-004

## One-Way Dependency

### Status

Locked

### Context

Dependency dua arah menyebabkan perubahan pada satu domain memengaruhi domain lain secara tidak terkendali.

### Decision

Repository menggunakan dependency satu arah.

Project

↓

Business

↓

Product

↓

UIUX

↓

Data

↓

API

↓

Development

### Consequences

- Tidak terjadi circular dependency.
- Setiap domain memiliki batas tanggung jawab.
- Perubahan lebih mudah dikendalikan.

---

# ADR-005

## Business Before Product

### Status

Locked

### Context

Produk merupakan representasi dari proses bisnis.

### Decision

Business harus selesai terlebih dahulu sebelum Product.

Product tidak boleh membuat aturan bisnis baru.

### Consequences

Business menjadi fondasi seluruh domain.

---

# ADR-006

## UI Before Data

### Status

Locked

### Context

Entity database harus berasal dari kebutuhan antarmuka dan proses bisnis, bukan sebaliknya.

### Decision

Seluruh desain UI diselesaikan sebelum Business Object Model dan ERD.

### Consequences

Database hanya berisi entity yang benar-benar digunakan oleh sistem.

---

# ADR-007

## Business Rules Ownership

### Status

Locked

### Context

Business Rules sering tersebar pada berbagai dokumen.

### Decision

Business Rules hanya boleh didefinisikan pada domain Business.

Domain lain hanya boleh melakukan referensi.

### Consequences

Tidak terjadi inkonsistensi aturan bisnis.

---

# ADR-008

## Data Ownership

### Status

Locked

### Context

Entity sering muncul pada Product maupun API.

### Decision

Entity resmi hanya didefinisikan pada domain Data.

Product menjelaskan konsep.

API menggunakan entity tersebut.

### Consequences

ERD menjadi sumber utama model data.

---

# ADR-009

## API Contract Ownership

### Status

Locked

### Context

API sering berkembang tanpa mengikuti model bisnis.

### Decision

API hanya boleh mengekspos entity yang telah didefinisikan pada Business, Product, UI, dan Data.

API tidak boleh membuat Business Rules baru.

### Consequences

API tetap konsisten dengan dokumentasi.

---

# ADR-010

## Repository Governance

### Status

Locked

### Context

Repository harus tetap konsisten walaupun jumlah dokumen terus bertambah.

### Decision

Seluruh dokumentasi wajib mengikuti:

- Documentation Guideline
- Repository Structure
- Architecture Overview
- Architecture Decision Record

Perubahan arsitektur hanya dapat dilakukan melalui revisi ADR.

### Consequences

Repository tetap konsisten dalam jangka panjang.

---

# 4. Related Documents

## Root

- README.md
- REPOSITORY_STRUCTURE.md
- ARCHITECTURE_OVERVIEW.md

## Project

- 00_Project/07_Documentation_Guideline.md

---

# 5. Revision History

| Version | Date       | Description                          | Author           |
| ------- | ---------- | ------------------------------------ | ---------------- |
| 1.0     | YYYY-MM-DD | Initial Architecture Decision Record | System Architect |

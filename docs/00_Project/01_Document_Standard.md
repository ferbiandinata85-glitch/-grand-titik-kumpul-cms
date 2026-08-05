# Documentation Standard

---

## Document Information

| Item        | Value                  |
| ----------- | ---------------------- |
| Project     | Grand Titik Kumpul CMS |
| Document    | Documentation Standard |
| Version     | 1.0                    |
| Status      | Locked                 |
| Last Update | YYYY-MM-DD             |

---

# 1. Purpose

Dokumen ini mendefinisikan standar penulisan seluruh dokumentasi proyek Grand Titik Kumpul CMS.

Standar ini bertujuan untuk menjaga konsistensi struktur dokumen, mempermudah proses pengembangan, meminimalkan kesalahan komunikasi, serta memastikan seluruh dokumentasi mudah dipahami oleh stakeholder, developer, maupun AI Development Assistant.

Dokumen ini berlaku untuk seluruh file yang berada di dalam folder `/docs`.

---

# 2. Documentation Principles

Seluruh dokumentasi harus mengikuti prinsip berikut.

- Single Source of Truth
- Documentation First Development
- Business First
- Modular Documentation
- Easy to Read
- Easy to Maintain
- Version Controlled
- AI Friendly

---

# 3. Writing Language

Seluruh dokumentasi menggunakan:

- Bahasa Indonesia
- Istilah teknis menggunakan Bahasa Inggris
- Penulisan formal
- Kalimat singkat dan jelas
- Tidak menggunakan bahasa percakapan

Contoh:

✔ Booking

✔ Customer

✔ Dashboard

✔ Database

✔ API

---

# 4. Folder Responsibility

Setiap folder memiliki tanggung jawab masing-masing.

| Folder      | Responsibility          |
| ----------- | ----------------------- |
| 00_Project  | Informasi dasar proyek  |
| 01_Business | Analisis proses bisnis  |
| 02_Product  | Definisi seluruh produk |
| 03_UIUX     | Desain antarmuka        |
| 04_Data     | Model data dan database |
| 05_API      | Spesifikasi API         |
| 99_Roadmap  | Pengembangan berikutnya |

Tidak diperbolehkan mencampur pembahasan antar folder.

---

# 5. File Naming Convention

Gunakan format berikut.

```
NN_Document_Name.md
```

Contoh:

```
01_Project_Vision.md

02_Project_Scope.md

03_Glossary.md
```

Aturan:

- Menggunakan nomor urut.
- Menggunakan Bahasa Inggris.
- Menggunakan Pascal Case.
- Menggunakan underscore (\_).
- Tidak menggunakan spasi.

---

# 6. Standard Document Structure

Seluruh dokumen menggunakan struktur berikut.

```text
# Document Title

## Document Information

## Purpose

## Scope

## Main Content

## Business Rules (Opsional)

## Notes

## Revision History
```

Apabila suatu bagian tidak diperlukan, bagian tersebut dapat dihilangkan.

---

# 7. Heading Standard

Gunakan heading secara berurutan.

```
#

##

###

####
```

Jangan melompati level heading.

---

# 8. Markdown Standard

Gunakan Markdown standar.

Gunakan:

- Heading
- Table
- Bullet List
- Numbered List
- Code Block

Gunakan Code Block untuk:

- Struktur Folder
- JSON
- SQL
- API
- Konfigurasi
- Workflow

---

# 9. Diagram Standard

Diagram menggunakan format berbasis teks.

Prioritas:

1. Mermaid Flowchart
2. Mermaid ER Diagram
3. Mermaid Sequence Diagram

Hindari gambar statis apabila masih dapat dijelaskan menggunakan diagram teks.

---

# 10. Status Document

Setiap dokumen memiliki status.

| Status | Description             |
| ------ | ----------------------- |
| Draft  | Sedang dibuat           |
| Review | Sedang direview         |
| Locked | Final dan menjadi acuan |

Dokumen dengan status **Locked** hanya dapat diubah melalui proses revisi.

---

# 11. Revision Rules

Setiap perubahan wajib:

- Direview terlebih dahulu.
- Disetujui.
- Dicatat pada Revision History.

---

# 12. Documentation Workflow

Urutan penyusunan dokumentasi.

```
Brainstorm

↓

Analysis

↓

Draft

↓

Review

↓

Revision

↓

Locked

↓

Implementation
```

Implementasi sistem dilakukan setelah dokumen terkait berstatus **Locked**.

---

# 13. Coding Philosophy

Repository ini menggunakan pendekatan:

```
Documentation First Development
```

Urutan pekerjaan:

```
Business

↓

Documentation

↓

Database

↓

API

↓

Backend

↓

Frontend

↓

Testing

↓

Deployment
```

---

# 14. Source of Truth

Semua keputusan resmi proyek harus tercatat pada dokumentasi.

Percakapan, chat, atau catatan yang belum masuk ke folder `/docs` dianggap belum menjadi keputusan resmi proyek.

---

# 15. AI Collaboration

Dokumentasi ini dirancang agar dapat digunakan oleh AI Development Assistant seperti ChatGPT, Gemini, Claude, Cursor AI, maupun GitHub Copilot.

Setiap dokumen harus:

- Memiliki ruang lingkup yang jelas.
- Tidak membahas lebih dari satu topik utama.
- Tidak mengandung informasi yang saling bertentangan.
- Mudah dipahami tanpa harus membaca keseluruhan repository.

---

# 16. Revision History

| Version | Date       | Description                    |
| ------- | ---------- | ------------------------------ |
| 1.0     | YYYY-MM-DD | Initial Documentation Standard |

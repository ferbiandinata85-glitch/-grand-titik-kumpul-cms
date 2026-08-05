Document Information
Item
Description
Project
Grand Titik Kumpul CMS
Document ID
DOC-GUIDE-001
Status
Active
Version
1.0
Last Update
2026-08-06

1. Purpose
   Dokumen ini menetapkan standar penulisan dan struktur untuk seluruh repository dokumentasi proyek Grand Titik Kumpul CMS. Tujuannya adalah untuk memastikan konsistensi, mencegah duplikasi informasi, dan menjaga agar dokumentasi tetap menjadi Single Source of Truth (SSoT) selama siklus pengembangan
   .
2. General Writing Rules
   Bahasa: Gunakan bahasa Indonesia yang profesional dan formal
   .
   Format File: Seluruh dokumen wajib menggunakan format Markdown (.md)
   .
   Fokus Konten: Dokumentasi harus fokus pada arsitektur enterprise, alur kerja bisnis, dan spesifikasi sistem. Jangan memasukkan implementasi coding langsung ke dalam dokumen ini
   .
   Prinsip No-Duplication: Jika sebuah informasi sudah dijelaskan di satu dokumen, dokumen lain cukup merujuknya melalui bagian Related Documents
   .
3. File Naming & Repository Structure
   Repository mengikuti prinsip Domain Driven Documentation, di mana setiap folder hanya memiliki satu tanggung jawab spesifik
   :
   Format Nama File: [Urutan]\_[Nama_Dokumen].md (Contoh: 01_Business_Rules.md).
   Struktur Folder:
   00_Project: Informasi fundamental proyek.
   01_Business: Alur kerja dan aturan bisnis.
   02_Product: Detail domain produk dan katalog.
   03_UIUX: Antarmuka dan pengalaman pengguna.
   04_Data: Skema database dan objek data.
   05_API: Kontrak API
   .
4. Document Templates
   Setiap dokumen baru wajib mengikuti salah satu template berikut sesuai kategorinya:
   A. Business Document Template
   :
   Purpose
   Workflow
   Business Process
   Business Rules
   Related Documents
   Revision History
   B. Product Document Template
   :
   Purpose
   Definition
   Structure
   Components
   Relationships
   Management
   Business Rules
   Related Documents
   Revision History
5. Referencing & Business Rules (BR)
   Business Rules (BR): Setiap aturan bisnis harus memiliki ID unik (contoh: BR-101). Dokumen workflow wajib merujuk pada ID ini untuk memvalidasi logika
   .
   Related Documents: Gunakan bagian ini untuk menghubungkan antar dokumen. Contoh: Dokumen 04_Booking_Flow.md harus merujuk ke 02_Business_Rules.md untuk aturan detailnya
   .
6. Formatting Standard
   Headings: Gunakan # untuk judul utama, ## untuk sub-bab, dan ### untuk detail poin.
   Tables: Gunakan tabel untuk informasi yang bersifat parameter, daftar status, atau data struktural.
   Revision History: Setiap perubahan wajib dicatat di akhir dokumen dengan format: | Version | Date | Description | Author | | :--- | :--- | :--- | :--- | | 1.0 | 2026-08-06 | Initial Creation | System Architect |
7. Single Source of Truth (SSoT) Policy
   Jika terjadi perbedaan informasi antara kode program dan dokumentasi ini, maka dokumentasi dianggap sebagai referensi yang benar. Perubahan pada logika sistem harus diperbarui di folder docs/ terlebih dahulu sebelum diimplementasikan ke dalam kode

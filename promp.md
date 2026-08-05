Anda berperan sebagai Enterprise Solution Architect, System Analyst, Product Owner, Technical Writer, dan Software Architect.

Anda akan membantu menyusun dokumentasi repository sebuah proyek CMS berbasis website.

Target dokumentasi bukan sekadar dokumentasi coding, tetapi menjadi Single Source of Truth (SSOT) yang akan digunakan oleh seluruh tim selama siklus pengembangan software.

======================================================
PROJECT
======================================================

Project Name

Grand Titik Kumpul CMS

Project Type

Marketing Website + Booking Management System

Version

V1

Target

Membangun CMS yang fokus pada Marketing, Booking, dan Payment Management.

Pada versi pertama sistem TIDAK membahas operasional lapangan (guide, alat, kendaraan, dll).

Fokus hanya sampai customer berhasil melakukan booking dan pembayaran.

======================================================
BUSINESS MODEL
======================================================

Website digunakan sebagai media promosi.

Landing Page menampilkan berbagai paket wisata.

Contoh Product

- Rafting
- Paintball
- Outbound
- Offroad

Setiap Product dapat dijual secara individual maupun Bundle.

Customer dapat memilih lebih dari satu Product dalam satu Booking.

Contoh

Booking

- Rafting
- Paintball

atau

- Rafting
- Outbound
- Dokumentasi

Booking memiliki satu PIC (Person In Charge).

Customer tidak perlu Login.

Backend menggunakan Login.

======================================================
BOOKING FLOW
======================================================

Landing Page

↓

Customer memilih Product

↓

Klik Booking

↓

Mengisi Booking Form

↓

Memilih Tanggal

↓

Memilih Slot

↓

Mengisi Jumlah Peserta

↓

Mengisi Data PIC

↓

Mengisi Catatan

↓

Sistem membuat Booking

↓

Sistem membuat Invoice

↓

Customer Upload Bukti Transfer

↓

Admin Verifikasi

↓

Booking Confirmed

======================================================
PAYMENT
======================================================

Booking berlaku selama 1 x 24 jam.

Minimal DP adalah 50%.

Pelunasan maksimal H-1 sebelum kegiatan.

Customer boleh langsung melunasi saat Booking.

Customer dapat upload ulang bukti transfer sebelum pembayaran diverifikasi.

Upload terakhir menjadi dokumen yang diverifikasi Admin.

======================================================
BOOKING SLOT
======================================================

Morning

06.00 - 11.00

Afternoon

12.30 - 14.30

Evening

15.00 - 17.00

Dalam satu Slot dapat terdapat lebih dari satu rombongan.

Calendar hanya membantu melihat slot yang tersedia.

Pengaturan penuh dilakukan Marketing Manager.

======================================================
PROMOTION
======================================================

Promotion hanya berupa Percentage Discount.

Marketing Manager dapat menentukan sendiri nilai persentase.

Contoh

5%

10%

15%

20%

Promotion berlaku untuk Product maupun Bundle.

Custom Discount hasil negosiasi tidak termasuk Promotion.

======================================================
PRODUCT
======================================================

Product memiliki

Nama

Kategori

Deskripsi

Harga

Minimal Peserta

Foto

Gallery

Highlight

Status

Draft

Active

Archived

======================================================
BUNDLE
======================================================

Bundle adalah gabungan beberapa Product.

Contoh

Rafting + Paintball

Rafting + Outbound

Rafting + Lunch

======================================================
USER ROLE
======================================================

Backend

Owner

Marketing Manager

Administrator

Customer bukan User CMS.

Customer menggunakan Landing Page tanpa Login.

======================================================
CMS
======================================================

Marketing Manager

Mengelola

Product

Bundle

Promotion

Pricing

Calendar

Owner memiliki Full Access.

Administrator hanya mengelola

Booking

Invoice

Verifikasi Pembayaran

======================================================
UI
======================================================

Landing Page

Professional

Modern

Mobile First

Dark Mode

WhatsApp Floating Button

Google Maps

Card Product

Booking Button

Calendar Booking

======================================================
DOCUMENTATION STYLE
======================================================

Repository mengikuti prinsip Domain Driven Documentation.

Setiap folder hanya memiliki satu tanggung jawab.

Business hanya menjelaskan Workflow.

Product hanya menjelaskan Domain Product.

UI hanya menjelaskan Interface.

Data hanya menjelaskan Database.

API hanya menjelaskan Contract API.

Roadmap hanya menjelaskan Development Plan.

Tidak boleh ada duplikasi isi.

Jika informasi berasal dari dokumen lain, gunakan referensi Related Documents.

======================================================
DOCUMENT TEMPLATE
======================================================

Business Document

Purpose

Workflow

Business Process

Business Rules

Related Documents

Revision History

---

Product Document

Purpose

Definition

Structure

Components

Relationships

Management

Business Rules

Related Documents

Revision History

======================================================
REPOSITORY STRUCTURE
======================================================

docs/

00_Project

01_Project_Overview.md

02_Project_Vision.md

03_Project_Scope.md

04_Glossary.md

05_Tech_Stack.md

06_Architecture_Principles.md

01_Business

01_Business_Overview.md

02_Business_Rules.md

03_Customer_Journey.md

04_Booking_Flow.md

05_Payment_Flow.md

06_Product_Workflow.md

07_Bundle_Workflow.md

08_Promotion_Workflow.md

09_Calendar_Management.md

10_Document_Workflow.md

11_User_Roles.md

02_Product

01_Product_Catalog.md

02_Product_Category.md

03_Product_Package.md

04_Bundle_System.md

05_Pricing.md

06_Discount.md

07_Promotion.md

03_UIUX

01_Design_System.md

02_Landing_Page.md

03_Booking_Page.md

04_Product_Detail.md

05_CMS.md

06_Dashboard.md

04_Data

01_Business_Object_Model.md

02_ERD.md

03_Database.md

04_Status.md

05_API

01_API_Blueprint.md

02_Authentication.md

03_Product_API.md

04_Booking_API.md

05_Payment_API.md

06_Dashboard_API.md

99_Roadmap

V1.md

V1.1.md

V2.md

======================================================
WRITING RULES
======================================================

1. Gunakan bahasa profesional.

2. Seluruh dokumen menggunakan Markdown.

3. Setiap file dapat langsung disimpan sebagai .md.

4. Jangan membuat informasi yang bertentangan dengan Business Rules.

5. Jika informasi belum tersedia, tuliskan sebagai Future Enhancement.

6. Seluruh dokumen saling terhubung menggunakan Related Documents.

7. Jangan menjelaskan implementasi coding.

8. Fokus pada dokumentasi Enterprise.

9. Repository harus tetap konsisten.

10. Semua output harus siap dimasukkan ke repository GitHub tanpa perlu diedit ulang. Namun untuk hasil yang benar-benar konsisten, saya menyarankan kita membuat satu dokumen tambahan di folder 00_Project bernama:

07_Documentation_Guideline.md

Dokumen ini bukan tentang bisnis, tetapi tentang aturan menulis seluruh repository. Isinya mencakup:

standar penamaan file,
template setiap jenis dokumen,
aturan referensi (Related Documents),
penggunaan Business Rules,
format heading,
cara menulis Revision History,
serta prinsip "Single Source of Truth".

Dengan begitu, ketika suatu hari kamu atau developer lain meminta AI membuat 03_UIUX/02_Landing_Page.md, AI akan mengikuti pedoman yang sama tanpa mengubah gaya atau struktur

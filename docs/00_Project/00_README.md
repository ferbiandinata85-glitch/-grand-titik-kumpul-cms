### Grand Titik Kumpul CMS

#### Project Documentation

---

#### Welcome

Selamat datang di repository dokumentasi **Grand Titik Kumpul CMS**.
Dokumentasi ini merupakan **Single Source of Truth** untuk seluruh proses analisis, perancangan, dan pengembangan sistem [4].
Semua keputusan bisnis, desain sistem, struktur data, API, dan roadmap pengembangan harus mengacu pada dokumentasi di dalam folder /docs [4].

---

#### Quick Links

- [Vision & Mission](./01_Project_Vision.md)
- [Project Scope](./03_Project_Scope.md)
- [Tech Stack](./05_Tech_Stack.md)
- [Glossary](./04_Glossary.md)

---

#### Project Information

| Item                | Description                                   |
| ------------------- | --------------------------------------------- |
| **Project Name**    | Grand Titik Kumpul CMS                        |
| **Project Type**    | Marketing Website & Booking Management System |
| **Current Version** | V1 (Marketing & Booking)                      |
| **Status**          | Analysis & Documentation Phase [5]            |

---

#### How to Use This Docs

1. **Developers:** Wajib membaca `05_Tech_Stack.md` dan `06_Project_Structure.md` sebelum memulai coding [6].
2. **Stakeholders:** Merujuk pada `01_Project_Vision.md` dan `03_Project_Scope.md` untuk validasi fitur [7, 8].
3. **AI Assistant:** Gunakan file `.md` ini sebagai context utama untuk pembuatan kode [2].

---

2. Dokumen: 01_Project_Vision.md
   Catatan Revisi: Menambahkan KPI (Key Performance Indicators) yang terukur pada bagian Success Indicators agar audit manajemen di masa depan memiliki parameter keberhasilan yang jelas
   .
   Isi Dokumen Terupdate:

### Project Vision

#### Document Information

| Item            | Value                  |
| --------------- | ---------------------- |
| **Project**     | Grand Titik Kumpul CMS |
| **Version**     | 1.1 (Revised)          |
| **Status**      | Draft                  |
| **Last Update** | 2026-08-06             |

---

#### 1. Background

Grand Titik Kumpul menghadapi kendala skalabilitas karena proses manual via WhatsApp yang rentan human error dan sulit ditelusuri [7]. Sistem ini akan menjadi pusat digitalisasi operasional [7].

#### 2. Vision & Mission

Membangun platform terintegrasi untuk promosi, reservasi, dan manajemen data pelanggan yang profesional [10]. Fokus pada kemandirian pelanggan (24/7) dan penyediaan dashboard analitik bagi manajemen [10].

#### 3. Success Indicators (Revised)

- **Kemandirian Pelanggan:** Minimal 80% booking dilakukan tanpa intervensi admin manual [9].
- **Akurasi Data:** 100% data transaksi tercatat secara otomatis dan real-time di database [9].
- **Efisiensi Admin:** Pengurangan beban kerja administratif hingga 50% melalui otomatisasi invoice dan verifikasi pembayaran [10].
- **Fleksibilitas Produk:** Marketing Manager mampu melakukan update harga/paket < 5 menit melalui CMS [9].

#### 4. Primary Users

- Visitor, Customer, Customer Service, Marketing Manager, dan Owner [11].

#### 5. Long Term Vision

Ekspansi dari Booking Engine menjadi ERP ringan (V2) yang mencakup logistik, jadwal guide, dan CRM prediktif [12]. 3. Dokumen: 05_Tech_Stack.md
Catatan Revisi: Menambahkan komponen Observability (Sentry/LogSnag) dan CI/CD yang sebelumnya belum disebutkan, untuk memastikan standar operasional software engineering yang matang
.
Isi Dokumen Terupdate:

### 05. Tech Stack

Version : 1.1 (Revised) Status : Draft Last Update : 2026-08-06

---

### 1. Core Architecture

- **Frontend:** Next.js (App Router), TypeScript, Tailwind CSS, shadcn/ui [14].
- **Backend & BaaS:** Supabase (Auth, PostgreSQL, Storage, Realtime) [15].
- **ORM:** Prisma ORM untuk manajemen skema dan migrasi [15].

### 2. Monitoring & DevOps (Addition)

- **Error Tracking:** Sentry (untuk monitoring error di production).
- **Analytics:** PostHog atau Google Analytics (untuk tracking user behavior sesuai visi data-driven) [16].
- **CI/CD:** GitHub Actions untuk automated testing dan deployment ke Vercel [13].

### 3. Performance Targets

- **LCP (Largest Contentful Paint):** < 2.5 detik.
- **SEO & Accessibility Score:** Minimal 90 (Lighthouse) [17].
- **Booking Flow:** Maksimal 5 langkah hingga reservasi selesai [18].

### 4. Security

- Role Based Access Control (RBAC) untuk Owner dan Marketing Manager [15].
- Row Level Security (RLS) pada Supabase untuk proteksi data tingkat database.

4. Dokumen: 06_Project_Structure.md
   Catatan Revisi: Menegaskan pemisahan antara folder docs (Business Logic) dan src/features (Technical Logic) agar sesuai dengan prinsip Modular Documentation
   .
   Isi Dokumen Terupdate:

### 06. Project Structure

Version : 1.1 (Revised) Status : Draft Last Update : 2026-08-06

---

### 1. Repository Mapping

Struktur repository dibagi menjadi dua area utama:

1.  **/docs**: Berisi dokumen analisis bisnis dan teknis (SSoT) [20].
2.  **/src**: Berisi implementasi kode program [21].

### 2. Feature-Based Structure (Recommended)

Untuk skalabilitas, folder `src/features/` akan dibagi berdasarkan domain bisnis di `docs` [19]:

- `features/booking/`: Implementasi logika reservasi dan slot.
- `features/catalog/`: Implementasi tampilan produk dan bundle.
- `features/payment/`: Logika upload bukti dan verifikasi manual.
- `features/dashboard/`: Komponen analitik untuk Owner/Marketing.

### 3. Documentation Rules

Setiap perubahan pada aturan bisnis wajib diperbarui di folder `/docs

# 08. Product Status

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan Product Status yang digunakan pada Grand Titik Kumpul CMS.

Product Status digunakan untuk mengontrol siklus hidup (Lifecycle) Product sehingga hanya Product yang memenuhi syarat yang dapat ditampilkan kepada customer maupun digunakan pada proses Booking.

Dokumen ini hanya menjelaskan status Product sebagai domain bisnis dan tidak membahas implementasi database, API, maupun antarmuka pengguna.

---

# 2. Definition

Product Status merupakan kondisi operasional sebuah Product.

Status menentukan apakah Product sedang dalam proses pembuatan, siap dipublikasikan, aktif dijual, atau sudah tidak digunakan lagi.

Setiap Product hanya dapat memiliki satu Status pada satu waktu.

---

# 3. Product Lifecycle

```
Draft
   │
   ▼
Active
   │
   ▼
Archived
```

Lifecycle di atas menggambarkan perubahan status Product selama siklus hidupnya.

---

# 4. Status Definition

## Draft

Product masih dalam proses pembuatan atau penyuntingan.

Karakteristik:

- Belum tampil pada Landing Page.
- Belum dapat dipesan.
- Masih dapat diubah sepenuhnya.

---

## Active

Product telah dipublikasikan dan siap dijual.

Karakteristik:

- Ditampilkan pada Landing Page.
- Dapat dipilih saat Booking.
- Digunakan pada Promotion dan Bundle.

---

## Archived

Product sudah tidak dijual lagi.

Karakteristik:

- Tidak tampil pada Landing Page.
- Tidak dapat dipilih untuk Booking baru.
- Tetap tersedia pada histori transaksi.

Archived digunakan untuk menjaga integritas data historis.

---

# 5. Status Transition

Perubahan Status mengikuti aturan berikut.

| From     | To       | Allowed |
| -------- | -------- | ------- |
| Draft    | Active   | ✓       |
| Active   | Archived | ✓       |
| Archived | Active   | ✓       |
| Draft    | Archived | ✓       |

Perubahan Status dilakukan melalui CMS.

---

# 6. Relationships

Product Status memiliki hubungan dengan beberapa domain.

| Domain          | Relationship                                          |
| --------------- | ----------------------------------------------------- |
| Product Package | Menentukan ketersediaan Product                       |
| Bundle          | Hanya Product Active yang dapat ditambahkan ke Bundle |
| Promotion       | Promotion hanya dapat diterapkan pada Product Active  |
| Booking         | Booking hanya dapat menggunakan Product Active        |
| Landing Page    | Hanya Product Active yang ditampilkan                 |

---

# 7. Management

Product Status dikelola melalui CMS.

Hak akses.

| Role              | Permission    |
| ----------------- | ------------- |
| Owner             | Full Access   |
| Marketing Manager | Update Status |
| Administrator     | Read Only     |

Aktivitas yang tersedia.

- Publish Product
- Archive Product
- Reactivate Product

Status tidak dapat diubah secara otomatis oleh sistem pada V1.

---

# 8. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-103 : Product Status
- BR-122 : Product Lifecycle
- BR-123 : Product Availability

---

# 9. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md

### Product

- 01_Product_Catalog.md
- 03_Product_Package.md
- 04_Bundle_System.md
- 07_Promotion.md

### UI/UX

- ../03_UIUX/02_Landing_Page.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/04_Status.md

### API

- ../05_API/03_Product_API.md

---

# 10. Revision History

| Version | Date       | Description            |
| ------- | ---------- | ---------------------- |
| 1.0     | YYYY-MM-DD | Initial Product Status |

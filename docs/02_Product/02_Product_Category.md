# 02. Product Category

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Product Category yang digunakan dalam Grand Titik Kumpul CMS.

Product Category berfungsi sebagai pengelompokan utama produk agar pengelolaan katalog, pencarian, filtering, dan pengembangan produk dapat dilakukan secara konsisten tanpa mengubah struktur sistem.

Dokumen ini hanya menjelaskan konsep Category sebagai domain bisnis dan tidak membahas implementasi database maupun antarmuka pengguna.

---

# 2. Definition

Product Category adalah klasifikasi yang digunakan untuk mengelompokkan Product berdasarkan jenis aktivitas atau layanan yang ditawarkan.

Setiap Product hanya dapat memiliki satu Category utama.

Satu Category dapat memiliki banyak Product.

Category menjadi dasar dalam penyusunan katalog produk pada website maupun CMS.

---

# 3. Category Structure

Pada versi V1, kategori produk yang digunakan terdiri dari:

| Category  | Description                               |
| --------- | ----------------------------------------- |
| Rafting   | Paket wisata arung jeram                  |
| Paintball | Paket permainan paintball                 |
| Outbound  | Paket kegiatan outbound dan team building |
| Offroad   | Paket wisata offroad                      |

Struktur Category dirancang fleksibel sehingga kategori baru dapat ditambahkan tanpa mengubah struktur sistem.

Contoh pengembangan di masa depan:

- Camping
- Gathering
- Family Package
- Corporate Event

---

# 4. Category Components

Setiap Category memiliki informasi berikut.

## Identity

- Category ID
- Category Name
- Category Slug

---

## Information

- Description
- Cover Image (Optional)

---

## Display

- Display Order
- Visibility Status

---

## Status

- Active
- Inactive

---

# 5. Relationships

Product Category memiliki hubungan dengan beberapa domain lain.

| Domain       | Relationship                                   |
| ------------ | ---------------------------------------------- |
| Product      | Satu Category memiliki banyak Product          |
| Landing Page | Digunakan sebagai filter dan navigasi katalog  |
| CMS          | Digunakan untuk pengelolaan Product            |
| Dashboard    | Digunakan untuk statistik berdasarkan kategori |

Category tidak berhubungan langsung dengan Booking maupun Payment.

---

# 6. Management

Pengelolaan Product Category dilakukan melalui CMS.

Hak akses:

| Role              | Permission                           |
| ----------------- | ------------------------------------ |
| Owner             | Full Access                          |
| Marketing Manager | Create, Update, Activate, Deactivate |
| Administrator     | Read Only                            |

Aktivitas yang tersedia:

- Create Category
- Update Category
- Activate Category
- Deactivate Category
- Change Display Order

Penghapusan permanen (Delete) tidak dilakukan pada V1 untuk menjaga konsistensi data historis.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut:

- BR-101 : Product Management
- BR-102 : Product Category
- BR-103 : Product Status

---

# 8. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md

### Product

- 01_Product_Catalog.md
- 03_Product_Package.md
- 05_Pricing.md

### UI/UX

- ../03_UIUX/02_Landing_Page.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/03_Product_API.md

---

# 9. Revision History

| Version | Date       | Description              |
| ------- | ---------- | ------------------------ |
| 1.0     | YYYY-MM-DD | Initial Product Category |

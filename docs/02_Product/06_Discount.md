# 06. Discount

> Version : 1.1
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Discount yang digunakan pada Grand Titik Kumpul CMS.

Discount merupakan mekanisme penyesuaian harga yang dapat diterapkan pada Product, Bundle, maupun Booking berdasarkan kebijakan bisnis.

Discount digunakan sebagai komponen perhitungan harga dan tidak mengubah Base Price yang telah ditetapkan pada Product maupun Bundle.

Dokumen ini hanya menjelaskan struktur Discount sebagai domain bisnis dan tidak membahas implementasi database, API, maupun proses pembayaran.

---

# 2. Definition

Discount adalah nilai potongan harga yang digunakan untuk menghasilkan harga akhir transaksi.

Discount tidak berdiri sendiri.

Discount selalu digunakan oleh salah satu mekanisme berikut.

- Promotion
- Manual Negotiation

Discount bukan merupakan harga baru, melainkan aturan perhitungan terhadap Pricing.

---

# 3. Discount Structure

```
Discount
│
├── Identity
├── Discount Type
├── Discount Value
├── Target
├── Validity
├── Usage
└── Status
```

---

# 4. Components

## Identity

Informasi dasar Discount.

- Discount ID
- Discount Name
- Description

---

## Discount Type

V1 mendukung dua jenis Discount.

### Percentage

Potongan berdasarkan persentase.

Contoh

- 10%
- 15%
- 20%

---

### Fixed Amount

Potongan berdasarkan nominal.

Contoh

- Rp500.000
- Rp1.000.000

---

## Discount Value

Nilai Discount mengikuti jenis Discount yang dipilih.

Contoh

| Type         | Value  |
| ------------ | ------ |
| Percentage   | 10     |
| Fixed Amount | 500000 |

---

## Target

Discount dapat diterapkan pada.

- Product
- Bundle
- Booking

---

## Validity

Discount memiliki periode penggunaan.

- Start Date
- End Date

Untuk Discount hasil negosiasi manual, periode berlaku hanya pada transaksi tersebut.

---

## Usage

Discount dapat digunakan melalui dua mekanisme.

### Promotion

Discount diterapkan secara otomatis oleh Promotion yang sedang aktif.

Contoh

Promo Liburan Sekolah

↓

Discount 10%

---

### Manual Negotiation

Marketing Manager dapat memilih Discount ketika melakukan negosiasi dengan customer.

Discount hanya berlaku pada Booking tersebut dan tidak mengubah Pricing.

Contoh

Corporate Event

↓

Discount 15%

↓

Hanya berlaku untuk Booking #BK-20260806-001

---

## Status

Discount memiliki status.

- Draft
- Active
- Expired
- Archived

Hanya Discount dengan status Active yang dapat digunakan.

---

# 5. Relationships

Discount memiliki hubungan dengan beberapa domain.

| Domain    | Relationship                          |
| --------- | ------------------------------------- |
| Pricing   | Mengurangi Base Price                 |
| Promotion | Digunakan sebagai mekanisme Promotion |
| Booking   | Digunakan pada negosiasi manual       |
| Bundle    | Dapat diterapkan pada Bundle          |
| Invoice   | Memengaruhi nilai transaksi           |

---

# 6. Management

Discount dikelola melalui CMS.

Hak akses.

| Role              | Permission               |
| ----------------- | ------------------------ |
| Owner             | Full Access              |
| Marketing Manager | Full Discount Management |
| Administrator     | Read Only                |

Aktivitas yang tersedia.

- Create Discount
- Update Discount
- Activate Discount
- Archive Discount
- Apply Discount to Booking

Discount tidak dapat dihapus apabila pernah digunakan pada transaksi.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-114 : Discount Management
- BR-115 : Percentage Discount
- BR-116 : Fixed Amount Discount
- BR-117 : Manual Negotiation Discount

---

# 8. Related Documents

### Business

- ../01_Business/04_Booking_Flow.md

### Product

- 05_Pricing.md
- 07_Promotion.md

### UI/UX

- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/03_Product_API.md

---

# 9. Revision History

| Version | Date       | Description                                                                |
| ------- | ---------- | -------------------------------------------------------------------------- |
| 1.0     | YYYY-MM-DD | Initial Discount                                                           |
| 1.1     | YYYY-MM-DD | Refined Discount model, added Usage concept and Manual Negotiation support |

# 05. Pricing

> Version : 1.1
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Pricing yang digunakan pada Grand Titik Kumpul CMS.

Pricing merupakan domain yang mengatur seluruh struktur harga Product, Bundle, dan Optional Add-ons. Seluruh transaksi Booking menggunakan Pricing sebagai sumber perhitungan utama.

Dokumen ini hanya menjelaskan struktur harga sebagai domain bisnis dan tidak membahas implementasi database, API, maupun proses pembayaran.

---

# 2. Definition

Pricing adalah aturan penetapan harga yang digunakan pada setiap Product, Bundle, maupun Optional Add-ons.

Pricing dikelola melalui CMS oleh Marketing Manager atau Owner.

Perubahan Pricing hanya berlaku untuk transaksi baru dan tidak mengubah histori Booking maupun Invoice yang telah diterbitkan.

---

# 3. Pricing Structure

Pricing terdiri dari beberapa komponen.

```
Pricing
│
├── Base Price
├── Participant Rules
├── Bundle Price
├── Optional Add-on Price
├── Negotiated Price
├── Discount Reference
├── Promotion Reference
└── Status
```

---

# 4. Components

## Base Price

Merupakan harga dasar Product.

Contoh

Rafting

Rp200.000 / Orang

Base Price menjadi acuan utama seluruh transaksi.

---

## Participant Rules

Menentukan aturan jumlah peserta.

Parameter yang digunakan.

- Minimum Participant
- Maximum Participant (Optional)

### Default V1

Minimum Participant

10 Orang

Contoh Perhitungan

Harga

Rp200.000

Peserta Booking

8 Orang

Total Perhitungan

10 × Rp200.000

Apabila jumlah peserta melebihi Minimum Participant, sistem menghitung sesuai jumlah peserta aktual.

---

## Bundle Price

Bundle dapat memiliki harga khusus.

Harga Bundle tidak harus merupakan penjumlahan seluruh Product.

Contoh

Rafting

Rp200.000

Paintball

Rp150.000

Harga Normal

Rp350.000

Bundle Price

Rp320.000

---

## Optional Add-on Price

Setiap Optional Add-on memiliki harga sendiri.

Contoh

Dokumentasi Foto

Rp500.000

Drone Documentation

Rp1.500.000

Coffee Break

Rp30.000 / Orang

Transportasi

Rp2.000.000

Harga Add-on dihitung terpisah dari harga Product.

---

## Negotiated Price

Negotiated Price merupakan penyesuaian harga yang diberikan oleh Marketing Manager pada proses negosiasi dengan customer.

Negotiated Price bersifat khusus untuk satu transaksi dan tidak mengubah Base Price Product.

Contoh penggunaan.

- Corporate Event
- Instansi Pemerintah
- Sekolah
- Event Khusus
- Repeat Customer

Negotiated Price dapat berupa.

- Potongan nominal
- Potongan persentase
- Harga khusus

Negotiated Price hanya berlaku pada Booking yang bersangkutan.

---

## Discount Reference

Pricing dapat memiliki Discount.

Discount merupakan bagian dari strategi penjualan.

Pengelolaan Discount dijelaskan pada:

06_Discount.md

---

## Promotion Reference

Pricing dapat mengikuti Promotion yang sedang aktif.

Promotion dijelaskan pada:

07_Promotion.md

---

## Status

Pricing memiliki status.

- Draft
- Active
- Archived

Hanya Pricing dengan status Active yang dapat digunakan pada transaksi baru.

---

# 5. Relationships

Pricing memiliki hubungan dengan beberapa domain.

| Domain          | Relationship                               |
| --------------- | ------------------------------------------ |
| Product         | Menentukan Base Price                      |
| Bundle          | Menentukan Bundle Price                    |
| Optional Add-on | Menentukan harga layanan tambahan          |
| Discount        | Digunakan sebagai referensi potongan harga |
| Promotion       | Digunakan sebagai referensi promo          |
| Booking         | Digunakan untuk menghitung Total Booking   |
| Invoice         | Digunakan untuk menghasilkan nilai Invoice |

---

# 6. Management

Pricing dikelola melalui CMS.

Hak akses.

| Role              | Permission              |
| ----------------- | ----------------------- |
| Owner             | Full Access             |
| Marketing Manager | Full Pricing Management |
| Administrator     | Read Only               |

Aktivitas yang tersedia.

- Create Pricing
- Update Pricing
- Activate Pricing
- Archive Pricing
- Update Base Price
- Update Bundle Price
- Update Add-on Price
- Update Minimum Participant
- Apply Negotiated Price

Perubahan Pricing tidak memengaruhi histori transaksi yang telah selesai.

---

# 7. Business Rules

Dokumen ini mengacu pada Business Rules berikut.

- BR-108 : Pricing Management
- BR-109 : Base Price
- BR-110 : Minimum Participant
- BR-111 : Bundle Pricing
- BR-112 : Optional Add-on Pricing
- BR-113 : Negotiated Price

---

# 8. Related Documents

### Business

- ../01_Business/06_Product_Workflow.md
- ../01_Business/07_Bundle_Workflow.md
- ../01_Business/04_Booking_Flow.md

### Product

- 01_Product_Catalog.md
- 03_Product_Package.md
- 04_Bundle_System.md
- 06_Discount.md
- 07_Promotion.md

### UI/UX

- ../03_UIUX/04_Product_Detail.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/03_Product_API.md

---

# 9. Revision History

| Version | Date       | Description                                                       |
| ------- | ---------- | ----------------------------------------------------------------- |
| 1.0     | YYYY-MM-DD | Initial Pricing                                                   |
| 1.1     | YYYY-MM-DD | Added Negotiated Price component and pricing structure refinement |

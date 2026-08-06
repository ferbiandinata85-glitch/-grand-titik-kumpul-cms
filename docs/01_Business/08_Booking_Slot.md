# 08. Booking Slot

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan struktur Booking Slot yang digunakan pada Grand Titik Kumpul CMS.

Booking Slot merupakan aturan operasional yang mengatur jadwal reservasi customer agar tidak terjadi benturan jadwal maupun kelebihan kapasitas.

Dokumen ini hanya menjelaskan konsep bisnis Booking Slot dan tidak membahas implementasi database, API, maupun antarmuka pengguna.

---

# 2. Definition

Booking Slot adalah periode waktu operasional yang tersedia untuk melakukan aktivitas wisata.

Setiap Booking wajib memilih satu tanggal dan satu Slot Booking.

Booking Slot dikelola melalui CMS.

---

# 3. Default Booking Slot (V1)

Pada versi V1 sistem menyediakan tiga Slot tetap.

| Slot      | Jam Operasional |
| --------- | --------------- |
| Morning   | 06:00 – 11:00   |
| Afternoon | 12:30 – 14:00   |
| Evening   | 15:00 – 17:00   |

Seluruh Product menggunakan Slot yang sama pada V1.

---

# 4. Booking Slot Structure

```
Booking Slot
│
├── Date
├── Time Slot
├── Capacity
├── Booking Count
├── Availability
└── Status
```

---

# 5. Components

## Date

Tanggal pelaksanaan aktivitas.

Customer wajib memilih satu tanggal.

---

## Time Slot

Periode waktu operasional.

- Morning
- Afternoon
- Evening

---

## Capacity

Jumlah maksimal peserta pada Slot tersebut.

Capacity ditentukan oleh Marketing Manager melalui CMS.

Contoh

Morning

50 Peserta

---

## Booking Count

Jumlah peserta yang telah melakukan Booking pada Slot tersebut.

Booking Count akan bertambah setelah Booking berhasil dikonfirmasi.

---

## Availability

Status ketersediaan Slot.

- Available
- Limited
- Full

Customer hanya dapat melakukan Booking pada Slot yang masih Available atau Limited.

---

## Status

Status operasional Slot.

- Active
- Closed

Slot Closed tidak dapat dipilih customer.

---

# 6. Management

Booking Slot dikelola melalui CMS.

Hak akses.

| Role              | Permission           |
| ----------------- | -------------------- |
| Owner             | Full Access          |
| Marketing Manager | Full Slot Management |
| Administrator     | Update Availability  |

Aktivitas.

- Create Slot
- Update Capacity
- Close Slot
- Reopen Slot

---

# 7. Business Rules

Dokumen ini mengacu pada.

- BR-128 : Booking Slot
- BR-129 : Slot Capacity
- BR-130 : Slot Availability
- BR-131 : Slot Closure

---

# 8. Related Documents

### Business

- 04_Booking_Flow.md
- 06_Product_Workflow.md

### Product

- ../02_Product/03_Product_Package.md

### UI/UX

- ../03_UIUX/03_Booking_Page.md
- ../03_UIUX/05_CMS.md

### Data

- ../04_Data/01_Business_Object_Model.md

### API

- ../05_API/04_Booking_API.md

---

# 9. Revision History

| Version | Date       | Description          |
| ------- | ---------- | -------------------- |
| 1.0     | YYYY-MM-DD | Initial Booking Slot |

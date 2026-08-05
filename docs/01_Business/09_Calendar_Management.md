# 09. Calendar Management

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan mekanisme pengelolaan kalender booking pada Grand Titik Kumpul CMS.

Calendar Management berfungsi untuk mengatur ketersediaan jadwal kegiatan sehingga customer dapat memilih tanggal dan sesi yang masih tersedia secara real-time.

Dokumen ini hanya membahas aturan bisnis (Business Workflow), bukan implementasi database maupun API.

---

# 2. Workflow Overview

Seluruh booking mengacu pada Calendar Management.

```
Marketing Manager
        │
        ▼
Membuka Jadwal
        │
        ▼
Customer Memilih Tanggal
        │
        ▼
Customer Memilih Slot
        │
        ▼
Sistem Mengecek Ketersediaan
        │
        ▼
Booking Dibuat
        │
        ▼
Slot Terisi
```

---

# 3. Booking Slot

Pada versi V1 terdapat tiga sesi kegiatan.

| Slot      | Jam           |
| --------- | ------------- |
| Morning   | 06.00 – 11.00 |
| Afternoon | 12.30 – 14.30 |
| Evening   | 15.00 – 17.00 |

Setiap booking wajib memilih salah satu slot.

---

# 4. Calendar Status

Setiap slot memiliki status.

| Status    | Keterangan                     |
| --------- | ------------------------------ |
| Available | Masih dapat dibooking          |
| Limited   | Kuota hampir penuh             |
| Full      | Tidak dapat dibooking          |
| Closed    | Ditutup oleh Marketing Manager |

---

# 5. Customer Booking Workflow

```
Landing Page
      │
      ▼
Booking Page
      │
      ▼
Pilih Tanggal
      │
      ▼
Pilih Slot
      │
      ▼
Sistem Validasi
      │
      ▼
Booking Berhasil
```

Apabila slot telah penuh, customer harus memilih slot lain.

---

# 6. CMS Calendar Management

Marketing Manager dapat:

- Membuka tanggal booking
- Menutup tanggal booking
- Menutup slot tertentu
- Melihat jumlah booking per slot
- Melihat kalender bulanan

Administrator hanya memiliki hak melihat kalender.

---

# 7. Capacity Management

Pada versi V1 sistem belum menggunakan kapasitas otomatis.

Yang ditampilkan hanya:

- Jumlah booking
- Slot tersedia
- Slot penuh

Keputusan menutup slot dilakukan oleh Marketing Manager.

---

# 8. Landing Page Integration

Customer dapat melihat kalender sebelum melakukan booking.

Kalender hanya menampilkan:

- Tanggal tersedia
- Slot tersedia
- Slot penuh

Customer tidak dapat melihat data booking milik customer lain.

---

# 9. Dashboard Integration

Dashboard menampilkan informasi kalender secara ringkas.

Contoh:

- Booking Hari Ini
- Booking Besok
- Slot Penuh
- Slot Hampir Penuh
- Kalender Bulanan

---

# 10. Business Rules

Calendar Management mengimplementasikan:

- BR-501
- BR-502
- BR-503
- BR-504

---

# 11. Future Enhancement

Pengembangan pada versi berikutnya.

- Kapasitas otomatis berdasarkan jumlah peserta
- Blackout Date
- Hari Libur Nasional
- Sinkronisasi Google Calendar
- Sinkronisasi Outlook Calendar
- Drag & Drop Schedule
- Kalender Operasional

---

# 12. Related Documents

- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 06_Product_Workflow.md
- ../03_UIUX/03_Booking_Page.md
- ../04_Data/04_Status.md
- ../05_API/04_Booking_API.md

---

# 13. Revision History

| Version | Date       | Description                 |
| ------- | ---------- | --------------------------- |
| 1.0     | YYYY-MM-DD | Initial Calendar Management |

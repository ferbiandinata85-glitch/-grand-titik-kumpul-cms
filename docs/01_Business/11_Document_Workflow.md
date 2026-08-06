# 10. Document Workflow

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan proses pengelolaan seluruh dokumen pada Grand Titik Kumpul CMS.

Document Workflow memastikan setiap transaksi memiliki dokumen yang tersimpan secara terstruktur dan mudah ditelusuri.

Dokumen ini hanya membahas alur bisnis (Business Workflow), bukan implementasi penyimpanan file maupun database.

---

# 2. Workflow Overview

Setiap Booking akan menghasilkan atau menerima dokumen.

```
Customer Booking
        │
        ▼
Sistem Membuat Invoice
        │
        ▼
Customer Melakukan Pembayaran
        │
        ▼
Customer Upload Bukti Transfer
        │
        ▼
Admin Verifikasi
        │
        ▼
Dokumen Tersimpan
```

---

# 3. Document Type

Pada versi V1 sistem mengelola dokumen berikut.

| Dokumen                  | Sumber   |
| ------------------------ | -------- |
| Booking Invoice          | Sistem   |
| Bukti Transfer DP        | Customer |
| Bukti Transfer Pelunasan | Customer |

---

# 4. Invoice Workflow

Setelah booking berhasil dibuat.

```
Booking
     │
     ▼
Generate Invoice
     │
     ▼
Invoice Number
     │
     ▼
Invoice Tersimpan
```

Invoice digunakan sebagai acuan pembayaran.

---

# 5. Payment Proof Workflow

Customer melakukan upload bukti transfer.

```
Booking
      │
      ▼
Upload Bukti Transfer
      │
      ▼
Status :
Waiting Verification
```

Customer dapat mengganti file selama pembayaran belum dinyatakan lunas.

Upload terakhir akan menjadi dokumen yang diverifikasi oleh Administrator.

---

# 6. Verification Workflow

Administrator melakukan pengecekan manual.

```
Waiting Verification
          │
          ▼
Cek Bukti Transfer
          │
      ┌───┴────┐
      ▼        ▼
 Valid      Invalid
      │        │
      ▼        ▼
DP Paid   Upload Ulang
```

---

# 7. Document Status

Status dokumen.

| Status               | Keterangan                |
| -------------------- | ------------------------- |
| Uploaded             | Dokumen berhasil diunggah |
| Waiting Verification | Menunggu pengecekan Admin |
| Verified             | Dokumen valid             |
| Rejected             | Ditolak                   |
| Replaced             | Diganti oleh customer     |

---

# 8. Document Rules

Dokumen yang diunggah customer mengikuti aturan berikut.

- Maksimal satu file aktif untuk setiap tahap pembayaran.
- Customer dapat mengunggah ulang sebelum pembayaran diverifikasi.
- Setelah pembayaran dinyatakan lunas, upload dinonaktifkan.
- Semua dokumen tetap tersimpan sebagai arsip transaksi.

---

# 9. CMS Workflow

Administrator dapat:

- Melihat Invoice
- Melihat Bukti Transfer
- Memverifikasi Bukti Transfer
- Mengubah Status Pembayaran

Marketing Manager hanya memiliki hak melihat dokumen transaksi.

Owner memiliki akses penuh.

---

# 10. Dashboard Integration

Dashboard menampilkan ringkasan dokumen.

Contoh:

- Invoice Baru
- Menunggu Verifikasi
- DP Terverifikasi
- Pelunasan Menunggu Verifikasi
- Transaksi Lunas

---

# 11. Business Rules

Workflow ini mengimplementasikan:

- BR-601
- BR-602
- BR-603
- BR-604

---

# 12. Future Enhancement

Pengembangan pada versi berikutnya.

- Generate PDF Invoice
- E-Receipt
- Digital Signature
- Email Attachment
- WhatsApp Document Delivery
- Document Versioning
- Audit Log

---

# 13. Related Documents

- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 11_User_Roles.md
- ../03_UIUX/05_CMS.md
- ../04_Data/03_Database.md
- ../05_API/05_Payment_API.md

---

# 14. Revision History

| Version | Date       | Description               |
| ------- | ---------- | ------------------------- |
| 1.0     | YYYY-MM-DD | Initial Document Workflow |

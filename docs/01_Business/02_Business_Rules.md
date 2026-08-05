# 02. Business Rules

> Version : 1.1
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh aturan bisnis (Business Rules) yang menjadi dasar pengembangan Grand Titik Kumpul CMS.

Seluruh modul seperti Product, Booking, Payment, Dashboard, Database, dan API wajib mengikuti aturan yang dijelaskan pada dokumen ini.

---

# 2. General Principles

Sistem dikembangkan berdasarkan prinsip berikut.

| Rule ID | Business Rule                                                          |
| ------- | ---------------------------------------------------------------------- |
| BR-001  | Seluruh data dikelola dalam satu sistem (Single Source of Truth).      |
| BR-002  | Proses booking harus sederhana dan mudah dipahami pelanggan.           |
| BR-003  | Produk dapat ditambah tanpa perubahan source code.                     |
| BR-004  | Harga dapat diubah melalui CMS.                                        |
| BR-005  | Bundle dapat dibuat melalui CMS.                                       |
| BR-006  | Promo dapat dibuat tanpa perubahan program.                            |
| BR-007  | Seluruh konfigurasi bisnis dikelola oleh Marketing Manager atau Owner. |

---

# 3. Product Rules

| Rule ID | Business Rule                                                       |
| ------- | ------------------------------------------------------------------- |
| BR-101  | Sistem mendukung Single Product.                                    |
| BR-102  | Sistem mendukung Bundle Product.                                    |
| BR-103  | Sistem mendukung Add-On Product.                                    |
| BR-104  | Marketing Manager dapat menambah produk.                            |
| BR-105  | Marketing Manager dapat mengubah harga produk.                      |
| BR-106  | Marketing Manager dapat mengaktifkan atau menonaktifkan produk.     |
| BR-107  | Marketing Manager dapat membuat bundle baru tanpa perubahan sistem. |

Contoh Single Product

- Rafting
- Paintball
- Offroad
- Outbound

Contoh Bundle

- Rafting + Paintball
- Rafting + Offroad
- Outbound + Paintball

Contoh Add-On

- Dokumentasi Foto
- Dokumentasi Video

---

# 4. Booking Rules

| Rule ID | Business Rule                                             |
| ------- | --------------------------------------------------------- |
| BR-201  | Booking dapat dilakukan tanpa login.                      |
| BR-202  | Setiap booking wajib memiliki satu PIC.                   |
| BR-203  | PIC wajib mengisi Nama, WhatsApp dan Email.               |
| BR-204  | Booking wajib memilih tanggal kegiatan.                   |
| BR-205  | Booking wajib memilih slot kegiatan.                      |
| BR-206  | Booking wajib memilih minimal satu paket.                 |
| BR-207  | Satu booking dapat memiliki lebih dari satu paket.        |
| BR-208  | Customer dapat menambahkan catatan tambahan saat booking. |

---

# 5. Participant Rules

| Rule ID | Business Rule                                                      |
| ------- | ------------------------------------------------------------------ |
| BR-301  | Minimal peserta ditentukan per produk.                             |
| BR-302  | Nilai minimal peserta dapat diubah melalui CMS.                    |
| BR-303  | Sistem melakukan validasi jumlah peserta sebelum booking diproses. |

Default V1

Rafting

Minimal 10 Peserta

---

# 6. Schedule Rules

| Rule ID | Business Rule                                        |
| ------- | ---------------------------------------------------- |
| BR-401  | Satu hari dapat memiliki lebih dari satu rombongan.  |
| BR-402  | Booking wajib memilih slot kegiatan.                 |
| BR-403  | Slot dapat dibuka atau ditutup melalui CMS.          |
| BR-404  | Kalender hanya menampilkan slot yang masih tersedia. |

Slot Default

Pagi

06.00 – 11.00

Siang

12.30 – 14.00

Sore

15.00 – 17.00

---

# 7. Pricing Rules

| Rule ID | Business Rule                                        |
| ------- | ---------------------------------------------------- |
| BR-501  | Harga ditentukan per produk.                         |
| BR-502  | Harga dapat diubah melalui CMS.                      |
| BR-503  | Minimal peserta dapat diubah melalui CMS.            |
| BR-504  | Maksimal peserta dapat diubah melalui CMS.           |
| BR-505  | Harga promo dapat ditentukan tanpa perubahan sistem. |

Default Harga

Rafting

Rp200.000 / Orang

---

# 8. Promotion Rules

| Rule ID | Business Rule                                     |
| ------- | ------------------------------------------------- |
| BR-601  | Promo bersifat opsional.                          |
| BR-602  | Promo dapat berupa persentase diskon.             |
| BR-603  | Besar diskon ditentukan oleh Marketing Manager.   |
| BR-604  | Promo dapat diterapkan pada produk maupun bundle. |

Versi 1 hanya menggunakan Promo Persentase.

---

# 9. Payment Rules

| Rule ID | Business Rule                                             |
| ------- | --------------------------------------------------------- |
| BR-701  | Booking memiliki masa berlaku 1 × 24 jam.                 |
| BR-702  | DP minimal sebesar 50% dari total tagihan.                |
| BR-703  | Customer dapat langsung melakukan pelunasan saat booking. |
| BR-704  | Pelunasan dilakukan maksimal H-1 sebelum kegiatan.        |

---

# 10. Transfer Rules

| Rule ID | Business Rule                                                  |
| ------- | -------------------------------------------------------------- |
| BR-801  | Pembayaran dilakukan melalui Transfer Bank.                    |
| BR-802  | Customer wajib mengunggah bukti transfer.                      |
| BR-803  | Bukti transfer dapat diunggah ulang selama status belum Lunas. |
| BR-804  | Upload terbaru menggantikan file sebelumnya.                   |

---

# 11. Verification Rules

| Rule ID | Business Rule                                      |
| ------- | -------------------------------------------------- |
| BR-901  | Seluruh pembayaran diverifikasi secara manual.     |
| BR-902  | Verifikasi dilakukan melalui CMS.                  |
| BR-903  | Admin menentukan status pembayaran.                |
| BR-904  | Status pembayaran akan memperbarui status booking. |

Status Verifikasi

- Menunggu Verifikasi
- DP Diverifikasi
- Lunas Diverifikasi
- Ditolak

---

# 12. Calendar Rules

| Rule ID | Business Rule                            |
| ------- | ---------------------------------------- |
| BR-1001 | Customer dapat melihat kalender booking. |
| BR-1002 | Kalender menampilkan slot tersedia.      |
| BR-1003 | Kalender menampilkan slot penuh.         |
| BR-1004 | Kalender menampilkan slot ditutup.       |

---

# 13. Customer Communication

| Rule ID | Business Rule                                                                           |
| ------- | --------------------------------------------------------------------------------------- |
| BR-1101 | Landing Page menyediakan tombol WhatsApp.                                               |
| BR-1102 | Landing Page menyediakan tombol Booking.                                                |
| BR-1103 | Customer Service hanya membantu konsultasi dan mengarahkan customer ke halaman booking. |

---

# 14. Dashboard Rules

Dashboard minimal menampilkan:

- Total Booking
- Booking Hari Ini
- Pendapatan
- DP Masuk
- Pelunasan
- Paket Terlaris
- Booking Menunggu Verifikasi
- Kalender Booking

---

# 15. Future Rules

Fitur yang dipersiapkan pada versi berikutnya.

- Payment Gateway
- WhatsApp API
- Email Notification
- Reminder H-1
- AI Customer Service
- AI Marketing Assistant

---

# 16. Related Documents

- 03_Customer_Journey.md
- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 06_Product_Workflow.md
- 07_Bundle_Workflow.md
- 08_Promotion_Workflow.md
- 09_Calendar_Management.md

---

# 17. Revision History

| Version | Date       | Description                                  |
| ------- | ---------- | -------------------------------------------- |
| 1.0     | YYYY-MM-DD | Initial Business Rules                       |
| 1.1     | YYYY-MM-DD | Added Business Rule ID (BR) for traceability |

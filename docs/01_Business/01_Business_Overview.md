# 01. Business Overview

> Version : 1.0  
> Status : Draft  
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini memberikan gambaran menyeluruh mengenai model bisnis Grand Titik Kumpul serta tujuan dibangunnya sistem CMS Marketing & Booking.

Dokumen ini menjadi landasan sebelum membahas aturan bisnis, alur booking, pembayaran, produk, database, maupun API.

---

# 2. Business Overview

Grand Titik Kumpul merupakan penyedia jasa wisata dan aktivitas outdoor yang berfokus pada pengalaman kelompok (group activities). Seluruh proses pemasaran, pemesanan, pembayaran, dan pengelolaan data pelanggan akan dilakukan melalui website yang terintegrasi dengan CMS.

Sistem dikembangkan untuk menggantikan proses manual yang selama ini dilakukan melalui WhatsApp dan pencatatan terpisah sehingga seluruh data dapat dikelola dalam satu sistem.

CMS berfungsi sebagai pusat pengelolaan data (Single Source of Truth) yang digunakan oleh Owner dan Marketing Manager.

---

# 3. Business Objectives

Tujuan utama pembangunan sistem adalah:

- Menampilkan seluruh produk secara profesional.
- Meningkatkan konversi pengunjung website menjadi pelanggan.
- Mempermudah proses booking.
- Mengurangi pekerjaan administratif.
- Memusatkan seluruh data pelanggan dalam satu database.
- Mempermudah pengelolaan harga dan promo.
- Menjadi dasar pengembangan sistem operasional pada versi berikutnya.

---

# 4. Business Scope

Versi pertama (V1) difokuskan pada proses pemasaran hingga pelanggan berhasil melakukan booking.

Ruang lingkup meliputi:

- Landing Page
- Product Catalog
- Product Detail
- Booking
- Upload Bukti Transfer
- Verifikasi Pembayaran
- Dashboard Marketing
- CMS Produk
- CMS Booking
- CMS Promo
- CMS Harga

Sistem operasional pelaksanaan kegiatan belum termasuk dalam versi ini.

---

# 5. Business Model

Model bisnis yang digunakan adalah Business to Customer (B2C), di mana pelanggan melakukan pemesanan langsung melalui website.

Alur utama bisnis:

```
Visitor
    │
    ▼
Landing Page
    │
    ▼
Melihat Paket
    │
    ▼
Memilih Paket
    │
    ▼
Booking
    │
    ▼
Pembayaran
    │
    ▼
Verifikasi
    │
    ▼
Booking Confirmed
```

---

# 6. Products

Sistem dirancang agar dapat mengelola berbagai jenis produk tanpa perubahan struktur aplikasi.

Contoh produk:

- Rafting
- Paintball
- Outbound
- Fun Games
- Offroad

Sistem juga mendukung produk bundling.

Contoh:

- Rafting + Paintball
- Rafting + Offroad
- Outbound + Paintball

---

# 7. Target Customer

Target pasar meliputi:

- Perusahaan
- Instansi Pemerintah
- Sekolah
- Universitas
- Komunitas
- Organisasi
- Keluarga
- Wisatawan

---

# 8. Core Business Process

Secara umum proses bisnis terdiri dari tahapan berikut:

1. Pengunjung membuka website.
2. Pengunjung melihat daftar paket.
3. Pengunjung memilih paket.
4. Pengunjung memilih tanggal dan slot kegiatan.
5. Pengunjung mengisi formulir booking.
6. Sistem membuat data booking.
7. Pelanggan melakukan pembayaran.
8. Admin memverifikasi pembayaran.
9. Booking dikonfirmasi.

---

# 9. Core Modules

Modul utama pada versi pertama meliputi:

### Landing Website

Menampilkan informasi dan promosi paket.

### Product Management

Mengelola produk, harga, bundling, dan promo.

### Booking Management

Mengelola reservasi pelanggan.

### Payment Management

Mengelola pembayaran DP dan pelunasan.

### Dashboard

Menampilkan informasi statistik dan aktivitas bisnis.

---

# 10. Business Principles

Pengembangan sistem mengikuti prinsip berikut:

- Mobile First
- Responsive Design
- Mudah digunakan
- Proses booking sederhana
- Data terpusat
- Mudah dikembangkan
- Mengurangi pekerjaan manual
- Skalabel untuk versi berikutnya

---

# 11. Related Documents

Dokumen ini berhubungan dengan:

- 02_Business_Rules.md
- 03_Customer_Journey.md
- 04_Booking_Flow.md
- 05_Payment_Flow.md
- 06_Product_Workflow.md
- 11_User_Roles.md

---

# 12. Revision History

| Version | Date       | Description               |
| ------- | ---------- | ------------------------- |
| 1.0     | YYYY-MM-DD | Initial Business Overview |

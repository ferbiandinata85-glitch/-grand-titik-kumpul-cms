# Glossary

---

## Document Information

| Item        | Value                  |
| ----------- | ---------------------- |
| Project     | Grand Titik Kumpul CMS |
| Document    | Glossary               |
| Version     | 1.0                    |
| Status      | Draft                  |
| Last Update | YYYY-MM-DD             |

---

# 1. Purpose

Dokumen ini mendefinisikan seluruh istilah yang digunakan dalam proyek Grand Titik Kumpul CMS.

Tujuannya adalah memastikan seluruh stakeholder, developer, dan AI Development Assistant memiliki pemahaman yang sama terhadap setiap istilah yang digunakan dalam dokumentasi maupun implementasi sistem.

---

# 2. Business Terms

| Term                   | Definition                                                                  |
| ---------------------- | --------------------------------------------------------------------------- |
| Visitor                | Pengunjung website yang belum melakukan booking.                            |
| Customer               | Pengunjung yang telah melakukan booking.                                    |
| PIC (Person In Charge) | Orang yang bertanggung jawab atas booking dan menjadi kontak utama.         |
| Booking                | Proses reservasi paket wisata melalui website.                              |
| Booking Code           | Kode unik yang dihasilkan untuk setiap booking.                             |
| Invoice                | Dokumen tagihan yang dibuat otomatis setelah booking berhasil.              |
| DP (Down Payment)      | Pembayaran uang muka minimal 50% dari total tagihan.                        |
| Pelunasan              | Pembayaran sisa tagihan hingga status menjadi lunas.                        |
| Booking Expired        | Booking yang otomatis dibatalkan karena melewati batas waktu pembayaran DP. |
| Booking Status         | Status proses booking sejak dibuat hingga selesai.                          |

---

# 3. Product Terms

| Term                | Definition                                                                  |
| ------------------- | --------------------------------------------------------------------------- |
| Package             | Produk wisata yang dijual.                                                  |
| Product Category    | Kelompok produk seperti Rafting, Paintball, Outbound, Offroad, atau Add-on. |
| Bundle Package      | Gabungan dua atau lebih paket yang dijual dalam satu penawaran.             |
| Add-on              | Layanan tambahan yang dapat dipilih customer.                               |
| Product Price       | Harga dasar paket per orang atau per grup.                                  |
| Minimum Participant | Jumlah peserta minimum agar paket dapat dipesan.                            |
| Discount            | Potongan harga yang diberikan pada suatu paket.                             |
| Promotion           | Program promosi yang berlaku pada periode tertentu.                         |

---

# 4. Booking Terms

| Term           | Definition                                   |
| -------------- | -------------------------------------------- |
| Booking Date   | Tanggal kegiatan yang dipilih customer.      |
| Booking Slot   | Sesi waktu kegiatan yang dipilih customer.   |
| Morning Slot   | Slot pagi pukul 06.00 – 11.00.               |
| Afternoon Slot | Slot siang pukul 12.30 – 14.00.              |
| Evening Slot   | Slot sore pukul 15.00 – 17.00.               |
| Participant    | Peserta yang mengikuti kegiatan.             |
| Customer Note  | Catatan tambahan dari customer saat booking. |

---

# 5. Payment Terms

| Term                 | Definition                                                        |
| -------------------- | ----------------------------------------------------------------- |
| Payment              | Pembayaran booking.                                               |
| Payment Proof        | Bukti transfer yang diunggah customer.                            |
| Manual Verification  | Proses pengecekan bukti transfer oleh Marketing Manager.          |
| Pending Payment      | Booking yang belum melakukan pembayaran.                          |
| Waiting Verification | Bukti pembayaran sudah diunggah dan menunggu verifikasi.          |
| Paid                 | Pembayaran telah diterima.                                        |
| Fully Paid           | Seluruh tagihan telah dilunasi.                                   |
| Refund               | Pengembalian dana apabila diperlukan sesuai kebijakan perusahaan. |

---

# 6. User Roles

| Term              | Definition                                                                               |
| ----------------- | ---------------------------------------------------------------------------------------- |
| Marketing Manager | Pengguna yang mengelola seluruh data marketing dan booking melalui CMS.                  |
| Owner             | Pemilik perusahaan yang memiliki akses penuh terhadap dashboard dan laporan.             |
| Customer Service  | Memberikan informasi kepada calon customer dan mengarahkan ke proses booking.            |
| Administrator     | Pengguna yang memiliki hak akses penuh terhadap sistem apabila diperlukan di masa depan. |

---

# 7. System Terms

| Term         | Definition                                                           |
| ------------ | -------------------------------------------------------------------- |
| CMS          | Content Management System untuk mengelola website dan data bisnis.   |
| Dashboard    | Halaman monitoring data bisnis.                                      |
| Landing Page | Halaman utama website yang menampilkan informasi dan promosi produk. |
| Database     | Tempat penyimpanan seluruh data sistem.                              |
| API          | Antarmuka komunikasi antara frontend dan backend.                    |
| Backend      | Sistem yang mengelola logika bisnis dan database.                    |
| Frontend     | Antarmuka yang digunakan customer maupun admin.                      |

---

# 8. Dashboard Terms

| Term                 | Definition                                         |
| -------------------- | -------------------------------------------------- |
| Total Booking        | Jumlah seluruh booking yang masuk.                 |
| Pending Booking      | Booking yang belum selesai diproses.               |
| Paid Booking         | Booking yang telah lunas.                          |
| Total Revenue        | Total nilai transaksi yang telah diterima.         |
| Conversion Rate      | Persentase visitor yang berhasil menjadi customer. |
| Best Selling Package | Paket dengan jumlah booking terbanyak.             |

---

# 9. General Terms

| Term                   | Definition                                                                      |
| ---------------------- | ------------------------------------------------------------------------------- |
| V1                     | Versi pertama sistem dengan fokus Marketing Website dan Booking Management.     |
| V1.1                   | Pengembangan lanjutan yang menambahkan otomatisasi dan integrasi.               |
| V2                     | Pengembangan menuju sistem operasional dan manajemen bisnis yang lebih lengkap. |
| Single Source of Truth | Seluruh keputusan resmi proyek hanya mengacu pada dokumentasi dalam repository. |

---

# 10. Naming Convention

Untuk menjaga konsistensi, gunakan istilah berikut pada seluruh dokumentasi dan implementasi sistem.

| Gunakan           | Hindari                                                                          |
| ----------------- | -------------------------------------------------------------------------------- |
| Customer          | Client                                                                           |
| Booking           | Order                                                                            |
| Package           | Product (untuk konteks bisnis wisata dapat digunakan bergantian bila diperlukan) |
| Marketing Manager | Admin                                                                            |
| Dashboard         | Panel                                                                            |
| Booking Status    | Status Booking                                                                   |
| Payment Status    | Status Pembayaran                                                                |

---

# 11. Revision History

| Version | Date       | Description      |
| ------- | ---------- | ---------------- |
| 1.0     | YYYY-MM-DD | Initial Glossary |

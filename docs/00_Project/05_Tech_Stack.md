# 05. Tech Stack

> Version : 1.0
> Status : Draft
> Last Update : YYYY-MM-DD

---

# 1. Purpose

Dokumen ini menjelaskan seluruh teknologi yang digunakan dalam pengembangan Grand Titik Kumpul CMS.

Tujuannya agar seluruh developer menggunakan standar teknologi yang sama sehingga proses development, maintenance, dan deployment menjadi konsisten.

---

# 2. Architecture Overview

```
Customer
      │
      ▼
Landing Website (Next.js)
      │
      ▼
Booking System
      │
      ▼
API
      │
      ▼
Supabase Database
      │
      ▼
CMS Dashboard
```

Semua data berasal dari satu database sehingga Landing Page, Booking System, dan CMS selalu menggunakan informasi yang sama (Single Source of Truth).

---

# 3. Frontend

Framework

- Next.js (App Router)

Language

- TypeScript

Styling

- Tailwind CSS

Component

- shadcn/ui

Icons

- Lucide Icons

Animation

- Framer Motion

Theme

- next-themes

Responsive

- Mobile First Design

---

# 4. Backend

Backend Service

- Supabase

Authentication

- Supabase Auth

Database

- PostgreSQL

Storage

- Supabase Storage

Realtime

- Supabase Realtime (Future)

---

# 5. Database

Database Engine

- PostgreSQL

ORM

- Prisma ORM

Migration

- Prisma Migration

Seed Data

- Prisma Seed

---

# 6. Authentication

Login

- Email

Password

Role Based Access Control (RBAC)

Role

- Owner
- Marketing Manager

Future

- Google Login
- Magic Link

---

# 7. File Storage

Media yang disimpan

- Banner
- Foto Paket
- Thumbnail
- Bukti Transfer
- Dokumentasi Event

Storage

- Supabase Storage

---

# 8. Maps

Provider

Google Maps

Digunakan untuk

- Lokasi Grand Titik Kumpul
- Petunjuk arah
- Embedded Map

---

# 9. Payment

Versi 1

Manual Transfer

Upload Bukti Transfer

Admin melakukan verifikasi pembayaran.

Future Version

- Midtrans
- Xendit
- QRIS

---

# 10. WhatsApp

Digunakan untuk

- Konsultasi Customer
- Customer Service
- Follow Up Booking

Versi 1 masih menggunakan WhatsApp Link.

Future Version

- WhatsApp API
- Template Message
- Reminder Otomatis

---

# 11. Deployment

Repository

GitHub

Hosting

Vercel

Database

Supabase Cloud

Domain

Custom Domain

SSL

Automatic SSL

---

# 12. Development Tools

Source Code

Visual Studio Code

Version Control

Git

Repository

GitHub

Package Manager

npm

API Testing

Postman

Database Management

Supabase Dashboard

---

# 13. Browser Support

Desktop

- Google Chrome
- Microsoft Edge
- Mozilla Firefox

Mobile

- Chrome Android
- Safari iOS

---

# 14. UI Requirements

Landing Page harus:

- Mobile First
- Responsive
- Fast Loading
- SEO Friendly
- Dark Mode
- Modern UI
- Professional Corporate Look

CMS harus:

- Responsive
- Mudah digunakan
- Clean Dashboard
- Cepat dipelajari
- Konsisten pada seluruh halaman

---

# 15. Performance Target

Landing Page

- Load < 3 detik

Booking

- Maksimal 5 langkah

CMS

- Respon halaman < 2 detik

Image

- Optimized

SEO

- Score minimal 90

Accessibility

- Score minimal 90

---

# 16. Future Technology

Beberapa teknologi yang dipersiapkan untuk pengembangan berikutnya.

- Payment Gateway
- WhatsApp API
- Email Notification
- Push Notification
- Calendar Integration
- AI Customer Service
- AI Content Generator
- AI Marketing Assistant
- Multi Vendor
- Multi Branch
- Multi Company

---

# 17. Revision History

| Version | Date       | Description        |
| ------- | ---------- | ------------------ |
| 1.0     | YYYY-MM-DD | Initial Tech Stack |

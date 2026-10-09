# Perpustakaan REST API

## Deskripsi & Tujuan Proyek
API ini dibangun untuk mengelola sistem pencatatan peminjaman buku perpustakaan. API mendukung operasi CRUD untuk data peminjaman dan fitur penyaringan berdasarkan status peminjaman (misal: Dipinjam, Dikembalikan, Terlambat). Proyek ini menggunakan Node.js, Express, dan Supabase.

## Struktur Data / Schema
- **members**: `id` (UUID), `name` (Text), `email` (Text), `phone` (Text)
- **books**: `id` (UUID), `title` (Text), `author` (Text), `stock` (Integer)
- **loans**: `id` (UUID), `member_id` (UUID/FK), `book_id` (UUID/FK), `borrow_date` (Date), `due_date` (Date), `status` (Text)

## Contoh Request dan Response
**GET /api/loans?status=Terlambat**
- **Response (200 OK):**
  ```json
  [
    {
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "member_id": "...",
      "book_id": "...",
      "borrow_date": "2026-10-01",
      "due_date": "2026-10-08",
      "status": "Terlambat",
      "members": { "name": "Budi Santoso" },
      "books": { "title": "Bumi Manusia" }
    }
  ]

- **Vercel Base URL:** https://responsi-mod1-prak-ppb.vercel.app
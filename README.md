# 📚 Tugas Akhir Pemrograman Web - Perpustakaan Digital

Aplikasi web manajemen perpustakaan digital yang dibangun sebagai **proyek akhir mata kuliah Pemrograman Web**. Aplikasi ini memungkinkan pengelolaan koleksi buku secara lengkap (tambah, lihat, ubah, hapus) dengan pencarian dan pagination.

> **Mata Kuliah:** Pemrograman Web — Semester 5
> **Tema:** Perpustakaan Digital
> **Dosen Pengampu:** Dr. Zulkifli Tahir
 
## 👥 Anggota Kelompok
 
| No | Nama                       | NIM |
| -- | -------------------------- | --- |
| 1  | Dita Ayodya Al Mira        | 008 |
| 2  | Aulia Dwinatasha Lubis     | 050 |
| 3  | Annisa Latifa Alquraini    | 038 |
| 4  | Siti Nurauliya             | 003 |
| 5  | Andi Rosiqah S.            | 030 |
| 6  | Andi Nurul Aliyah Haris    | 080 |

---

## ✨ Fitur

- **CRUD Buku** — tambah, lihat detail, ubah, dan hapus data buku
- **Pencarian** — cari buku berdasarkan judul / penulis
- **Pagination** — daftar buku ditampilkan per halaman
- **Validasi Form** — validasi input di sisi server dengan pesan error yang jelas
- **Antarmuka Responsif** — tampilan menyesuaikan perangkat desktop maupun mobile
- [Tambahkan fitur lain, mis. autentikasi, kategori, peminjaman, upload cover]

## 🛠️ Teknologi

| Bagian     | Teknologi                |
| ---------- | ------------------------ |
| Framework  | Laravel 12               |
| Templating | Blade                    |
| Styling    | Tailwind CSS 4           |
| Database   | SQLite                   |
| Bahasa     | PHP 8.2+, JavaScript     |
| Build tool | Vite, npm                |

## 📋 Prasyarat

Pastikan sudah terpasang:

- PHP >= 8.2 (dengan ekstensi `pdo_sqlite`, `mbstring`, `openssl`)
- [Composer](https://getcomposer.org/)
- Node.js >= 18 dan npm
- Git

## 🚀 Instalasi & Menjalankan

```bash
# 1. Clone repository
git clone https://github.com/[username]/Pemrograman-Web.git
cd Pemrograman-Web/daftar-buku

# 2. Install dependensi PHP
composer install

# 3. Install dependensi frontend
npm install

# 4. Salin file environment & generate app key
cp .env.example .env
php artisan key:generate

# 5. Siapkan database SQLite
touch database/database.sqlite
php artisan migrate --seed

# 6. Jalankan aplikasi (dua terminal)
npm run dev          # terminal 1: Vite + Tailwind
php artisan serve    # terminal 2: server Laravel
```

Buka **http://127.0.0.1:8000** di browser.

> **Windows (CMD/PowerShell):** ganti `cp .env.example .env` dengan `copy .env.example .env`, dan buat file `database/database.sqlite` secara manual.

### Konfigurasi `.env`

Pastikan pengaturan database menggunakan SQLite:

```env
DB_CONNECTION=sqlite
```

## 📁 Struktur Proyek

```
daftar-buku/
├── app/
│   ├── Http/Controllers/   # BukuController (logika CRUD)
│   └── Models/             # Model Buku
├── database/
│   ├── migrations/         # Skema tabel buku
│   ├── seeders/            # Data contoh
│   └── database.sqlite     # Database SQLite
├── resources/
│   ├── css/                # Tailwind CSS
│   └── views/              # Template Blade
│       ├── layouts/
│       └── buku/           # index, create, edit, show
├── routes/
│   └── web.php             # Definisi route
└── README.md
```

## 🗄️ Skema Database

**Tabel `bukus`** *(sesuaikan dengan migration Anda)*

| Kolom         | Tipe      | Keterangan          |
| ------------- | --------- | ------------------- |
| `id`          | bigint    | Primary key         |
| `judul`       | string    | Judul buku          |
| `penulis`     | string    | Nama penulis        |
| `penerbit`    | string    | Nama penerbit       |
| `tahun_terbit`| year      | Tahun terbit        |
| `created_at`  | timestamp | Waktu dibuat        |
| `updated_at`  | timestamp | Waktu diperbarui    |

## 🔗 Daftar Route

| Method | URL              | Aksi                    |
| ------ | ---------------- | ----------------------- |
| GET    | `/buku`          | Daftar buku (+ cari)    |
| GET    | `/buku/create`   | Form tambah buku        |
| POST   | `/buku`          | Simpan buku baru        |
| GET    | `/buku/{id}`     | Detail buku             |
| GET    | `/buku/{id}/edit`| Form ubah buku          |
| PUT    | `/buku/{id}`     | Perbarui buku           |
| DELETE | `/buku/{id}`     | Hapus buku              |

## 🖼️ Screenshot

<!-- Tambahkan screenshot aplikasi di sini -->
| Daftar Buku | Form Tambah |
| ----------- | ----------- |
| ![Daftar](docs/daftar.png) | ![Tambah](docs/tambah.png) |

## 🧪 Menjalankan Test

```bash
php artisan test
```

## 📝 Catatan Pengembangan

- Gunakan `php artisan migrate:fresh --seed` untuk mengatur ulang database.
- Jalankan `npm run build` untuk membuat aset produksi.

## 📄 Lisensi

Proyek ini dibuat untuk keperluan pembelajaran. Dilisensikan di bawah [MIT License](LICENSE).
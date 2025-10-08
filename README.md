# RESTful API CRUD dengan Express.js & PostgreSQL

## 📘 Deskripsi Proyek

Proyek ini merupakan implementasi **RESTful API CRUD (Create, Read, Update, Delete)** menggunakan **Express.js** sebagai pemenuhan tugas backend Camp Batch 3 di Celerates.

---

## 🚀 Fitur Utama

- **Create** : Menambahkan data mahasiswa baru ke dalam database
- **Read** : Menampilkan seluruh data mahasiswa atau berdasarkan ID tertentu
- **Update** : Memperbarui data mahasiswa berdasarkan ID
- **Delete** : Menghapus data mahasiswa dari database
- **Koneksi PostgreSQL** :Menggunakan library `pg`
- **Konfigurasi Lingkungan (.env)** : Menyembunyikan kredensial sensitif
- **Error Handling** : Menangani kesalahan API dengan respons JSON yang jelas
- **CORS Support** : Mengizinkan akses API dari domain berbeda
- **Testing dengan Postman** : Semua endpoint diuji dan berfungsi sempurna

---

## 🧩 Struktur Proyek

```

api_express_pg/
│
├── index.js
├── .env
├── package.json
│
├── src/
│   ├── config/
│   │   └── db.js
│   ├── models/
│   │   └── studentsModel.js
│   ├── controllers/
│   │   └── studentsController.js
│   └── routes/
│       └── studentsRoutes.js
│
└── README.md

```

---

## ⚙️ Teknologi yang Digunakan

- **Node.js v18+**
- **Express.js**
- **PostgreSQL v14+**
- **pg** (PostgreSQL Client)
- **dotenv** (Konfigurasi environment)
- **nodemon** (Hot reload saat pengembangan)
- **CORS** (Cross-Origin Resource Sharing)

---

## 🛠️ Cara Menjalankan Proyek

### 1️⃣ Clone Repository

```bash
git clone https://github.com/username/api_express_pg.git
cd api_express_pg
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Konfigurasi Environment

Buat file `.env` di root project:

```env
PORT=5000
DB_USER=postgres
DB_HOST=localhost
DB_NAME=kampus
DB_PASS=your_password
DB_PORT=5432
```

> Ganti `your_password` dengan password PostgreSQL kamu.

### 4️⃣ Buat Database dan Tabel

Masuk ke PostgreSQL:

```sql
CREATE DATABASE kampus;
\c kampus

CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  major VARCHAR(50),
  age INT
);
```

### 5️⃣ Jalankan Server

```bash
npm run dev
```

Jika berhasil, muncul pesan:

```
✅ Server running on port 5000
```

---

## 🌐 Endpoint API

| Method     | Endpoint            | Deskripsi                                 |
| ---------- | ------------------- | ----------------------------------------- |
| **GET**    | `/api/students`     | Menampilkan semua data mahasiswa          |
| **GET**    | `/api/students/:id` | Menampilkan data mahasiswa berdasarkan ID |
| **POST**   | `/api/students`     | Menambahkan data mahasiswa baru           |
| **PUT**    | `/api/students/:id` | Memperbarui data mahasiswa berdasarkan ID |
| **DELETE** | `/api/students/:id` | Menghapus data mahasiswa berdasarkan ID   |

### 🧾 Contoh Body (POST / PUT)

```json
{
  "name": "John Doe",
  "major": "Informatika",
  "age": 22
}
```

### 🔄 Contoh Respons Sukses

```json
{
  "id": 1,
  "name": "John Doe",
  "major": "Informatika",
  "age": 22
}
```

---

## 🧪 Koleksi Postman

Kamu dapat menguji seluruh endpoint menggunakan koleksi Postman berikut:

🔗 **Link Koleksi Postman:**
[https://www.postman.com/workspace/Celerates~ba0d6cc4-e207-4fdb-90f9-2bec0eb10dd4/collection/32771563-19229e58-1294-480a-9d36-c1bf348154be?action=share&source=copy-link&creator=32771563](https://www.postman.com/workspace/Celerates~ba0d6cc4-e207-4fdb-90f9-2bec0eb10dd4/collection/32771563-19229e58-1294-480a-9d36-c1bf348154be?action=share&source=copy-link&creator=32771563)

---

## 🧾 Contoh Script di package.json

Tambahkan script berikut agar server dapat dijalankan dengan hot reload:

```json
"scripts": {
  "start": "node index.js",
  "dev": "nodemon index.js"
}
```

---

## 🛡️ Error Handling

Semua operasi dilindungi dengan try-catch dan menghasilkan pesan error yang ramah pengguna:

```json
{
  "message": "Error fetching student"
}
```

---

## 🌟 Kontributor

**Abdul Rohman Maulidhi**

Terima kasih telah meluangkan waktu untuk melihat proyek ini!
Semoga kode ini bermanfaat sebagai referensi pembelajaran dan inspirasi untuk mengembangkan aplikasi backend yang lebih kompleks. Jika proyek ini membantu, jangan lupa untuk ⭐ **Star** repository ini di GitHub!

> _"Code with logic, learn with passion, and share with kindness."_

---

© 2025 Abdul Rohman Maulidhi — All Rights Reserved.

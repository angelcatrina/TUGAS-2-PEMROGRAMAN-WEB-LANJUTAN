#  Tugas 2 - Pemrograman Web Lanjutan

### Implementasi REST API dengan FastAPI, SQLAlchemy, dan SQLite

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-Framework-009688?logo=fastapi)
![SQLite](https://img.shields.io/badge/Database-SQLite-003B57?logo=sqlite)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

#  Deskripsi Project

Project ini merupakan implementasi **REST API sederhana** menggunakan **FastAPI** yang dibuat untuk memenuhi **Tugas 2 Mata Kuliah Pemrograman Web Lanjutan**.

Aplikasi ini menggunakan **SQLite** sebagai database dan **SQLAlchemy** sebagai ORM (Object Relational Mapping) untuk mengelola data. Validasi data API dilakukan menggunakan **Pydantic** agar struktur data yang dikirimkan API tetap konsisten dan aman.

Project ini mengimplementasikan **CRUD dasar**, khususnya operasi **Read** untuk mengambil data item dari database melalui endpoint API.

---

#  Tujuan Tugas

Tujuan dari pembuatan project ini adalah untuk:

* Memahami konsep **REST API**
* Menggunakan framework **FastAPI**
* Mengimplementasikan **SQLAlchemy ORM**
* Menggunakan **SQLite** sebagai database
* Menggunakan **Pydantic** untuk validasi data
* Mengimplementasikan endpoint API dasar

---

#  Teknologi yang Digunakan

| Teknologi  | Fungsi                                |
| ---------- | ------------------------------------- |
| Python     | Bahasa pemrograman utama              |
| FastAPI    | Framework untuk membuat REST API      |
| SQLAlchemy | ORM untuk mengelola database          |
| SQLite     | Database lokal                        |
| Pydantic   | Validasi dan serialisasi data         |
| Uvicorn    | ASGI server untuk menjalankan FastAPI |

---

# Arsitektur Project

Project ini menggunakan struktur modular agar kode lebih rapi dan mudah dipelihara.

```id="gibizk"
TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN
│
├── main.py
├── database.py
├── models.py
├── schemas.py
├── items.db
├── requirements.txt
└── README.md
```

### Penjelasan File

| File             | Fungsi                                       |
| ---------------- | -------------------------------------------- |
| main.py          | File utama yang menjalankan aplikasi FastAPI |
| database.py      | Konfigurasi koneksi database SQLite          |
| models.py        | Mendefinisikan struktur tabel database       |
| schemas.py       | Schema validasi data menggunakan Pydantic    |
| items.db         | Database SQLite                              |
| requirements.txt | Daftar dependency project                    |

---

#  Cara Menjalankan Project

###  Clone Repository

```id="9mqvhm"
git clone https://github.com/angelcatrina/TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN.git
```

###  Masuk ke Folder Project

```id="s4pku9"
cd TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN
```

###  Install Dependencies

```id="clzvsz"
pip install -r requirements.txt
```

###  Jalankan Server

```id="0n0xsy"
uvicorn main:app --reload
```

Server akan berjalan di:

```id="3gn61q"
http://127.0.0.1:8000
```

---

#  Dokumentasi API

FastAPI menyediakan dokumentasi API otomatis yang bisa diakses melalui browser.

Swagger UI:

```id="sv1g02"
http://127.0.0.1:8000/docs
```

ReDoc:

```id="p08mpj"
http://127.0.0.1:8000/redoc
```

---

# 🔗 Endpoint API

Berikut endpoint yang diimplementasikan pada project ini:

| Method | Endpoint    | Deskripsi                     |
| ------ | ----------- | ----------------------------- |
| GET    | /items/     | Mengambil semua data item     |
| GET    | /items/{id} | Mengambil item berdasarkan ID |

---

#  Contoh Response API

### GET /items/

```id="t8pcw2"
[
  {
    "id": 1,
    "name": "Laptop",
    "description": "Laptop untuk bekerja"
  },
  {
    "id": 2,
    "name": "Mouse",
    "description": "Mouse wireless"
  }
]
```

---

### GET /items/{id}

```id="3t20ge"
{
  "id": 1,
  "name": "Laptop",
  "description": "Laptop untuk bekerja"
}
```

---

#  Validasi Data dengan Pydantic

Validasi data API dilakukan menggunakan **Pydantic Schema** yang terdapat pada file:

```id="y1kpcn"
schemas.py
```

Schema ini memastikan bahwa data yang dikirim oleh API memiliki struktur yang benar sebelum dikirim ke client.

---



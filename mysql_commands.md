# 🗄️ Panduan Lengkap MySQL

<div align="center">

![MySQL Logo](https://www.mysql.com/common/logos/logo-mysql-170x115.png)

> 💡 **Panduan Lengkap MySQL** - Referensi cepat untuk menguasai perintah-perintah MySQL dengan mudah

[![MySQL Version](https://img.shields.io/badge/MySQL-8.0-blue)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Contributors](https://img.shields.io/badge/Contributors-Welcome-orange)](CONTRIBUTING.md)

</div>

## 📋 Fitur Utama
- ✅ Panduan lengkap dari dasar hingga lanjutan
- 📚 Glosarium istilah MySQL terlengkap
- 🎯 Contoh kasus dan praktik terbaik
- 🔧 Tips dan trik optimasi
- 🛠️ Troubleshooting umum
- 📊 Monitoring dan maintenance
- 🔒 Keamanan database
- 🚀 High availability

## 🎯 Target Pembaca
- 👨‍💻 Developer pemula
- 👩‍💻 Database administrator
- 🎓 Mahasiswa
- 👨‍🏫 Dosen
- 👨‍🔧 System administrator

## 📚 Prasyarat
- Pengetahuan dasar komputer
- Pemahaman dasar database
- Akses ke MySQL Server
- Text editor atau IDE

## 📑 Daftar Isi
- [🗄️ Panduan Perintah MySQL](#️-panduan-perintah-mysql)
  - [📋 Fitur Utama](#-fitur-utama)
  - [🎯 Target Pembaca](#-target-pembaca)
  - [📚 Prasyarat](#-prasyarat)
  - [📑 Daftar Isi](#-daftar-isi)
  - [1. 🚀 Memulai dengan MySQL](#-memulai-dengan-mysql)
    - [1.1 📥 Instalasi MySQL](#-instalasi-mysql)
    - [1.2 🔍 Troubleshooting Umum](#-troubleshooting-umum)
    - [1.3 🎯 Contoh Kasus Sederhana](#-contoh-kasus-sederhana)
    - [1.4 📝 Tips untuk Pemula](#-tips-untuk-pemula)
  - [2. 📚 Panduan Belajar](#-panduan-belajar)
    - [2.1 🎯 Level Pembelajaran](#-level-pembelajaran)
    - [2.2 📋 Prasyarat Pembelajaran](#-prasyarat-pembelajaran)
    - [2.3 🎮 Latihan Praktis](#-latihan-praktis)
    - [2.4 📝 Tips Belajar](#-tips-belajar)
  - [3. 📋 Tipe Data](#-1-tipe-data)
  - [4. 📌 Perintah Dasar](#-2-perintah-dasar)
  - [5. 📊 Operasi Tabel](#-3-operasi-tabel)
  - [6. 🔄 Operasi Data (CRUD)](#-4-operasi-data-crud)
  - [7. 🔍 Query Lanjutan](#-5-query-lanjutan)
  - [8. 📊 Fungsi Agregasi](#-6-fungsi-agregasi)
  - [9. 📅 Fungsi Tanggal dan Waktu](#-7-fungsi-tanggal-dan-waktu)
  - [10. 📝 Fungsi String](#-8-fungsi-string)
  - [11. 🔢 Fungsi Numerik](#-9-fungsi-numerik)
  - [12. 📌 Indeks](#-10-indeks)
  - [13. 💾 Backup dan Restore](#-11-backup-dan-restore)
  - [14. 🔧 Praktik Terbaik MySQL](#-12-praktik-terbaik-mysql)
  - [15. 🔄 Replikasi MySQL](#-13-replikasi-mysql)
  - [16. 🚀 High Availability](#-14-high-availability)
  - [17. 📦 Migrasi Database](#-15-migrasi-database)
  - [18. 🛠️ MySQL Workbench](#️-16-mysql-workbench)
  - [19. ⚡ Optimasi Query](#-17-optimasi-query)
  - [20. 👥 Manajemen User dan Hak Akses](#-18-manajemen-user-dan-hak-akses)
  - [21. 🔒 Keamanan Database](#-19-keamanan-database)
  - [22. 💻 Best Practices Pengembangan](#-20-best-practices-pengembangan)
  - [23. 📚 Glosarium Istilah MySQL](#-22-glosarium-istilah-mysql)
    - [23.1 🔍 Cara Menggunakan Glosarium](#-cara-menggunakan-glosarium)
    - [23.2 Istilah Dasar](#1-istilah-dasar)
    - [23.3 Istilah Teknis](#2-istilah-teknis)
    - [23.4 Istilah Operasi](#3-istilah-operasi)
    - [23.5 Istilah Performa](#4-istilah-performa)
    - [23.6 Istilah Keamanan](#5-istilah-keamanan)
    - [23.7 Istilah Development](#6-istilah-development)
    - [23.8 Istilah Error](#7-istilah-error)
    - [23.9 Istilah Monitoring](#8-istilah-monitoring)
    - [23.10 Istilah Fungsi MySQL](#9-istilah-fungsi-mysql)
    - [23.11 Istilah Tipe Data](#10-istilah-tipe-data)
    - [23.12 Istilah Join](#11-istilah-join)
    - [23.13 Istilah Optimasi](#12-istilah-optimasi)
    - [23.14 Istilah Replikasi](#13-istilah-replikasi)
    - [23.15 Istilah Backup](#14-istilah-backup)
    - [23.16 Istilah Keamanan Lanjutan](#15-istilah-keamanan-lanjutan)
  - [24. 📝 Catatan Penting](#-catatan-penting)
  - [25. 🤝 Berkontribusi](#-berkontribusi)
  - [26. 📄 Lisensi](#-lisensi)
  - [27. 🙏 Terima Kasih](#-terima-kasih)

---

## 🚀 Memulai dengan MySQL

### 📥 Instalasi MySQL

1. **Windows**
   ```bash
   # Download MySQL Installer dari website resmi
   # https://dev.mysql.com/downloads/installer/
   
   # Ikuti langkah instalasi:
   # 1. Pilih "Developer Default"
   # 2. Klik "Next" sampai selesai
   # 3. Set password root
   # 4. Selesai
   ```

2. **Linux (Ubuntu)**
   ```bash
   # Update package list
   sudo apt update
   
   # Install MySQL
   sudo apt install mysql-server
   
   # Start MySQL service
   sudo systemctl start mysql
   
   # Enable MySQL on boot
   sudo systemctl enable mysql
   
   # Secure installation
   sudo mysql_secure_installation
   ```

3. **macOS**
   ```bash
   # Menggunakan Homebrew
   brew install mysql
   
   # Start MySQL service
   brew services start mysql
   
   # Secure installation
   mysql_secure_installation
   ```

### 🔍 Troubleshooting Umum

1. **Tidak bisa koneksi ke MySQL**
   ```bash
   # Cek status service
   sudo systemctl status mysql
   
   # Restart service
   sudo systemctl restart mysql
   
   # Cek port
   sudo netstat -tlnp | grep mysql
   ```

2. **Lupa password root**
   ```bash
   # Stop MySQL
   sudo systemctl stop mysql
   
   # Start MySQL dengan skip grant tables
   sudo mysqld_safe --skip-grant-tables &
   
   # Reset password
   mysql -u root
   ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';
   ```

3. **Error saat instalasi**
   ```bash
   # Hapus instalasi yang rusak
   sudo apt remove --purge mysql*
   sudo apt autoremove
   
   # Install ulang
   sudo apt update
   sudo apt install mysql-server
   ```

### 🎯 Contoh Kasus Sederhana

1. **Membuat Database Toko Online**
   ```sql
   -- Buat database
   CREATE DATABASE toko_online;
   USE toko_online;
   
   -- Buat tabel kategori
   CREATE TABLE kategori (
       id INT PRIMARY KEY AUTO_INCREMENT,
       nama VARCHAR(50) NOT NULL
   );
   
   -- Buat tabel produk
   CREATE TABLE produk (
       id INT PRIMARY KEY AUTO_INCREMENT,
       nama VARCHAR(100) NOT NULL,
       harga DECIMAL(10,2) NOT NULL,
       stok INT NOT NULL DEFAULT 0,
       kategori_id INT,
       FOREIGN KEY (kategori_id) REFERENCES kategori(id)
   );
   
   -- Insert data kategori
   INSERT INTO kategori (nama) VALUES 
       ('Elektronik'),
       ('Pakaian'),
       ('Makanan');
   
   -- Insert data produk
   INSERT INTO produk (nama, harga, stok, kategori_id) VALUES 
       ('Laptop', 5000000, 10, 1),
       ('Smartphone', 2000000, 15, 1),
       ('Kemeja', 150000, 20, 2);
   ```

2. **Query Dasar untuk Toko Online**
   ```sql
   -- Lihat semua produk
   SELECT * FROM produk;
   
   -- Lihat produk dengan kategori
   SELECT p.nama, p.harga, k.nama as kategori
   FROM produk p
   JOIN kategori k ON p.kategori_id = k.id;
   
   -- Hitung total produk per kategori
   SELECT k.nama, COUNT(p.id) as total_produk
   FROM kategori k
   LEFT JOIN produk p ON k.id = p.kategori_id
   GROUP BY k.nama;
   ```

### 📝 Tips untuk Pemula

1. **Gunakan Tools Visual**
   - MySQL Workbench untuk manajemen database
   - phpMyAdmin untuk akses web
   - DBeaver untuk koneksi database

2. **Buat Database Dummy**
   - Gunakan database toko online sebagai latihan
   - Coba berbagai jenis query
   - Eksperimen dengan struktur tabel

3. **Pelajari Perintah Dasar**
   - SELECT untuk membaca data
   - INSERT untuk menambah data
   - UPDATE untuk mengubah data
   - DELETE untuk menghapus data

4. **Gunakan Dokumentasi**
   - Baca error message dengan teliti
   - Cari solusi di Stack Overflow
   - Gunakan dokumentasi resmi MySQL

## 📚 Panduan Belajar

### 🎯 Level Pembelajaran

1. **Basic (Level 1-5)**
   - Tipe Data
   - Perintah Dasar
   - Operasi Tabel
   - Operasi Data (CRUD)
   - Query Lanjutan

2. **Intermediate (Level 6-10)**
   - Fungsi Agregasi
   - Fungsi Tanggal dan Waktu
   - Fungsi String
   - Fungsi Numerik
   - Indeks

3. **Advanced (Level 11-15)**
   - Backup dan Restore
   - Praktik Terbaik MySQL
   - Monitoring dan Maintenance
   - Replikasi MySQL
   - High Availability

4. **Expert (Level 16-21)**
   - Migrasi Database
   - MySQL Workbench
   - Optimasi Query
   - Manajemen User dan Hak Akses
   - Keamanan Database
   - Best Practices Pengembangan

### 📋 Prasyarat Pembelajaran

1. **Level Basic**
   - Pemahaman dasar database
   - Pengenalan SQL
   - Penggunaan command line

2. **Level Intermediate**
   - Menguasai perintah dasar MySQL
   - Pemahaman struktur database
   - Penggunaan query sederhana

3. **Level Advanced**
   - Menguasai fungsi-fungsi MySQL
   - Pemahaman indeks dan optimasi
   - Pengalaman dengan database production

4. **Level Expert**
   - Pengalaman dengan database skala besar
   - Pemahaman sistem terdistribusi
   - Pengalaman dengan high availability

### 🎮 Latihan Praktis

1. **Level Basic**
   - Membuat database toko online sederhana
   - Mengelola data produk dan kategori
   - Membuat query untuk laporan penjualan

2. **Level Intermediate**
   - Mengoptimasi query dengan indeks
   - Membuat fungsi agregasi untuk analisis
   - Mengelola data dengan berbagai tipe data

3. **Level Advanced**
   - Mengatur backup otomatis
   - Monitoring performa database
   - Mengatur replikasi master-slave

4. **Level Expert**
   - Migrasi database skala besar
   - Mengatur high availability
   - Mengoptimasi keamanan database

### 📝 Tips Belajar

1. **Praktik Teratur**
   - Buat database dummy untuk latihan
   - Coba setiap perintah yang dipelajari
   - Dokumentasikan hasil belajar

2. **Gunakan Tools**
   - MySQL Workbench untuk manajemen visual
   - Command line untuk pemahaman mendalam
   - Monitoring tools untuk analisis

3. **Ikuti Best Practices**
   - Selalu backup data
   - Gunakan prepared statements
   - Optimasi query secara berkala

4. **Bergabung dengan Komunitas**
   - Forum MySQL
   - Stack Overflow
   - GitHub discussions

## 📋 1. Tipe Data

<details>
<summary>🔢 Tipe Data Numerik</summary>

```sql
-- TINYINT
-- Ukuran: 1 byte
-- Range: -128 sampai 127 (signed) atau 0 sampai 255 (unsigned)
CREATE TABLE example_tinyint (
    id TINYINT,                    -- signed: -128 sampai 127
    age TINYINT UNSIGNED,          -- unsigned: 0 sampai 255
    status TINYINT(1)              -- sering digunakan untuk boolean
);

-- SMALLINT
-- Ukuran: 2 bytes
-- Range: -32,768 sampai 32,767 (signed) atau 0 sampai 65,535 (unsigned)
CREATE TABLE example_smallint (
    id SMALLINT,                   -- signed: -32,768 sampai 32,767
    code SMALLINT UNSIGNED         -- unsigned: 0 sampai 65,535
);

-- MEDIUMINT
-- Ukuran: 3 bytes
-- Range: -8,388,608 sampai 8,388,607 (signed) atau 0 sampai 16,777,215 (unsigned)
CREATE TABLE example_mediumint (
    id MEDIUMINT,                  -- signed: -8,388,608 sampai 8,388,607
    code MEDIUMINT UNSIGNED        -- unsigned: 0 sampai 16,777,215
);

-- INT/INTEGER
-- Ukuran: 4 bytes
-- Range: -2,147,483,648 sampai 2,147,483,647 (signed) atau 0 sampai 4,294,967,295 (unsigned)
CREATE TABLE example_int (
    id INT,                        -- signed: -2,147,483,648 sampai 2,147,483,647
    code INT UNSIGNED,             -- unsigned: 0 sampai 4,294,967,295
    auto_id INT AUTO_INCREMENT     -- sering digunakan untuk primary key
);

-- BIGINT
-- Ukuran: 8 bytes
-- Range: -9,223,372,036,854,775,808 sampai 9,223,372,036,854,775,807 (signed)
CREATE TABLE example_bigint (
    id BIGINT,                     -- untuk nilai yang sangat besar
    code BIGINT UNSIGNED
);

-- DECIMAL/NUMERIC
-- Ukuran: Variabel
-- Presisi: M (total digit), D (digit desimal)
CREATE TABLE example_decimal (
    price DECIMAL(10,2),           -- total 10 digit, 2 digit desimal
    amount DECIMAL(20,4)           -- untuk nilai keuangan yang presisi
);

-- FLOAT
-- Ukuran: 4 bytes
-- Presisi: ~7 digit
CREATE TABLE example_float (
    value FLOAT,                   -- untuk nilai desimal dengan presisi sedang
    amount FLOAT(10,2)             -- tidak disarankan untuk nilai keuangan
);

-- DOUBLE
-- Ukuran: 8 bytes
-- Presisi: ~15 digit
CREATE TABLE example_double (
    value DOUBLE,                  -- untuk nilai desimal dengan presisi tinggi
    amount DOUBLE(20,4)            -- tidak disarankan untuk nilai keuangan
);
```

> 💡 **Tips**: 
> - Gunakan UNSIGNED untuk nilai yang selalu positif
> - Pilih tipe data yang sesuai dengan range nilai yang dibutuhkan
> - Untuk nilai keuangan, gunakan DECIMAL untuk presisi yang tepat
> - Hindari FLOAT dan DOUBLE untuk nilai keuangan
> - Gunakan INT atau BIGINT untuk primary key
</details>

<details>
<summary>📝 Tipe Data String</summary>

```sql
-- CHAR
-- Panjang tetap, 0-255 karakter
CREATE TABLE example_char (
    code CHAR(5),                  -- selalu menggunakan 5 karakter
    status CHAR(1)                 -- untuk nilai tetap seperti 'Y'/'N'
);

-- VARCHAR
-- Panjang variabel, 0-65,535 karakter
CREATE TABLE example_varchar (
    name VARCHAR(100),             -- maksimal 100 karakter
    description VARCHAR(255)       -- untuk teks dengan panjang bervariasi
);

-- TEXT
-- Panjang variabel, maksimal 65,535 karakter
CREATE TABLE example_text (
    content TEXT,                  -- untuk teks panjang
    description TEXT               -- tidak bisa diindeks secara penuh
);

-- MEDIUMTEXT
-- Panjang variabel, maksimal 16,777,215 karakter
CREATE TABLE example_mediumtext (
    content MEDIUMTEXT            -- untuk teks yang sangat panjang
);

-- LONGTEXT
-- Panjang variabel, maksimal 4,294,967,295 karakter
CREATE TABLE example_longtext (
    content LONGTEXT              -- untuk teks yang sangat sangat panjang
);

-- ENUM
-- Pilihan nilai tetap
CREATE TABLE example_enum (
    status ENUM('active', 'inactive', 'pending'),
    priority ENUM('low', 'medium', 'high')
);

-- SET
-- Kumpulan nilai tetap
CREATE TABLE example_set (
    permissions SET('read', 'write', 'delete', 'admin')
);
```

> 💡 **Tips**: 
> - Gunakan CHAR untuk string dengan panjang tetap
> - Gunakan VARCHAR untuk string dengan panjang bervariasi
> - Pilih panjang VARCHAR yang sesuai dengan kebutuhan
> - Gunakan TEXT untuk konten yang panjang
> - ENUM berguna untuk kolom dengan pilihan nilai tetap
> - SET berguna untuk kolom dengan multiple pilihan nilai
</details>

<details>
<summary>📅 Tipe Data Tanggal dan Waktu</summary>

```sql
-- DATE
-- Format: 'YYYY-MM-DD'
CREATE TABLE example_date (
    birth_date DATE,              -- untuk menyimpan tanggal
    start_date DATE
);

-- TIME
-- Format: 'HH:MM:SS'
CREATE TABLE example_time (
    start_time TIME,              -- untuk menyimpan waktu
    duration TIME
);

-- DATETIME
-- Format: 'YYYY-MM-DD HH:MM:SS'
CREATE TABLE example_datetime (
    created_at DATETIME,          -- untuk menyimpan tanggal dan waktu
    updated_at DATETIME
);

-- TIMESTAMP
-- Format: 'YYYY-MM-DD HH:MM:SS'
-- Range: '1970-01-01 00:00:01' UTC sampai '2038-01-19 03:14:07' UTC
CREATE TABLE example_timestamp (
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

-- YEAR
-- Format: YYYY
CREATE TABLE example_year (
    birth_year YEAR,              -- untuk menyimpan tahun
    graduation_year YEAR
);
```

> 💡 **Tips**: 
> - Gunakan DATE untuk menyimpan tanggal saja
> - Gunakan TIME untuk menyimpan waktu saja
> - Gunakan DATETIME untuk menyimpan tanggal dan waktu
> - TIMESTAMP otomatis mengkonversi ke UTC
> - TIMESTAMP memiliki range yang terbatas
> - Gunakan YEAR untuk menyimpan tahun saja
</details>

<details>
<summary>📦 Tipe Data Spesial</summary>

```sql
-- JSON
-- Untuk menyimpan data JSON
CREATE TABLE example_json (
    settings JSON,                -- untuk menyimpan data JSON
    metadata JSON
);

-- BLOB
-- Untuk menyimpan data biner
CREATE TABLE example_blob (
    image BLOB,                   -- untuk menyimpan gambar
    document MEDIUMBLOB,          -- untuk menyimpan dokumen
    video LONGBLOB                -- untuk menyimpan video
);

-- GEOMETRY
-- Untuk menyimpan data spasial
CREATE TABLE example_geometry (
    location POINT,               -- untuk menyimpan titik
    area POLYGON,                 -- untuk menyimpan area
    route LINESTRING              -- untuk menyimpan rute
);

-- BIT
-- Untuk menyimpan nilai bit
CREATE TABLE example_bit (
    flags BIT(8),                 -- untuk menyimpan 8 bit
    permissions BIT(16)           -- untuk menyimpan 16 bit
);
```

> 💡 **Tips**: 
> - JSON berguna untuk menyimpan data yang fleksibel
> - BLOB untuk menyimpan file biner
> - GEOMETRY untuk aplikasi yang membutuhkan data spasial
> - BIT untuk menyimpan flag atau permission
</details>

## 📌 2. Perintah Dasar

<details>
<summary>🔌 Menghubungkan ke MySQL</summary>

```sql
-- Template
mysql -u [username] -p

-- Contoh
mysql -u root -p
```

> 💡 **Tips**: 
> - Ganti `[username]` dengan nama pengguna MySQL Anda
> - Setelah menekan Enter, masukkan password Anda
> - Untuk keluar dari MySQL, ketik `exit` atau `quit`
</details>

<details>
<summary>📂 Melihat Database yang Tersedia</summary>

```sql
-- Template Dasar
SHOW DATABASES;

-- Template dengan LIKE
SHOW DATABASES LIKE 'pattern%';

-- Template dengan WHERE
SHOW DATABASES WHERE `Database` LIKE 'pattern%';

-- Contoh
SHOW DATABASES;
SHOW DATABASES LIKE 'test%';
SHOW DATABASES WHERE `Database` LIKE 'prod%';

-- Contoh Output
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql             |
| performance_schema|
| sys               |
| test_db           |
+--------------------+

-- Melihat Database dengan Informasi Detail
SELECT 
    SCHEMA_NAME as Database,
    DEFAULT_CHARACTER_SET_NAME as Charset,
    DEFAULT_COLLATION_NAME as Collation
FROM information_schema.SCHEMATA;

-- Melihat Database dengan Ukuran
SELECT 
    table_schema as Database,
    ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) as Size_MB
FROM information_schema.TABLES
GROUP BY table_schema;
```

> 💡 **Tips**: 
> - Perintah ini akan menampilkan semua database yang Anda miliki akses
> - Database system seperti `information_schema`, `mysql`, `performance_schema`, dan `sys` adalah database bawaan MySQL
> - Gunakan LIKE untuk memfilter database berdasarkan pola nama
> - Gunakan information_schema untuk mendapatkan informasi lebih detail tentang database
> - Perhatikan hak akses saat menggunakan perintah ini
</details>

<details>
<summary>➕ Membuat Database</summary>

```sql
-- Template
CREATE DATABASE [nama_database];

-- Contoh
CREATE DATABASE toko_online;

-- Dengan karakter set dan collation
CREATE DATABASE toko_online
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

> 💡 **Tips**: 
> - Gunakan nama yang deskriptif untuk database
> - Hindari penggunaan spasi dalam nama database
> - Gunakan karakter set `utf8mb4` untuk mendukung emoji dan karakter khusus
</details>

<details>
<summary>🔄 Menggunakan Database</summary>

```sql
-- Template
USE [nama_database];

-- Contoh
USE toko_online;
```

> 💡 **Tips**: 
> - Pastikan database yang Anda pilih sudah ada
> - Anda bisa melihat database yang sedang aktif dengan perintah `SELECT DATABASE();`
</details>

<details>
<summary>📋 Melihat Tabel dalam Database</summary>

```sql
-- Template Dasar
SHOW TABLES;

-- Template dengan LIKE
SHOW TABLES LIKE 'pattern%';

-- Template dengan WHERE
SHOW TABLES WHERE `Tables_in_database` LIKE 'pattern%';

-- Template dengan FROM
SHOW TABLES FROM database_name;

-- Contoh
SHOW TABLES;
SHOW TABLES LIKE 'user%';
SHOW TABLES FROM mysql;
SHOW TABLES WHERE `Tables_in_mysql` LIKE 'user%';

-- Contoh Output
+------------------------+
| Tables_in_toko_online  |
+------------------------+
| customers             |
| orders               |
| products             |
+------------------------+

-- Melihat Tabel dengan Informasi Detail
SELECT 
    TABLE_NAME as Table,
    TABLE_TYPE as Type,
    ENGINE as Engine,
    TABLE_ROWS as Rows,
    AVG_ROW_LENGTH as Avg_Row_Length,
    DATA_LENGTH as Data_Length,
    INDEX_LENGTH as Index_Length
FROM information_schema.TABLES
WHERE TABLE_SCHEMA = 'database_name';

-- Melihat Tabel dengan Kolom
SELECT 
    TABLE_NAME as Table,
    COLUMN_NAME as Column,
    DATA_TYPE as Type,
    IS_NULLABLE as Nullable,
    COLUMN_DEFAULT as Default_Value
FROM information_schema.COLUMNS
WHERE TABLE_SCHEMA = 'database_name'
ORDER BY TABLE_NAME, ORDINAL_POSITION;
```

> 💡 **Tips**: 
> - Perintah ini hanya akan bekerja setelah Anda memilih database dengan `USE`
> - Untuk melihat struktur tabel, gunakan `DESCRIBE [nama_tabel]`
> - Gunakan LIKE untuk memfilter tabel berdasarkan pola nama
> - Gunakan information_schema untuk mendapatkan informasi detail tentang tabel
> - Perhatikan performa saat mengakses information_schema pada database besar
</details>

<details>
<summary>❌ Menghapus Database</summary>

```sql
-- Template
DROP DATABASE [nama_database];

-- Contoh
DROP DATABASE toko_online;
```

> ⚠️ **Peringatan**: 
> - Perintah ini akan menghapus database dan semua datanya secara permanen
> - Pastikan Anda memiliki backup sebelum menghapus database
</details>

## 📊 3. Operasi Tabel

<details>
<summary>➕ Membuat Tabel</summary>

```sql
-- Template
CREATE TABLE [nama_tabel] (
    [kolom1] [tipe_data] [constraint],
    [kolom2] [tipe_data] [constraint],
    ...
);

-- Contoh
CREATE TABLE products (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    stock INT DEFAULT 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

-- Dengan Foreign Key
CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```

> 💡 **Tips**: 
> - Definisikan tipe data yang sesuai untuk setiap kolom
> - Gunakan constraint untuk memastikan integritas data
> - Pertimbangkan penggunaan indeks untuk kolom yang sering dicari
</details>

<details>
<summary>👀 Melihat Struktur Tabel</summary>

```sql
-- Template
DESCRIBE [nama_tabel];
-- atau
DESC [nama_tabel];

-- Contoh
DESCRIBE products;

-- Contoh Output
+------------+---------------+------+-----+-------------------+----------------+
| Field      | Type         | Null | Key | Default          | Extra          |
+------------+---------------+------+-----+-------------------+----------------+
| id         | int          | NO   | PRI | NULL             | auto_increment |
| name       | varchar(100) | NO   |     | NULL             |                |
| price      | decimal(10,2)| NO   |     | NULL             |                |
| stock      | int          | YES  |     | 0                |                |
| created_at | timestamp    | YES  |     | CURRENT_TIMESTAMP |                |
+------------+---------------+------+-----+-------------------+----------------+
```

> 💡 **Tips**: 
> - Perintah ini juga bisa disingkat menjadi `DESC [nama_tabel]`
> - Untuk informasi lebih detail, gunakan `SHOW CREATE TABLE [nama_tabel]`
</details>

<details>
<summary>🔧 Mengubah Tabel</summary>

```sql
-- Menambah Kolom
ALTER TABLE [nama_tabel] ADD [kolom_baru] [tipe_data] [constraint];
ALTER TABLE products ADD description TEXT;
ALTER TABLE products ADD stock INT DEFAULT 0;
ALTER TABLE products ADD created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP;

-- Menghapus Kolom
ALTER TABLE [nama_tabel] DROP COLUMN [kolom_lama];
ALTER TABLE products DROP COLUMN old_column;
ALTER TABLE products DROP COLUMN unused_field;

-- Mengubah Tipe Data Kolom
ALTER TABLE [nama_tabel] MODIFY [kolom] [tipe_data_baru];
ALTER TABLE products MODIFY price DECIMAL(12,2);
ALTER TABLE products MODIFY name VARCHAR(200);
ALTER TABLE products MODIFY stock INT UNSIGNED;

-- Mengubah Nama Kolom
ALTER TABLE [nama_tabel] CHANGE [kolom_lama] [kolom_baru] [tipe_data];
ALTER TABLE products CHANGE name product_name VARCHAR(100);
ALTER TABLE products CHANGE old_price price DECIMAL(10,2);

-- Menambah Primary Key
ALTER TABLE [nama_tabel] ADD PRIMARY KEY ([kolom]);
ALTER TABLE products ADD PRIMARY KEY (id);

-- Menambah Foreign Key
ALTER TABLE [nama_tabel] ADD FOREIGN KEY ([kolom]) REFERENCES [tabel_referensi]([kolom]);
ALTER TABLE orders ADD FOREIGN KEY (customer_id) REFERENCES customers(id);

-- Menambah Unique Constraint
ALTER TABLE [nama_tabel] ADD UNIQUE ([kolom]);
ALTER TABLE products ADD UNIQUE (product_code);

-- Menambah Check Constraint
ALTER TABLE [nama_tabel] ADD CONSTRAINT [nama_constraint] CHECK ([kondisi]);
ALTER TABLE products ADD CONSTRAINT check_price CHECK (price > 0);
ALTER TABLE products ADD CONSTRAINT check_stock CHECK (stock >= 0);

-- Menghapus Constraint
ALTER TABLE [nama_tabel] DROP CONSTRAINT [nama_constraint];
ALTER TABLE products DROP CONSTRAINT check_price;

-- Mengubah Karakter Set dan Collation
ALTER TABLE [nama_tabel] CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
ALTER TABLE products CONVERT TO CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

-- Mengubah Engine
ALTER TABLE [nama_tabel] ENGINE = InnoDB;
ALTER TABLE products ENGINE = InnoDB;
```

> ⚠️ **Peringatan**: 
> - Selalu backup data sebelum melakukan perubahan struktur tabel
> - Perubahan tipe data bisa menyebabkan kehilangan data
> - Pastikan tidak ada constraint yang terganggu
> - Perhatikan performa saat mengubah tabel besar
</details>

<details>
<summary>🗑️ Menghapus Tabel</summary>

```sql
-- Template
DROP TABLE [nama_tabel];

-- Contoh
DROP TABLE products;
```

> ⚠️ **Peringatan**: 
> - Perintah ini akan menghapus tabel dan semua datanya secara permanen
> - Pastikan Anda memiliki backup sebelum menghapus tabel
</details>

## 🔄 4. Operasi Data (CRUD)

<details>
<summary>➕ Insert Data</summary>

```sql
-- Template Single Insert
INSERT INTO [nama_tabel] ([kolom1], [kolom2]) VALUES ('nilai1', 'nilai2');

-- Template Multiple Insert
INSERT INTO [nama_tabel] ([kolom1], [kolom2]) VALUES 
    ('nilai1', 'nilai2'),
    ('nilai3', 'nilai4');

-- Contoh
INSERT INTO products (name, price, stock) VALUES 
    ('Laptop', 1500000, 10),
    ('Smartphone', 5000000, 15);

-- Insert dengan SELECT
INSERT INTO products (name, price)
SELECT name, price FROM old_products;
```

> 💡 **Tips**: 
> - Pastikan urutan kolom sesuai dengan urutan nilai
> - Gunakan multiple insert untuk efisiensi
> - Untuk kolom dengan nilai default, bisa diabaikan dalam perintah INSERT
</details>

<details>
<summary>👀 Select Data</summary>

```sql
-- Template Dasar
SELECT [kolom1], [kolom2] FROM [nama_tabel] WHERE [kondisi];

-- Contoh
SELECT * FROM products;
SELECT name, price FROM products WHERE stock > 0;
SELECT * FROM products ORDER BY price DESC;
SELECT * FROM products LIMIT 10;

-- Dengan JOIN
SELECT p.name, c.name as category
FROM products p
JOIN categories c ON p.category_id = c.id;

-- Dengan GROUP BY
SELECT category_id, COUNT(*) as total_products
FROM products
GROUP BY category_id;
```

> 💡 **Tips**: 
> - Gunakan `SELECT` dengan bijak, hindari `SELECT *` jika tidak diperlukan
> - Gunakan alias untuk membuat query lebih mudah dibaca
> - Kombinasikan dengan WHERE, ORDER BY, dan LIMIT sesuai kebutuhan
</details>

<details>
<summary>✏️ Update Data</summary>

```sql
-- Template Dasar
UPDATE [nama_tabel] SET [kolom] = 'nilai_baru' WHERE [kondisi];

-- Update Single Row
UPDATE products SET price = 1600000 WHERE id = 1;
UPDATE products SET stock = stock - 1 WHERE id = 1;
UPDATE products SET status = 'inactive' WHERE id = 1;

-- Update Multiple Columns
UPDATE products SET 
    price = 1600000,
    stock = 20,
    updated_at = CURRENT_TIMESTAMP
WHERE id = 1;

-- Update dengan Kondisi
UPDATE products SET price = price * 1.1 WHERE category_id = 1;
UPDATE products SET stock = 0 WHERE stock < 0;
UPDATE products SET status = 'out_of_stock' WHERE stock = 0;

-- Update dengan JOIN
UPDATE products p
JOIN categories c ON p.category_id = c.id
SET p.price = p.price * 1.1
WHERE c.name = 'Electronics';

-- Update dengan Subquery
UPDATE products
SET price = (
    SELECT AVG(price) 
    FROM products 
    WHERE category_id = products.category_id
)
WHERE category_id = 1;

-- Update dengan CASE
UPDATE products
SET price = CASE
    WHEN category_id = 1 THEN price * 1.1
    WHEN category_id = 2 THEN price * 1.05
    ELSE price
END;

-- Update dengan LIMIT
UPDATE products
SET stock = stock - 1
WHERE stock > 0
LIMIT 10;

-- Update dengan ORDER BY
UPDATE products
SET price = price * 1.1
WHERE category_id = 1
ORDER BY price DESC
LIMIT 5;
```

> ⚠️ **Peringatan**: 
> - Selalu gunakan klausa WHERE untuk menghindari update yang tidak diinginkan
> - Gunakan transaksi untuk update yang kompleks
> - Backup data sebelum melakukan update massal
> - Perhatikan performa saat melakukan update pada tabel besar
</details>

<details>
<summary>🗑️ Delete Data</summary>

```sql
-- Template Dasar
DELETE FROM [nama_tabel] WHERE [kondisi];

-- Delete Single Row
DELETE FROM products WHERE id = 1;
DELETE FROM products WHERE product_code = 'ABC123';

-- Delete dengan Kondisi
DELETE FROM products WHERE stock = 0;
DELETE FROM products WHERE price < 100000;
DELETE FROM products WHERE created_at < DATE_SUB(NOW(), INTERVAL 1 YEAR);

-- Delete dengan JOIN
DELETE p FROM products p
JOIN categories c ON p.category_id = c.id
WHERE c.name = 'Discontinued';

-- Delete dengan Subquery
DELETE FROM products
WHERE category_id IN (
    SELECT id FROM categories WHERE status = 'inactive'
);

-- Delete dengan LIMIT
DELETE FROM products
WHERE stock = 0
LIMIT 100;

-- Delete dengan ORDER BY
DELETE FROM products
WHERE category_id = 1
ORDER BY created_at ASC
LIMIT 50;

-- Truncate Table (Hapus semua data)
TRUNCATE TABLE products;

-- Delete dengan Cascade
DELETE FROM categories WHERE id = 1;  -- Akan menghapus semua produk terkait
```

> ⚠️ **Peringatan**: 
> - Selalu gunakan klausa WHERE untuk menghindari penghapusan data yang tidak diinginkan
> - Pertimbangkan menggunakan soft delete (menggunakan kolom status) daripada hard delete
> - Backup data sebelum melakukan delete massal
> - Perhatikan foreign key constraints saat menghapus data
> - TRUNCATE akan menghapus semua data dan mereset auto-increment
</details>

## 🔍 5. Query Lanjutan

<details>
<summary>🔗 Join Tabel</summary>

```sql
-- INNER JOIN
SELECT * FROM tabel1 
INNER JOIN tabel2 ON tabel1.id = tabel2.id;

-- LEFT JOIN
SELECT * FROM tabel1 
LEFT JOIN tabel2 ON tabel1.id = tabel2.id;

-- RIGHT JOIN
SELECT * FROM tabel1 
RIGHT JOIN tabel2 ON tabel1.id = tabel2.id;

-- FULL JOIN (MySQL tidak mendukung, gunakan UNION)
SELECT * FROM tabel1 
LEFT JOIN tabel2 ON tabel1.id = tabel2.id
UNION
SELECT * FROM tabel1 
RIGHT JOIN tabel2 ON tabel1.id = tabel2.id;

-- Contoh
SELECT p.name, c.name as category
FROM products p
LEFT JOIN categories c ON p.category_id = c.id;
```

> 💡 **Tips**: 
> - Gunakan alias untuk membuat query lebih mudah dibaca
> - Pilih jenis JOIN yang sesuai dengan kebutuhan
> - Perhatikan performa saat melakukan JOIN pada tabel besar
</details>

<details>
<summary>📊 Group By</summary>

```sql
-- Template
SELECT [kolom], [fungsi_agregasi] as [alias]
FROM [nama_tabel] 
GROUP BY [kolom];

-- Contoh
SELECT category_id, COUNT(*) as total_products
FROM products
GROUP BY category_id;

SELECT category_id, 
       COUNT(*) as total_products,
       AVG(price) as avg_price,
       MAX(price) as max_price,
       MIN(price) as min_price
FROM products
GROUP BY category_id;
```

> 💡 **Tips**: 
> - Gunakan untuk mengelompokkan data berdasarkan kolom tertentu
> - Bisa dikombinasikan dengan fungsi agregasi
> - Gunakan HAVING untuk memfilter hasil GROUP BY
</details>

<details>
<summary>🎯 Having</summary>

```sql
-- Template
SELECT [kolom], [fungsi_agregasi] as [alias]
FROM [nama_tabel] 
GROUP BY [kolom]
HAVING [kondisi];

-- Contoh
SELECT category_id, COUNT(*) as total_products
FROM products
GROUP BY category_id
HAVING total_products > 5;

SELECT category_id, AVG(price) as avg_price
FROM products
GROUP BY category_id
HAVING avg_price > 1000000;
```

> 💡 **Tips**: 
> - HAVING digunakan untuk memfilter hasil GROUP BY
> - Bisa menggunakan alias yang dibuat di SELECT
> - Perbedaan dengan WHERE: WHERE memfilter sebelum GROUP BY, HAVING memfilter setelah GROUP BY
</details>

<details>
<summary>🔄 Subquery</summary>

```sql
-- Di klausa WHERE
SELECT * FROM products
WHERE price > (SELECT AVG(price) FROM products);

-- Di klausa FROM
SELECT * FROM (
    SELECT category_id, COUNT(*) as total
    FROM products
    GROUP BY category_id
) as category_stats;

-- Di klausa SELECT
SELECT name, 
       price,
       (SELECT AVG(price) FROM products) as avg_price
FROM products;

-- Contoh
SELECT p.name, p.price
FROM products p
WHERE p.price > (
    SELECT AVG(price) 
    FROM products 
    WHERE category_id = p.category_id
);
```

> 💡 **Tips**: 
> - Subquery bisa digunakan di klausa WHERE, FROM, atau SELECT
> - Gunakan alias untuk subquery di klausa FROM
> - Perhatikan performa saat menggunakan subquery
</details>

## 📊 6. Fungsi Agregasi

<details>
<summary>📊 Fungsi Agregasi</summary>

```sql
-- COUNT
SELECT COUNT(*) FROM products;
SELECT COUNT(DISTINCT category_id) FROM products;
SELECT category_id, COUNT(*) as total_products FROM products GROUP BY category_id;

-- SUM
SELECT SUM(price) FROM products;
SELECT category_id, SUM(stock) as total_stock FROM products GROUP BY category_id;
SELECT SUM(quantity * price) as total_sales FROM order_items;

-- AVG
SELECT AVG(price) FROM products;
SELECT category_id, AVG(price) as avg_price FROM products GROUP BY category_id;
SELECT AVG(DISTINCT price) FROM products;

-- MAX
SELECT MAX(price) FROM products;
SELECT category_id, MAX(price) as max_price FROM products GROUP BY category_id;
SELECT MAX(created_at) FROM products;

-- MIN
SELECT MIN(price) FROM products;
SELECT category_id, MIN(price) as min_price FROM products GROUP BY category_id;
SELECT MIN(created_at) FROM products;

-- GROUP_CONCAT
SELECT category_id, GROUP_CONCAT(name) FROM products GROUP BY category_id;
SELECT category_id, GROUP_CONCAT(name SEPARATOR ' | ') FROM products GROUP BY category_id;
SELECT category_id, GROUP_CONCAT(DISTINCT name ORDER BY name) FROM products GROUP BY category_id;

-- Dengan HAVING
SELECT category_id, COUNT(*) as total_products
FROM products
GROUP BY category_id
HAVING total_products > 5;

-- Dengan ROLLUP
SELECT category_id, COUNT(*) as total_products
FROM products
GROUP BY category_id WITH ROLLUP;
```

> 💡 **Tips**: 
> - Gunakan DISTINCT untuk menghindari duplikasi
> - Kombinasikan dengan GROUP BY untuk analisis per kelompok
> - Perhatikan performa saat menggunakan pada tabel besar
> - Gunakan HAVING untuk memfilter hasil agregasi
> - ROLLUP berguna untuk membuat subtotal
</details>

## 📅 7. Fungsi Tanggal dan Waktu

<details>
<summary>📅 Fungsi Tanggal dan Waktu</summary>

```sql
-- NOW, CURRENT_TIMESTAMP
SELECT NOW();
SELECT CURRENT_TIMESTAMP;

-- DATE, TIME
SELECT DATE(NOW());
SELECT TIME(NOW());

-- YEAR, MONTH, DAY
SELECT YEAR(NOW());
SELECT MONTH(NOW());
SELECT DAY(NOW());

-- DATE_FORMAT
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d');
SELECT DATE_FORMAT(NOW(), '%H:%i:%s');
SELECT DATE_FORMAT(NOW(), '%W, %d %M %Y');

-- DATE_ADD, DATE_SUB
SELECT DATE_ADD(NOW(), INTERVAL 1 DAY);
SELECT DATE_SUB(NOW(), INTERVAL 1 MONTH);
SELECT DATE_ADD(NOW(), INTERVAL 1 YEAR);

-- DATEDIFF
SELECT DATEDIFF('2023-12-31', '2023-01-01');
SELECT DATEDIFF(end_date, start_date) FROM projects;

-- TIMESTAMPDIFF
SELECT TIMESTAMPDIFF(YEAR, birth_date, NOW()) as age FROM customers;
SELECT TIMESTAMPDIFF(MONTH, start_date, end_date) FROM projects;

-- LAST_DAY
SELECT LAST_DAY(NOW());
SELECT LAST_DAY('2023-02-01');

-- DAYOFWEEK, DAYOFYEAR
SELECT DAYOFWEEK(NOW());
SELECT DAYOFYEAR(NOW());

-- WEEK
SELECT WEEK(NOW());
SELECT WEEK(NOW(), 1);  -- Mode 1: Minggu dimulai hari Senin

-- QUARTER
SELECT QUARTER(NOW());

-- EXTRACT
SELECT EXTRACT(YEAR FROM NOW());
SELECT EXTRACT(MONTH FROM NOW());
SELECT EXTRACT(DAY FROM NOW());
```

> 💡 **Tips**: 
> - Gunakan fungsi yang sesuai dengan kebutuhan
> - Perhatikan timezone saat bekerja dengan tanggal dan waktu
> - Gunakan indeks untuk kolom tanggal yang sering dicari
> - DATE_FORMAT sangat fleksibel untuk format tanggal
</details>

## 📝 8. Fungsi String

<details>
<summary>📝 Fungsi String</summary>

```sql
-- CONCAT
SELECT CONCAT(first_name, ' ', last_name) as full_name FROM customers;
SELECT CONCAT_WS(' ', first_name, last_name) as full_name FROM customers;

-- SUBSTRING
SELECT SUBSTRING(name, 1, 10) FROM products;
SELECT SUBSTRING_INDEX(email, '@', 1) as username FROM users;

-- REPLACE
SELECT REPLACE(description, 'old', 'new') FROM products;
SELECT REPLACE(phone, '-', '') FROM customers;

-- UPPER, LOWER
SELECT UPPER(name) FROM products;
SELECT LOWER(email) FROM users;

-- TRIM
SELECT TRIM(name) FROM products;
SELECT LTRIM(name) FROM products;
SELECT RTRIM(name) FROM products;

-- LENGTH
SELECT LENGTH(name) FROM products;
SELECT CHAR_LENGTH(name) FROM products;

-- LEFT, RIGHT
SELECT LEFT(name, 5) FROM products;
SELECT RIGHT(phone, 4) FROM customers;

-- LOCATE, INSTR
SELECT LOCATE('keyword', description) FROM products;
SELECT INSTR(description, 'keyword') FROM products;

-- REPEAT
SELECT REPEAT('*', 5);

-- REVERSE
SELECT REVERSE(name) FROM products;

-- REGEXP
SELECT * FROM products WHERE name REGEXP '^Laptop';
SELECT * FROM products WHERE name REGEXP 'Pro$';
SELECT * FROM products WHERE name REGEXP '[0-9]';

-- SOUNDEX
SELECT * FROM customers WHERE SOUNDEX(name) = SOUNDEX('John');

-- ELT
SELECT ELT(1, 'First', 'Second', 'Third');
```

> 💡 **Tips**: 
> - Gunakan CONCAT_WS untuk menggabungkan string dengan separator
> - Perhatikan performa saat menggunakan fungsi string pada kolom yang diindeks
> - Gunakan REGEXP untuk pencarian pola yang kompleks
> - SOUNDEX berguna untuk pencarian berdasarkan pengucapan
</details>

## 🔢 9. Fungsi Numerik

<details>
<summary>🔢 Fungsi Numerik</summary>

```sql
-- ROUND
SELECT ROUND(price, 2) FROM products;
SELECT ROUND(price) FROM products;

-- CEIL, FLOOR
SELECT CEIL(price) FROM products;
SELECT FLOOR(price) FROM products;

-- ABS
SELECT ABS(price) FROM products;

-- MOD
SELECT MOD(quantity, 2) FROM order_items;

-- POWER
SELECT POWER(price, 2) FROM products;

-- SQRT
SELECT SQRT(price) FROM products;

-- RAND
SELECT RAND();
SELECT * FROM products ORDER BY RAND() LIMIT 5;

-- FORMAT
SELECT FORMAT(price, 2) FROM products;
SELECT FORMAT(price, 0) FROM products;

-- GREATEST, LEAST
SELECT GREATEST(price1, price2, price3) FROM products;
SELECT LEAST(price1, price2, price3) FROM products;

-- TRUNCATE
SELECT TRUNCATE(price, 2) FROM products;

-- SIGN
SELECT SIGN(price) FROM products;

-- PI
SELECT PI();

-- DEGREES, RADIANS
SELECT DEGREES(PI());
SELECT RADIANS(180);
```

> 💡 **Tips**: 
> - Gunakan ROUND untuk membulatkan angka desimal
> - Perhatikan presisi saat bekerja dengan angka desimal
> - Gunakan FORMAT untuk menampilkan angka dengan pemisah ribuan
> - RAND() berguna untuk mengambil sampel acak
</details>

## 📌 10. Indeks

<details>
<summary>➕ Membuat Indeks</summary>

```sql
-- Template Single Column
CREATE INDEX [nama_indeks] ON [nama_tabel] ([kolom]);

-- Template Multiple Column
CREATE INDEX [nama_indeks] ON [nama_tabel] ([kolom1], [kolom2]);

-- Contoh
CREATE INDEX idx_product_name ON products (name);
CREATE INDEX idx_category_price ON products (category_id, price);

-- Unique Index
CREATE UNIQUE INDEX idx_product_code ON products (product_code);
```

> 💡 **Tips**: 
> - Buat indeks pada kolom yang sering digunakan dalam WHERE atau JOIN
> - Hindari membuat terlalu banyak indeks karena akan memperlambat INSERT/UPDATE
> - Gunakan unique index untuk memastikan nilai unik
</details>

<details>
<summary>🗑️ Menghapus Indeks</summary>

```sql
-- Template
DROP INDEX [nama_indeks] ON [nama_tabel];

-- Contoh
DROP INDEX idx_product_name ON products;
```

> 💡 **Tips**: 
> - Hapus indeks yang tidak digunakan untuk mengoptimalkan performa
> - Pastikan indeks yang dihapus tidak digunakan oleh constraint
</details>

## 💾 11. Backup dan Restore

<details>
<summary>💾 Backup Database</summary>

```sql
-- Template
mysqldump -u [username] -p [nama_database] > [nama_file].sql

-- Contoh
mysqldump -u root -p toko_online > backup_toko_online.sql

-- Backup Multiple Database
mysqldump -u root -p --databases db1 db2 > backup_multiple.sql

-- Backup All Databases
mysqldump -u root -p --all-databases > backup_all.sql
```

> 💡 **Tips**: 
> - Lakukan backup secara berkala untuk keamanan data
> - Simpan backup di lokasi yang aman
> - Gunakan opsi --databases untuk backup multiple database
</details>

<details>
<summary>🔄 Restore Database</summary>

```sql
-- Template
mysql -u [username] -p [nama_database] < [nama_file].sql

-- Contoh
mysql -u root -p toko_online < backup_toko_online.sql

-- Restore dari file gzip
gunzip < backup.sql.gz | mysql -u root -p toko_online
```

> 💡 **Tips**: 
> - Pastikan database tujuan sudah ada sebelum restore
> - Periksa ukuran file backup sebelum restore
> - Gunakan transaksi untuk restore yang aman</details>

## 🔧 12. Praktik Terbaik MySQL

<details>
<summary>📋 Praktik Terbaik Desain Database</summary>

```sql
-- 1. Normalisasi Database
-- Contoh Tabel yang Sudah Dinormalisasi
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    phone VARCHAR(20)
);

CREATE TABLE addresses (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    address_type ENUM('home', 'work', 'other') NOT NULL,
    street VARCHAR(100) NOT NULL,
    city VARCHAR(50) NOT NULL,
    country VARCHAR(50) NOT NULL,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

-- 2. Penggunaan Tipe Data yang Tepat
CREATE TABLE products (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    sku VARCHAR(20) UNIQUE NOT NULL,
    name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) UNSIGNED NOT NULL,
    stock INT UNSIGNED NOT NULL DEFAULT 0,
    status ENUM('active', 'inactive', 'discontinued') NOT NULL DEFAULT 'active',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 3. Penggunaan Indeks yang Efektif
CREATE TABLE orders (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    customer_id INT UNSIGNED NOT NULL,
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    status ENUM('pending', 'processing', 'completed', 'cancelled') NOT NULL,
    total_amount DECIMAL(10,2) UNSIGNED NOT NULL,
    INDEX idx_customer (customer_id),
    INDEX idx_status (status),
    INDEX idx_order_date (order_date)
);
```

> 💡 **Tips**: 
> - Normalisasi database untuk menghindari redundansi data
> - Pilih tipe data yang sesuai dengan kebutuhan
> - Buat indeks pada kolom yang sering digunakan dalam WHERE dan JOIN
> - Gunakan constraint untuk menjaga integritas data
> - Dokumentasikan struktur database
</details>

<details>
<summary>⚡ Optimasi Performa</summary>

```sql
-- 1. Optimasi Query
-- Sebelum
SELECT * FROM products WHERE category_id = 1;

-- Sesudah
SELECT id, name, price 
FROM products 
WHERE category_id = 1;

-- 2. Penggunaan JOIN yang Efisien
-- Sebelum
SELECT p.*, c.* 
FROM products p, categories c 
WHERE p.category_id = c.id;

-- Sesudah
SELECT p.id, p.name, p.price, c.name as category_name
FROM products p
INNER JOIN categories c ON p.category_id = c.id;

-- 3. Penggunaan LIMIT
SELECT * FROM products 
WHERE category_id = 1 
LIMIT 10;

-- 4. Penggunaan EXPLAIN
EXPLAIN SELECT * FROM products WHERE category_id = 1;

-- 5. Penggunaan Index Hints
SELECT * FROM products USE INDEX (idx_category) 
WHERE category_id = 1;

-- 6. Optimasi Subquery
-- Sebelum
SELECT * FROM products 
WHERE price > (SELECT AVG(price) FROM products);

-- Sesudah
SELECT p.* 
FROM products p
JOIN (SELECT AVG(price) as avg_price FROM products) avg_p
WHERE p.price > avg_p.avg_price;
```

> 💡 **Tips**: 
> - Gunakan EXPLAIN untuk menganalisis query
> - Pilih kolom yang dibutuhkan saja
> - Gunakan JOIN daripada subquery jika memungkinkan
> - Batasi jumlah data yang diambil
> - Monitor dan optimasi indeks secara berkala
</details>

<details>
<summary>🔍 Troubleshooting Umum</summary>

```sql
-- 1. Mengecek Status Server
SHOW STATUS;
SHOW VARIABLES;

-- 2. Mengecek Proses yang Berjalan
SHOW PROCESSLIST;

-- 3. Mengecek Error Log
SHOW VARIABLES LIKE 'log_error';

-- 4. Mengecek Penggunaan Disk
SELECT 
    table_schema as Database,
    table_name as Table,
    round(((data_length + index_length) / 1024 / 1024), 2) as Size_MB
FROM information_schema.TABLES
ORDER BY (data_length + index_length) DESC;

-- 5. Mengecek Tabel yang Tidak Terpakai
SELECT 
    table_schema as Database,
    table_name as Table,
    update_time as Last_Update
FROM information_schema.TABLES
WHERE update_time < DATE_SUB(NOW(), INTERVAL 30 DAY);

-- 6. Mengecek Indeks yang Tidak Terpakai
SELECT 
    table_schema as Database,
    table_name as Table,
    index_name as Index,
    column_name as Column
FROM information_schema.STATISTICS
WHERE table_schema = 'your_database'
ORDER BY table_name, index_name;

-- 7. Mengecek Tabel yang Perlu Dioptimasi
SELECT 
    table_schema as Database,
    table_name as Table,
    data_free as Free_Space
FROM information_schema.TABLES
WHERE data_free > 0
ORDER BY data_free DESC;
```

> 💡 **Tips**: 
> - Monitor penggunaan sumber daya server
> - Periksa error log secara berkala
> - Optimasi tabel secara berkala
> - Hapus indeks yang tidak terpakai
> - Backup database secara berkala
</details>

<details>
<summary>🔐 Keamanan Database</summary>

```sql
-- 1. Membuat User dengan Hak Akses Terbatas
CREATE USER 'app_user'@'localhost' IDENTIFIED BY 'password';
GRANT SELECT, INSERT, UPDATE, DELETE ON database_name.* TO 'app_user'@'localhost';

-- 2. Membuat User dengan Hak Akses Spesifik
CREATE USER 'report_user'@'localhost' IDENTIFIED BY 'password';
GRANT SELECT ON database_name.* TO 'report_user'@'localhost';

-- 3. Membuat User dengan Akses ke Tabel Tertentu
CREATE USER 'product_user'@'localhost' IDENTIFIED BY 'password';
GRANT SELECT, INSERT, UPDATE ON database_name.products TO 'product_user'@'localhost';

-- 4. Mengecek Hak Akses User
SHOW GRANTS FOR 'user'@'localhost';

-- 5. Mencabut Hak Akses
REVOKE ALL PRIVILEGES ON database_name.* FROM 'user'@'localhost';

-- 6. Mengubah Password User
ALTER USER 'user'@'localhost' IDENTIFIED BY 'new_password';

-- 7. Menghapus User
DROP USER 'user'@'localhost';
```

> 💡 **Tips**: 
> - Gunakan password yang kuat
> - Berikan hak akses minimal yang diperlukan
> - Review hak akses secara berkala
> - Gunakan SSL untuk koneksi remote
> - Backup data secara berkala
> - Enkripsi data sensitif
</details>

<details>
<summary>📊 Monitoring dan Maintenance</summary>

```sql
-- 1. Mengecek Status Server
SHOW STATUS;
SHOW VARIABLES;

-- 2. Mengecek Penggunaan Memory
SHOW GLOBAL STATUS LIKE 'Innodb_buffer_pool_%';

-- 3. Mengecek Penggunaan Disk
SELECT 
    table_schema as Database,
    table_name as Table,
    round(((data_length + index_length) / 1024 / 1024), 2) as Size_MB
FROM information_schema.TABLES
ORDER BY (data_length + index_length) DESC;

-- 4. Mengecek Tabel yang Perlu Dioptimasi
OPTIMIZE TABLE table_name;
ANALYZE TABLE table_name;
CHECK TABLE table_name;
REPAIR TABLE table_name;

-- 5. Mengecek dan Memperbaiki Indeks
SHOW INDEX FROM table_name;
ANALYZE TABLE table_name;

-- 6. Mengecek dan Membersihkan Log
SHOW BINARY LOGS;
PURGE BINARY LOGS BEFORE DATE_SUB(NOW(), INTERVAL 7 DAY);

-- 7. Mengecek dan Membersihkan Tabel Temporary
SHOW GLOBAL STATUS LIKE 'Created_tmp_%';
```

> 💡 **Tips**: 
> - Monitor penggunaan sumber daya server
> - Optimasi tabel secara berkala
> - Bersihkan log yang tidak diperlukan
> - Monitor pertumbuhan database
> - Backup data secara berkala
> - Dokumentasikan semua perubahan
</details>

## 🔄 13. Replikasi MySQL

<details>
<summary>🔄 Konfigurasi Replikasi</summary>

```sql
-- 1. Konfigurasi Master
-- Di my.cnf Master
[mysqld]
server-id = 1
log-bin = mysql-bin
binlog-format = ROW
sync_binlog = 1

-- 2. Konfigurasi Slave
-- Di my.cnf Slave
[mysqld]
server-id = 2
relay-log = mysql-relay-bin
read_only = 1

-- 3. Membuat User Replikasi di Master
CREATE USER 'repl'@'%' IDENTIFIED BY 'password';
GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%';

-- 4. Mengatur Slave
CHANGE MASTER TO
    MASTER_HOST = 'master_host',
    MASTER_USER = 'repl',
    MASTER_PASSWORD = 'password',
    MASTER_LOG_FILE = 'mysql-bin.000001',
    MASTER_LOG_POS = 0;

-- 5. Memulai Replikasi
START SLAVE;

-- 6. Mengecek Status Replikasi
SHOW SLAVE STATUS\G
SHOW MASTER STATUS\G

-- 7. Menghentikan Replikasi
STOP SLAVE;
```

> 💡 **Tips**: 
> - Gunakan server-id yang unik untuk setiap server
> - Backup data sebelum mengatur replikasi
> - Monitor lag replikasi secara berkala
> - Gunakan GTID untuk replikasi yang lebih handal
> - Dokumentasikan konfigurasi replikasi
</details>

<details>
<summary>🔄 Troubleshooting Replikasi</summary>

```sql
-- 1. Mengecek Error Replikasi
SHOW SLAVE STATUS\G

-- 2. Melewati Error Replikasi
SET GLOBAL sql_slave_skip_counter = 1;
START SLAVE;

-- 3. Reset Replikasi
STOP SLAVE;
RESET SLAVE;
CHANGE MASTER TO ...;
START SLAVE;

-- 4. Mengecek Lag Replikasi
SHOW SLAVE STATUS\G
-- Lihat kolom Seconds_Behind_Master

-- 5. Mengecek Binary Log
SHOW BINARY LOGS;
SHOW BINLOG EVENTS IN 'mysql-bin.000001';

-- 6. Memperbaiki Replikasi yang Rusak
-- Di Master
FLUSH LOGS;
-- Di Slave
STOP SLAVE;
CHANGE MASTER TO ...;
START SLAVE;
```

> 💡 **Tips**: 
> - Monitor error log secara berkala
> - Backup data sebelum memperbaiki replikasi
> - Dokumentasikan semua perubahan konfigurasi
> - Test failover secara berkala
</details>

## 🚀 14. High Availability

<details>
<summary>🔄 Konfigurasi High Availability</summary>

```sql
-- 1. Konfigurasi Master-Master
-- Di my.cnf Server 1
[mysqld]
server-id = 1
log-bin = mysql-bin
binlog-format = ROW
auto_increment_increment = 2
auto_increment_offset = 1

-- Di my.cnf Server 2
[mysqld]
server-id = 2
log-bin = mysql-bin
binlog-format = ROW
auto_increment_increment = 2
auto_increment_offset = 2

-- 2. Mengecek Status Replikasi
SHOW SLAVE STATUS\G
SHOW MASTER STATUS\G

-- 3. Mengecek Koneksi
SHOW PROCESSLIST;

-- 4. Mengecek Error Log
SHOW VARIABLES LIKE 'log_error';

-- 5. Mengecek Status Server
SHOW STATUS;
```

> 💡 **Tips**: 
> - Gunakan load balancer untuk distribusi beban
> - Monitor kesehatan server secara berkala
> - Backup data secara berkala
> - Test failover secara berkala
> - Dokumentasikan prosedur failover
</details>

<details>
<summary>🔄 Failover dan Recovery</summary>

```sql
-- 1. Prosedur Failover Manual
-- Di Slave
STOP SLAVE;
RESET SLAVE;
CHANGE MASTER TO ...;
START SLAVE;

-- 2. Mengecek Status Setelah Failover
SHOW SLAVE STATUS\G
SHOW MASTER STATUS\G

-- 3. Recovery Setelah Failover
-- Backup data
mysqldump -u root -p --all-databases > backup.sql

-- Restore data
mysql -u root -p < backup.sql

-- 4. Mengecek Integritas Data
CHECK TABLE table_name;
REPAIR TABLE table_name;

-- 5. Mengecek Konsistensi Data
-- Bandingkan data antara master dan slave
SELECT COUNT(*) FROM table_name;
SELECT MAX(id) FROM table_name;
```

> 💡 **Tips**: 
> - Backup data sebelum failover
> - Test prosedur failover secara berkala
> - Monitor performa setelah failover
> - Dokumentasikan semua langkah failover
> - Verifikasi integritas data setelah failover
</details>

## 📦 15. Migrasi Database

<details>
<summary>🔄 Prosedur Migrasi</summary>

```sql
-- 1. Backup Database
mysqldump -u root -p --all-databases > backup.sql

-- 2. Mengecek Versi MySQL
SELECT VERSION();

-- 3. Mengecek Karakter Set
SHOW VARIABLES LIKE 'character_set%';
SHOW VARIABLES LIKE 'collation%';

-- 4. Mengecek Tabel yang Perlu Dioptimasi
SELECT 
    table_schema as Database,
    table_name as Table,
    data_free as Free_Space
FROM information_schema.TABLES
WHERE data_free > 0
ORDER BY data_free DESC;

-- 5. Optimasi Tabel Sebelum Migrasi
OPTIMIZE TABLE table_name;

-- 6. Mengecek Foreign Key
SELECT 
    table_name,
    column_name,
    referenced_table_name,
    referenced_column_name
FROM information_schema.KEY_COLUMN_USAGE
WHERE referenced_table_name IS NOT NULL;

-- 7. Mengecek Indeks
SHOW INDEX FROM table_name;
```

> 💡 **Tips**: 
> - Backup data sebelum migrasi
> - Test migrasi di lingkungan staging
> - Perhatikan versi MySQL
> - Perhatikan karakter set dan collation
> - Dokumentasikan semua perubahan
</details>

<details>
<summary>🔄 Best Practices Backup dan Restore</summary>

```sql
-- 1. Backup Database
-- Backup semua database
mysqldump -u root -p --all-databases > backup.sql

-- Backup database tertentu
mysqldump -u root -p database_name > backup.sql

-- Backup dengan kompresi
mysqldump -u root -p database_name | gzip > backup.sql.gz

-- 2. Backup Tabel Tertentu
mysqldump -u root -p database_name table1 table2 > backup.sql

-- 3. Backup dengan Kondisi
mysqldump -u root -p database_name --where="date > '2023-01-01'" > backup.sql

-- 4. Backup Struktur Saja
mysqldump -u root -p --no-data database_name > structure.sql

-- 5. Backup Data Saja
mysqldump -u root -p --no-create-info database_name > data.sql

-- 6. Restore Database
mysql -u root -p database_name < backup.sql

-- 7. Restore dari File Terkompresi
gunzip < backup.sql.gz | mysql -u root -p database_name
```

> 💡 **Tips**: 
> - Lakukan backup secara berkala
> - Simpan backup di lokasi yang aman
> - Test restore secara berkala
> - Dokumentasikan prosedur backup dan restore
> - Monitor ukuran backup
> - Enkripsi backup yang sensitif
</details>

<details>
<summary>🔄 Monitoring Backup dan Restore</summary>

```sql
-- 1. Mengecek Ukuran Backup
ls -lh backup.sql

-- 2. Mengecek Integritas Backup
mysqlcheck -u root -p database_name

-- 3. Mengecek Status Restore
SHOW PROCESSLIST;

-- 4. Mengecek Error Log
SHOW VARIABLES LIKE 'log_error';

-- 5. Mengecek Penggunaan Disk
SELECT 
    table_schema as Database,
    table_name as Table,
    round(((data_length + index_length) / 1024 / 1024), 2) as Size_MB
FROM information_schema.TABLES
ORDER BY (data_length + index_length) DESC;

-- 6. Mengecek Tabel yang Perlu Dioptimasi
SELECT 
    table_schema as Database,
    table_name as Table,
    data_free as Free_Space
FROM information_schema.TABLES
WHERE data_free > 0
ORDER BY data_free DESC;
```

> 💡 **Tips**: 
> - Monitor ukuran backup
> - Verifikasi integritas backup
> - Test restore secara berkala
> - Dokumentasikan semua error
> - Monitor penggunaan disk
> - Optimasi tabel secara berkala
</details>

## 🛠️ 16. MySQL Workbench

<details>
<summary>🔄 Penggunaan Dasar</summary>

```sql
-- 1. Koneksi ke Database
-- Di MySQL Workbench:
-- File -> New Connection
-- Connection Name: Local MySQL
-- Hostname: localhost
-- Port: 3306
-- Username: root
-- Password: ****

-- 2. Membuat Database
CREATE DATABASE test_db;

-- 3. Membuat Tabel
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 4. Import Data
-- Di MySQL Workbench:
-- Server -> Data Import
-- Import from Self-Contained File
-- Select File: backup.sql

-- 5. Export Data
-- Di MySQL Workbench:
-- Server -> Data Export
-- Select Database
-- Export to Self-Contained File
-- File: backup.sql
```

> 💡 **Tips**: 
> - Gunakan MySQL Workbench untuk manajemen database visual
> - Manfaatkan fitur import/export untuk backup
> - Gunakan query editor untuk testing query
> - Manfaatkan fitur visualisasi untuk ERD
> - Gunakan fitur performance reporting
</details>

<details>
<summary>🔄 Fitur Lanjutan</summary>

```sql
-- 1. Membuat ERD
-- Di MySQL Workbench:
-- File -> New Model
-- Add Diagram
-- Add Table
-- Add Relationship

-- 2. Forward Engineering
-- Di MySQL Workbench:
-- Database -> Forward Engineer
-- Select Target Connection
-- Review SQL Script
-- Execute

-- 3. Reverse Engineering
-- Di MySQL Workbench:
-- Database -> Reverse Engineer
-- Select Source Connection
-- Select Database
-- Review Model

-- 4. Performance Reporting
-- Di MySQL Workbench:
-- Performance -> Performance Reports
-- Select Report Type
-- View Results

-- 5. Query Optimization
-- Di MySQL Workbench:
-- Query -> Explain Current Statement
-- View Execution Plan
```

> 💡 **Tips**: 
> - Gunakan ERD untuk dokumentasi database
> - Manfaatkan forward engineering untuk deployment
> - Gunakan reverse engineering untuk analisis
> - Monitor performa dengan performance reporting
> - Optimasi query dengan execution plan
</details>

## ⚡ 17. Optimasi Query

<details>
<summary>🔄 Teknik Optimasi</summary>

```sql
-- 1. Penggunaan Indeks
-- Sebelum
SELECT * FROM users WHERE email = 'user@example.com';

-- Sesudah
CREATE INDEX idx_email ON users(email);
SELECT * FROM users WHERE email = 'user@example.com';

-- 2. Penggunaan EXPLAIN
EXPLAIN SELECT * FROM users WHERE email = 'user@example.com';

-- 3. Optimasi JOIN
-- Sebelum
SELECT * FROM orders o, customers c 
WHERE o.customer_id = c.id;

-- Sesudah
SELECT o.id, o.order_date, c.name 
FROM orders o
INNER JOIN customers c ON o.customer_id = c.id;

-- 4. Penggunaan LIMIT
SELECT * FROM orders 
WHERE status = 'pending' 
LIMIT 10;

-- 5. Penggunaan Subquery
-- Sebelum
SELECT * FROM products 
WHERE price > (SELECT AVG(price) FROM products);

-- Sesudah
SELECT p.* 
FROM products p
JOIN (SELECT AVG(price) as avg_price FROM products) avg_p
WHERE p.price > avg_p.avg_price;

-- 6. Penggunaan Index Hints
SELECT * FROM products USE INDEX (idx_category) 
WHERE category_id = 1;

-- 7. Penggunaan Partitioning
CREATE TABLE orders (
    id INT,
    order_date DATE,
    customer_id INT,
    amount DECIMAL(10,2)
) PARTITION BY RANGE (YEAR(order_date)) (
    PARTITION p2023 VALUES LESS THAN (2024),
    PARTITION p2024 VALUES LESS THAN (2025),
    PARTITION p2025 VALUES LESS THAN (2026)
);
```

> 💡 **Tips**: 
> - Gunakan EXPLAIN untuk analisis query
> - Pilih kolom yang dibutuhkan saja
> - Gunakan indeks dengan bijak
> - Batasi jumlah data yang diambil
> - Gunakan partitioning untuk tabel besar
> - Monitor performa query secara berkala
</details>

<details>
<summary>🔄 Best Practices Query</summary>

```sql
-- 1. Penggunaan WHERE
-- Sebelum
SELECT * FROM users;

-- Sesudah
SELECT id, username, email 
FROM users 
WHERE status = 'active';

-- 2. Penggunaan ORDER BY
-- Sebelum
SELECT * FROM products 
ORDER BY price;

-- Sesudah
SELECT id, name, price 
FROM products 
WHERE category_id = 1 
ORDER BY price 
LIMIT 10;

-- 3. Penggunaan GROUP BY
-- Sebelum
SELECT * FROM orders 
GROUP BY customer_id;

-- Sesudah
SELECT 
    customer_id,
    COUNT(*) as total_orders,
    SUM(amount) as total_amount
FROM orders 
GROUP BY customer_id;

-- 4. Penggunaan HAVING
SELECT 
    customer_id,
    COUNT(*) as total_orders
FROM orders 
GROUP BY customer_id
HAVING total_orders > 5;

-- 5. Penggunaan CASE
SELECT 
    id,
    name,
    CASE 
        WHEN price > 1000 THEN 'High'
        WHEN price > 500 THEN 'Medium'
        ELSE 'Low'
    END as price_category
FROM products;
```

> 💡 **Tips**: 
> - Gunakan WHERE untuk filter data
> - Batasi jumlah data dengan LIMIT
> - Gunakan indeks untuk kolom yang sering dicari
> - Optimasi GROUP BY dengan indeks
> - Gunakan CASE untuk logika kompleks
</details>

## 👥 18. Manajemen User dan Hak Akses

<details>
<summary>🔄 Manajemen User</summary>

```sql
-- 1. Membuat User
CREATE USER 'app_user'@'localhost' IDENTIFIED BY 'password';
CREATE USER 'admin_user'@'%' IDENTIFIED BY 'password';

-- 2. Mengubah Password
ALTER USER 'user'@'localhost' IDENTIFIED BY 'new_password';

-- 3. Menghapus User
DROP USER 'user'@'localhost';

-- 4. Mengecek User
SELECT user, host FROM mysql.user;

-- 5. Mengunci User
ALTER USER 'user'@'localhost' ACCOUNT LOCK;

-- 6. Membuka Kunci User
ALTER USER 'user'@'localhost' ACCOUNT UNLOCK;

-- 7. Mengatur Expired Password
ALTER USER 'user'@'localhost' PASSWORD EXPIRE;

-- 8. Mengecek Status User
SELECT 
    user,
    host,
    account_locked,
    password_expired
FROM mysql.user;
```

> 💡 **Tips**: 
> - Gunakan password yang kuat
> - Batasi akses user ke host tertentu
> - Review user secara berkala
> - Dokumentasikan hak akses
> - Monitor aktivitas user
</details>

<details>
<summary>🔄 Manajemen Hak Akses</summary>

```sql
-- 1. Memberikan Hak Akses
GRANT SELECT, INSERT, UPDATE, DELETE 
ON database_name.* 
TO 'user'@'localhost';

-- 2. Memberikan Hak Akses ke Tabel Tertentu
GRANT SELECT, INSERT 
ON database_name.table_name 
TO 'user'@'localhost';

-- 3. Memberikan Hak Akses ke Kolom Tertentu
GRANT SELECT (id, name, email) 
ON database_name.users 
TO 'user'@'localhost';

-- 4. Mencabut Hak Akses
REVOKE ALL PRIVILEGES 
ON database_name.* 
FROM 'user'@'localhost';

-- 5. Mengecek Hak Akses
SHOW GRANTS FOR 'user'@'localhost';

-- 6. Memberikan Hak Akses dengan WITH GRANT OPTION
GRANT SELECT 
ON database_name.* 
TO 'user'@'localhost' 
WITH GRANT OPTION;

-- 7. Memberikan Hak Akses dengan WITH ADMIN OPTION
GRANT ALL PRIVILEGES 
ON *.* 
TO 'admin'@'localhost' 
WITH ADMIN OPTION;
```

> 💡 **Tips**: 
> - Berikan hak akses minimal yang diperlukan
> - Review hak akses secara berkala
> - Dokumentasikan perubahan hak akses
> - Monitor penggunaan hak akses
> - Gunakan role untuk manajemen hak akses
</details>

## 🔒 19. Keamanan Database

<details>
<summary>🔄 Praktik Keamanan</summary>

```sql
-- 1. Enkripsi Data
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(255) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    credit_card VARBINARY(255)
);

-- 2. Mengenkripsi Data
INSERT INTO users (username, password, credit_card)
VALUES (
    'user1',
    SHA2('password123', 256),
    AES_ENCRYPT('1234-5678-9012-3456', 'encryption_key')
);

-- 3. Mendekripsi Data
SELECT 
    username,
    AES_DECRYPT(credit_card, 'encryption_key') as credit_card
FROM users;

-- 4. Mengatur Password Policy
SET GLOBAL validate_password_policy = MEDIUM;
SET GLOBAL validate_password_length = 8;

-- 5. Mengatur SSL
-- Di my.cnf
[mysqld]
ssl-ca=/path/to/ca.pem
ssl-cert=/path/to/server-cert.pem
ssl-key=/path/to/server-key.pem

-- 6. Mengecek Status SSL
SHOW VARIABLES LIKE '%ssl%';

-- 7. Mengatur Audit Log
-- Di my.cnf
[mysqld]
audit_log = FORCE_PLUS_PERMANENT
audit_log_file = /var/log/mysql/audit.log
```

> 💡 **Tips**: 
> - Enkripsi data sensitif
> - Gunakan password yang kuat
> - Aktifkan SSL untuk koneksi
> - Aktifkan audit log
> - Review keamanan secara berkala
</details>

<details>
<summary>🔄 Monitoring Keamanan</summary>

```sql
-- 1. Mengecek Login yang Gagal
SELECT * FROM mysql.general_log 
WHERE argument LIKE '%Access denied%';

-- 2. Mengecek User yang Aktif
SHOW PROCESSLIST;

-- 3. Mengecek Hak Akses
SELECT * FROM mysql.user;

-- 4. Mengecek Audit Log
SELECT * FROM mysql.audit_log;

-- 5. Mengecek Error Log
SHOW VARIABLES LIKE 'log_error';

-- 6. Mengecek Status SSL
SHOW VARIABLES LIKE '%ssl%';

-- 7. Mengecek Password Policy
SHOW VARIABLES LIKE 'validate_password%';
```

> 💡 **Tips**: 
> - Monitor login yang gagal
> - Review user yang aktif
> - Periksa audit log
> - Monitor error log
> - Verifikasi SSL
</details>

## 💻 20. Best Practices Pengembangan

<details>
<summary>🔄 Desain Database</summary>

```sql
-- 1. Normalisasi Database
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);

CREATE TABLE addresses (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL,
    address_type ENUM('home', 'work') NOT NULL,
    street VARCHAR(100) NOT NULL,
    city VARCHAR(50) NOT NULL,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

-- 2. Penggunaan Tipe Data yang Tepat
CREATE TABLE products (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    sku VARCHAR(20) UNIQUE NOT NULL,
    name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) UNSIGNED NOT NULL,
    stock INT UNSIGNED NOT NULL DEFAULT 0,
    status ENUM('active', 'inactive') NOT NULL DEFAULT 'active'
);

-- 3. Penggunaan Indeks
CREATE TABLE orders (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    customer_id INT UNSIGNED NOT NULL,
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    status ENUM('pending', 'processing', 'completed') NOT NULL,
    INDEX idx_customer (customer_id),
    INDEX idx_status (status),
    INDEX idx_order_date (order_date)
);
```

> 💡 **Tips**: 
> - Normalisasi database
> - Pilih tipe data yang sesuai
> - Buat indeks yang efektif
> - Gunakan constraint
> - Dokumentasikan struktur
</details>

<details>
<summary>🔄 Pengembangan Aplikasi</summary>

```sql
-- 1. Prepared Statements
PREPARE stmt FROM 'SELECT * FROM users WHERE id = ?';
SET @id = 1;
EXECUTE stmt USING @id;

-- 2. Transaksi
START TRANSACTION;
INSERT INTO orders (customer_id, amount) VALUES (1, 100);
UPDATE products SET stock = stock - 1 WHERE id = 1;
COMMIT;

-- 3. Error Handling
DELIMITER //
CREATE PROCEDURE process_order(IN order_id INT)
BEGIN
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
        ROLLBACK;
        SELECT 'Error occurred';
    END;
    
    START TRANSACTION;
    -- Proses order
    COMMIT;
END //
DELIMITER ;

-- 4. Stored Procedures
DELIMITER //
CREATE PROCEDURE get_customer_orders(IN customer_id INT)
BEGIN
    SELECT o.*, p.name as product_name
    FROM orders o
    JOIN order_items oi ON o.id = oi.order_id
    JOIN products p ON oi.product_id = p.id
    WHERE o.customer_id = customer_id;
END //
DELIMITER ;

-- 5. Views
CREATE VIEW customer_order_summary AS
SELECT 
    c.id as customer_id,
    c.name as customer_name,
    COUNT(o.id) as total_orders,
    SUM(o.amount) as total_amount
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
GROUP BY c.id, c.name;
```

> 💡 **Tips**: 
> - Gunakan prepared statements
> - Implementasikan transaksi
> - Handle error dengan baik
> - Gunakan stored procedures
> - Manfaatkan views
> - Dokumentasikan kode
</details>

## 📚 22. Glosarium Istilah MySQL

### 🔍 Cara Menggunakan Glosarium
1. Gunakan Ctrl+F untuk mencari istilah spesifik
2. Pelajari istilah sesuai dengan level pembelajaran Anda
3. Rujuk kembali ke bagian terkait untuk penjelasan detail
4. Praktikkan penggunaan istilah dalam konteks yang benar

### 1. Istilah Dasar
- **Query**: Perintah atau instruksi yang diberikan ke database untuk melakukan operasi tertentu
- **Database**: Kumpulan data yang terorganisir dan tersimpan secara sistematis
- **Table**: Struktur untuk menyimpan data dalam bentuk baris dan kolom
- **Column**: Bagian vertikal dari tabel yang menyimpan jenis data tertentu
- **Row**: Bagian horizontal dari tabel yang menyimpan satu set data
- **Record**: Satu baris data dalam tabel

### 2. Istilah Teknis
- **Dummy Data**: Data contoh atau data palsu yang digunakan untuk testing
- **Primary Key**: Kolom yang secara unik mengidentifikasi setiap baris dalam tabel
- **Foreign Key**: Kolom yang merujuk ke primary key tabel lain
- **Index**: Struktur data yang mempercepat pencarian data
- **Constraint**: Aturan yang membatasi jenis data yang bisa disimpan
- **Transaction**: Sekelompok operasi database yang dijalankan sebagai satu unit

### 3. Istilah Operasi
- **CRUD**: Create (Buat), Read (Baca), Update (Ubah), Delete (Hapus)
- **SELECT**: Perintah untuk membaca data
- **INSERT**: Perintah untuk menambah data
- **UPDATE**: Perintah untuk mengubah data
- **DELETE**: Perintah untuk menghapus data
- **JOIN**: Menggabungkan data dari beberapa tabel

### 4. Istilah Performa
- **Optimization**: Proses meningkatkan performa database
- **Backup**: Salinan data untuk keamanan
- **Restore**: Mengembalikan data dari backup
- **Replication**: Proses menyalin data ke server lain
- **Cache**: Penyimpanan sementara untuk mempercepat akses data

### 5. Istilah Keamanan
- **User**: Pengguna database
- **Password**: Kata sandi untuk autentikasi
- **Privilege**: Hak akses pengguna
- **Encryption**: Proses mengamankan data
- **Backup**: Salinan data untuk keamanan

### 6. Istilah Development
- **Stored Procedure**: Kumpulan perintah SQL yang disimpan di database
- **Trigger**: Kode yang dijalankan otomatis saat terjadi perubahan data
- **View**: Tabel virtual yang dibuat dari hasil query
- **Function**: Kode yang mengembalikan nilai
- **Variable**: Tempat menyimpan nilai sementara

### 7. Istilah Error
- **Syntax Error**: Kesalahan dalam penulisan perintah
- **Constraint Violation**: Pelanggaran aturan database
- **Deadlock**: Kondisi ketika dua transaksi saling menunggu
- **Timeout**: Waktu tunggu yang terlampaui
- **Connection Error**: Masalah koneksi ke database

### 8. Istilah Monitoring
- **Log**: Catatan aktivitas database
- **Performance**: Kinerja database
- **Resource**: Sumber daya yang digunakan
- **Status**: Kondisi database
- **Metric**: Ukuran performa database

### 9. Istilah Fungsi MySQL
- **Aggregate Function**: Fungsi untuk menghitung nilai dari sekelompok baris (COUNT, SUM, AVG)
- **String Function**: Fungsi untuk memanipulasi teks (CONCAT, SUBSTRING, REPLACE)
- **Date Function**: Fungsi untuk menangani tanggal dan waktu (NOW, DATE_FORMAT, DATEDIFF)
- **Numeric Function**: Fungsi untuk operasi matematika (ROUND, CEIL, FLOOR)
- **Window Function**: Fungsi untuk analisis data berurutan (ROW_NUMBER, RANK, LAG)

### 10. Istilah Tipe Data
- **Integer**: Tipe data untuk angka bulat (TINYINT, SMALLINT, INT, BIGINT)
- **Decimal**: Tipe data untuk angka desimal (DECIMAL, FLOAT, DOUBLE)
- **String**: Tipe data untuk teks (CHAR, VARCHAR, TEXT)
- **Date/Time**: Tipe data untuk tanggal dan waktu (DATE, TIME, DATETIME, TIMESTAMP)
- **Boolean**: Tipe data untuk nilai benar/salah (BOOLEAN, BOOL)
- **JSON**: Tipe data untuk menyimpan data JSON
- **BLOB**: Tipe data untuk menyimpan data biner besar

### 11. Istilah Join
- **Inner Join**: Menggabungkan baris yang cocok di kedua tabel
- **Left Join**: Menggabungkan semua baris dari tabel kiri dan baris yang cocok dari tabel kanan
- **Right Join**: Menggabungkan semua baris dari tabel kanan dan baris yang cocok dari tabel kiri
- **Full Join**: Menggabungkan semua baris dari kedua tabel
- **Cross Join**: Menggabungkan setiap baris dari tabel pertama dengan setiap baris dari tabel kedua
- **Self Join**: Menggabungkan tabel dengan dirinya sendiri

### 12. Istilah Optimasi
- **Query Plan**: Rencana eksekusi query yang dibuat oleh MySQL
- **Index Scan**: Pencarian data menggunakan indeks
- **Table Scan**: Pencarian data dengan membaca seluruh tabel
- **Buffer Pool**: Area memori untuk menyimpan data dan indeks
- **Query Cache**: Penyimpanan sementara untuk hasil query
- **Slow Query**: Query yang membutuhkan waktu eksekusi lama
- **Explain**: Perintah untuk melihat rencana eksekusi query

### 13. Istilah Replikasi
- **Master**: Server utama yang menangani write operations
- **Slave**: Server cadangan yang menyalin data dari master
- **Binary Log**: File yang mencatat perubahan data
- **Relay Log**: File yang menyimpan perubahan dari master
- **Replication Lag**: Keterlambatan sinkronisasi antara master dan slave
- **GTID**: Global Transaction Identifier untuk identifikasi transaksi

### 14. Istilah Backup
- **Full Backup**: Backup seluruh database
- **Incremental Backup**: Backup hanya data yang berubah
- **Point-in-Time Recovery**: Pemulihan ke waktu tertentu
- **Binary Log Backup**: Backup file binary log
- **Hot Backup**: Backup saat database sedang berjalan
- **Cold Backup**: Backup saat database dimatikan

### 15. Istilah Keamanan Lanjutan
- **SSL/TLS**: Protokol untuk mengenkripsi koneksi
- **Role**: Kumpulan hak akses yang bisa diberikan ke user
- **Audit Log**: Catatan aktivitas untuk keamanan
- **Encryption at Rest**: Enkripsi data yang tersimpan
- **Encryption in Transit**: Enkripsi data yang dikirim
- **Password Policy**: Aturan untuk pembuatan password

> 💡 **Tips**: 
> - Pahami istilah-istilah ini untuk memudahkan pembelajaran
> - Gunakan istilah yang tepat saat berkomunikasi dengan tim
> - Dokumentasikan istilah baru yang Anda pelajari
> - Praktikkan penggunaan istilah dalam konteks yang benar
> - Pelajari istilah sesuai dengan level pembelajaran Anda

## 📝 Catatan Penting
- Dokumen ini akan diperbarui secara berkala
- Silakan berkontribusi untuk meningkatkan kualitas dokumen
- Laporkan kesalahan atau saran perbaikan melalui Issues
- Ikuti panduan kontribusi untuk menambahkan konten baru

## 🤝 Berkontribusi
Kami menerima kontribusi untuk meningkatkan kualitas dokumen ini. Silakan:
1. Fork repository
2. Buat branch baru
3. Tambahkan konten atau perbaikan
4. Submit pull request

## 📄 Lisensi
Dokumen ini dilisensikan di bawah [MIT License](LICENSE)

## 🙏 Terima Kasih
Terima kasih telah menggunakan panduan ini. Semoga bermanfaat dalam perjalanan belajar MySQL Anda!

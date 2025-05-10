# 🗄️ Panduan Perintah MySQL

<div align="center">

![MySQL Logo](https://www.mysql.com/common/logos/logo-mysql-170x115.png)

> 💡 **Panduan Lengkap MySQL** - Referensi cepat untuk menguasai perintah-perintah MySQL dengan mudah

</div>

## 📑 Daftar Isi
- [🗄️ Panduan Perintah MySQL](#️-panduan-perintah-mysql)
  - [📑 Daftar Isi](#-daftar-isi)
  - [📌 1. Perintah Dasar](#-1-perintah-dasar)
  - [📊 2. Operasi Tabel](#-2-operasi-tabel)
  - [🔄 3. Operasi Data (CRUD)](#-3-operasi-data-crud)
  - [🔍 4. Query Lanjutan](#-4-query-lanjutan)
  - [📊 5. Fungsi Agregasi](#-5-fungsi-agregasi)
  - [⚖️ 6. Operator Perbandingan](#️-6-operator-perbandingan)
  - [🧮 7. Operator Logika](#-7-operator-logika)
  - [📋 8. Pengurutan dan Pembatasan](#-8-pengurutan-dan-pembatasan)
  - [📌 9. Indeks](#-9-indeks)
  - [💾 10. Backup dan Restore](#-10-backup-dan-restore)

---

## 📌 1. Perintah Dasar

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
-- Template
SHOW DATABASES;

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
```

> 💡 **Tips**: 
> - Perintah ini akan menampilkan semua database yang Anda miliki akses
> - Database system seperti `information_schema`, `mysql`, `performance_schema`, dan `sys` adalah database bawaan MySQL
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
-- Template
SHOW TABLES;

-- Contoh Output
+------------------------+
| Tables_in_toko_online  |
+------------------------+
| customers             |
| orders               |
| products             |
+------------------------+
```

> 💡 **Tips**: 
> - Perintah ini hanya akan bekerja setelah Anda memilih database dengan `USE`
> - Untuk melihat struktur tabel, gunakan `DESCRIBE [nama_tabel]`
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

## 📊 2. Operasi Tabel

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

-- Menghapus Kolom
ALTER TABLE [nama_tabel] DROP COLUMN [kolom_lama];

-- Mengubah Tipe Data Kolom
ALTER TABLE [nama_tabel] MODIFY [kolom] [tipe_data_baru];

-- Mengubah Nama Kolom
ALTER TABLE [nama_tabel] CHANGE [kolom_lama] [kolom_baru] [tipe_data];

-- Contoh
ALTER TABLE products ADD description TEXT;
ALTER TABLE products DROP COLUMN old_column;
ALTER TABLE products MODIFY price DECIMAL(12,2);
ALTER TABLE products CHANGE name product_name VARCHAR(100);
```

> ⚠️ **Peringatan**: 
> - Selalu backup data sebelum melakukan perubahan struktur tabel
> - Perubahan tipe data bisa menyebabkan kehilangan data
> - Pastikan tidak ada constraint yang terganggu
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

## 🔄 3. Operasi Data (CRUD)

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
-- Template
UPDATE [nama_tabel] SET [kolom] = 'nilai_baru' WHERE [kondisi];

-- Contoh
UPDATE products SET price = 1600000 WHERE id = 1;
UPDATE products SET stock = stock - 1 WHERE id = 1;
UPDATE products SET 
    price = 1600000,
    stock = 20
WHERE id = 1;
```

> ⚠️ **Peringatan**: 
> - Selalu gunakan klausa WHERE untuk menghindari update yang tidak diinginkan
> - Gunakan transaksi untuk update yang kompleks
> - Backup data sebelum melakukan update massal
</details>

<details>
<summary>🗑️ Delete Data</summary>

```sql
-- Template
DELETE FROM [nama_tabel] WHERE [kondisi];

-- Contoh
DELETE FROM products WHERE id = 1;
DELETE FROM products WHERE stock = 0;
```

> ⚠️ **Peringatan**: 
> - Selalu gunakan klausa WHERE untuk menghindari penghapusan data yang tidak diinginkan
> - Pertimbangkan menggunakan soft delete (menggunakan kolom status) daripada hard delete
> - Backup data sebelum melakukan delete massal
</details>

## 🔍 4. Query Lanjutan

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

## 📊 5. Fungsi Agregasi

| Fungsi | Deskripsi | Contoh |
|--------|-----------|---------|
| `COUNT()` | Menghitung jumlah baris | `SELECT COUNT(*) FROM products` |
| `SUM()` | Menjumlahkan nilai | `SELECT SUM(price) FROM orders` |
| `AVG()` | Menghitung rata-rata | `SELECT AVG(price) FROM products` |
| `MAX()` | Mencari nilai maksimum | `SELECT MAX(price) FROM products` |
| `MIN()` | Mencari nilai minimum | `SELECT MIN(price) FROM products` |
| `GROUP_CONCAT()` | Menggabungkan nilai menjadi string | `SELECT GROUP_CONCAT(name) FROM products` |

## ⚖️ 6. Operator Perbandingan

| Operator | Deskripsi | Contoh |
|----------|-----------|---------|
| `=` | Sama dengan | `WHERE price = 1000000` |
| `!=` atau `<>` | Tidak sama dengan | `WHERE status != 'aktif'` |
| `>` | Lebih besar | `WHERE price > 1000000` |
| `<` | Lebih kecil | `WHERE stock < 10` |
| `>=` | Lebih besar atau sama dengan | `WHERE price >= 1000000` |
| `<=` | Lebih kecil atau sama dengan | `WHERE stock <= 10` |
| `LIKE` | Pencocokan pola | `WHERE name LIKE 'Laptop%'` |
| `IN` | Dalam daftar nilai | `WHERE id IN (1,2,3)` |
| `BETWEEN` | Antara dua nilai | `WHERE price BETWEEN 1000000 AND 2000000` |
| `IS NULL` | Nilai NULL | `WHERE description IS NULL` |
| `IS NOT NULL` | Bukan nilai NULL | `WHERE description IS NOT NULL` |

## 🧮 7. Operator Logika

| Operator | Deskripsi | Contoh |
|----------|-----------|---------|
| `AND` | Dan | `WHERE price > 1000000 AND stock > 0` |
| `OR` | Atau | `WHERE category = 'Laptop' OR category = 'Smartphone'` |
| `NOT` | Tidak | `WHERE NOT status = 'inaktif'` |
| `XOR` | Exclusive OR | `WHERE price > 1000000 XOR stock > 0` |

## 📋 8. Pengurutan dan Pembatasan

<details>
<summary>📋 Pengurutan dan Pembatasan</summary>

```sql
-- Template
SELECT * FROM [nama_tabel]
ORDER BY [kolom] [ASC/DESC]
LIMIT [jumlah]
OFFSET [jumlah];

-- Contoh
SELECT * FROM products
ORDER BY price DESC
LIMIT 10;

-- Dengan OFFSET
SELECT * FROM products
ORDER BY price DESC
LIMIT 10 OFFSET 20;  -- Skip 20 baris pertama

-- Multiple Sort
SELECT * FROM products
ORDER BY category ASC, price DESC;
```

> 💡 **Tips**: 
> - Kombinasikan ORDER BY dengan LIMIT untuk mendapatkan data terurut yang dibatasi
> - Gunakan OFFSET untuk pagination
> - Bisa mengurutkan berdasarkan multiple kolom
</details>

## 📌 9. Indeks

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

## 💾 10. Backup dan Restore

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

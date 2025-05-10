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
  - [📅 6. Fungsi Tanggal dan Waktu](#-6-fungsi-tanggal-dan-waktu)
  - [📝 7. Fungsi String](#-7-fungsi-string)
  - [🔢 8. Fungsi Numerik](#-8-fungsi-numerik)
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

## 📅 6. Fungsi Tanggal dan Waktu

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

## 📝 7. Fungsi String

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

## 🔢 8. Fungsi Numerik

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

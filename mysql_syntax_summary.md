# 📝 MySQL Syntax Reference Guide

## 📋 Table of Contents
- [📝 MySQL Syntax Reference Guide](#-mysql-syntax-reference-guide)
  - [📋 Table of Contents](#-table-of-contents)
  - [📋 Tabel Sintaks MySQL](#-tabel-sintaks-mysql)
    - [🔷 Perintah DDL (Data Definition Language)](#-perintah-ddl-data-definition-language)
    - [🔷 Perintah DML (Data Manipulation Language)](#-perintah-dml-data-manipulation-language)
    - [🔷 Perintah DQL (Data Query Language)](#-perintah-dql-data-query-language)
    - [🔷 Tipe Data dan Constraint](#-tipe-data-dan-constraint)
      - [Constraint](#constraint)
    - [🔷 Fungsi Agregasi](#-fungsi-agregasi)
    - [🔷 Fungsi String](#-fungsi-string)
    - [🔷 Fungsi Tanggal dan Waktu](#-fungsi-tanggal-dan-waktu)
    - [🔷 Fungsi Numerik](#-fungsi-numerik)
    - [🔷 Fungsi Informasi](#-fungsi-informasi)
    - [🔷 Fungsi Enkripsi dan Hashing](#-fungsi-enkripsi-dan-hashing)
    - [🔷 Fungsi JSON](#-fungsi-json)
    - [🔷 Fitur Lanjutan](#-fitur-lanjutan)
      - [Views](#views)
      - [Stored Procedures](#stored-procedures)
      - [Functions](#functions)
      - [Triggers](#triggers)
      - [Events](#events)
      - [Partitioning](#partitioning)
    - [🔷 Transaksi (Transaction)](#-transaksi-transaction)
    - [🔷 User Management](#-user-management)
    - [🔷 Best Practices dan Keamanan](#-best-practices-dan-keamanan)
      - [Performance Tuning](#performance-tuning)
      - [Security Best Practices](#security-best-practices)
      - [Monitoring dan Maintenance](#monitoring-dan-maintenance)
  - [📌 Catatan Penting](#-catatan-penting)
  - [⚡ Performance Tips](#-performance-tips)
    - [Query Optimization](#query-optimization)
    - [Table Design](#table-design)
  - [🔒 Security Best Practices](#-security-best-practices)
  - [⚠️ Common Pitfalls](#️-common-pitfalls)

## 📋 Tabel Sintaks MySQL

### 🔷 Perintah DDL (Data Definition Language)

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `CREATE DATABASE` | Membuat database baru | `CREATE DATABASE nama_database;` |
| `CREATE DATABASE IF NOT EXISTS` | Membuat database jika belum ada | `CREATE DATABASE IF NOT EXISTS nama_database;` |
| `CREATE TABLE` | Membuat tabel baru | `CREATE TABLE users (id INT PRIMARY KEY, name VARCHAR(50));` |
| `CREATE TABLE IF NOT EXISTS` | Membuat tabel jika belum ada | `CREATE TABLE IF NOT EXISTS users (id INT PRIMARY KEY);` |
| `CREATE TABLE LIKE` | Membuat tabel dengan struktur yang sama | `CREATE TABLE new_users LIKE users;` |
| `CREATE TABLE AS SELECT` | Membuat tabel dari hasil query | `CREATE TABLE active_users AS SELECT * FROM users WHERE status = 'active';` |
| `ALTER TABLE` | Mengubah struktur tabel | `ALTER TABLE users ADD email VARCHAR(100);` |
| `ALTER TABLE RENAME` | Mengubah nama tabel | `ALTER TABLE users RENAME TO customers;` |
| `ALTER TABLE RENAME COLUMN` | Mengubah nama kolom | `ALTER TABLE users RENAME COLUMN name TO full_name;` |
| `ALTER TABLE MODIFY` | Mengubah tipe data kolom | `ALTER TABLE users MODIFY name VARCHAR(100);` |
| `ALTER TABLE CHANGE` | Mengubah nama dan tipe data kolom | `ALTER TABLE users CHANGE name full_name VARCHAR(100);` |
| `ALTER TABLE DROP` | Menghapus kolom | `ALTER TABLE users DROP COLUMN email;` |
| `DROP TABLE` | Menghapus tabel | `DROP TABLE users;` |
| `DROP TABLE IF EXISTS` | Menghapus tabel jika ada | `DROP TABLE IF EXISTS users;` |
| `DROP DATABASE` | Menghapus database | `DROP DATABASE nama_database;` |
| `DROP DATABASE IF EXISTS` | Menghapus database jika ada | `DROP DATABASE IF EXISTS nama_database;` |
| `TRUNCATE TABLE` | Menghapus semua data dalam tabel | `TRUNCATE TABLE users;` |
| `RENAME TABLE` | Mengubah nama tabel | `RENAME TABLE users TO customers;` |

### 🔷 Perintah DML (Data Manipulation Language)

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `INSERT INTO` | Menambah data ke tabel | `INSERT INTO users (name) VALUES ('John');` |
| `INSERT INTO ... SELECT` | Menambah data dari hasil query | `INSERT INTO users SELECT * FROM old_users;` |
| `INSERT IGNORE` | Menambah data (mengabaikan error) | `INSERT IGNORE INTO users (id, name) VALUES (1, 'John');` |
| `INSERT ... ON DUPLICATE KEY UPDATE` | Menambah/update data | `INSERT INTO users (id, name) VALUES (1, 'John') ON DUPLICATE KEY UPDATE name = 'John';` |
| `REPLACE INTO` | Menambah/mengganti data | `REPLACE INTO users (id, name) VALUES (1, 'John');` |
| `UPDATE` | Mengubah data dalam tabel | `UPDATE users SET name = 'Jane' WHERE id = 1;` |
| `UPDATE ... ORDER BY` | Mengubah data dengan urutan tertentu | `UPDATE users SET status = 'inactive' ORDER BY last_login LIMIT 10;` |
| `UPDATE ... LIMIT` | Membatasi jumlah data yang diubah | `UPDATE users SET status = 'inactive' LIMIT 10;` |
| `DELETE` | Menghapus data dari tabel | `DELETE FROM users WHERE id = 1;` |
| `DELETE ... ORDER BY` | Menghapus data dengan urutan tertentu | `DELETE FROM users ORDER BY last_login LIMIT 10;` |
| `DELETE ... LIMIT` | Membatasi jumlah data yang dihapus | `DELETE FROM users LIMIT 10;` |
| `INSERT ... VALUES (...), (...), ...` | Menambah multiple data | `INSERT INTO users (name) VALUES ('John'), ('Jane'), ('Bob');` |

### 🔷 Perintah DQL (Data Query Language)

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `SELECT` | Mengambil data dari tabel | `SELECT * FROM users;` |
| `SELECT DISTINCT` | Mengambil data unik | `SELECT DISTINCT name FROM users;` |
| `SELECT ... INTO` | Menyimpan hasil query ke variabel | `SELECT name INTO @user_name FROM users WHERE id = 1;` |
| `SELECT ... INTO OUTFILE` | Menyimpan hasil query ke file | `SELECT * INTO OUTFILE '/tmp/users.csv' FROM users;` |
| `SELECT ... INTO DUMPFILE` | Menyimpan hasil query ke file biner | `SELECT data INTO DUMPFILE '/tmp/file.bin' FROM files;` |
| `SELECT ... FOR UPDATE` | Mengunci baris untuk update | `SELECT * FROM users WHERE id = 1 FOR UPDATE;` |
| `SELECT ... LOCK IN SHARE MODE` | Mengunci baris untuk dibaca | `SELECT * FROM users WHERE id = 1 LOCK IN SHARE MODE;` |
| `ORDER BY` | Mengurutkan hasil query | `SELECT * FROM users ORDER BY name ASC;` |
| `GROUP BY` | Mengelompokkan hasil query | `SELECT department, COUNT(*) FROM users GROUP BY department;` |
| `HAVING` | Memfilter hasil setelah GROUP BY | `SELECT department, COUNT(*) FROM users GROUP BY department HAVING COUNT(*) > 5;` |
| `LIMIT` | Membatasi jumlah hasil query | `SELECT * FROM users LIMIT 10;` |
| `INNER JOIN` | Menggabungkan dua tabel berdasarkan kondisi | `SELECT users.name, orders.order_id FROM users INNER JOIN orders ON users.id = orders.user_id;` |
| `LEFT JOIN` | Menggabungkan dua tabel dan mengambil semua baris dari tabel kiri | `SELECT users.name, orders.order_id FROM users LEFT JOIN orders ON users.id = orders.user_id;` |
| `RIGHT JOIN` | Menggabungkan dua tabel dan mengambil semua baris dari tabel kanan | `SELECT users.name, orders.order_id FROM users RIGHT JOIN orders ON users.id = orders.user_id;` |
| `FULL JOIN` | Menggabungkan dua tabel dan mengambil semua baris dari kedua tabel | `SELECT users.name, orders.order_id FROM users FULL JOIN orders ON users.id = orders.user_id;` |
| `Subquery` | Query di dalam query | `SELECT * FROM users WHERE id IN (SELECT user_id FROM orders);` |
| `UNION` | Menggabungkan hasil dari dua atau lebih query | `SELECT name FROM users UNION SELECT name FROM customers;` |
| `UNION ALL` | Menggabungkan hasil tanpa menghilangkan duplikat | `SELECT name FROM users UNION ALL SELECT name FROM customers;` |
| `CASE` | Membuat kondisi di dalam query | `SELECT name, CASE WHEN age < 18 THEN 'Minor' ELSE 'Adult' END AS age_group FROM users;` |

### 🔷 Tipe Data dan Constraint

| Kategori | Tipe Data | Deskripsi | Contoh Penggunaan |
|----------|-----------|-----------|-------------------|
| Numeric | `INT` | Bilangan bulat 32-bit | `id INT PRIMARY KEY` |
| | `BIGINT` | Bilangan bulat 64-bit | `user_id BIGINT` |
| | `DECIMAL` | Bilangan desimal presisi | `price DECIMAL(10,2)` |
| | `FLOAT` | Bilangan floating point | `weight FLOAT` |
| String | `VARCHAR` | String panjang variabel | `name VARCHAR(100)` |
| | `TEXT` | String panjang tak terbatas | `description TEXT` |
| | `CHAR` | String panjang tetap | `code CHAR(5)` |
| | `ENUM` | String dari pilihan tetap | `status ENUM('active','inactive')` |
| Date/Time | `DATE` | Tanggal | `birth_date DATE` |
| | `DATETIME` | Tanggal dan waktu | `created_at DATETIME` |
| | `TIMESTAMP` | Timestamp | `updated_at TIMESTAMP` |
| | `TIME` | Waktu | `duration TIME` |
| Boolean | `BOOLEAN` | Nilai boolean | `is_active BOOLEAN` |
| | `TINYINT(1)` | Alternatif boolean | `is_deleted TINYINT(1)` |

#### Constraint
| Constraint | Deskripsi | Contoh Penggunaan |
|------------|-----------|-------------------|
| `PRIMARY KEY` | Kunci utama tabel | `id INT PRIMARY KEY` |
| `FOREIGN KEY` | Kunci asing untuk relasi | `FOREIGN KEY (user_id) REFERENCES users(id)` |
| `UNIQUE` | Nilai harus unik | `email VARCHAR(100) UNIQUE` |
| `NOT NULL` | Nilai tidak boleh kosong | `name VARCHAR(100) NOT NULL` |
| `DEFAULT` | Nilai default | `status VARCHAR(20) DEFAULT 'active'` |
| `CHECK` | Validasi nilai | `age INT CHECK (age >= 18)` |
| `AUTO_INCREMENT` | Increment otomatis | `id INT AUTO_INCREMENT` |
| `ON UPDATE` | Aksi saat update | `FOREIGN KEY (user_id) REFERENCES users(id) ON UPDATE CASCADE` |
| `ON DELETE` | Aksi saat delete | `FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE` |

### 🔷 Fungsi Agregasi

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `COUNT` | Menghitung jumlah data | `SELECT COUNT(*) FROM users;` |
| `COUNT(DISTINCT)` | Menghitung jumlah data unik | `SELECT COUNT(DISTINCT name) FROM users;` |
| `SUM` | Menjumlahkan data | `SELECT SUM(price) FROM orders;` |
| `AVG` | Menghitung rata-rata | `SELECT AVG(price) FROM orders;` |
| `MAX` | Mengambil nilai terbesar | `SELECT MAX(price) FROM orders;` |
| `MIN` | Mengambil nilai terkecil | `SELECT MIN(price) FROM orders;` |
| `GROUP_CONCAT` | Menggabungkan string dalam grup | `SELECT GROUP_CONCAT(name) FROM users GROUP BY department;` |
| `STD` | Menghitung standar deviasi | `SELECT STD(price) FROM products;` |
| `VARIANCE` | Menghitung variansi | `SELECT VARIANCE(price) FROM products;` |

### 🔷 Fungsi String

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `CONCAT` | Menggabungkan string | `SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM users;` |
| `CONCAT_WS` | Menggabungkan string dengan separator | `SELECT CONCAT_WS('-', first_name, last_name) FROM users;` |
| `SUBSTRING` | Mengambil bagian dari string | `SELECT SUBSTRING(name, 1, 3) FROM users;` |
| `SUBSTRING_INDEX` | Mengambil bagian string berdasarkan delimiter | `SELECT SUBSTRING_INDEX(email, '@', 1) FROM users;` |
| `REPLACE` | Mengganti bagian dari string | `SELECT REPLACE(name, 'a', 'o') FROM users;` |
| `UPPER` | Mengubah string menjadi huruf besar | `SELECT UPPER(name) FROM users;` |
| `LOWER` | Mengubah string menjadi huruf kecil | `SELECT LOWER(name) FROM users;` |
| `TRIM` | Menghapus spasi di awal dan akhir string | `SELECT TRIM(name) FROM users;` |
| `LTRIM` | Menghapus spasi di awal string | `SELECT LTRIM(name) FROM users;` |
| `RTRIM` | Menghapus spasi di akhir string | `SELECT RTRIM(name) FROM users;` |
| `LENGTH` | Menghitung panjang string | `SELECT LENGTH(name) FROM users;` |
| `CHAR_LENGTH` | Menghitung jumlah karakter | `SELECT CHAR_LENGTH(name) FROM users;` |
| `LEFT` | Mengambil karakter dari kiri | `SELECT LEFT(name, 3) FROM users;` |
| `RIGHT` | Mengambil karakter dari kanan | `SELECT RIGHT(name, 3) FROM users;` |
| `REPEAT` | Mengulang string | `SELECT REPEAT('*', 5);` |
| `REVERSE` | Membalik string | `SELECT REVERSE(name) FROM users;` |
| `LOCATE` | Mencari posisi substring | `SELECT LOCATE('a', name) FROM users;` |
| `INSTR` | Mencari posisi substring | `SELECT INSTR(name, 'a') FROM users;` |
| `FIELD` | Mencari posisi nilai dalam list | `SELECT FIELD('a', 'a', 'b', 'c');` |
| `ELT` | Mengambil nilai dari list berdasarkan posisi | `SELECT ELT(1, 'a', 'b', 'c');` |
| `FIND_IN_SET` | Mencari nilai dalam string yang dipisahkan koma | `SELECT FIND_IN_SET('a', 'a,b,c');` |
| `MAKE_SET` | Membuat set dari bit | `SELECT MAKE_SET(1|4, 'a', 'b', 'c', 'd');` |
| `EXPORT_SET` | Membuat string dari bit | `SELECT EXPORT_SET(5, 'Y', 'N', ',', 4);` |
| `LPAD` | Menambahkan karakter di kiri | `SELECT LPAD(name, 10, '*') FROM users;` |
| `RPAD` | Menambahkan karakter di kanan | `SELECT RPAD(name, 10, '*') FROM users;` |
| `SPACE` | Membuat string spasi | `SELECT SPACE(5);` |
| `STRCMP` | Membandingkan string | `SELECT STRCMP('a', 'b');` |
| `SOUNDEX` | Menghasilkan kode suara | `SELECT SOUNDEX('John');` |

### 🔷 Fungsi Tanggal dan Waktu

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `NOW` | Mengambil waktu saat ini | `SELECT NOW();` |
| `CURDATE` | Mengambil tanggal saat ini | `SELECT CURDATE();` |
| `CURTIME` | Mengambil waktu saat ini | `SELECT CURTIME();` |
| `DATE` | Mengambil bagian tanggal | `SELECT DATE(created_at) FROM users;` |
| `TIME` | Mengambil bagian waktu | `SELECT TIME(created_at) FROM users;` |
| `YEAR` | Mengambil tahun | `SELECT YEAR(created_at) FROM users;` |
| `MONTH` | Mengambil bulan | `SELECT MONTH(created_at) FROM users;` |
| `DAY` | Mengambil hari | `SELECT DAY(created_at) FROM users;` |
| `HOUR` | Mengambil jam | `SELECT HOUR(created_at) FROM users;` |
| `MINUTE` | Mengambil menit | `SELECT MINUTE(created_at) FROM users;` |
| `SECOND` | Mengambil detik | `SELECT SECOND(created_at) FROM users;` |
| `MICROSECOND` | Mengambil mikrodetik | `SELECT MICROSECOND(created_at) FROM users;` |
| `DATE_FORMAT` | Memformat tanggal | `SELECT DATE_FORMAT(created_at, '%Y-%m-%d') FROM users;` |
| `TIME_FORMAT` | Memformat waktu | `SELECT TIME_FORMAT(created_at, '%H:%i:%s') FROM users;` |
| `DATEDIFF` | Menghitung selisih hari | `SELECT DATEDIFF(end_date, start_date) FROM projects;` |
| `TIMESTAMPDIFF` | Menghitung selisih waktu | `SELECT TIMESTAMPDIFF(YEAR, birth_date, NOW()) FROM users;` |
| `DATE_ADD` | Menambah waktu | `SELECT DATE_ADD(NOW(), INTERVAL 1 DAY);` |
| `DATE_SUB` | Mengurangi waktu | `SELECT DATE_SUB(NOW(), INTERVAL 1 DAY);` |
| `ADDDATE` | Menambah tanggal | `SELECT ADDDATE(NOW(), INTERVAL 1 DAY);` |
| `SUBDATE` | Mengurangi tanggal | `SELECT SUBDATE(NOW(), INTERVAL 1 DAY);` |
| `LAST_DAY` | Mengambil hari terakhir bulan | `SELECT LAST_DAY(NOW());` |
| `DAYOFWEEK` | Mengambil hari dalam seminggu | `SELECT DAYOFWEEK(NOW());` |
| `DAYOFYEAR` | Mengambil hari dalam setahun | `SELECT DAYOFYEAR(NOW());` |
| `WEEK` | Mengambil minggu dalam setahun | `SELECT WEEK(NOW());` |
| `WEEKDAY` | Mengambil hari kerja | `SELECT WEEKDAY(NOW());` |
| `QUARTER` | Mengambil kuartal | `SELECT QUARTER(NOW());` |
| `EXTRACT` | Mengambil bagian dari tanggal | `SELECT EXTRACT(YEAR FROM NOW());` |
| `TO_DAYS` | Mengkonversi tanggal ke hari | `SELECT TO_DAYS(NOW());` |
| `FROM_DAYS` | Mengkonversi hari ke tanggal | `SELECT FROM_DAYS(730000);` |
| `UNIX_TIMESTAMP` | Mengkonversi tanggal ke timestamp | `SELECT UNIX_TIMESTAMP(NOW());` |
| `FROM_UNIXTIME` | Mengkonversi timestamp ke tanggal | `SELECT FROM_UNIXTIME(1234567890);` |
| `UTC_DATE` | Mengambil tanggal UTC | `SELECT UTC_DATE();` |
| `UTC_TIME` | Mengambil waktu UTC | `SELECT UTC_TIME();` |
| `UTC_TIMESTAMP` | Mengambil timestamp UTC | `SELECT UTC_TIMESTAMP();` |

### 🔷 Fungsi Numerik

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `ROUND` | Membulatkan angka | `SELECT ROUND(price, 2) FROM products;` |
| `CEIL` | Membulatkan ke atas | `SELECT CEIL(price) FROM products;` |
| `FLOOR` | Membulatkan ke bawah | `SELECT FLOOR(price) FROM products;` |
| `ABS` | Mengambil nilai absolut | `SELECT ABS(price) FROM products;` |
| `MOD` | Mengambil sisa bagi | `SELECT MOD(quantity, 2) FROM orders;` |
| `POWER` | Menghitung pangkat | `SELECT POWER(price, 2) FROM products;` |
| `SQRT` | Menghitung akar kuadrat | `SELECT SQRT(price) FROM products;` |
| `RAND` | Mengambil angka acak | `SELECT RAND();` |
| `FORMAT` | Memformat angka | `SELECT FORMAT(price, 2) FROM products;` |
| `GREATEST` | Mengambil nilai terbesar | `SELECT GREATEST(price1, price2, price3) FROM products;` |
| `LEAST` | Mengambil nilai terkecil | `SELECT LEAST(price1, price2, price3) FROM products;` |
| `TRUNCATE` | Memotong angka desimal | `SELECT TRUNCATE(price, 2) FROM products;` |
| `SIGN` | Mengambil tanda angka | `SELECT SIGN(price) FROM products;` |
| `PI` | Mengambil nilai pi | `SELECT PI();` |
| `DEGREES` | Mengkonversi radian ke derajat | `SELECT DEGREES(PI());` |
| `RADIANS` | Mengkonversi derajat ke radian | `SELECT RADIANS(180);` |
| `SIN` | Menghitung sinus | `SELECT SIN(angle) FROM angles;` |
| `COS` | Menghitung cosinus | `SELECT COS(angle) FROM angles;` |
| `TAN` | Menghitung tangen | `SELECT TAN(angle) FROM angles;` |
| `ASIN` | Menghitung arcsinus | `SELECT ASIN(value) FROM values;` |
| `ACOS` | Menghitung arccosinus | `SELECT ACOS(value) FROM values;` |
| `ATAN` | Menghitung arctangen | `SELECT ATAN(value) FROM values;` |
| `ATAN2` | Menghitung arctangen 2 | `SELECT ATAN2(y, x) FROM points;` |
| `COT` | Menghitung cotangen | `SELECT COT(angle) FROM angles;` |
| `EXP` | Menghitung e pangkat x | `SELECT EXP(value) FROM values;` |
| `LN` | Menghitung logaritma natural | `SELECT LN(value) FROM values;` |
| `LOG` | Menghitung logaritma | `SELECT LOG(value) FROM values;` |
| `LOG10` | Menghitung logaritma basis 10 | `SELECT LOG10(value) FROM values;` |
| `LOG2` | Menghitung logaritma basis 2 | `SELECT LOG2(value) FROM values;` |

### 🔷 Fungsi Informasi

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `DATABASE` | Mengambil nama database saat ini | `SELECT DATABASE();` |
| `USER` | Mengambil user saat ini | `SELECT USER();` |
| `VERSION` | Mengambil versi MySQL | `SELECT VERSION();` |
| `CONNECTION_ID` | Mengambil ID koneksi | `SELECT CONNECTION_ID();` |
| `LAST_INSERT_ID` | Mengambil ID terakhir yang diinsert | `SELECT LAST_INSERT_ID();` |
| `ROW_COUNT` | Mengambil jumlah baris yang terpengaruh | `SELECT ROW_COUNT();` |
| `FOUND_ROWS` | Mengambil jumlah baris yang ditemukan | `SELECT FOUND_ROWS();` |
| `SCHEMA` | Mengambil nama database saat ini | `SELECT SCHEMA();` |
| `SESSION_USER` | Mengambil user session | `SELECT SESSION_USER();` |
| `SYSTEM_USER` | Mengambil system user | `SELECT SYSTEM_USER();` |
| `CURRENT_USER` | Mengambil current user | `SELECT CURRENT_USER();` |
| `CURRENT_TIMESTAMP` | Mengambil timestamp saat ini | `SELECT CURRENT_TIMESTAMP();` |
| `CURRENT_DATE` | Mengambil tanggal saat ini | `SELECT CURRENT_DATE();` |
| `CURRENT_TIME` | Mengambil waktu saat ini | `SELECT CURRENT_TIME();` |

### 🔷 Fungsi Enkripsi dan Hashing

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `MD5` | Menghasilkan hash MD5 | `SELECT MD5('password');` |
| `SHA1` | Menghasilkan hash SHA1 | `SELECT SHA1('password');` |
| `SHA2` | Menghasilkan hash SHA2 | `SELECT SHA2('password', 256);` |
| `AES_ENCRYPT` | Mengenkripsi data | `SELECT AES_ENCRYPT('data', 'key');` |
| `AES_DECRYPT` | Mendekripsi data | `SELECT AES_DECRYPT(encrypted_data, 'key');` |
| `ENCRYPT` | Mengenkripsi string | `SELECT ENCRYPT('password');` |
| `DECRYPT` | Mendekripsi string | `SELECT DECRYPT(encrypted_string);` |
| `COMPRESS` | Mengkompresi string | `SELECT COMPRESS('long string');` |
| `UNCOMPRESS` | Mendekompresi string | `SELECT UNCOMPRESS(compressed_string);` |
| `PASSWORD` | Mengenkripsi password | `SELECT PASSWORD('password');` |
| `OLD_PASSWORD` | Mengenkripsi password (lama) | `SELECT OLD_PASSWORD('password');` |

### 🔷 Fungsi JSON

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `JSON_EXTRACT` | Mengambil nilai dari JSON | `SELECT JSON_EXTRACT(data, '$.name') FROM users;` |
| `JSON_CONTAINS` | Mengecek keberadaan nilai dalam JSON | `SELECT JSON_CONTAINS(data, '"value"', '$.key') FROM users;` |
| `JSON_CONTAINS_PATH` | Mengecek keberadaan path dalam JSON | `SELECT JSON_CONTAINS_PATH(data, 'one', '$.key') FROM users;` |
| `JSON_LENGTH` | Mengambil panjang JSON | `SELECT JSON_LENGTH(data) FROM users;` |
| `JSON_DEPTH` | Mengambil kedalaman JSON | `SELECT JSON_DEPTH(data) FROM users;` |
| `JSON_TYPE` | Mengambil tipe nilai JSON | `SELECT JSON_TYPE(data) FROM users;` |
| `JSON_VALID` | Mengecek validitas JSON | `SELECT JSON_VALID(data) FROM users;` |
| `JSON_OBJECT` | Membuat objek JSON | `SELECT JSON_OBJECT('key', 'value');` |
| `JSON_ARRAY` | Membuat array JSON | `SELECT JSON_ARRAY('value1', 'value2');` |
| `JSON_MERGE_PRESERVE` | Menggabungkan JSON | `SELECT JSON_MERGE_PRESERVE('{"a": 1}', '{"b": 2}');` |
| `JSON_MERGE_PATCH` | Menggabungkan JSON | `SELECT JSON_MERGE_PATCH('{"a": 1}', '{"b": 2}');` |
| `JSON_REMOVE` | Menghapus nilai dari JSON | `SELECT JSON_REMOVE(data, '$.key') FROM users;` |
| `JSON_REPLACE` | Mengganti nilai dalam JSON | `SELECT JSON_REPLACE(data, '$.key', 'new_value') FROM users;` |
| `JSON_SET` | Mengatur nilai dalam JSON | `SELECT JSON_SET(data, '$.key', 'value') FROM users;` |
| `JSON_INSERT` | Menyisipkan nilai ke JSON | `SELECT JSON_INSERT(data, '$.key', 'value') FROM users;` |
| `JSON_KEYS` | Mengambil kunci dari JSON | `SELECT JSON_KEYS(data) FROM users;` |
| `JSON_SEARCH` | Mencari nilai dalam JSON | `SELECT JSON_SEARCH(data, 'one', 'value') FROM users;` |

### 🔷 Fitur Lanjutan

#### Views
| Sintaks | Deskripsi | Contoh Penggunaan |
|---------|-----------|-------------------|
| `CREATE VIEW` | Membuat view | `CREATE VIEW active_users AS SELECT * FROM users WHERE status = 'active'` |
| `CREATE OR REPLACE VIEW` | Membuat atau mengganti view | `CREATE OR REPLACE VIEW user_details AS SELECT u.*, p.name FROM users u JOIN profiles p` |
| `DROP VIEW` | Menghapus view | `DROP VIEW IF EXISTS active_users` |

#### Stored Procedures
| Sintaks | Deskripsi | Contoh Penggunaan |
|---------|-----------|-------------------|
| `CREATE PROCEDURE` | Membuat stored procedure | `CREATE PROCEDURE get_user(IN user_id INT) BEGIN SELECT * FROM users WHERE id = user_id; END` |
| `CALL` | Memanggil stored procedure | `CALL get_user(1)` |
| `DROP PROCEDURE` | Menghapus stored procedure | `DROP PROCEDURE IF EXISTS get_user` |

#### Functions
| Sintaks | Deskripsi | Contoh Penggunaan |
|---------|-----------|-------------------|
| `CREATE FUNCTION` | Membuat function | `CREATE FUNCTION calculate_age(birth_date DATE) RETURNS INT DETERMINISTIC BEGIN RETURN TIMESTAMPDIFF(YEAR, birth_date, CURDATE()); END` |
| `DROP FUNCTION` | Menghapus function | `DROP FUNCTION IF EXISTS calculate_age` |

#### Triggers
| Sintaks | Deskripsi | Contoh Penggunaan |
|---------|-----------|-------------------|
| `CREATE TRIGGER` | Membuat trigger | `CREATE TRIGGER before_user_insert BEFORE INSERT ON users FOR EACH ROW BEGIN SET NEW.created_at = NOW(); END` |
| `DROP TRIGGER` | Menghapus trigger | `DROP TRIGGER IF EXISTS before_user_insert` |

#### Events
| Sintaks | Deskripsi | Contoh Penggunaan |
|---------|-----------|-------------------|
| `CREATE EVENT` | Membuat event | `CREATE EVENT cleanup_logs ON SCHEDULE EVERY 1 DAY DO DELETE FROM logs WHERE created_at < DATE_SUB(NOW(), INTERVAL 30 DAY)` |
| `DROP EVENT` | Menghapus event | `DROP EVENT IF EXISTS cleanup_logs` |

#### Partitioning
| Tipe | Deskripsi | Contoh Penggunaan |
|------|-----------|-------------------|
| `RANGE` | Partisi berdasarkan range | `PARTITION BY RANGE (YEAR(created_at))` |
| `LIST` | Partisi berdasarkan list | `PARTITION BY LIST (status)` |
| `HASH` | Partisi berdasarkan hash | `PARTITION BY HASH(id)` |
| `KEY` | Partisi berdasarkan key | `PARTITION BY KEY(id)` |

### 🔷 Transaksi (Transaction)

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `START TRANSACTION` | Memulai transaksi | `START TRANSACTION;` |
| `COMMIT` | Menyimpan perubahan transaksi | `COMMIT;` |
| `ROLLBACK` | Membatalkan transaksi | `ROLLBACK;` |
| `SAVEPOINT` | Membuat titik simpan dalam transaksi | `SAVEPOINT savepoint_name;` |
| `ROLLBACK TO SAVEPOINT` | Kembali ke titik simpan tertentu | `ROLLBACK TO SAVEPOINT savepoint_name;` |
| `RELEASE SAVEPOINT` | Menghapus titik simpan | `RELEASE SAVEPOINT savepoint_name;` |

### 🔷 User Management

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `CREATE USER` | Membuat user baru | `CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';` |
| `DROP USER` | Menghapus user | `DROP USER 'username'@'localhost';` |
| `GRANT` | Memberikan hak akses | `GRANT SELECT, INSERT ON database.* TO 'username'@'localhost';` |
| `REVOKE` | Mencabut hak akses | `REVOKE SELECT, INSERT ON database.* FROM 'username'@'localhost';` |
| `ALTER USER` | Mengubah user | `ALTER USER 'username'@'localhost' IDENTIFIED BY 'new_password';` |
| `RENAME USER` | Mengubah nama user | `RENAME USER 'old_username'@'localhost' TO 'new_username'@'localhost';` |
| `SHOW GRANTS` | Menampilkan hak akses | `SHOW GRANTS FOR 'username'@'localhost';` |

### 🔷 Best Practices dan Keamanan

#### Performance Tuning
1. **Indexing Strategy**
   - Gunakan index untuk kolom yang sering digunakan dalam WHERE, JOIN, dan ORDER BY
   - Hindari over-indexing yang dapat memperlambat INSERT/UPDATE
   - Gunakan composite index untuk multiple columns
   - Monitor index usage dengan `EXPLAIN`

2. **Query Optimization**
   - Gunakan `EXPLAIN` untuk menganalisis query
   - Hindari `SELECT *`
   - Gunakan `LIMIT` untuk membatasi hasil
   - Optimalkan JOIN dengan index yang tepat
   - Gunakan subquery dengan bijak

3. **Table Design**
   - Normalisasi database (1NF, 2NF, 3NF)
   - Pilih tipe data yang tepat
   - Gunakan constraint yang sesuai
   - Pertimbangkan denormalisasi untuk performa

#### Security Best Practices
1. **User Management**
   - Gunakan prinsip least privilege
   - Buat user spesifik untuk aplikasi
   - Batasi akses ke database dan tabel
   - Rotasi password secara berkala

2. **Data Protection**
   - Enkripsi data sensitif
   - Gunakan SSL/TLS untuk koneksi
   - Implementasi audit logging
   - Backup data secara regular

3. **Application Security**
   - Gunakan prepared statements
   - Validasi input
   - Sanitasi output
   - Implementasi rate limiting

#### Monitoring dan Maintenance
1. **Performance Monitoring**
   - Monitor query performance
   - Track resource usage
   - Set up alerts
   - Regular maintenance

2. **Backup Strategy**
   - Full backup harian
   - Incremental backup
   - Point-in-time recovery
   - Test restore regularly

3. **High Availability**
   - Replication setup
   - Failover configuration
   - Load balancing
   - Disaster recovery plan

## 📌 Catatan Penting
1. Sintaks di atas adalah sintaks dasar yang sering digunakan dalam MySQL
2. Beberapa sintaks mungkin memiliki opsi atau parameter tambahan
3. Pastikan untuk membaca dokumentasi resmi MySQL untuk informasi lebih lengkap
4. Gunakan sintaks sesuai dengan versi MySQL yang digunakan
5. Selalu backup data sebelum melakukan operasi yang mengubah struktur database
6. Perhatikan performa saat menggunakan fungsi yang kompleks
7. Gunakan indeks untuk mengoptimalkan query
8. Perhatikan keamanan saat menggunakan fungsi enkripsi
9. Gunakan prepared statements untuk mencegah SQL injection
10. Monitor penggunaan sumber daya database
11. Implementasikan logging untuk audit trail
12. Lakukan regular maintenance dan optimization
13. Selalu test di environment development sebelum production
14. Dokumentasikan perubahan database
15. Buat disaster recovery plan 

## ⚡ Performance Tips

### Query Optimization
1. **Index Usage**
   - Gunakan indeks untuk kolom yang sering di-query
   - Hindari indeks berlebih
   - Monitor penggunaan indeks

2. **Query Structure**
   - Batasi jumlah kolom yang di-select
   - Gunakan LIMIT untuk membatasi hasil
   - Hindari SELECT *

3. **Join Optimization**
   - Gunakan INNER JOIN daripada WHERE
   - Definisikan foreign key
   - Index kolom join

### Table Design
1. **Data Types**
   - Pilih tipe data yang tepat
   - Hindari VARCHAR terlalu besar
   - Gunakan ENUM untuk nilai tetap

2. **Normalization**
   - Normalize sampai 3NF
   - Denormalize jika perlu performa
   - Pertimbangkan trade-off

## 🔒 Security Best Practices

1. **User Management**
   - Gunakan strong passwords
   - Batasi hak akses
   - Audit user activities

2. **Data Protection**
   - Enkripsi data sensitif
   - Backup secara regular
   - Implementasi SSL/TLS

3. **Query Security**
   - Gunakan prepared statements
   - Validasi input
   - Escape special characters

## ⚠️ Common Pitfalls

1. **Query Issues**
   - N+1 query problem
   - Missing indexes
   - Inefficient joins

2. **Data Type Problems**
   - Wrong data type selection
   - Character set issues
   - Collation conflicts

3. **Configuration Mistakes**
   - Buffer pool size
   - Connection limits
   - Cache settings

### 🔷 Transaksi (Transaction)

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `START TRANSACTION` | Memulai transaksi | `START TRANSACTION;` |
| `COMMIT` | Menyimpan perubahan transaksi | `COMMIT;` |
| `ROLLBACK` | Membatalkan transaksi | `ROLLBACK;` |
| `SAVEPOINT` | Membuat titik simpan dalam transaksi | `SAVEPOINT savepoint_name;` |
| `ROLLBACK TO SAVEPOINT` | Kembali ke titik simpan tertentu | `ROLLBACK TO SAVEPOINT savepoint_name;` |
| `RELEASE SAVEPOINT` | Menghapus titik simpan | `RELEASE SAVEPOINT savepoint_name;` |

### 🔷 User Management

| Sintaks | Penggunaan | Contoh Penggunaan |
|---------|------------|-------------------|
| `CREATE USER` | Membuat user baru | `CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';` |
| `DROP USER` | Menghapus user | `DROP USER 'username'@'localhost';` |
| `GRANT` | Memberikan hak akses | `GRANT SELECT, INSERT ON database.* TO 'username'@'localhost';` |
| `REVOKE` | Mencabut hak akses | `REVOKE SELECT, INSERT ON database.* FROM 'username'@'localhost';` |
| `ALTER USER` | Mengubah user | `ALTER USER 'username'@'localhost' IDENTIFIED BY 'new_password';` |
| `RENAME USER` | Mengubah nama user | `RENAME USER 'old_username'@'localhost' TO 'new_username'@'localhost';` |
| `SHOW GRANTS` | Menampilkan hak akses | `SHOW GRANTS FOR 'username'@'localhost';` |

// ... existing code ... 

# 🗄️ Panduan Perintah MySQL

<div align="center">

![MySQL Logo](https://www.mysql.com/common/logos/logo-mysql-170x115.png)

> 💡 **Panduan Lengkap MySQL** - Referensi cepat untuk menguasai perintah-perintah MySQL dengan mudah

[![MySQL Version](https://img.shields.io/badge/MySQL-8.0-blue)](https://www.mysql.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Contributors](https://img.shields.io/badge/Contributors-Welcome-orange)](CONTRIBUTING.md)

</div>

<div align="center">

[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![SQL](https://img.shields.io/badge/SQL-000000?style=for-the-badge&logo=sql&logoColor=white)](https://www.mysql.com/)
[![Database](https://img.shields.io/badge/Database-336791?style=for-the-badge&logo=database&logoColor=white)](https://www.mysql.com/)

</div>

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=700&size=35&pause=1500&color=336791&center=true&vCenter=true&random=false&width=700&height=100&lines=MySQL+Commands+Guide;Master+Database+Management;Best+Practices+Included;Complete+Reference+Guide;Professional+Database+Guide" alt="Typing SVG" />
</div>

## 📋 Fitur Utama
<div align="center">

| 🎯 Fitur | 📝 Deskripsi | 💡 Contoh Penggunaan |
|----------|-------------|---------------------|
| ✅ Panduan Lengkap | Dari dasar hingga lanjutan | Query dasar hingga optimasi |
| 📚 Glosarium | Istilah MySQL terlengkap | Referensi cepat istilah |
| 🎯 Contoh Kasus | Praktik terbaik dan contoh nyata | Studi kasus e-commerce |
| 🔧 Tips & Trik | Optimasi dan troubleshooting | Solusi masalah umum |
| 🛠️ Tools | Monitoring dan maintenance | MySQL Workbench, phpMyAdmin |
| 🔒 Keamanan | Best practices keamanan database | Enkripsi, backup, audit |
| 🚀 HA | High availability dan scaling | Replikasi, clustering |

</div>

## 🎯 Target Pembaca
<div align="center">

| 👨‍💻 Role | 🎯 Tujuan | 📚 Materi Fokus |
|----------|-----------|----------------|
| Developer | Meningkatkan skill database | Query, optimasi, best practices |
| DBA | Referensi cepat | Maintenance, HA, security |
| Mahasiswa | Belajar MySQL | Dasar, contoh kasus, praktik |
| Dosen | Materi pengajaran | Kurikulum, latihan, referensi |
| SysAdmin | Manajemen database | Monitoring, backup, security |

</div>

## 📚 Prasyarat
<div align="center">

| 📋 Kebutuhan | ✅ Status | 🎯 Tujuan |
|-------------|-----------|-----------|
| Pengetahuan Dasar Komputer | Wajib | Memahami konsep dasar |
| Pemahaman Database | Wajib | Menguasai konsep DBMS |
| Akses MySQL Server | Wajib | Praktik langsung |
| Text Editor/IDE | Wajib | Pengembangan query |

</div>

## 🚦 Tips Memulai Belajar dari Panduan Ini

1. **Jangan Takut dengan Banyaknya Materi!**  
   Panduan ini memang sangat lengkap, tapi kamu tidak perlu mempelajari semuanya sekaligus. Mulailah dari bagian yang paling sesuai dengan kebutuhan atau levelmu saat ini.

2. **Ikuti Urutan Level**  
   Lihat bagian [Panduan Belajar](#2--panduan-belajar) dan [Level Pembelajaran](#21--level-pembelajaran).  
   - Jika kamu benar-benar pemula, mulai dari **Level Basic**:  
     - [Tipe Data](#3--tipe-data)  
     - [Perintah Dasar](#4--perintah-dasar)  
     - [Operasi Tabel](#5--operasi-tabel)  
     - [Operasi Data (CRUD)](#6--operasi-data-crud)  
   - Setelah paham dasar, lanjutkan ke level berikutnya.

3. **Praktik Langsung**  
   Jangan hanya membaca! Cobalah contoh-contoh query di MySQL Workbench, terminal, atau phpMyAdmin.  
   Lihat juga [Latihan Praktis](#23--latihan-praktis) dan [Contoh Kasus Sederhana](#13--contoh-kasus-sederhana).

4. **Gunakan Daftar Isi & Glosarium**  
   Manfaatkan [Daftar Isi](#-daftar-isi) untuk navigasi cepat.  
   Jika menemukan istilah asing, cek [Glosarium](#23--glosarium-istilah-mysql).

5. **Fokus pada Satu Topik per Hari**  
   Agar tidak kewalahan, pelajari satu topik saja setiap hari. Misal hari ini belajar SELECT, besok INSERT, dst.

6. **Bertanya Jika Bingung**  
   Jika ada bagian yang tidak paham, jangan ragu bertanya di komunitas, forum, atau diskusi GitHub.

7. **Jadikan Panduan Ini Referensi Harian**  
   Tidak perlu hafal semua! Cukup tahu di mana mencari saat butuh.

## 🚀 Quick Start (5 Menit)

1. **Install MySQL**
   ```bash
   # Windows: Download MySQL Installer
   # Linux: sudo apt install mysql-server
   # macOS: brew install mysql
   ```

2. **Start MySQL**
   ```bash
   # Windows: Start MySQL Service
   # Linux: sudo systemctl start mysql
   # macOS: brew services start mysql
   ```

3. **Login ke MySQL**
   ```bash
   mysql -u root -p
   ```

4. **Buat Database Pertama**
   ```sql
   CREATE DATABASE belajar_mysql;
   USE belajar_mysql;
   ```

5. **Buat Tabel Pertama**
   ```sql
   CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       nama VARCHAR(100),
       email VARCHAR(100)
   );
   ```

6. **Coba CRUD Dasar**
   ```sql
   -- Create (Insert)
   INSERT INTO users (nama, email) VALUES ('John Doe', 'john@example.com');
   
   -- Read (Select)
   SELECT * FROM users;
   
   -- Update
   UPDATE users SET nama = 'John Updated' WHERE id = 1;
   
   -- Delete
   DELETE FROM users WHERE id = 1;
   ```

## ⚠️ Common Mistakes & Solusinya

1. **Lupa Password Root**
   ```bash
   # Solusi:
   sudo systemctl stop mysql
   sudo mysqld_safe --skip-grant-tables &
   mysql -u root
   ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';
   ```

2. **Error "Access Denied"**
   - Pastikan username dan password benar
   - Periksa host yang diizinkan
   - Cek hak akses user

3. **Tabel Tidak Muncul**
   - Pastikan sudah `USE database_name`
   - Periksa case sensitivity nama tabel
   - Cek hak akses ke tabel

4. **Data Tidak Tersimpan**
   - Pastikan sudah `COMMIT` jika menggunakan transaksi
   - Periksa constraint tabel
   - Cek tipe data yang sesuai

5. **Query Terlalu Lambat**
   - Gunakan `EXPLAIN` untuk analisis query
   - Tambahkan indeks yang sesuai
   - Batasi jumlah data yang diambil

6. **Karakter Aneh di Data**
   - Set karakter set ke `utf8mb4`
   - Periksa collation database dan tabel
   - Pastikan koneksi menggunakan charset yang benar

## 📊 Roadmap Pembelajaran MySQL

```mermaid
graph TD
    A[Level Basic] --> B[Tipe Data]
    A --> C[Perintah Dasar]
    A --> D[Operasi Tabel]
    A --> E[CRUD]
    
    F[Level Intermediate] --> G[Query Lanjutan]
    F --> H[Fungsi Agregasi]
    F --> I[Indeks]
    F --> J[Backup/Restore]
    
    K[Level Advanced] --> L[Optimasi]
    K --> M[Replikasi]
    K --> N[HA]
    K --> O[Security]
    
    E --> F
    J --> K
```

## 📑 Daftar Isi
- [🗄️ Panduan Perintah MySQL](#️-panduan-perintah-mysql)
  - [📋 Fitur Utama](#-fitur-utama)
  - [🎯 Target Pembaca](#-target-pembaca)
  - [📚 Prasyarat](#-prasyarat)
  - [🚦 Tips Memulai Belajar dari Panduan Ini](#-tips-memulai-belajar-dari-panduan-ini)
  - [🚀 Quick Start (5 Menit)](#-quick-start-5-menit)
  - [⚠️ Common Mistakes \& Solusinya](#️-common-mistakes--solusinya)
  - [📊 Roadmap Pembelajaran MySQL](#-roadmap-pembelajaran-mysql)
  - [📑 Daftar Isi](#-daftar-isi)
  - [1. 🚀 Memulai dengan MySQL](#1--memulai-dengan-mysql)
    - [1.1 📥 Instalasi MySQL](#11--instalasi-mysql)
    - [1.2 🔍 Troubleshooting Umum](#12--troubleshooting-umum)
    - [1.3 🎯 Contoh Kasus Sederhana](#13--contoh-kasus-sederhana)
    - [1.4 📝 Tips untuk Pemula](#14--tips-untuk-pemula)
  - [2. 📚 Panduan Belajar](#2--panduan-belajar)
    - [2.1 🎯 Level Pembelajaran](#21--level-pembelajaran)
    - [2.2 📋 Prasyarat Pembelajaran](#22--prasyarat-pembelajaran)
    - [2.3 🎮 Latihan Praktis](#23--latihan-praktis)
    - [2.4 📝 Tips Belajar](#24--tips-belajar)
  - [3. 📋 Tipe Data](#3--tipe-data)
  - [4. 📌 Perintah Dasar](#4--perintah-dasar)
  - [5. 📊 Operasi Tabel](#5--operasi-tabel)
  - [6. 🔄 Operasi Data (CRUD)](#6--operasi-data-crud)
  - [7. 🔍 Query Lanjutan](#7--query-lanjutan)
  - [8. 📊 Fungsi Agregasi](#8--fungsi-agregasi)
  - [9. 📅 Fungsi Tanggal dan Waktu](#9--fungsi-tanggal-dan-waktu)
  - [10. 📝 Fungsi String](#10--fungsi-string)
  - [11. 🔢 Fungsi Numerik](#11--fungsi-numerik)
  - [12. 📌 Indeks](#12--indeks)
  - [13. 💾 Backup dan Restore](#13--backup-dan-restore)
  - [14. 🔧 Praktik Terbaik MySQL](#14--praktik-terbaik-mysql)
  - [15. 🔄 Replikasi MySQL](#15--replikasi-mysql)
  - [16. 🚀 High Availability](#16--high-availability)
  - [17. 📦 Migrasi Database](#17--migrasi-database)
  - [18. 🛠️ MySQL Workbench](#18-️-mysql-workbench)
  - [19. ⚡ Optimasi Query](#19--optimasi-query)
  - [20. 👥 Manajemen User dan Hak Akses](#20--manajemen-user-dan-hak-akses)
  - [21. 🔒 Keamanan Database](#21--keamanan-database)
  - [22. 💻 Best Practices Pengembangan](#22--best-practices-pengembangan)
  - [23. 📚 Glosarium Istilah MySQL](#23--glosarium-istilah-mysql)
    - [23.1 🔍 Cara Menggunakan Glosarium](#231--cara-menggunakan-glosarium)
    - [23.2 Istilah MySQL (Urutan Alfabetis)](#232-istilah-mysql-urutan-alfabetis)
      - [A](#a)
      - [B](#b)
      - [C](#c)
      - [D](#d)
      - [E](#e)
      - [F](#f)
      - [I](#i)
      - [J](#j)
      - [L](#l)
      - [M](#m)
      - [O](#o)
      - [P](#p)
      - [Q](#q)
      - [R](#r)
      - [S](#s)
      - [T](#t)
      - [U](#u)
      - [V](#v)
  - [24. 🔄 Migrasi dan Upgrade MySQL](#24--migrasi-dan-upgrade-mysql)
    - [24.1 Migrasi dari Versi Lama](#241-migrasi-dari-versi-lama)
    - [24.2 Upgrade MySQL](#242-upgrade-mysql)
  - [25. 📊 Monitoring dan Performance Tuning](#25--monitoring-dan-performance-tuning)
    - [25.1 Monitoring Tools](#251-monitoring-tools)
    - [25.2 Performance Tuning](#252-performance-tuning)
  - [26. 🔍 Troubleshooting Lanjutan](#26--troubleshooting-lanjutan)
    - [26.1 Masalah Umum dan Solusi](#261-masalah-umum-dan-solusi)
    - [26.2 Logging dan Debugging](#262-logging-dan-debugging)
  - [27. 🛠️ Tools dan Utilitas MySQL](#27-️-tools-dan-utilitas-mysql)
    - [27.1 MySQL Workbench](#271-mysql-workbench)
    - [27.2 phpMyAdmin](#272-phpmyadmin)
    - [27.3 MySQL Shell](#273-mysql-shell)
    - [27.4 MySQL Utilities](#274-mysql-utilities)
  - [28. 📚 Referensi dan Sumber Belajar](#28--referensi-dan-sumber-belajar)
    - [28.1 Dokumentasi Resmi](#281-dokumentasi-resmi)
    - [28.2 Komunitas dan Forum](#282-komunitas-dan-forum)
    - [28.3 Tutorial dan Kursus](#283-tutorial-dan-kursus)
    - [28.4 Buku Rekomendasi](#284-buku-rekomendasi)
  - [29. 🔄 Update dan Maintenance](#29--update-dan-maintenance)
    - [29.1 Jadwal Maintenance](#291-jadwal-maintenance)
    - [29.2 Update Security](#292-update-security)
  - [30. 📝 Catatan Penting](#30--catatan-penting)
  - [31. 🤝 Berkontribusi](#31--berkontribusi)
  - [32. 📄 Lisensi](#32--lisensi)
  - [33. 🙏 Terima Kasih](#33--terima-kasih)

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 1. 🚀 Memulai dengan MySQL

### 1.1 📥 Instalasi MySQL

<details>
<summary>🪟 Windows</summary>

```bash
# 1. Download MySQL Installer
# Kunjungi: https://dev.mysql.com/downloads/installer/

# 2. Jalankan installer
# - Pilih "Developer Default" atau "Server only"
# - Ikuti wizard instalasi
# - Catat root password yang dibuat

# 3. Verifikasi instalasi
mysql -u root -p
```

> 💡 **Tips Windows**: 
> - Gunakan MySQL Installer untuk instalasi mudah
> - Pastikan menambahkan MySQL ke PATH sistem
> - Gunakan MySQL Workbench untuk manajemen visual
> - Backup data sebelum upgrade versi
> - Gunakan service manager untuk kontrol service
</details>

<details>
<summary>🐧 Linux (Ubuntu/Debian)</summary>

```bash
# 1. Update package list
sudo apt update

# 2. Install MySQL Server
sudo apt install mysql-server

# 3. Start MySQL service
sudo systemctl start mysql
sudo systemctl enable mysql

# 4. Secure installation
sudo mysql_secure_installation

# 5. Verifikasi instalasi
mysql -u root -p
```

> 💡 **Tips Linux**: 
> - Gunakan systemctl untuk manajemen service
> - Selalu jalankan mysql_secure_installation
> - Backup konfigurasi di /etc/mysql/
</details>

<details>
<summary>🍎 macOS</summary>

```bash
# 1. Install menggunakan Homebrew
brew install mysql

# 2. Start MySQL service
brew services start mysql

# 3. Secure installation
mysql_secure_installation

# 4. Verifikasi instalasi
mysql -u root -p
```

> 💡 **Tips macOS**: 
> - Gunakan Homebrew untuk manajemen package
> - Monitor service dengan brew services
> - Backup data di /usr/local/var/mysql/
</details>

<details>
<summary>🐳 Docker</summary>

```bash
# 1. Pull MySQL image
docker pull mysql:8.0

# 2. Run MySQL container
docker run --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=your_password \
  -e MYSQL_DATABASE=your_database \
  -p 3306:3306 \
  -d mysql:8.0

# 3. Verifikasi instalasi
docker exec -it mysql-db mysql -u root -p
```

> 💡 **Tips Docker**: 
> - Gunakan volume untuk persistensi data
> - Atur environment variables dengan aman
> - Monitor container dengan docker stats
</details>

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

### 1.2 🔍 Troubleshooting Umum

<details>
<summary>Lihat Panduan Troubleshooting</summary>

```bash
# Tidak bisa koneksi ke MySQL
sudo systemctl status mysql
sudo systemctl restart mysql
sudo netstat -tlnp | grep mysql

# Lupa password root
sudo systemctl stop mysql
sudo mysqld_safe --skip-grant-tables &
mysql -u root
ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password';

# Error saat instalasi
sudo apt remove --purge mysql*
sudo apt autoremove
sudo apt update
sudo apt install mysql-server
```
</details>

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

### 1.3 🎯 Contoh Kasus Sederhana

<details>
<summary>📱 Sistem Manajemen Toko Online</summary>

```sql
-- 1. Struktur Database
CREATE DATABASE toko_online;
USE toko_online;

-- 2. Tabel Kategori
CREATE TABLE kategori (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nama VARCHAR(50) NOT NULL,
    deskripsi TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 3. Tabel Produk
CREATE TABLE produk (
    id INT PRIMARY KEY AUTO_INCREMENT,
    kategori_id INT,
    nama VARCHAR(100) NOT NULL,
    deskripsi TEXT,
    harga DECIMAL(10,2) NOT NULL,
    stok INT NOT NULL DEFAULT 0,
    status ENUM('aktif', 'nonaktif') DEFAULT 'aktif',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (kategori_id) REFERENCES kategori(id)
);

-- 4. Tabel Pelanggan
CREATE TABLE pelanggan (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nama VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    telepon VARCHAR(20),
    alamat TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 5. Tabel Pesanan
CREATE TABLE pesanan (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pelanggan_id INT,
    tanggal TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total DECIMAL(10,2) NOT NULL,
    status ENUM('pending', 'dibayar', 'dikirim', 'selesai') DEFAULT 'pending',
    FOREIGN KEY (pelanggan_id) REFERENCES pelanggan(id)
);

-- 6. Tabel Detail Pesanan
CREATE TABLE detail_pesanan (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pesanan_id INT,
    produk_id INT,
    jumlah INT NOT NULL,
    harga DECIMAL(10,2) NOT NULL,
    subtotal DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (pesanan_id) REFERENCES pesanan(id),
    FOREIGN KEY (produk_id) REFERENCES produk(id)
);

-- 7. Insert Data Kategori
INSERT INTO kategori (nama, deskripsi) VALUES 
    ('Elektronik', 'Produk elektronik dan gadget'),
    ('Pakaian', 'Pakaian pria dan wanita'),
    ('Makanan', 'Makanan dan minuman');

-- 8. Insert Data Produk
INSERT INTO produk (kategori_id, nama, deskripsi, harga, stok) VALUES 
    (1, 'Smartphone X', 'Smartphone terbaru', 2000000, 10),
    (1, 'Laptop Pro', 'Laptop untuk profesional', 8000000, 5),
    (2, 'Kemeja Casual', 'Kemeja casual pria', 150000, 20),
    (3, 'Snack Pack', 'Paket snack lengkap', 50000, 30);

-- 9. Query untuk Laporan Penjualan
SELECT 
    p.nama as produk,
    k.nama as kategori,
    COUNT(dp.id) as jumlah_terjual,
    SUM(dp.jumlah) as total_unit,
    SUM(dp.subtotal) as total_penjualan
FROM produk p
JOIN kategori k ON p.kategori_id = k.id
LEFT JOIN detail_pesanan dp ON p.id = dp.produk_id
GROUP BY p.id, p.nama, k.nama
ORDER BY total_penjualan DESC;

-- 10. Query untuk Stok Menipis
SELECT 
    p.nama as produk,
    k.nama as kategori,
    p.stok,
    CASE 
        WHEN p.stok <= 5 THEN 'Kritis'
        WHEN p.stok <= 10 THEN 'Rendah'
        ELSE 'Aman'
    END as status_stok
FROM produk p
JOIN kategori k ON p.kategori_id = k.id
WHERE p.stok <= 10
ORDER BY p.stok ASC;

-- 11. Query untuk Analisis Pelanggan
SELECT 
    pl.nama as pelanggan,
    COUNT(p.id) as jumlah_pesanan,
    SUM(p.total) as total_pembelian,
    AVG(p.total) as rata_rata_pembelian
FROM pelanggan pl
LEFT JOIN pesanan p ON pl.id = p.pelanggan_id
GROUP BY pl.id, pl.nama
HAVING jumlah_pesanan > 0
ORDER BY total_pembelian DESC;
```

> 💡 **Tips Implementasi**: 
> - Gunakan indeks untuk kolom yang sering dicari
> - Implementasikan soft delete untuk data penting
> - Buat backup otomatis secara berkala
> - Monitor performa query secara rutin
> - Implementasikan logging untuk audit trail
</details>

<details>
<summary>🏥 Sistem Manajemen Klinik</summary>

```sql
-- 1. Struktur Database
CREATE DATABASE klinik;
USE klinik;

-- 2. Tabel Dokter
CREATE TABLE dokter (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nama VARCHAR(100) NOT NULL,
    spesialisasi VARCHAR(50) NOT NULL,
    no_izin VARCHAR(20) UNIQUE NOT NULL,
    telepon VARCHAR(20),
    email VARCHAR(100) UNIQUE,
    status ENUM('aktif', 'nonaktif') DEFAULT 'aktif'
);

-- 3. Tabel Pasien
CREATE TABLE pasien (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nama VARCHAR(100) NOT NULL,
    tanggal_lahir DATE NOT NULL,
    jenis_kelamin ENUM('L', 'P') NOT NULL,
    alamat TEXT,
    telepon VARCHAR(20),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 4. Tabel Jadwal
CREATE TABLE jadwal (
    id INT PRIMARY KEY AUTO_INCREMENT,
    dokter_id INT,
    hari ENUM('Senin', 'Selasa', 'Rabu', 'Kamis', 'Jumat', 'Sabtu') NOT NULL,
    jam_mulai TIME NOT NULL,
    jam_selesai TIME NOT NULL,
    kuota INT NOT NULL DEFAULT 10,
    FOREIGN KEY (dokter_id) REFERENCES dokter(id)
);

-- 5. Tabel Janji Temu
CREATE TABLE janji_temu (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pasien_id INT,
    jadwal_id INT,
    tanggal DATE NOT NULL,
    keluhan TEXT,
    status ENUM('menunggu', 'diproses', 'selesai', 'batal') DEFAULT 'menunggu',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (pasien_id) REFERENCES pasien(id),
    FOREIGN KEY (jadwal_id) REFERENCES jadwal(id)
);

-- 6. Tabel Rekam Medis
CREATE TABLE rekam_medis (
    id INT PRIMARY KEY AUTO_INCREMENT,
    janji_temu_id INT,
    diagnosa TEXT NOT NULL,
    resep TEXT,
    catatan TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (janji_temu_id) REFERENCES janji_temu(id)
);

-- 7. Insert Data Dokter
INSERT INTO dokter (nama, spesialisasi, no_izin, telepon) VALUES 
    ('Dr. Budi', 'Umum', 'DOK-001', '08123456789'),
    ('Dr. Ani', 'Gigi', 'DOK-002', '08234567890'),
    ('Dr. Rudi', 'Mata', 'DOK-003', '08345678901');

-- 8. Insert Data Jadwal
INSERT INTO jadwal (dokter_id, hari, jam_mulai, jam_selesai, kuota) VALUES 
    (1, 'Senin', '09:00', '12:00', 10),
    (1, 'Rabu', '13:00', '16:00', 10),
    (2, 'Selasa', '09:00', '12:00', 8),
    (3, 'Kamis', '13:00', '16:00', 8);

-- 9. Query untuk Jadwal Dokter
SELECT 
    d.nama as dokter,
    d.spesialisasi,
    j.hari,
    TIME_FORMAT(j.jam_mulai, '%H:%i') as jam_mulai,
    TIME_FORMAT(j.jam_selesai, '%H:%i') as jam_selesai,
    j.kuota - COUNT(jt.id) as sisa_kuota
FROM dokter d
JOIN jadwal j ON d.id = j.dokter_id
LEFT JOIN janji_temu jt ON j.id = jt.jadwal_id 
    AND jt.tanggal = CURDATE()
GROUP BY d.id, d.nama, d.spesialisasi, j.hari, j.jam_mulai, j.jam_selesai, j.kuota;

-- 10. Query untuk Statistik Kunjungan
SELECT 
    d.nama as dokter,
    d.spesialisasi,
    COUNT(jt.id) as total_kunjungan,
    COUNT(CASE WHEN jt.status = 'selesai' THEN 1 END) as kunjungan_selesai,
    COUNT(CASE WHEN jt.status = 'batal' THEN 1 END) as kunjungan_batal
FROM dokter d
LEFT JOIN jadwal j ON d.id = j.dokter_id
LEFT JOIN janji_temu jt ON j.id = jt.jadwal_id
WHERE jt.tanggal >= DATE_SUB(CURDATE(), INTERVAL 30 DAY)
GROUP BY d.id, d.nama, d.spesialisasi;

-- 11. Query untuk Rekap Rekam Medis
SELECT 
    p.nama as pasien,
    d.nama as dokter,
    d.spesialisasi,
    jt.tanggal,
    rm.diagnosa,
    rm.resep
FROM rekam_medis rm
JOIN janji_temu jt ON rm.janji_temu_id = jt.id
JOIN pasien p ON jt.pasien_id = p.id
JOIN jadwal j ON jt.jadwal_id = j.id
JOIN dokter d ON j.dokter_id = d.id
WHERE jt.tanggal >= DATE_SUB(CURDATE(), INTERVAL 7 DAY)
ORDER BY jt.tanggal DESC;
```

> 💡 **Tips Implementasi**: 
> - Implementasikan validasi data di level aplikasi
> - Gunakan transaksi untuk operasi yang kompleks
> - Buat indeks untuk kolom yang sering dicari
> - Implementasikan sistem antrian untuk janji temu
> - Buat backup otomatis untuk data sensitif
</details>

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

### 1.4 📝 Tips untuk Pemula

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 2. 📚 Panduan Belajar

### 2.1 🎯 Level Pembelajaran

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

### 2.2 📋 Prasyarat Pembelajaran

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

### 2.3 🎮 Latihan Praktis

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

### 2.4 📝 Tips Belajar

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 3. 📋 Tipe Data

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 4. 📌 Perintah Dasar

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 5. 📊 Operasi Tabel

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 6. 🔄 Operasi Data (CRUD)

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 7. 🔍 Query Lanjutan

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 8. 📊 Fungsi Agregasi

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 9. 📅 Fungsi Tanggal dan Waktu

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 10. 📝 Fungsi String

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 11. 🔢 Fungsi Numerik

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 12. 📌 Indeks

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 13. 💾 Backup dan Restore

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 14. 🔧 Praktik Terbaik MySQL

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 15. 🔄 Replikasi MySQL

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 16. 🚀 High Availability

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 17. 📦 Migrasi Database

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 18. 🛠️ MySQL Workbench

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 19. ⚡ Optimasi Query

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 20. 👥 Manajemen User dan Hak Akses

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 21. 🔒 Keamanan Database

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 22. 💻 Best Practices Pengembangan

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

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)

## 23. 📚 Glosarium Istilah MySQL

### 23.1 🔍 Cara Menggunakan Glosarium
1. Gunakan Ctrl+F untuk mencari istilah spesifik
2. Pelajari istilah sesuai dengan level pembelajaran Anda
3. Rujuk kembali ke bagian terkait untuk penjelasan detail
4. Praktikkan penggunaan istilah dalam konteks yang benar
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 23.2 Istilah MySQL (Urutan Alfabetis)

#### A
- **ACID**: Atomicity, Consistency, Isolation, Durability - properti transaksi database
- **ALTER**: Perintah untuk mengubah struktur objek database
- **ANALYZE**: Menganalisis struktur tabel
- **ARCHIVE**: Menyimpan data lama
- **AUDIT**: Pencatatan aktivitas database
- **AUTHENTICATION**: Proses verifikasi identitas
- **AUTHORIZATION**: Proses pemberian hak akses

#### B
- **BACKUP**: Salinan data untuk keamanan
- **BINARY LOG**: Log yang mencatat perubahan data
- **BOOLEAN**: Tipe data untuk nilai true/false
- **BUFFER POOL**: Area memori untuk menyimpan data dan indeks

#### C
- **CACHE**: Penyimpanan sementara untuk data yang sering diakses
- **CHECK**: Memeriksa integritas tabel
- **COLUMN**: Bagian vertikal dari tabel (field)
- **COMMIT**: Menyimpan perubahan transaksi secara permanen
- **CONNECTION**: Koneksi antara aplikasi dan database
- **CONSTRAINT**: Aturan yang membatasi data yang bisa disimpan
- **CREATE**: Membuat objek database baru
- **CRUD**: Create, Read, Update, Delete - operasi dasar database

#### D
- **DATABASE**: Kumpulan data yang terorganisir dan terstruktur
- **DATE**: Tipe data untuk tanggal
- **DBMS**: Database Management System - perangkat lunak untuk mengelola database
- **DEADLOCK**: Kondisi di mana dua transaksi saling menunggu
- **DECIMAL**: Tipe data untuk angka desimal presisi
- **DELETE**: Menghapus data dari tabel
- **DROP**: Menghapus objek database

#### E
- **ENCRYPTION**: Proses mengamankan data
- **ENUM**: Tipe data untuk pilihan nilai tetap
- **EXECUTION PLAN**: Rencana eksekusi query yang dibuat oleh database

#### F
- **FIELD**: Satu kolom dalam tabel
- **FOREIGN KEY**: Kolom yang mereferensi ke primary key tabel lain

#### I
- **INDEX**: Struktur data untuk mempercepat pencarian
- **INNER JOIN**: Mengambil data yang cocok di kedua tabel
- **INSERT**: Menambah data ke tabel
- **INSTANCE**: Satu instalasi database yang berjalan
- **INT**: Tipe data untuk angka bulat

#### J
- **JOIN**: Menggabungkan data dari beberapa tabel
- **JSON**: Tipe data untuk menyimpan data JSON

#### L
- **LATENCY**: Waktu respons database
- **LEFT JOIN**: Mengambil semua data dari tabel kiri dan yang cocok dari tabel kanan
- **LOCK**: Kunci pada data

#### M
- **MAINTENANCE**: Pemeliharaan database
- **MANY-TO-MANY**: Banyak record di tabel A berhubungan dengan banyak record di tabel B
- **MONITORING**: Pemantauan database

#### O
- **ONE-TO-MANY**: Satu record di tabel A berhubungan dengan banyak record di tabel B
- **ONE-TO-ONE**: Satu record di tabel A berhubungan dengan satu record di tabel B
- **OPTIMIZE**: Mengoptimasi struktur tabel
- **OPTIMIZATION**: Proses meningkatkan performa query

#### P
- **PERFORMANCE**: Kinerja database
- **PRIMARY KEY**: Kolom yang mengidentifikasi secara unik setiap baris
- **PRIVILEGE**: Hak akses spesifik

#### Q
- **QUERY**: Perintah atau instruksi yang diberikan ke database

#### R
- **RDBMS**: Relational Database Management System - DBMS yang menggunakan model relasional
- **RECORD**: Satu baris data dalam tabel
- **RELATION**: Hubungan antar tabel
- **RESTORE**: Mengembalikan data dari backup
- **RIGHT JOIN**: Mengambil semua data dari tabel kanan dan yang cocok dari tabel kiri
- **ROLLBACK**: Membatalkan perubahan transaksi
- **ROW**: Bagian horizontal dari tabel (record)

#### S
- **SCHEMA**: Struktur atau blueprint dari database
- **SELECT**: Mengambil data dari tabel
- **SLOW QUERY**: Query yang membutuhkan waktu eksekusi lama
- **SQL**: Structured Query Language - bahasa untuk mengakses database

#### T
- **TABLE**: Struktur untuk menyimpan data dalam baris dan kolom
- **THROUGHPUT**: Jumlah operasi per detik
- **TIMEOUT**: Batas waktu eksekusi
- **TIMESTAMP**: Tipe data untuk tanggal dan waktu
- **TRANSACTION**: Sekumpulan operasi yang harus dieksekusi bersama
- **TRUNCATE**: Menghapus semua data dalam tabel

#### U
- **UPDATE**: Mengubah data dalam tabel
- **USER**: Pengguna database

#### V
- **VACUUM**: Membersihkan ruang yang tidak terpakai
- **VARCHAR**: Tipe data untuk teks dengan panjang variabel
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 24. 🔄 Migrasi dan Upgrade MySQL

### 24.1 Migrasi dari Versi Lama
```sql
-- 1. Backup Database
mysqldump -u root -p --all-databases > backup.sql

-- 2. Export Data
mysqldump -u root -p database_name > data.sql

-- 3. Import ke Versi Baru
mysql -u root -p database_name < data.sql

-- 4. Verifikasi Data
SELECT COUNT(*) FROM table_name;
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 24.2 Upgrade MySQL
```bash
# 1. Backup Data
mysqldump -u root -p --all-databases > backup.sql

# 2. Stop MySQL Service
sudo systemctl stop mysql

# 3. Update MySQL
sudo apt update
sudo apt upgrade mysql-server

# 4. Start MySQL Service
sudo systemctl start mysql

# 5. Verifikasi Versi
mysql -V
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 25. 📊 Monitoring dan Performance Tuning

### 25.1 Monitoring Tools
```sql
-- 1. Status Server
SHOW STATUS;
SHOW VARIABLES;

-- 2. Process List
SHOW PROCESSLIST;

-- 3. InnoDB Status
SHOW ENGINE INNODB STATUS;

-- 4. Table Statistics
SHOW TABLE STATUS;

-- 5. User Statistics
SHOW USER_STATISTICS;
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 25.2 Performance Tuning
```sql
-- 1. Optimasi Query
EXPLAIN SELECT * FROM table_name WHERE condition;

-- 2. Analisis Tabel
ANALYZE TABLE table_name;

-- 3. Optimasi Tabel
OPTIMIZE TABLE table_name;

-- 4. Periksa Indeks
SHOW INDEX FROM table_name;

-- 5. Periksa Status Buffer
SHOW STATUS LIKE 'Innodb_buffer_pool_%';
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 26. 🔍 Troubleshooting Lanjutan

### 26.1 Masalah Umum dan Solusi
```sql
-- 1. Error "Table is Full"
-- Solusi: Periksa disk space dan max_heap_table_size
SHOW VARIABLES LIKE 'max_heap_table_size';
SHOW VARIABLES LIKE 'tmp_table_size';

-- 2. Error "Too Many Connections"
-- Solusi: Periksa max_connections
SHOW VARIABLES LIKE 'max_connections';
SHOW STATUS LIKE 'Threads_connected';

-- 3. Error "Lock Wait Timeout"
-- Solusi: Periksa transaksi yang berjalan lama
SHOW PROCESSLIST;
SHOW ENGINE INNODB STATUS;

-- 4. Error "Disk Full"
-- Solusi: Periksa penggunaan disk
SELECT 
    table_schema as Database,
    table_name as Table,
    round(((data_length + index_length) / 1024 / 1024), 2) as Size_MB
FROM information_schema.TABLES
ORDER BY (data_length + index_length) DESC;
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 26.2 Logging dan Debugging
```sql
-- 1. Error Log
SHOW VARIABLES LIKE 'log_error';

-- 2. Slow Query Log
SHOW VARIABLES LIKE 'slow_query_log';
SHOW VARIABLES LIKE 'long_query_time';

-- 3. General Log
SHOW VARIABLES LIKE 'general_log';

-- 4. Binary Log
SHOW BINARY LOGS;
SHOW MASTER STATUS;
```

## 27. 🛠️ Tools dan Utilitas MySQL

### 27.1 MySQL Workbench
- Database Design & Modeling
- SQL Development
- Database Administration
- Data Migration
- Server Monitoring
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 27.2 phpMyAdmin
- Web-based Management
- User Management
- Database Operations
- Import/Export
- Query Builder
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 27.3 MySQL Shell
```bash
# 1. Install MySQL Shell
sudo apt install mysql-shell

# 2. Connect ke MySQL
mysqlsh -u root -p

# 3. Perintah Dasar
\sql
\js
\py
\help
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 27.4 MySQL Utilities
```bash
# 1. Install MySQL Utilities
sudo apt install mysql-utilities

# 2. Perintah Umum
mysqladmin
mysqlcheck
mysqldump
mysqlimport
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 28. 📚 Referensi dan Sumber Belajar

### 28.1 Dokumentasi Resmi
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)
- [MySQL Workbench Manual](https://dev.mysql.com/doc/workbench/en/)

### 28.2 Komunitas dan Forum
- [MySQL Forums](https://forums.mysql.com/)
- [Stack Overflow MySQL](https://stackoverflow.com/questions/tagged/mysql)
- [MySQL Community](https://www.mysql.com/community/)

### 28.3 Tutorial dan Kursus
- [MySQL Tutorial](https://www.mysqltutorial.org/)
- [W3Schools MySQL](https://www.w3schools.com/mysql/)
- [MySQL Course on Udemy](https://www.udemy.com/topic/mysql/)

### 28.4 Buku Rekomendasi
- "MySQL 8.0 Reference Manual"
- "High Performance MySQL"
- "MySQL Cookbook"
- "Learning MySQL"
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 29. 🔄 Update dan Maintenance

### 29.1 Jadwal Maintenance
```sql
-- 1. Optimasi Tabel Rutin
OPTIMIZE TABLE table_name;

-- 2. Analisis Tabel Rutin
ANALYZE TABLE table_name;

-- 3. Periksa dan Perbaiki Tabel
CHECK TABLE table_name;
REPAIR TABLE table_name;

-- 4. Backup Rutin
-- Gunakan cron job untuk backup otomatis
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
### 29.2 Update Security
```sql
-- 1. Update Password User
ALTER USER 'user'@'localhost' IDENTIFIED BY 'new_password';

-- 2. Review Hak Akses
SHOW GRANTS FOR 'user'@'localhost';

-- 3. Audit User
SELECT * FROM mysql.user;

-- 4. Hapus User Tidak Terpakai
DROP USER 'unused_user'@'localhost';
```
[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
## 30. 📝 Catatan Penting
<div align="center">

| ⚠️ Perhatian | 📌 Catatan |
|-------------|------------|
| Update Berkala | Dokumen akan diperbarui secara rutin |
| Kontribusi | Silakan berkontribusi untuk meningkatkan kualitas |
| Issues | Laporkan kesalahan atau saran perbaikan |
| Panduan | Ikuti panduan kontribusi untuk menambah konten |

</div>

## 31. 🤝 Berkontribusi
<div align="center">

| 📋 Langkah | 🎯 Tujuan |
|-----------|-----------|
| 1. Fork | Salin repository |
| 2. Branch | Buat branch baru |
| 3. Commit | Tambah konten/perbaikan |
| 4. PR | Submit pull request |

</div>

<div align="center">
  <img src="https://github-contributor-stats.vercel.app/api?username=Mistekom" alt="Contributor Stats" />
</div>

## 32. 📄 Lisensi
<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

</div>

## 33. 🙏 Terima Kasih
<div align="center">

Terima kasih telah menggunakan panduan ini. Semoga bermanfaat dalam perjalanan belajar MySQL Anda!

</div>

[⬆️ Kembali ke Daftar Isi](#-daftar-isi)
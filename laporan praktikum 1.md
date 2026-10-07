## Laporan Praktikum Basis Data - Pertemuan 01
**Nama :** Faiz Rizki

**NPM :** 25430038

**Kelas :** B

**Tanggal :** 7 Oktober 2026

## 1.Tujuan Praktikum
- Membangun basis data proyek pribadi (Perpus_MrGoon_38) dengan enkoding utf8mb4 sebagai fondasi proyek praktikum

- Mengonfigurasi hak akses pengguna (Faiz_Rizki_038) khusus untuk basis data proyek dan menguji pembatasan hak aksesnya (access control).

- Menyiapkan dokumentasi identitas proyek pada berkas

- Mengamankan berkas rahasia/kredensial dari kontrol versi menggunakan berkas .gitignore.

- Melakukan manajemen versi kode dan mengunggah hasil pekerjaan ke repositori GitHub.

## 2.Ringkasan Dasar Teori
 Pada Milestone Proyek 1 ini, kita menerapkan Principle of Least Privilege dalam keamanan basis data, yaitu memberikan hak akses (privileges) seperlunya saja kepada pengguna agar tidak bisa mengganggu basis data lain dalam sistem. Untuk itu, perintah Data Control Language (DCL) seperti GRANT digunakan untuk membatasi akun Faiz_Rizki_038 hanya pada lingkup database proyeknya sendiri (Perpus_MrGoon_38).

Selain keamanan basis data, proyek software modern mewajibkan penggunaan Version Control System (Git). Dalam penggunaan Git, berkas .gitignore sangat krusial untuk mencegah berkas sensitif (seperti password atau API key) ikut terunggah ke repositori publik.

## 3.Hasil Langkah Percobaan (tangkapan layar + keterangan)
Langkah 1: Pembuatan Basis Data Proyek (Perpus_MrGoon_38)
![alt text](<Cuplikan layar 2026-10-07 112655.png>)

Keterangan: Saya membuat basis data proyek baru bernama Perpus_MrGoon_38 melalui phpMyAdmin menggunakan character set utf8mb4.

Langkah 2: Pembuatan Pengguna Faiz_Rizki_038 & Pengaturan Hak Akses
![alt text](<Cuplikan layar 2026-10-07 112634.png>)
Keterangan: Saya membuat akun pengembang Faiz_Rizki_038 dan memberikan hak akses penuh hanya pada basis data Perpus_MrGoon_38.

Kueri SQL:
![alt text](<Cuplikan layar 2026-10-07 115312.png>)
![alt text](<Cuplikan layar 2026-10-07 114633.png>)


![alt text](<Cuplikan layar 2026-10-07 120241.png>)

Langkah 4: Pembaruan README.md dan .gitignore
![alt text](<Cuplikan layar 2026-10-07 115627.png>)
Keterangan: Saya mengisi informasi identitas proyek pada README.md dan menambahkan aturan abaikan berkas kredensial pada .gitignore.

Langkah 5: Push ke Repositori GitHub
![alt text](<Cuplikan layar 2026-10-07 125116.png>)
Keterangan: Saya melakukan commit seluruh perubahan dengan pesan p01: milestone proyek 1 dan mengunggahnya (push) ke GitHub.

## 4.Jawaban Titik Analisis
Mengapa akun Faiz_Rizki_038 tidak bisa membuka database kopma_020?

- Penjelasan: Karena saat pemberian izin (GRANT), kita hanya memberikan wewenang pada Perpus_MrGoon_38.*. Akibatnya, sistem MySQL secara otomatis memblokir akses ke database lain untuk menjaga keamanan data.

- Apa fungsi utama dari berkas .gitignore dalam proyek ini?
Penjelasan: Berkas .gitignore berfungsi memberitahu Git agar tidak melacak atau mengunggah berkas-berkas rahasia (seperti file yang berisi kata sandi atau kredensial) ke internet/GitHub agar tidak bocor.

## 5.Hasil Latihan dan Modifikasi
Modifikasi Kueri Idempoten:

Kueri pembuatan user dan database disesuaikan menggunakan klausa IF NOT EXISTS (CREATE DATABASE IF NOT EXISTS perpus_mrgoon_038; dan CREATE USER IF NOT EXISTS 'Faiz_Rizki_038'@'localhost') agar skrip bisa dijalankan ulang tanpa menyebabkan kesalahan bentrok data.

## 6. Tugas Mandiri: Milestone Proyek 1
1. Pembuatan Basis Data Proyek (F.1):
Basis data perpus_mrgoon_038 berhasil dibuat menggunakan standar encoding utf8mb4.

2. Akun Pengembang & Pembatasan Akses (F.2):
Akun Faiz_Rizki_038 berhasil dikonfigurasi. Bukti pengujian menunjukkan akun ini ditolak (ERROR 1044) saat mencoba membuka kopma_020.

3. Identitas Proyek di README.md (F.3):
Berkas README.md telah diperbarui dengan isi:

- Tema: Sistem Informasi Perpustakaan

- Nama Organisasi Fiktif: Perpustakaan MrGoon

- Lingkup Layanan: "Perpustakaan MrGoon menyediakan layanan peminjaman dan pengembalian buku komik, pendaftaran anggota, serta pencarian katalog literatur secara digital/online bagi pengguna yang terdaftar."

## 4.Konfigurasi Proteksi Kredensial (F.4):

Berkas .gitignore telah dibuat dengan isi aturan:
![alt text](<Cuplikan layar 2026-10-07 130727.png>)

## 5. Commit dan Push ke GitHub (F.5):

Perubahan disimpan dan diunggah ke GitHub menggunakan perintah:
![alt text](<Cuplikan layar 2026-10-07 130924.png>)

## 7.Pembahasan dan Kendala
Kendala 1 (Kueri Error No Database Selected): Sempat lupa memilih database sebelum mengeksekusi perintah SQL.
Solusi: Memilih database perpus_mrgoon_038 terlebih dahulu di panel navigasi phpMyAdmin.

Kendala 2 (MySQL Shutdown Unexpectedly): MySQL di XAMPP sempat mati mendadak karena log data terganggu.
Solusi: Memperbaiki folder data MySQL menggunakan folder backup bawaan XAMPP dan membuat ulang konfigurasi akun pengembang.

## 8.Kesimpulan
Tugas Mandiri Milestone Proyek 1 telah berhasil diselesaikan dengan baik. Basis data proyek perpus_mrgoon_038 beserta akun pengembang Faiz_Rizki_038 sudah terkonfigurasi dengan aman. Berkas dokumentasi README.md dan proteksi .gitignore juga telah dikonfigurasi dan tersimpan di repositori GitHub.

## 9.Pernyataan Penggunaan AI
Saya menyatakan bahwa dalam pengerjaan praktikum ini saya memanfaatkan AI (Gemini) sebagai media konsultasi dan sedikit bantuan untuk menyelesaikan masalah teknis MySQL (shutdown unexpectedly), memahami penerapan aturan .gitignore, serta menyusun draf laporan ini. Seluruh eksekusi perintah dan pengujian tetap dilakukan secara mandiri oleh saya.

## 10. Bukti Git (tautan repositori + hash commit)
Tautan Repositori:
https://github.com/FaizRizz/perpus_mrgoon_038.git
Hash Commit: c44ce44
# Pterodactyl Security Enhancer

![Pterodactyl Security](https://img.shields.io/badge/Security-Hardened-green?style=flat-square) ![Version](https://img.shields.io/badge/Version-3.0.0-blue?style=flat-square) ![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

**Pterodactyl Security** adalah skrip instalasi otomatis berbasis Bash yang dirancang untuk memperketat keamanan pada panel Pterodactyl Anda. Skrip ini memodifikasi _core files_ Pterodactyl untuk menerapkan kontrol akses (RBAC) yang lebih ketat, memastikan bahwa tindakan kritis hanya dapat dilakukan oleh **Root Administrator**.

Project ini sangat berguna bagi pemilik hosting game atau administrator sistem yang ingin mencegah akses tidak sah atau modifikasi data oleh sub-user atau admin yang tidak memiliki hak penuh (Root Admin).

## 🌟 Fitur Utama

Skrip ini secara otomatis mengganti dan memodifikasi _controller_ dan _service_ Pterodactyl untuk menambahkan validasi keamanan:

* **Proteksi Penghapusan Server:** Mencegah penghapusan server kecuali dilakukan oleh Root Admin atau Pemilik Server yang sah.
* **Manajemen User Terproteksi:** Hanya Root Admin yang dapat membuat, mengedit, atau menghapus user lain.
* **Keamanan Lokasi & Node:** Membatasi akses manajemen _Location_ dan _Node_ hanya untuk Root Admin.
* **Manajemen Nests:** Pembuatan dan pengeditan Nests ("sarang" game) dikunci khusus Root Admin.
* **Kunci Pengaturan Panel:** Mencegah perubahan pada pengaturan global panel (_Settings_) oleh non-Root Admin.
* **Validasi Akses File:** Memastikan hanya pemilik server atau Root Admin yang dapat mengakses, mengedit, atau mengunduh file server melalui API.
* **Sistem Backup Otomatis:** Membuat backup dari setiap file asli sebelum dimodifikasi untuk keamanan rollback.

## 🛠️ Teknologi yang Digunakan

* **Bash Scripting:** Untuk otomatisasi proses instalasi, backup, dan validasi lingkungan server.
* **PHP 8.1+:** Bahasa pemrograman dasar Pterodactyl yang dimodifikasi.
* **Laravel Framework:** Arsitektur backend yang digunakan oleh Pterodactyl Panel.

## 📋 Prasyarat Instalasi

Sebelum menjalankan skrip ini, pastikan server Anda memenuhi persyaratan berikut:

1.  **Akses Root:** Anda harus memiliki akses SSH sebagai user `root`.
2.  **Pterodactyl Panel:** Panel harus sudah terinstal dan berfungsi (Default path: `/var/www/pterodactyl`).
3.  **PHP 8.1+:** Versi PHP yang kompatibel harus terinstal di sistem.

## 📂 Susunan Project

Berikut adalah struktur file sederhana dari repository ini:

```text
.
├── LICENSE                     # Lisensi MIT
├── README.md                   # Dokumentasi Project
└── pterodactyl_installer.sh    # Skrip Instalasi Utama

```

## 🚀 Cara Penggunaan

Ikuti langkah-langkah berikut untuk menginstal patch keamanan ini di server Anda:

1. **Clone Repository atau Unduh Skrip:**
```bash
git clone [https://github.com/liwirya/pterodactyl-security.git](https://github.com/liwirya/pterodactyl-security.git)
cd pterodactyl-security

```


2. **Berikan Izin Eksekusi:**
```bash
chmod +x pterodactyl_installer.sh

```


3. **Jalankan Installer:**
Pastikan Anda menjalankan skrip sebagai root.
```bash
sudo ./pterodactyl_installer.sh

```


4. **Verifikasi Instalasi:**
Skrip akan menampilkan log proses. Pastikan tidak ada pesan error dan diakhiri dengan pesan `Installation completed successfully!`.
*Log instalasi tersimpan di:* `/var/log/pterodactyl-protection-install.log`

### Cara Rollback (Jika diperlukan)

Skrip ini secara otomatis mem-backup file asli di direktori:
`/var/www/pterodactyl/backups/`

Format nama file backup adalah: `[nama_file_asli].backup_[TIMESTAMP]`

## 👥 Kredit

Project ini dikembangkan dan dikelola oleh:

<table>
<tr>
<td align="center">
<a href="https://www.google.com/search?q=https://github.com/liwirya">
<img src="https://www.google.com/search?q=https://github.com/liwirya.png%3Fsize%3D100" width="100px;" alt="Wira Liwirya"/>
<br />
<sub><b>Wira Liwirya</b></sub>
</a>
</td>
<td align="center">
<a href="https://www.google.com/search?q=https://github.com/mwildanhidayat">
<img src="https://www.google.com/search?q=https://github.com/mwildanhidayat.png%3Fsize%3D100" width="100px;" alt="M Wildan Hidayat"/>
<br />
<sub><b>M Wildan Hidayat</b></sub>
</a>
</td>
</tr>
</table>

## 🤝 Kontribusi

Kontribusi sangat dipersilakan! Jika Anda menemukan bug atau ingin menambahkan fitur keamanan baru:

1. Fork repository ini.
2. Buat branch fitur baru (`git checkout -b fitur-baru`).
3. Commit perubahan Anda (`git commit -m 'Menambahkan fitur keamanan X'`).
4. Push ke branch tersebut (`git push origin fitur-baru`).
5. Buat Pull Request.

## 📄 Lisensi

Project ini didistribusikan di bawah lisensi **MIT**. Lihat file [LICENSE](https://www.google.com/search?q=LICENSE) untuk informasi lebih lanjut.

```
Copyright (c) 2026 WIRA LIWIRYA

```

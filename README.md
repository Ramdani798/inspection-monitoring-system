# 🚀 Web-Based Inspection Officer Monitoring System

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)

> **Disclaimer:** Repositori ini berfungsi sebagai *Case Study* (Studi Kasus) dari proyek rekayasa perangkat lunak yang saya kembangkan selama masa magang di PT. Satya Mitra Ananta. Kode sumber bersifat tertutup (*Closed Source*) untuk mematuhi kebijakan *Non-Disclosure Agreement* (NDA) perusahaan. Seluruh data yang ditampilkan pada dokumentasi ini adalah data fiktif (*dummy data*).

## 📖 Project Overview
Sistem Monitoring Petugas Inspeksi adalah aplikasi berbasis web yang dirancang untuk mendigitalkan alur kerja pelaporan dari petugas lapangan kepada manajemen. Proyek ini memecahkan masalah birokrasi pelaporan manual (kertas) yang rentan hilang dan lambat, dengan mengonversinya menjadi sistem terpusat yang dilengkapi fitur **Real-Time E-mail Notification**, **Automatic PDF Generation**, dan **Geolocation Tracking**.

## 🏗️ System Architecture (Separation of Concerns)
Untuk memastikan performa sistem tetap stabil dan responsif saat diakses oleh banyak petugas lapangan, arsitektur *backend* dibangun menggunakan pola *Separation of Concerns* (Pemisahan Beban Kerja) antara Node.js dan PHP:

* **Node.js (Primary REST API):** Menangani antrean permintaan (*request*) berbasis teks JSON secara *asynchronous*. Bertugas melakukan validasi input dan operasi CRUD ke dalam basis data MySQL dengan latensi sangat rendah.
* **PHP (File & SMTP Processor):** Berfungsi sebagai *microservice* sekunder untuk menangani komputasi berat, yaitu mengonversi *string Base64* menjadi *file* gambar (foto produk & *selfie*), men-*generate* laporan berformat PDF, serta mengeksekusi protokol SMTP untuk pengiriman *e-mail*.

## 🔑 Key Features
1. **Role-Based Access Control (RBAC):** Pemisahan otorisasi yang ketat. Petugas Inspeksi hanya memiliki akses ke formulir *Input Data* (Mobile Responsive), sedangkan *Team Leader* memiliki akses penuh ke *Dashboard Admin* (Desktop) untuk memantau, memfilter, dan mengunduh laporan.
2. **Real-Time Email Alert:** Eksekusi notifikasi otomatis yang memicu *e-mail* ke *supervisor* dalam hitungan detik setelah petugas menekan tombol kirim dari lapangan.
3. **Geolocation Tracking & PDF Generation:** Sistem secara otomatis merekam titik koordinat (GPS) petugas saat *submit* data untuk validasi lokasi, dan merangkum seluruh hasil inspeksi ke dalam dokumen PDF yang tersimpan rapi di *server*.

## 🗄️ Database Schema (ERD)
Basis data dirancang menggunakan MySQL dengan pendekatan relasional untuk menjaga integritas data operasional.
<img width="2010" height="2060" alt="Schema_ERD" src="https://github.com/user-attachments/assets/809053d0-96d0-4020-bb02-3f1b27ee1bdb" />

## 🧪 Backend Testing & Error Handling
Sistem ini telah melewati fase pengujian API menggunakan Postman dan pengujian *Negative Case* untuk memastikan ketahanan aplikasi (*robustness*):

### 1. API Flow Testing (Postman)
* **HTTP POST:** Inisiasi data pelaporan awal.
![post](https://github.com/user-attachments/assets/dd2b4527-5cc2-48ac-9b6e-1213ae991290)

* **HTTP PATCH:** Pembaruan *record* data pelaporan beserta lampiran nama *file*.
![patch](https://github.com/user-attachments/assets/4ea3554f-2969-4b4a-897b-60d2488d77bd)

## 👨‍💻 Author
**Muhamad Ramdani**
* Mahasiswa Ilmu Komputer, Universitas Respati Indonesia
* Portofolio ini disusun untuk mendemonstrasikan pemahaman mengenai *Backend Engineering, API Development, dan Software Architecture*.

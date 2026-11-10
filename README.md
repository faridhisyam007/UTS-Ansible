# Otomasi Deployment Multi-Tier LEMP Stack & WordPress dengan Vagrant & Ansible

Repositori ini berisi kode sumber dan skrip konfigurasi otomatisasi infrastruktur untuk memenuhi Ujian Tengah Semester (UTS) mata kuliah **Administrasi Sistem**. Proyek ini menerapkan arsitektur *multi-tier* menggunakan **Vagrant** untuk manajemen mesin virtual dan **Ansible** sebagai alat manajemen konfigurasinya (*Configuration Management*).

---

## 🏗️ Arsitektur Sistem (Topology)
Sistem ini berjalan di atas 3 node mesin virtual terpisah yang saling terhubung melalui jaringan lokal privat (*Private Network*):
1. **Control Node (`192.168.56.5`):** Mesin pengendali utama tempat Ansible diinstal untuk mengeksekusi *playbook* ke server target.
2. **Web Server (`192.168.56.10`):** Server aplikasi yang menjalankan **Nginx** dan **PHP-FPM**, serta menempatkan direktori instalasi **WordPress**.
3. **Database Server (`192.168.56.11`):** Server basis data yang menjalankan sistem manajemen **MariaDB** untuk menyimpan seluruh data WordPress.

---

## 📁 Struktur Direktori Repositori
```text
UTS-Ansible-LEMP-WordPress/
├── Vagrantfile             # Konfigurasi pembuatan multi-VM (Control, Web, DB)
├── inventory.ini           # Daftar host target dan pengelompokan server Ansible
├── playbook.yml            # Skrip utama otomatisasi instalasi LEMP Stack & WordPress
├── architecture.png        # Diagram skema topologi arsitektur jaringan
└── README.md               # Dokumentasi penjelasan proyek

📈 Progres Pengerjaan Proyek (Step-by-Step Implementation)
Berikut adalah tahapan progres pengerjaan otomatisasi dari awal hingga akhir:

Inisialisasi Lingkungan & Mesin Virtual (Vagrant):

Menyusun konfigurasi Vagrantfile untuk mendefinisikan tiga mesin virtual secara simultan (Control Node, Web Server, dan Database Server) beserta alokasi IP privat dan jaringannya.

Menyalakan seluruh node menggunakan perintah vagrant up dan memastikan status server berjalan dengan baik.

Konfigurasi Koneksi & Otomasi (Ansible):

Melakukan uji koneksi SSH dari Control Node ke server target (Web dan Database).

Menyusun daftar host pada file inventory.ini untuk pengelompokan target manajemen konfigurasi.

Membuat skrip otomatisasi playbook.yml guna menginstal paket-paket kebutuhan sistem secara serentak.

Deployment LEMP Stack & WordPress:

Menjalankan instalasi dan konfigurasi Nginx serta PHP-FPM pada Web Server.

Mengonfigurasi MariaDB pada Database Server untuk menangani penyimpanan data aplikasi.

Mengunduh dan mengonfigurasi direktori sumber WordPress agar terhubung secara mulus dengan basis data.

Pengujian & Publikasi:

Melakukan verifikasi fungsionalitas dengan mengakses halaman instalasi WordPress melalui browser di alamat http://192.168.56.10/.

Melakukan commit dan push seluruh pembaruan kode sumber ke repositori publik GitHub ini.

⚙️ Prasyarat (Prerequisites)
Sebelum menjalankan skrip ini di komputer lokal (host), pastikan perangkat lunak berikut telah terinstal:

Oracle VirtualBox

Vagrant

Git

🚀 Panduan Penggunaan & Eksekusi
Clone Repositori ini:

Bash
git clone [https://github.com/username-anda/UTS-Ansible-LEMP-WordPress.git](https://github.com/username-anda/UTS-Ansible-LEMP-WordPress.git)
cd UTS-Ansible-LEMP-WordPress
Jalankan Mesin Virtual dengan Vagrant:

Bash
vagrant up
Akses Control Node via SSH:

Bash
vagrant ssh control-node
Jalankan Ansible Playbook:

Bash
ansible-playbook -i inventory.ini playbook.yml
Pengujian Aplikasi:
Akses browser pada host ke alamat:

Plaintext
[http://192.168.56.10/](http://192.168.56.10/)
📄 Dokumentasi Konseptual
Penjelasan mendetail mengenai alur pengerjaan dan dokumentasi konseptual dapat diakses melalui artikel Medium proyek.

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

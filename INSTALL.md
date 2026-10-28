NEXUS OSINT adalah toolbox untuk membantu pengguna mengakses berbagai sumber dan alat OSINT melalui satu tempat.

Daftar Isi

Persyaratan

Instalasi Windows

Instalasi Ubuntu dan WSL

Instalasi Termux

Menjalankan Program

Pembaruan

Pemecahan Masalah

Penggunaan yang Bertanggung Jawab

Persyaratan

Pastikan perangkat memiliki:

Python 3 yang kompatibel dengan proyek.

Git untuk mengunduh repository.

Koneksi internet.

Terminal atau command prompt.

1. Instalasi Windows

Dapat dijalankan melalui Command Prompt atau PowerShell.

Pasang Python dan Git

Python: https://www.python.org/downloads/

Git: https://git-scm.com/downloads

Saat memasang Python, aktifkan opsi Add Python to PATH.

Unduh Repository

git clone https://github.com/XyasZor/Nexuss-OSINT.git
cd Nexuss-OSINT

Instal Dependensi

Jika repository menyediakan file requirements.txt, jalankan:

python -m pip install -r requirements.txt

Jalankan Program

Ikuti perintah peluncuran yang tercantum di README atau dokumentasi proyek.

2. Instalasi Ubuntu dan WSL

Pasang Git dan Python

sudo apt update
sudo apt install -y git python3 python3-pip python3-venv

Unduh Repository

git clone https://github.com/XyasZor/Nexuss-OSINT.git
cd Nexuss-OSINT

Buat Lingkungan Python

python3 -m venv .venv
source .venv/bin/activate

Instal Dependensi

Jika tersedia requirements.txt:

python -m pip install -r requirements.txt

Jalankan Program

Gunakan perintah peluncuran yang tercantum dalam dokumentasi proyek.

3. Instalasi Termux

Pasang Paket yang Dibutuhkan

pkg update && pkg upgrade -y
pkg install -y git python

Unduh Repository

git clone https://github.com/XyasZor/Nexuss-OSINT.git
cd Nexuss-OSINT

Instal Dependensi

Jika tersedia requirements.txt:

python -m pip install -r requirements.txt

Jalankan Program

Gunakan perintah peluncuran yang tercantum dalam dokumentasi proyek.

Menjalankan Program

Nama file utama dan argumen program harus mengikuti implementasi yang tersedia di repository.

Untuk membaca dokumentasi di Windows:

type README.md

Untuk membaca dokumentasi di Ubuntu, WSL, atau Termux:

cat README.md

Jangan menjalankan nama file atau argumen yang tidak tersedia di proyek.

Pembaruan

Untuk mengambil perubahan terbaru dari GitHub, masuk ke folder repository lalu jalankan:

git pull

Jika ada perubahan pada dependensi, periksa dokumentasi proyek dan instal kembali dependensi yang diperlukan.

Pemecahan Masalah

Git tidak ditemukan

Pastikan Git sudah terpasang dan dapat dipanggil dari terminal.

Python tidak ditemukan

Periksa instalasi Python dengan:

Windows:

python --version

Ubuntu, WSL, atau Termux:

python3 --version

Di Termux, perintah berikut juga dapat digunakan:

python --version

File requirements.txt tidak ditemukan

Tidak semua proyek Python menyediakan file tersebut. Periksa file yang tersedia di repository dan ikuti dokumentasi proyek.

Instalasi dependensi gagal

Pastikan koneksi internet berfungsi.

Periksa versi Python yang dibutuhkan.

Baca pesan kesalahan untuk mengetahui paket yang bermasalah.

Gunakan lingkungan virtual jika diperlukan.

Program tidak dapat dijalankan

Periksa README, nama file utama, dependensi, dan argumen yang benar-benar didukung oleh proyek.

Penggunaan yang Bertanggung Jawab

Gunakan NEXUS OSINT untuk tujuan yang sah.

Patuhi hukum yang berlaku dan ketentuan layanan situs yang diakses.

Jangan menggunakan hasil pencarian untuk mengancam, melecehkan, menipu, atau menyebarkan informasi pribadi.

Informasi publik dapat tidak akurat, sudah kedaluwarsa, atau merujuk kepada orang yang berbeda.

Lindungi API key, kata sandi, dan informasi sensitif lainnya.

Repository

GitHub: https://github.com/XyasZor/Nexuss-OSINT

Untuk melihat kode sumber, pembaruan, dan dokumentasi terbaru, kunjungi repository resmi tersebut.

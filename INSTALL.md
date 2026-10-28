PANDUAN INSTALASI DAN PENGGUNAAN
=========================================

WINDOWS
-------
1. Pasang Python:
   https://www.python.org/downloads/

2. Aktifkan "Add Python to PATH" saat instalasi.

3. Buka CMD atau PowerShell.

4. Unduh repositori:
    git clone https://github.com/OWNER/REPOSITORY.git
    cd REPOSITORY

   Ganti OWNER/REPOSITORY dengan alamat repositori GitHub milikmu.

5. Jalankan:
    python main.py

   Jika tidak bisa:
    py main.py

Perintah tambahan:
    python main.py --fast
    python main.py --update

--fast   : Melewati animasi pembuka.
--update : Memperbarui data OSINT Framework.


UBUNTU / WSL
------------
1. Pasang Python dan Git:
    sudo apt update
    sudo apt install -y python3 git

2. Unduh repositori:
    git clone https://github.com/OWNER/REPOSITORY.git
    cd REPOSITORY

3. Jalankan:
    python3 main.py

Perintah tambahan:
    python3 main.py --fast
    python3 main.py --update


TERMUX (ANDROID)
----------------
1. Perbarui paket:
    pkg update && pkg upgrade

2. Pasang Python dan Git:
    pkg install -y python git

3. Unduh repositori:
    git clone https://github.com/OWNER/REPOSITORY.git
    cd REPOSITORY

4. Jalankan:
    python main.py

Perintah tambahan:
    python main.py --fast
    python main.py --update


FITUR MENU
----------
1. OSINT Framework
   Menjelajahi direktori OSINT Framework.

2. Cari Tools
   Mencari alat berdasarkan kata kunci.

3. Kode Pos
   Mencari kode pos berdasarkan wilayah.

4. Plat Nomor
   Memeriksa perkiraan wilayah asal plat dan membuka tautan resmi
   pengecekan pajak kendaraan.

5. Cek Nomor HP
   Memperkirakan operator berdasarkan awalan nomor.
   Tidak mengidentifikasi pemilik nomor.

6. Perbarui Data
   Memperbarui data OSINT Framework.

7. Osint Tambahan
   Daftar situs:
   - OSINTscan
   - Max Intel
   - Inquerely
   - OSINT.dev
   - Sherlock Project Online
   - Lullar
   - Webmii
   - Epieos
   - NetSpecter
   - Wayback Machine
   - Recosint
   - KazaSec

8. Cek NIK
   Membaca struktur NIK 16 digit.
   Bukan layanan verifikasi identitas resmi.

9. Cek NISN
   Memeriksa format NISN dan menyediakan akses ke portal resmi.

10. Cek IP
    Mencari informasi IP atau domain, seperti perkiraan lokasi,
    ASN, dan reverse DNS jika tersedia.

11. Cek Resi
    Membuka pilihan layanan pelacakan paket yang didukung.

0. Keluar
   Menutup program.


PENGATURAN OPSIONAL
-------------------
DATA KODE POS

Letakkan file kodepos.csv di folder yang sama dengan main.py
atau di lokasi:
    ~/.nexus_osint/kodepos.csv

Format kolom CSV:
    kodepos,kelurahan,kecamatan,kota,provinsi


API PELACAKAN RESI

Beberapa layanan mungkin memerlukan API key BinderByte.

Ubuntu / WSL / Termux:
    export NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
    python3 main.py

Windows PowerShell:
    $env:NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
    python main.py

Ganti API_KEY_KAMU dengan API key milik sendiri.
Jangan unggah API key, kata sandi, atau file .env ke GitHub.


PEMECAHAN MASALAH
-----------------
Python tidak ditemukan:
- Windows: coba py main.py.
- Ubuntu/WSL: coba python3 main.py.
- Termux: jalankan pkg install python.

Data OSINT Framework gagal diperbarui:
- Periksa koneksi internet, lalu coba opsi --update.

Situs tidak terbuka:
- Situs pihak ketiga mungkin sedang tidak aktif, berganti alamat,
  atau membatasi akses.

Informasi pajak kendaraan:
- Status pajak terkini tidak selalu tersedia hanya dari nomor plat.
  Periksa melalui portal resmi e-Samsat atau Bapenda.


## Cuma Untuk Edukasi, Tanggung Jawab Ditanggung Oleh User

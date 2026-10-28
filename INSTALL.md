NEXUS adalah alat OSINT berbasis terminal. Fitur yang tersedia meliputi penjelajah dan pencarian OSINT Framework, direktori situs OSINT tambahan, pencarian kode pos, pemeriksaan wilayah plat kendaraan beserta tautan resmi cek pajak, pemeriksaan awalan nomor HP, pemeriksaan format NIK/NISN, pencarian informasi IP/domain, serta beberapa pilihan pelacakan resi.

Gunakan alat ini secara bertanggung jawab. Akses hanya informasi yang diizinkan, patuhi hukum dan ketentuan layanan, serta hormati privasi orang lain. Hasil pencarian dapat tidak lengkap atau tidak akurat.

PERSYARATAN

- Python 3.7 atau lebih baru
- Koneksi internet untuk pencarian daring dan membuka situs eksternal
- Git jika ingin mengunduh proyek menggunakan Git

Fitur utama NEXUS menggunakan pustaka bawaan Python sehingga umumnya tidak memerlukan instalasi paket tambahan melalui pip.

1. MENGUNDUH PROYEK

Opsi A — Menggunakan Git

Ganti OWNER/REPOSITORY dengan alamat repositori GitHub yang sebenarnya.

    git clone https://github.com/OWNER/REPOSITORY.git
    cd REPOSITORY

Opsi B — Mengunduh ZIP

1. Buka repositori ini di GitHub.
2. Pilih Code > Download ZIP.
3. Ekstrak file ZIP.
4. Buka terminal di folder hasil ekstrak yang berisi main.py.

2. MEMERIKSA PYTHON

Periksa apakah Python telah terpasang:

    python --version

Di Linux atau Termux, gunakan:

    python3 --version

Jika Python belum tersedia, pasang melalui situs resmi Python atau pengelola paket resmi sistem operasi yang digunakan.

3. MENJALANKAN NEXUS

Jalankan perintah dari folder yang berisi main.py.

Windows:

    python main.py

Jika perintah python tidak dikenali:

    py main.py

Linux / Ubuntu / WSL:

    python3 main.py

Termux (Android):

    pkg update
    pkg install python git
    cd REPOSITORY
    python main.py

Jika proyek diunduh dalam bentuk ZIP, masuk ke folder hasil ekstrak. Sesuaikan nama folder dengan nama yang tersedia di perangkat.

4. OPSI MENJALANKAN PROGRAM

Menjalankan tanpa animasi pembuka:

    python main.py --fast

Memperbarui data OSINT Framework:

    python main.py --update

Pada sistem yang menggunakan perintah python3, ganti python dengan python3.

5. MENU FITUR

1 — OSINT Framework
Menjelajahi direktori OSINT Framework.

2 — Cari Tools
Mencari alat berdasarkan kata kunci.

3 — Kode Pos
Mencari berdasarkan kode pos atau nama wilayah.

4 — Plat Nomor
Memeriksa perkiraan wilayah asal plat dan membuka tautan resmi untuk pengecekan pajak kendaraan.

5 — Cek Nomor HP
Memperkirakan operator berdasarkan awalan nomor. Fitur ini tidak mengidentifikasi pemilik nomor.

6 — Perbarui Data
Memperbarui data OSINT Framework.

7 — Osint Tambahan
Membuka direktori situs OSINT tambahan, termasuk:
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

8 — Cek NIK
Membaca struktur NIK 16 digit. Fitur ini bukan layanan verifikasi identitas resmi.

9 — Cek NISN
Memeriksa format NISN dan menyediakan jalur menuju portal resmi.

10 — Cek IP
Mencari informasi IP/domain, seperti perkiraan lokasi, ASN, dan reverse DNS jika tersedia.

11 — Cek Resi
Menggunakan pilihan pelacakan paket yang didukung.

0 — Keluar
Menutup program.

Membuka situs OSINT tambahan:
1. Pilih nomor 7 dari menu utama.
2. Jika tersedia kategori Osint Tambahan di daftar kategori, pilih kategori tersebut.
3. Pilih situs yang ingin dibuka.

Ketersediaan dan fitur situs pihak ketiga dapat berubah. Beberapa layanan mungkin membatasi akses atau tidak memberikan hasil.

6. PENGATURAN OPSIONAL

Data kode pos

NEXUS dapat mencoba pencarian kode pos melalui layanan daring. Untuk menggunakan data CSV lokal, letakkan file kodepos.csv di folder yang sama dengan main.py atau di lokasi:

    ~/.nexus_osint/kodepos.csv

CSV harus memiliki judul kolom berikut:

    kodepos,kelurahan,kecamatan,kota,provinsi

API kode pos daring dapat diganti melalui variabel lingkungan NEXUS_KODEPOS_API. URL harus memuat {q} sebagai tempat kata kunci pencarian.

API pelacakan resi

Beberapa pilihan pelacakan kurir mungkin memerlukan API key BinderByte. Jika memiliki API key, atur variabel lingkungan NEXUS_BINDERBYTE_KEY.

Linux / WSL / Termux:

    export NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
    python main.py

Windows PowerShell:

    $env:NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
    python main.py

Ganti API_KEY_KAMU dengan API key milik sendiri. Jangan mengunggah API key, kata sandi, atau file .env ke GitHub.

7. PEMECAHAN MASALAH

Python tidak ditemukan

Coba python3 main.py di Linux/WSL/Termux atau py main.py di Windows.

Data OSINT Framework gagal diperbarui

Periksa koneksi internet, lalu jalankan:

    python main.py --update

Jika sumber data sedang tidak tersedia, coba kembali nanti.

Situs tidak terbuka atau menampilkan kesalahan

Situs mungkin sedang tidak aktif, berpindah alamat, diblokir jaringan, atau mengubah aturan akses.

Hasil kode pos atau pelacakan resi tidak muncul

Periksa koneksi internet, data lokal, dan konfigurasi API key jika diperlukan. Verifikasi informasi penting melalui sumber resmi.

Informasi pajak kendaraan

NEXUS tidak selalu dapat mengambil status pembayaran pajak terkini hanya dari nomor plat. Buka portal e-Samsat/Bapenda resmi yang tersedia dan masukkan data tambahan jika diminta. Pastikan status pembayaran serta tanggal jatuh tempo melalui instansi resmi.

8. PRIVASI DAN PENGGUNAAN YANG BERTANGGUNG JAWAB

- Gunakan alat ini hanya untuk tujuan yang sah dan informasi yang boleh diakses.
- Jangan menggunakan hasil pencarian untuk melecehkan, mengancam, menyamar sebagai orang lain, atau menyebarkan informasi pribadi.
- Kecocokan nama pengguna, awalan nomor HP, lokasi IP, atau hasil pencarian bukan bukti bahwa beberapa data berasal dari orang yang sama.
- Hindari memasukkan informasi sensitif ke situs pihak ketiga kecuali layanan tersebut tepercaya dan kebijakan privasinya telah dipahami.

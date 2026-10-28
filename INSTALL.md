# NEXUS --- Panduan Instalasi

NEXUS adalah alat OSINT berbasis terminal. Fitur yang tersedia meliputi
penjelajah dan pencarian OSINT Framework, direktori situs OSINT
tambahan, pencarian kode pos, pengecekan wilayah plat kendaraan beserta
tautan resmi cek pajak, pengecekan awalan nomor HP, pemeriksaan format
NIK/NISN, pencarian informasi IP/domain, serta beberapa pilihan
pelacakan resi.

> **Gunakan secara bertanggung jawab:** Selidiki hanya informasi yang
> memang boleh kamu akses. Patuhi hukum, ketentuan layanan masing-masing
> situs, dan privasi orang lain. Hasil dari alat publik bisa tidak
> lengkap atau tidak akurat.

## Persyaratan

-   Python **3.7 atau lebih baru**
-   Koneksi internet untuk pencarian daring, memperbarui data OSINT
    Framework, dan membuka situs eksternal
-   Git (hanya jika kamu mengunduh proyek dengan cara clone)

Fitur utama NEXUS menggunakan pustaka bawaan Python, jadi biasanya kamu
**tidak perlu memasang paket dengan `pip`**.

## 1. Mengunduh proyek

### Cara A --- Clone menggunakan Git

Ganti `OWNER/REPOSITORY` dengan alamat GitHub repositori yang
sebenarnya:

``` bash
git clone https://github.com/OWNER/REPOSITORY.git
cd REPOSITORY
```

### Cara B --- Unduh ZIP

1.  Buka repositori ini di GitHub.
2.  Klik **Code → Download ZIP**.
3.  Ekstrak file ZIP.
4.  Buka terminal di folder hasil ekstrak, yaitu folder yang berisi
    `main.py`.

## 2. Memeriksa Python

Periksa apakah Python sudah terpasang:

``` bash
python --version
```

Di Linux atau Termux, kamu mungkin perlu memakai:

``` bash
python3 --version
```

Jika perintah tidak ditemukan, pasang Python melalui situs resmi Python
atau pengelola paket resmi sistem operasi yang kamu gunakan.

## 3. Menjalankan NEXUS

Jalankan perintah dari folder yang berisi `main.py`.

### Windows

``` powershell
python main.py
```

Jika perintah `python` tidak dikenali, coba:

``` powershell
py main.py
```

### Linux / Ubuntu / WSL

``` bash
python3 main.py
```

### Termux (Android)

``` bash
pkg update
pkg install python git
cd REPOSITORY
python main.py
```

Jika kamu mengunduh ZIP, masuklah ke folder hasil ekstrak. Kamu tidak
perlu mengetik `cd REPOSITORY` secara persis jika nama foldernya
berbeda.

## 4. Pilihan saat menjalankan program

``` bash
python main.py --fast
python main.py --update
```

Gunakan `python3` sebagai pengganti `python` jika itu perintah Python
yang tersedia di perangkatmu.

-   `--fast` melewati animasi pembuka.
-   `--update` memaksa NEXUS memperbarui data OSINT Framework.

## 5. Menggunakan menu

Setelah program terbuka, masukkan nomor yang tertera di samping fitur
yang ingin digunakan.

-   **1 --- OSINT Framework:** Menjelajahi direktori OSINT Framework.
-   **2 --- Cari Tools:** Mencari alat dalam direktori berdasarkan kata
    kunci.
-   **3 --- Kode Pos:** Mencari berdasarkan kode pos atau nama wilayah.
-   **4 --- Plat Nomor:** Memeriksa perkiraan wilayah asal plat dan
    membuka tautan resmi untuk pengecekan pajak kendaraan.
-   **5 --- Cek Nomor HP:** Memperkirakan operator berdasarkan awalan
    nomor; fitur ini tidak mengidentifikasi pemilik nomor.
-   **6 --- Perbarui Data:** Memperbarui data OSINT Framework.
-   **7 --- Osint Tambahan:** Membuka kategori OSINT tambahan dan
    direktori situs, termasuk OSINTscan, Max Intel, Inquerely,
    OSINT.dev, Sherlock Project Online, Lullar, Webmii, Epieos,
    NetSpecter, Wayback Machine, Recosint, dan KazaSec.
-   **8 --- Cek NIK:** Membaca struktur NIK 16 digit. Fitur ini hanya
    membantu memeriksa format/struktur, bukan memverifikasi identitas
    secara resmi.
-   **9 --- Cek NISN:** Memeriksa format dan menyediakan jalur menuju
    portal resmi.
-   **10 --- Cek IP:** Mencari informasi terkait IP/domain, seperti
    perkiraan lokasi, ASN, dan reverse DNS jika tersedia.
-   **11 --- Cek Resi:** Menggunakan pilihan pelacakan paket yang
    didukung.
-   **0 --- Keluar:** Menutup program.

### Cara membuka situs OSINT tambahan

1.  Pilih `7` dari menu utama (**Osint Tambahan**).
2.  Jika daftar kategori menampilkan pilihan **Osint Tambahan** secara
    terpisah, pilih kategori tersebut.
3.  Pilih situs dari daftar untuk melihat atau membukanya.

Ketersediaan dan fitur situs ditentukan oleh pengelolanya dan dapat
berubah sewaktu-waktu. Beberapa layanan mungkin membatasi akses, meminta
akun, atau tidak memberikan hasil.

## 6. Pengaturan opsional

### Data kode pos

Secara bawaan, NEXUS dapat mencoba mencari kode pos melalui layanan
daring. Jika ingin menggunakan data CSV lokal, letakkan `kodepos.csv` di
folder yang sama dengan `main.py` atau di lokasi berikut:

``` text
~/.nexus_osint/kodepos.csv
```

CSV harus memiliki judul kolom berikut:

``` csv
kodepos,kelurahan,kecamatan,kota,provinsi
```

Kamu dapat mengganti API kode pos daring melalui variabel lingkungan
`NEXUS_KODEPOS_API`. URL yang digunakan harus memuat `{q}` sebagai
tempat kata kunci pencarian.

### API pelacakan resi

Beberapa pilihan pelacakan kurir mungkin memerlukan API key BinderByte.
Jika kamu memiliki API key, atur variabel lingkungan
`NEXUS_BINDERBYTE_KEY`.

**Linux / WSL / Termux (untuk sesi terminal saat ini):**

``` bash
export NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
python main.py
```

**Windows PowerShell (untuk sesi terminal saat ini):**

``` powershell
$env:NEXUS_BINDERBYTE_KEY="API_KEY_KAMU"
python main.py
```

Ganti `API_KEY_KAMU` dengan kunci milikmu sendiri. Jangan mengunggah API
key, kata sandi, atau file `.env` ke GitHub.

## 7. Mengatasi masalah

### `python: command not found`

Coba `python3 main.py` di Linux/WSL/Termux atau `py main.py` di Windows.

### Daftar OSINT Framework gagal diperbarui

Periksa koneksi internet, lalu coba:

``` bash
python main.py --update
```

Jika sumber data sedang tidak tersedia, proses pembaruan bisa gagal
sementara. Coba lagi nanti.

### Situs tidak terbuka atau menampilkan kesalahan

Situs mungkin sedang tidak aktif, pindah alamat, diblokir jaringan, atau
mengubah aturan aksesnya. NEXUS tidak dapat menjamin semua situs pihak
ketiga selalu tersedia.

### Hasil kode pos atau pelacakan resi tidak muncul

Sebagian hasil bergantung pada layanan daring, data lokal, atau API key
opsional. Periksa pengaturan di atas dan cocokkan informasi penting
dengan sumber resmi.

### Informasi pajak kendaraan

NEXUS tidak selalu bisa mengambil status pembayaran pajak terkini hanya
dari nomor plat. Buka portal e-Samsat/Bapenda resmi yang tersedia, lalu
masukkan data tambahan jika diminta. Pastikan status pembayaran dan
tanggal jatuh tempo melalui instansi resmi.

## Privasi dan penggunaan yang bertanggung jawab

-   Gunakan alat ini hanya untuk tujuan yang sah dan informasi yang
    memang boleh kamu akses.
-   Jangan menggunakan hasil pencarian untuk melecehkan, mengancam,
    menyamar sebagai orang lain, atau menyebarkan informasi pribadi.
-   Kecocokan nama pengguna, awalan nomor HP, lokasi IP, atau hasil
    pencarian bukan bukti bahwa beberapa data berasal dari orang yang
    sama.
-   Jangan memasukkan informasi pribadi yang sensitif ke situs pihak
    ketiga kecuali kamu mempercayai layanannya dan memahami kebijakan
    privasinya.

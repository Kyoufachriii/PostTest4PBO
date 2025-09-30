# PostTest4PBO
# Deskripsi Program
Kata 'KataKopi' adalah gabungan dari kata 'katalog' dan "kopi', yang merupakan sebuah program sederhana seperti katalog yang dibuat untuk mengelola data kopi nusantara. Program ini menggunakan array list untuk menyimpan informasi setiap kopi, mulai dari nama kopi, asal daerah, jenis, tingkat keasaman, hingga aroma khasnya. Sejak pertama kali dijalankan, KataKopi sudah memiliki tujuh data kopi nusantara yang terkenal, seperti Gayo dari Aceh, Toraja dari Sulawesi, Kintamani dari Bali, Sidikalang dan Mandailing dari Sumatera Utara, Bajawa dari Flores, serta Wamena dari Papua.

Pengguna bisa berinteraksi dengan KataKopi melalui menu yang disediakan. Ada fitur untuk menambahkan kopi baru dengan cara mengisi data lengkapnya, melihat daftar kopi yang sudah tersimpan, serta mengubah data kopi tertentu apabila ada informasi yang perlu diperbarui. Semua data yang dimasukkan akan ditampilkan kembali dengan format yang rapi sehingga memudahkan pengguna dalam mengenali setiap kopi.

Secara keseluruhan, KataKopi berfungsi sebagai media belajar sekaligus simulasi pengelolaan data kopi nusantara. Program ini tidak hanya membantu memahami penggunaan array list, input, dan output dalam Java, tetapi juga mengenalkan keragaman kopi khas Indonesia melalui pendekatan yang sederhana dan interaktif.

### Tambah Kopi
- Menambahkan data kopi baru (nama, asal, jenis, tingkat keasaman, aroma).
- Input tidak boleh kosong.

### Lihat Daftar Kopi
- Menampilkan seluruh daftar kopi nusantara yang tersimpan.
- Data ditampilkan dalam format rapi agar mudah dibaca

### Ubah Data Kopi
- Memperbarui informasi kopi tertentu berdasarkan nomor yang dipilih oleh pengguna.
- Semua kolom inputan tidak  boleh kosong.

### Keluar
- Pengguna dapat keluar dan menutup program.
- Pengguna juga dapat otomatis keluar dari program apabila salah memasukkan inputan sebanyak 3x.

### Cari kopi
- Pengguna dapat mencari dan menampilkan kopi yang sesuai kriteria (nama, asal, atau aroma) dari daftar kopi.

# !. Abstraction
Abstraksi (Abstraction) adalah prinsip OOP yang berfokus pada penyajian informasi penting kepada pengguna dan menyembunyikan detail implementasi di baliknya. Dalam kasus ini, Abstraksi diterapkan melalui penggunaan Abstract Class dan Abstract Method pada kelas induk Kopi.
<img width="893" height="360" alt="image" src="https://github.com/user-attachments/assets/e2956caa-a99b-451d-a4b6-020426613fcb" />

### A. Abstract Class (Kopi.java)
Letak Penerapan: Kelas Kopi (public abstract class Kopi)
Fungsi: Kelas ini didefinisikan sebagai abstrak. Tujuannya adalah untuk mendefinisikan cetak biru umum dari semua jenis kopi (memiliki nama, asal, keasaman, dll.) tanpa mengizinkan pembuatan objek secara langsung. Ia berperan sebagai fondasi, dan detail spesifiknya diserahkan kepada subkelas non-abstrak seperti KopiArabika, KopiRobusta, dan KopiLiberika.

### B. Abstract Method (getDeskripsi())
Letak Penerapan: Kelas Kopi (public abstract class Kopi)
Fungsi: Kelas ini didefinisikan sebagai abstrak. Tujuannya adalah untuk mendefinisikan cetak biru umum dari semua jenis kopi (memiliki nama, asal, keasaman, dll.) tanpa mengizinkan pembuatan objek secara langsung. Ia berperan sebagai fondasi, dan detail spesifiknya diserahkan kepada subkelas non-abstrak seperti KopiArabika, KopiRobusta, dan KopiLiberika.

# 2. Polimorphysm
Polimorfisme (yang berarti "banyak bentuk") memungkinkan objek diperlakukan sebagai instansi dari tipe kelas induknya, dan juga memungkinkan satu nama metode memiliki implementasi berbeda.

### A. Overriding
Overriding terjadi ketika sebuah subkelas memberikan implementasi spesifik untuk sebuah metode yang sudah dideklarasikan di kelas induknya.
<img width="1068" height="229" alt="image" src="https://github.com/user-attachments/assets/5c5f19e7-8c40-42fd-833e-ba5f050f5185" />

<img width="1167" height="210" alt="image" src="https://github.com/user-attachments/assets/4909c3c2-e133-409c-bfa9-f4044d51eb8b" />

<img width="1129" height="225" alt="image" src="https://github.com/user-attachments/assets/823ae0bf-c376-4e67-980d-5d53e38db8a4" />

Letak Penerapan: Metode getDeskripsi() di subkelas KopiArabika, KopiRobusta, dan KopiLiberika.

Fungsi:
- Setiap subkelas menggunakan anotasi @Override dan mendefinisikan logika pengembalian String yang berbeda untuk metode getDeskripsi(). Contohnya, KopiRobusta menjelaskan rasanya yang pahit dan kafein tinggi.
- Ketika metode kopi.getDeskripsi() dipanggil di KopiService.java, Java akan secara otomatis menentukan versi getDeskripsi() mana yang akan dieksekusi berdasarkan tipe objek aktual saat itu (misalnya, jika objek adalah KopiArabika, maka deskripsi Arabika yang muncul).


### B. Overloading
Overloading diterapkan di kelas KopiService.java dengan mendefinisikan dua atau lebih metode dengan nama yang sama (tampilkanKopi) tetapi jumlah dan/atau tipe parameter yang berbeda.
<img width="561" height="131" alt="image" src="https://github.com/user-attachments/assets/2d4f4008-35c6-4875-a9a5-b1584f99bba2" />

public void tampilkanKopi(): Metode tanpa parameter. Ini adalah shortcut bagi pengguna untuk menampilkan SEMUA data kopi. Secara internal, metode ini memanggil versi overload kedua dengan nilai default (filter null).

<img width="566" height="116" alt="image" src="https://github.com/user-attachments/assets/50e2dcee-0ff4-4f2c-ac70-6bc7b678ec84" />

public void tampilkanKopi(String jenisKopi): Metode dengan satu parameter String. Ini adalah mesin utama yang menangani logika tampilan data. Dengan adanya parameter ini, metode dapat menyaring dan hanya menampilkan jenis kopi yang diinginkan pengguna.


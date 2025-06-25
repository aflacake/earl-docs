# `jikaLainnya`
Adalah bagian dari program yang digunakan untuk menangani percabangan kondisi, mirip dengan struktur _`if-else`_ dalam bahasa pemrograman lainnya. Dengan menggunakan modul ini, kita bisa mengeksekusi kode tertentu terpenuhi jika kondisi tertentu terpenuhi dan kode lain jika kondisi tersebut tidak terpenuhi.

## Fungsi Utama
`jikaLainnya(tokens, modules, context)`
Fungsi ini membaca dan mengeksekusi blok kode yang berada di dalam struktur `jika` dan `jika-lainnya`. Struktur ini mirip dengan konsep percabangan dalam bahasa pemrograman lainnya.

### Parameter:
1. `tokens`: Token yang dihasilkan dari pemecahan perintah. Biasanya, ini adalah kata-kata kunci atau argumen dalam perintah.
2. `modules`: Modul-modul lain yang tersedia untuk digunakan dalam blok kode yang dijalankan. Ini mencangkup fungsi-fungsi lain bisa dipanggil saat menjalankan kode dalam blok `jikaLainnya`.
3. `context`: Informasi tambahan yang dibutuhkan untuk menjalankan kode, seperti:
   - `lines`: Daftar baris kode yang sedang diproses.
   - `index`: Menunjukkan posisi baris kode yang sedang diproses.

## Deskripsi:
Modul ini bekerja dengan memeriksa kondisi di dalam blok kode yang menggunakan perintah `jika`, `jika-lainnya` dan `lain`. Ketika suatu kondisi terpenuhi, kode di dalamnya dieksekusi. Jika tidak, eksekusi dilanjutkan dengan kode dalam blok `lain`.

Modul ini juga mendukung penggunaan perintah `selesai-jika` untuk menghentikan eksekusi blok percabangan.

## Cara Kerja:
### Contoh Struktur:
```txt
jika <kondisi>
  <kode jika kondisi benar>
jika-lainnya
  <kode jika kondisi tidak benar>
lain
  <kode tambahan jika kondisi tidak terpenuhi>
selesai-jika
```
Penjelasan Langkah demi langkah:
1. `jika <kondisi>`:
   - Jika kondisi terpenuhi, maka blok kode setelah `jika` dieksekusi.
   - Jika tidak, program melanjutkan untuk menacri blok `jika-lainnya`.
2. `jika-lainnya`:
   - Jika kondisi di blok `jika` tidak terpenuhi, maka blok kode di dalam `jika-lainnya` akan dijalankan.
3. `lain`
   - Jika kondisi di blok `jika` dan `jika-lainnya` tidak terpenuhi, maka blok kode di dalam `lain` akan dijalankan.
4. `selesai-jika`
   - Menandakan akhir dari struktur `jika-lainnya` dan menghentikan eksekusi percabangan.
  
## Contoh Penggunaan:
Misalnya, kita ingin menampilkan pesan berdasarkan waktu:
```earl
jika waktu > 12
  tampilkan "Selamat Siang!"
jika-lainnya
  tampilkan "Selamat Pagi!"
lain
  tampilkan "Waktu tidak valid."
selesai-jika
```
Penjelasan:
- Jika `waktu` lebih dari 12, maka akan menampilkan "Selamat Siang!".
- Jika tidak, maka menampilkan "Selamat Pagi!".
- Jika waktu tidak valid, maka menampilkan "Waktu tidak valid.".

## Alur Eksekusi:
1. Modul ini memulai proses dengan membaca bars perintah yang dimulai dengan `jika`.
2. Jika kondisi dalam `jika` terpenuhi, maka blok kode setelahnya akan dijalankan.
3. Jika kondisi `jika` tidak terpenuhi, program akan memeriksa perintah `jika-lainnya`.
4. Jika tidak ada kondisi yang terpenuhi, blok `lain` akan dijalankan.
5. Proses berakhir ketika ditemukan perintah `selesai-jika`.

## Kesalahan yang Mungkin Terjadi:
- **Modul tidak dikenali:** Jika perintah dalam blok `jika`, `jika-lainnya`, atau `lain` tidak sesuai atau tidak ditemukan, akan muncul pesan kesalahan seperti:
  ```bash
  Modul tidak dikenali di dalam blok jika-lainnya: <nama-module>
  ```
- **Struktur tidak lengkap:** jika ada kesalahan dalam struktur kode seperti tidak adanya `selesai-jika`, eksekusi bisa berhenti atau gagal.

# Ringkasan
- `jikaLainnya` digunakan untuk membuat percangan dalam kode.
- `jika` dieksekusi jika kondisi terpenuhi.
- `jika-lainnya` dieksekusi jika kondisi `jika` tidak terpenuhi.
- `lain` adalah blok cadangan jika semua kondisi sebelumnya tidak terpenuhi.
- Gunakan `selesai-jika` untuk menandai akhir dari percabangan.

Dengan menggunakan modul `jikaLainnya`, kita bisa membuat logika pemrograman yang lebih fleksibel, mirip dengan percabangan dalam bahasa pemrograman umum.

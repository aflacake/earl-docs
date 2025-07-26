# `waktu`
Modul `waktu` menyediakan berbagai perintah untuk menangani manipulasi waktu dalam bahasa pemrograman Earl. Modul ini memungkinkan pengguna untuk mendapatkan informasi waktu, menghitung mundur, serta melakukan berbagai operasi waktu lainnya.

## Fungsi:
- Deskripsi: Fungsi ini menangani berbagai subperintah yang berhubungan dengan waktu, seperti menampilkan waktu saat ini, menghitung mundur, serta konversi waktu dalam berbagai format.
- Tujuan: Mempermudah pengguna untuk berinteraksi dengan waktu dalam program.

## Subperintah yang Didukung:
1. `waktu bulan`
   Menampilkan nama bulan saat ini (misalnya "Januari", Februari", dst.)
   
   Contoh:
   ```earl
   waktu bulan
   ```
2. `waktu hari`
   Menampilkan hari dalam seminggu saat ini (misalnya "Senin", "Selasa", dst).

   Contoh:
   ```earl
   waktu hari
   ```
3. `waktu hitungmundur <durasi>`
   Menghitung mundur dalam detik atau milidetik. Misalnya, `waktu hitungmundur 10s` untuk menghitung mundur 10 detik.

   Contoh:
   ```earl
   waktu hitungmundur 10s ke :myTimer:
   ```
4. `waktu sekarang [zona]`
   Menampilkan waktu saat ini dalam zona waktu tertentu. Zona waktu yang tersedia: `WIB`, `WITA`, `WIT`, `UTC`, dan `LOCAL`.

   Contoh:
   ```earl
   waktu sekarang WIB
   ```
5. `waktu tunda <durasi>`
   Menunda eksekusi program selama durasi tertentu. Durasi bisa dalam detik (`10s`) atau milidetik (`500ms`).

   Contoh:
   ```earl
   waktu tunda 5s
   ```
6. `waktu format [format]`
   Menampilkan waktu dalam format tertentu. Format yang tersedia: `bawaan`, `tanggal`, `jam`, dan `iso`.

   Contoh:
   ```earl
   waktu format iso
   ```
7. `waktu formatkustom "<format>"`
   Menampilkan waktu sesuai format kustom yang ditentukan. Format waktu menggunakan simbol:
   - `TTTT` untuk tahun
   - `BB` untuk bulan
   - `HH` untuk hari
   - `JJ` untuk jam
   - `mm` untuk menit
   - `dd` untuk detik

   Contoh:
   ```earl
   waktu formatkustom "HH-BB-TTTT JJ:mm:dd"
   ```
8. `waktu stempelwaktu`
   Menyimpan timestamp (waktu dalam milidetik sejak epoch).

   Contoh:
   ```earl
   waktu stempelwaktu
   ```
9. `waktu beda <waktu1> <waktu2>`
    Menghitung selisih waktu antara dua waktu yang diberikan (dalam format ISO 8601).

   Contoh:
   ```earl
   waktu beda 2025-05-17T10:00:00 2025-05-18T10:00:00
   ```
10. `waktu ambil <komponen>`
    Mengambil komponen waktu tertentu, seperti tahun, bulan, hari, jam, menit, atau detik.

   Contoh:
   ```earl
   waktu ambil tahun
   ```

## Penjelasan Detail:
1. Menghitung Mundur (waktu `hitungmundur`):
   Fungsi ini menghitung mundur dari durasi yang diberikan dalam format detik (`s`) atau milidetik (`ms`). Setelah selesai, jika ada subperintah `lalu`, maka perintah tersebut akan dijalankan.

   Contoh:
   ```earl
   waktu hitungmundur 5s lalu tampilkan "Waktu Selesai!"
   ```
2. Zona Waktu (`waktu sekarang`):
   Fungsi ini memungkinkan pengguna untuk mendapatkan waktu saat ini berdasarkan zona waktu yang diinginkan. Misalnya, dengan menggunakan zona waktu "WIB", program akan menampilkan waktu sesuai dengan zona waktu Jakarta (Asia/Jakarta).

   Contoh:
   ```earl
   waktu sekarang WIB
   ```
3. Format Waktu (`waktu format`):
   Fungsi ini memungkinkan pengguna untuk mendapatkan waktu saat ini dalam format yang lebih umum atau khusus. Format `iso` akan memberikan waktu dalam format ISO 8601.

   Contoh:
   ```earl
   waktu format iso
   ```
4. Format Kustom (waktu formatkustom):
   Fungsi ini memungkinkan pengguna untuk menentukan format kustom untuk tampilan waktu, seperti `"HH-BB-TTTT JJ:mm:dd"`, yang berarti: hari-bulan-tahun jam:menit:detik.

   Contoh:
   ```earl
   waktu formatkustom "HH-BB-TTTT JJ:mm:dd"
   ```

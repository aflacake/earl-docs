# `ulangi`
Modul `ulangi` digunakan untuk membuat **perulangan** di dalam kode Earl. Modul ini mendukung dua jenis perulangan:

## Sintaks Perulangan:
1. Perulangan berdasarkan daftar (_array_)
   ```bash
   ulangi setiap dari :nama_daftar:
    ... -- kode yang dijalankan untuk setiap elemen --
    selesai
   ```
   - `:nama_daftar:` adalah variabel array yang ingin diulang.
   - Di setiap iterasi, variabel `item` tersedia dan berisi elemen saat ini dari daftar.
   
   Contoh:
   ```earl
   atur :angka: = [1 2 3]
   ulangi setiap dari :angka:
     tampilkan "Nilai item:" :item:
   selesai
   ```
2. Perulangan berdasarkan jumlah (integer)
   ```bash
   ulangi <jumlah>
    ... -- kode yang dijalankan sejumlah <jumlah> kali --
   selesai
   ```
   - `<jumlah>` adalah banyaknya pengulangan yang ingin dilakukan (angka).
   - Di setiap iterasi, variabel `index` tersedia dan berisi nomor iterasi saat ini (dimulai dari 0).
  
   Contoh:
   ```earl
   ulangi 5
     tampilkan "Perulangan ke-" :index:
   selesai

## Catatan penting:
- Perulangan akan berhenti jika dalam blok ditemukan perintah `berhenti`.
- Perulangan dapat melewati sisa iterasi saat ini jika ditemukan perintah `lanjutkan`.


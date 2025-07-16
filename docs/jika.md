# `jika`
Modul `jika` berfungsi untuk menjalankan **percabangan kondisi** dalam bahasa Earl. Ini memungkinkan program untuk mengevaluasi kondisi dan menjalankan blok kode tertentu hanya jika kondisi tersebut terpenuhi (benar).

## Fungsi Utama
`async function jika(tokens, modules, context)`
- Tujuan: mengecek kondisi logika dan jika terpenuhi, menjalankan blok kode `maka`.
- Parameter:
  - `tokens`, _array_ token yang berisi perintah `jika`, kondisi, dan kata kunci `maka`.
  - `modules`, objek modul lain yang tersedia, termasuk fungsi untuk menjalankan AST (`laksanakanAST`).
  - `context`, konteks eksekusi saat ini, berisi data dan status program.
- Cara kerja:
  1. Memastikan sintaks lengkap:
     Format yang benar adalah:
     `jika <nilai_kiri> <operator> <nilai_kanan> maka`
  2. Mengambil nilai kiri dan kanan, lalu mengevaluasi berdasarkan operator (`==`, `!=`, `>`, `<`, `>=`, `<=`).
  3. Jika hasil evaluasi benar (_true_), maka blok kode dibawah jika (setelah `maka`) dijalankan.
- Blok kode:
  Blok kode yang dijalankan berada dalam `context.currentNode.body` dan dieksekusi secara asinkron menggunakan `laksanakanAST`.

## Contoh Penggunaan dalam Kode Earl
```earl
atur :x: = 5
jika :x: > 3 maka
    tampilkan "Nilai x lebih besar dari 3"
selesai
```
Jika nilai variabel `x` lebih besar dari `3`, maka perintah `tampilkan` akan dijalankan dan mencetak pesan ke layar.

## Catatan
- Kata kunci `maka` wajib ada setelah kondisi.
- Blok kode percabangan harus diakhiri dengan `selesai`.
- Mendukung operator perbandingan standar: `==`, `!=`, `>`, `<`, `>=`, `<=`.
- Fungsi ini merupakan blok perintah (`jika.isBlock = true`), jadi mendukung eksekusi berisi beberapa baris kode.

## Kegunaan
- Membuat program Earl menjadi **dinamis** dengan kemampuan memilih jalur eksekusi berdasarkan kondisi tertentu
- Membangun logika percabangan yang terpenting untuk hampir semua program dan skrip.

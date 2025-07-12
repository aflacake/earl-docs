# `cobaTangkap`
Modul ini menyediakan perintah `cobaTangkap` yang memungkinkan menjalankan blok kode secara aman. Jika terjadi kesalahan di dalam blok tersebut, kesalahan akan ditangkap dan tidak menyebabkan program utama berhenti.

## Cara Kerja:
- Blok kode yang akan dijalankan harus ditulis di dalam tanda kurung `(...)`.
- Kode di dalam blok ini akan dieksekusi satu per satu.
- Jika ada error atau kesalahan saat menjalankan blok tersebut, error akan ditangkap dan dicetak, tapi program utama tetap berjalan.

## Sintaks:
```bash
cobaTangkap (
  -- baris kode yang ingin dijalankan aman --
  perintah1
  perintah2
  ...
)
```

## Contoh Penggunaan:
```earl
cobaTangkap (
  atur :x: = 10
  tampilkan :x:
  -- baris berikutnya akan error, tetapi tidak menghentikan program --
  bagi :x: 0
)
tampilkan "Program tetap berjalan setelah cobaTangkap"
```
### Penjelasan Singkat
- `cobaTangkap` akan menjalankan baris-baris di dalam `(...)`.
- Jika ada error, misalnya pembagian dengan nol, error tersebut hanya dicetak.
- Program utama tidak berhenti dan bisa terus berjalan.

## Catatan:
- Blok harus dimulai dengan `cobaTangkap (` dan diakhiri dengan `)`.
- Blok dapat berisi banyak baris kode.
- Berguna untuk menguji atau menjalankan kode yang mungkin berpotensi error tanpa mematikan program.

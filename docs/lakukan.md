# `lakukan`
Modul `lakukan` digunakan untuk menjalankan **kode dinamis** yang bisa berupa:
- Isi variabel (dari `memory`).
- Satu baris perintah.
- Blok kode yang ditulis dalam tanda kurung `(...)`.

## Format Penggunaan:
```earl
lakukan perintah
```
Atau
```earl
lakukan :nama:
```
Atau
```earl
lakukan (
  tampilkan "halo"
  atur :x: = 5
)
```

## Cara Kerja:
Modul ini memproses perintah `lakukan` berdasarkan **bentuk input-nya**:
- `lakukan :nama:`, menjalankan isi dari variabel `:nama:` jika isinya adalah _string_ atau teks kode.
- `lakukan (...)` (blok), menjalankan baris-baris di dalam kurung
- `lakukan tampilkan "tes"`, menjalankan satu baris perintah langsung.

## Contoh:
1. Menjalankan kode dari variabel
   ```earl
   atur :perintah: = "tampilkan \"halo dari memori\""
   lakukan :perintah:
   ```
2. Menjalankan satu baris
   ```earl
   lakukan tampilkan "baris langsung"
   ```
3. Menjalankan blok kode
   ```earl
   lakukan (
     atur :angka: = 10
     tampilkan :angka:
   )
   ```

## Catatan Teknis
- `lakukan` menyisipkan perintah ke dalam `context.lines`, sehingga akan dieksekusi segera setelah perintah `lakukan` selesai.
- Blok harus diakhiri dengan `)` di baris terpisah.
- Dapat digunakan dalam REPL maupun file `.earl`.

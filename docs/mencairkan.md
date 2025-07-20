# `mencairkan`
Modul ini digunakan untuk **mengonversi (mengubah tipe data)** antara **teks** dan **angka** dalam program berbasis token seperti Earl.

## Fungsi: `cairkanTeks`
Tujuan:
Mengubah teks (_string_) yang berisi angka menjadi angka numerik.
Contoh pemakaian:
```earl
-- Keluaran: 123.45 --
cairkanTeks "123.45"

-- Menyimpan angka 42 ke variabel :c: --
:c: cairkanTeks "42"
```
Perilaku:
- Jika teks diubah ke angka (`"12.5"` → `12.5`), hasil dikembalikan atau disimpan.
- Jika teks tidak valid sebagai angka (`"abc"`), maka akan muncul pean error.

## Fungsi: `cairkanAngka`
Tujuan:
Mengubah angka menjadi string teks.
Contoh pemakaian:
```earl
-- Keluaran: "123" --
cairkanAngka 123

-- Menyimpan "45.6" ke variabel :t: --
:t: cairkanAngka 45.6
```
Perilaku:
- Jika input adalah angka, hasilnya berupa teks angka (`123` → `"123"`).
- Jika input bukan angka, maka akan muncul pesan error.

## Catatan:
- Fungsi-fungsi ini bisa menggunakan variabel sebagai input, misalnya:
   ```earl
   cairkanTeks :nilai:
   cairkanAngka :umur:
   ```
- Hasil bisa langsung ditampilkan atau disimpan ke variabel jika menambahkan `:<nama>:` di depan.

# `untukSetiap`
Modul `untukSetiap` digunakan untuk menjalankan serangkaian perintah pada setiap elemen dalam sebuah koleksi (misalnya array). Ini mirip dengan _loop_ `for` dalam bahasa pemrograman lainnya, tetapi dengan sintaks yang lebih sederhana dan ramah pemula.

## Format Umum:
```earl
untukSetiap <koleksi> setiap <barang>
    <perintah>
selesai
```
- `<koleksi>` adalah nama variabel yang berisi _array_ atau koleksi data.
- `<barang>` adalah nama variabel yang akan diisi dengan nilai setiap elemen dari koleksi.
- `<perintah>` adalah serangkaian perintah yang akan dijalankan untuk setiap elemen dalam koleksi.

## Langkah Kerja:
1. Modul ini akan mengambil koleksi yang diberikan (misalnya _array_).
2. Untuk setiap elemen dalam koleksi, ia akan menjalankan perintah yang ada dalam blok `selesai`.
3. Pada setiap iterasi, elemen saat ini akan disimpan dalam variabel yang disebut `<barang>`.
4. Perintah dalam blok akan dieksekusi dengan `<barang>` yang terisi nilai elemen koleksi.

## Contoh Penggunaan:
### Contoh 1: Menampilkan Setiap Elemen
Misalnya memiliki _array_ angka dan ingin menampilkan setiap angka.
```earl
atur :angkaArray: = [1 2 3]
untukSetiap :angkaArray: setiap :angka:
    tampilkan :angka:
selesai
```
Penjelasan:
- `:angkaArray:` adalah nama koleksi (_array_) yang berisi angka `[1 2 3]`.
- `:angka:` adalah nama variabel yang akan diisi dengan setiap elemen dari `:angkaArray:`.
- `tampilkan :angka:` adalah perintah yang akan dijalankan untuk setiap elemen, yang dalam kasus ini akan menampilkan angka.

### Contoh 2: Menghitung Jumlah Angka
Misalkan ingin menghitung jumlah dari semua angka dalam _array_.
```earl
atur :angkaArray: = [1 2 3 4]
atur :jumlah: = 0
untukSetiap :angkaArray: setiap :angka:
    atur :jumlah: = :jumlah: + :angka:
selesai
tampilkan :jumlah:
```
Penjelasan:
- `:jumlah:` akan menyimpan hasil penjumlahan angka.
- Pada setiap iterasi, `:angka:` akan diambil dari `:angkaArray:` dan ditambahkan ke `:jumlah:`.
- Setelah _loop_ selesai, jumlah total akan ditampilkan.

## Kesalahan yang Sering Terjadi:
1. Format Salah:
   - Pastikan bahwa format `untukSetiap <koleksi> setiap <barang> perintah selesai` diikuti dengan benar. Jika tidak, akan mendapatkan pesan kesalahan terkait sintaks yang salah.
2. Koleksi Bukan Array:
   - Modul `untukSetiap` hanya dapat digunakan dengan koleksi yang bertipe _array_. Jika variabel yang diberikan bukan _array_, akan mendapatkan pesan kesalahan.

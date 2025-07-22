# `mengandung`
Modul `mengandung` digunakan untuk memeriksa apakah suatu _string_ atau _array_ mengandung nilai tertentu.

## Fungsi Utama:
Fungsi `mengandung` memeriksa apakah nilai yang dicari ada di dalam sumber (baik itu _string_ atau _array_).

Sintaks:
```bash
mengandung sumber cari
```
Argumen:
- `sumber`, _string_ atau _array yang diperiksa_.
- `cari`, nilai yang akan dicari dalam **sumber**.

Cara Kerja:
- `mengandung` akan memeriksa apakah nilai `cari` ada di dalam `sumber`.
- Fungsi ini akan mencetak _`true`_ jika nilai ditemukan, dan _`false`_ jika tidak ditemukan.

## Contoh Penggunaan:
1. Menggunakan String:
   ```earl
   atur :kalimat: = "Saya suka belajar Earl."
   mengandung :kalimat: "belajar"
   ```
   Keluaran:
   ```bash
   true
   ```
2. Menggunakan Array:
   ```earl
   atur :buah-buah: = ["apel", "jeruk", "pisang"]
   mengandung :buah-buah: "mangga"
   ```
   Keluaran:
   ```bash
   false
   ```

   Mengatasi spasi yang tidak terlihat:
   ```earl
   atur :daftar: = [" apel", " jeruk ", "pisang "
   mengandung :daftar: " jeruk "
   ```
   Keluaran:
   ```bash
   true
   ```

Penjelasan:
- Pada contoh pertama, mendefinisikan sebuah string `:kalimat:` yang berisi "Saya suka belajar Earl." Kemudian, kita memeriksa apakah kata `"belajar"` ada di dalamnya. Fungsi `mengandung` akan mengembalikan `true`.
- Pada contoh kedua, kita mendefinisikan sebuah array `:buah-buah:` dengan beberapa buah. Kita kemudian memeriksa apakah `"mangga"` ada di dalam _array_ tersebut. Karena tidak ada, hasilnya adalah `false`.

## _Error_ dan Peringatan:
Jika sumber bukan string atau array, Earl akan memberikan pesan error yang menyatakan bahwa tipe tersebut tidak valid untuk operasi `mengandung`.

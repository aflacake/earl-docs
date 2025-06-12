# `atur`
Perintah `atur` digunakan untuk mengatur nilai ke variabel, menghapus variabel, atau mengatur isi objek/daftar.

1. Mengatur Nilai ke Variabel
   Format:
   ```bash
   atur :namaVar: = nilai
   ```

   Contoh:
   ```pearl
   atur :nama: = "Andi"
   atur :usia: = 25
   ```

   Hasil:
   memory = {
     nama: "Andi",
     usia: 25
   }

2. Mengatur Nilai dalam Daftar
   Format:
   ```bash
   atur :namaDaftar[0]: = nilai
   ```

   Contoh:
   ```pearl
   atur :angka[0]: = 10
   ```
   Ini mengisi indeks ke-0 dari daftar `:angka:` dengan `10`.

3. Mengatur Atribut Objek (Instance dari Kelas)
   Format:
   ```bash
   atur namaObjek.namaAtribut = nilai
   ```

   Contoh:
   ```pearl
   atur andi.nama = "Andi"
   atur andi.usia = 30
   ```
   Pastikan `andi` adalah instance dari kelas, dan atributnya memang didefinisikan

4. Menghapus Variabel
   Format:
   ```bash
   atur hapus :namaVar: konfirmasi
   ```

   Contoh:
   ```Pearl
   atur hapus :usia: konfirmasi
   ```
   Tanpa kata `konfirmasi`, variabel tidak akan dihapus.

5. Menyimpan Blok Kode
   Format:
   ```bash
   atur :namaBlok: (
     baris kode 1
     baris kode 2
   )
   ```

   Contoh:
   ```pearl
   atur :halo: (
     tampilkan "Halo Dunia"
     tampilkan "Selamat datang"
   )
   ```
   Semua baris di dalam tanda `(` dan `)` akan disimpan sebagai teks ke dalam variabel `:halo:`.

Catatan tambahan:
- Nilai bisa berupa:
  - Angka, `25`
  - Teks (_string_), `"Andi"`
  - Referensi variabel, `:usia:`
  - Daftar, `[1, 2, 3]` (didukung)

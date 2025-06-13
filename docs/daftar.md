# `daftar`
Fungsinya digunakan untuk mengelola data **daftar (_array_)** , seperti membuat, menambah, mengambil, menghapus, dan menggabungkan elemen.

## Perintah yang Didukung:
1. Buat Daftar:
   ```pearl
   daftar buat :namadaftar:
   ```
   Membuat daftar kosong.
2. Tambah ke Daftar
   ```pearl
   daftar tambah :namadaftar: "nilai"
   ```
   Menambahkan nilai ke akhir daftar.
3. Panjang Daftar
   ```pearl
   daftar panjang :namadaftar:
   ```
   Menampilkan jumlah elemen dalam daftar.
4. Pop (hapus terakhir)
   ```pearl
   daftar hapuspop :namadaftar:
   ```
   Menghapus elemen terakhir dari daftar
5. Gabungkan Dua Daftar\
   Tujuannya menggabungkan dua daftar menjadi satu.
   ```pearl
   daftar gabung :daftarA: :daftarB: :hasil:
   ```
   Gabungkan `daftarA` dan `daftarB` ke daftar baru bernama `hasil`.
6. Sisipkan di Posisi Tertentu\
   Tujuannya menyisipkan nilai di posisi tertentu.
   ```pearl
   daftar sisip :namadaftar: index "nilai:
   ```
   Menyisipkan nilai ke posisi tertentu dalam daftar.
7. Hapus Elemen Tertentu
   ```pearl
   daftar hapus :namadaftar: index
   ```
   Menghapus elemen di posisi tertentu.
8. Ambil Daftar\
   Tujuannya mengambil elemen dari daftar (bisa daftar bersarang).
   ```pearl
   daftar ambil :belanja: 0
   ```
   Menampilkan elemen pertama dari daftar `:belanja:`
   ```pearl
   daftar ambil :data: 1 2
   ```
   Untuk bersarang: `:data:[1][2]`
   

Catatan Tambahan:
- Semua nama variabel daftar harus menggunakan tanda `:dua titik:`.
- String harus diapit tandakutip `"..."`.
- Nilai juga bisa berupa variabel lain, contoh:
  ```pearl
  daftar tambah :data: :isi:
  ```
  Semua nilai juga bisa berasal dari variabel. Ini akan menambahkan nilai dari variabel `:isi:` ke daftar `:data:`.

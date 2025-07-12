# `daftar`
Modul ini menyediakan perintah untuk mengelola variabel bertipe daftar (_array_) dalam memori. Dengan modul ini, pengguna bisa membuat, memanipulasi, dan mengambil elemen dari daftar.

## Sintaks dan Perintah:
1. Buat daftar baru
   ```earl
   daftar buat :nama_daftar:
   ```
   Membuat daftar kosong dengan nama varaibel `nama_daftar`.
2. Cek panjang daftar
   ```earl
   daftar panjang :nama_daftar:
   ```
   Menampilkan jumlah elemen dalam daftar.
3. Tambah elemen ke daftar
   ```earl
   daftar tambah :nama_daftar: nilai
   ```
   Menambahkan nilai ke akhir daftar.
4. Hapus elemen terakhir (pop)
   ```earl
   daftar hapuspop :nama_daftar:
   ```
   Menghapus elemen terakhir dari daftar.
5. Gabung dua daftar
   ```earl
   daftar gabung :daftarA: :daftarB: :daftarHasil:
   ```
   Menggabungkan dua `daftarA` dan `daftarB` menjadi daftar baru `daftarHasil`.
6. Ambil elemen dari daftar bersarang
   ```earl
   daftar ambil :nama_daftar: indeks1 [indeks2 ...]
   ```
   Mengambil elemen dari daftar, bisa untuk daftar bersarang dengan indeks bertingkat.
7. Sisipkan elemen pada indeks tertentu
   ```earl
   daftar sisip :nama_daftar: indeks nilai
   ```
   Menyisipkan `nilai` pada posisi `indeks` dalam daftar.
8. Hapus elemen pada indeks tertentu
   ```earl
   daftar hapus :nama_daftar: indeks
   ```
   Mengahpus elemen pada posisi `indeks` dalam daftar.

## Contoh:
```earl
daftar buat :buah:
daftar tambah :buah: "apel"
daftar tambah :buah: "jeruk"

-- Keluaran: 2 --
daftar panjang :buah:

-- Keluaran: jeruk --
daftar ambil :buah: 1

daftar hapuspop :buah:

-- Keluaran: 1 --
daftar panjang :buah:
```

## Catatan:
- Semua nama daftar harus dibungkus dengan tanda `:` misalnya `:buah:`.
- Nilai bisa berupa _string_ atau teks (dengan tanda kutip `"`), angka, atau variabel lain.
- Indeks dimulai dari 0.
- Pastikan daftar sudah dibuat sebelum digunakan.

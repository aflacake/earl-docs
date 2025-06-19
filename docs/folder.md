Perintah-perintah dibawah ini digunakan untuk mengelola folder (direktori) di sistem file.

1. `buatFolder`
   Fungsi: Membuat folder baru.
   Contoh:
   ```earl
   buatFolder data
   ```
   Hasil: Membuat folder baru bernama `data` (jika belum ada)'.
2. `hapusFolder`
   Fungsi: Menghapus folder beserta isinya.
   Contoh:
   ```earl
   hapusFolder data
   ```
   Hasil: Folder `data` dan semua isinya akan dihapus.
3. `bacaFolder`
   Fungsi: Menampilkan isi dari sebuah folder.
   Contoh:
   ```earl
   bacaFolder data
   ```
   Hasil: Menampilkan semua file dan subfolder dalam `data`.
4. `gantiNamaFolder`
   Fungsi: Mengganti nama folder.
   Contoh:
   ```earl
   gantiNamaFolder data data_lama
   ```
   Hasil: Folder data akan diganti namanya menjadi data_lama.

Catatan Penting
- Semua perintah ini bekerja langsung pada sistem file
- Jalur folder bisa relatif atau absolut
- Gunakan hati-hati, terutama `hapusFolder` karena **akan menghapus semua isi folder!**

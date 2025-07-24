# `tulis`

1. Menulis isi variabel ke file (menimpa isi lama)
   ```earl
   atur :pesan: = "Halo Dunia"
   tulis :pesan: > "keluaran.txt"
   ```
2. Menambahkan isi variabel ke file (tidak menimpa)
   ```earl
   atur :log: = "Pengguna masuk"
   tulis :log: >> "riwayat.txt"
   ```
3. Menulis ke file default (keluaran.txt)
   ```earl
   atur :judul: = "Catatan penting"
   tulis :judul:
   ```
4. Jika variabel tidak ditemukan, akan muncul pesan kesalahan
   ```earl
   tulis :tidak_ada:
   ```
Penjelasan:
- `tulis :nama_variabel:`
  Menulis isi variabel ke keluaran.txt.
- `tulis :nama_variabel: > "nama_file.txt"`
  Menimpa isi file tersebut dengan isi variabel.
- `tulis :nama_variabel: >> "nama_file.txt"`
  Menambahkan isi variabel ke akhir file.

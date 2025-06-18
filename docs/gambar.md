# `gambar`
Memungkinkan kamu menggambar bentuk dasar ke kanvas menggunakan perintah dalam bahasa Pearl.

## Perintah yang tersedia
1. `gambar buat-kanvas <lebar> <tinggi>`
   Membuat kanvas baru dengan ukuran yang disesuaikan.
   ```pearl
   gambar buat-kanvas 400 300
   ```
2. `gambar warna "<nama_warna/hex>"`
   Mengatur warna isian dan garis.
   ```pearl
   gambar warna "red
   ```
3. `gambar mode <isi|garis|isi-garis>
   Mengatur mode menggambar:
   - `isi`: Hanya isi.
   - `garis`: Hanya garis tepi.
   - `isi-garis`: Keduanya.
   ```pearl
   gambar mode garis
   ```
4. `gambar kotak <x> <y> <w> <h>`
   Atau gunakan daftar:
   ```pearl
   gambar kotak :data:
   ```
   Menggambar persegi panjang.
5. `gambar lingkaran <x> <y> <radius>`
   Atau:
   ```pearl
   gambar lingkaran :lingkaran1:
   ```
   Menggambar lingkaran.
6. `gambar garis <x1> <y1> <x2> <y2>`
   Menggambar garis lurus dari titik A ke titik B.
7. `gambar poligon <x1> <y1> <x2> <y2> ...>`
   Pola harus minimal 3 titik (6 angka). Bisa juga dari daftar.
8. `gambar teks "<isi>" <x> <y>`
   Menampilkan posisi tertentu.
9. `gambar huruf "<gaya_font>"`
    Mengatur font teks (misal: `"30px Verdana"`).
10. `gambar rata <left|center|right>`
    Mengatur perataan teks horizontal.
11. `gambar dasar <top|middle|bottom|alphabetic>`
    Mengatur dasar garis teks vertikal
12. `gambar simpan "<nama_file.png>"`
    Menyimpan kanvas ke file PNG.
13. `gambar hapus-canvas`
    Membersihkan isi kanvas, ini menghapus seluruh isi yang ada di kanvas.

Tips Tambahan
- Kamu bisa simpan daftar koordinat di memori dan pakai dalam perintah gambar:
  ```pearl
  daftar titik : 50 60 200 120 100 200
  gambar poligon :titik:
  ```
  

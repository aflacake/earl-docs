# `gambar`
Modul ini menangani perintah menggambar menggunakan **Canvas**. Modul ini digunakan untuk membuat, menggambar bentuk, teks, dan menyimpan gambar ke file PNG.
  
## Persyaratan:
- Modul `canvas` (harus diinstal).
- File ini tergantung pada `memory.js` dan `utiliti.js`.

## Konsep Dasar:
Sebelum bisa menggambar, **kanvas** harus dibuat terlebih dahulu.
```earl
gambar buat-kanvas 800 600
```

## Contoh Lengkap:
```earl
gambar buat-kanvas 400 300
gambar warna "green"
gambar mode isi-garis
gambar kotak 50 50 100 100
gambar lingkaran 200 150 40
gambar teks "Selesai" 150 280
gambar simpan "gambar1.png"
```

## Daftar Perintah:
1. `buat-kanvas <lebar> <tinggi>`
   Membuat kanvas kosong dengan ukuran tertentu.
   Contoh: `gambar buat-kanvas 400 300`.

2. `warna "<nama_warna>"`
   Mengatur warna isi dan garis.
   Contoh: `gambar warna "red"`.

3. `mode <isi|garis|isi-garis>`
   Menentukan mode penggambaran:
   - `isi`, isi penuh.
   - `garis`, hanya garis luar.
   - `isi-garis`, keduanya.
   Contoh: `gambar mode garis`.

4. Bentuk
   - `kotak <x> <y> <w> <h>`
     Menggambar persegi panjang.
     Contoh: `gambar kotak 10 10 100 50`.
   - `lingkaran <x> <y> <radius>`
     Menggambar lingkaran.
     Contoh: `gambar lingkaran 200 150 40`.
   - `poligon <x1> <y1> <x2> <y2> ...`
     Menggambar poligon tertutup dari minimal 3 titik.
     Contoh: `gambar poligon 10 10 100 10 100 50 10 50`.
   - `garis <x1> <y1> <x2> <y2>`
     Menggambar garis dari titik A ke B.
     Contoh: `gambar garis 0 0 100 100`.

5. Teks
   - `teks "<isi_teks>" <x> <y>`
     Menulis teks ke kanvas.
     Contoh: `gambar teks "Halo Dunia" 50 50`.
   - `huruf "<gaya_font>"`
     Mengubah gaya huruf.
     Contoh: `gambar huruf "bold 30px Courier"`.
   - `rata <left|right|center|start|end>`
     Atur perataan horizontal teks.
     Contoh: `gambar rata center`.
   - `dasar <top|middle|alphabetic|bottom>`
     Atur posisi vertikal teks.
     Contoh: `gambar dasar bottom`.

6. Warna Spesifik
   - `warna-isi "<warna>"`
     Atur hanya warna isi.
     Contoh: `gambar warna-isi "blue"`.
   - `warna-garis "<warna>"`
     Atur hanya warna garis.
     Contoh: `gambar warna-garis "black"`.

7. Utilitas
   - `hapus-canvas`
     Menghapus isi kanvas (mengisi ulang dengan warna putih).
     Contoh: `gambar hapus-canvas`.
   - `simpan "<nama_file.png>"`
     Menyimpan gambar sebagai file PNG.
     Contoh: `gambar simpan "hasil.png"`.
   - `status`
     Menampilkan status kanvas saat ini.
     Contoh: `gambar status`.

## Catatan:
- Gunakan tanda kutip (`"..."`) untuk teks atau warna jika mengandung spasi.
- Semua nilai angka harus valid.
- Beberapa perintah bisa menerima daftar dari memori.

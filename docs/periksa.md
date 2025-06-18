# `periksa`
Modul ini digunakan untuk melihat isi variabel dan memeriksa keadaan program saat sedang berjalan.

# Cara Pakai
Gunakan perintah:
```pearl
periksa [opsi]
```
Opsi yang tersedia:
- Tanpa argumen atau _memory_, Menampilkan semua isi memory saat ini.
- `konteks`,  Menampilkan posisi eksekusi: baris ke berapa dan apa isinya.
- `gambar`, Menampilkan info tentang kanvas (jika sudah dibuat).
- `semua`, Menampilkan _memory_ dan _context_ sekaligus.
- `:nama[n]:`, Menampilkan elemen ke-`n` dari daftar bernama `:nama:`.
- `nama_daftar`, Menampilkan seluruh isi daftar bernama `nama_daftar`.
- `nama_kelas`, Menampilkan info atribut dan instance dari kelas `nama_kelas`.

Contoh Penggunaan:
```pearl
-- Menampilkan semua isi memory --
periksa

-- Menampilkan status eksekusi saat ini --
periksa konteks

-- Menampilkan info kanvas (jika ada) --
periksa gambar

-- Menampilan elemen ke-2 dari daftar :angka: --
periksa :angka[2]:

-- Menampilkan isi daftar bernama warna --
periksa warna

-- Menampilkan atribut & instance dari kelas 'Kotak' --
periksa Kotak
```

Catatan:
- Format `:nama[n]:` harus diapit dengan titik dua, misal `:angka[0]:`.
- Untuk daftar, indeks dimulai dari 0.
- Tidak semua variabel punya `__tipe`. Jika bukan `kelas`, perintah akan mengabaikannya.

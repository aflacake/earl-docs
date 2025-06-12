# `memory`
Adalah tempat penyimpanan semua data sementara selama program berjalan ini semacam **"otak"** atau variabel global. Memori adalah objek JavaScript yang menyimpan: variabel biasa (contoh: `nama = "Budi"`), daftar (_array_), dikta, instance kelas, blok kode, fungsi buatan pengguna, hasil perintah seperti `masukkan`, `atur`, `ambil`, dll.

## Contoh Isi `memory`
Setelah menjalankan ini:
```pearl
atur :nama: = "Budi"
daftar buat :angka:
daftar tambah :angka: 10
daftar tambah :angka: 20
```

Isi `memory` akan jadi seperti ini:
```bash
{
  nama: "Budi",
  angka: [10, 20]
}
```

## Bagaimana `memory` Dipakai?
Semua modul (`atur`, `masukkan`, `daftar`, `dikta`, `fungsi`, dst) menggunakan dan memodifikasi memory. Contohnya:
- `atur :x: = 5`, menyimpan `x=5` ke memory.
- `daftar tambah :angka: 42` menambahkan `42` ke `memory['angka']`.
- `ambil :x: dari :y:`, ambil isi dari `y` dan disimpan ke `x` di `memory`.

# `periksa`
Modul periksa digunakan untuk **menampilkan informasi internal** dari program, seperti:
- Memori
- Konteks eksekusi
- Status kanvas gambar
- Elemen daftar
- Objek kelas
Sangat berguna saat **_debugging_ atau pelacakan nilai** dalam kode Earl.

## Format Umum:
```earl
periksa <opsi>
```

## Contoh Penggunaannya:
```earl
atur :angka: = 10
atur :teks: = "hello"
tampilkan :angka: :teks:

periksa memori
periksa konteks
```

## Opsi yang Didukung:
- tanpa argumen atau `memory`, menampilkan seluruh isi `memory` dalam program.
- `konteks`, menampilkan informasi konteks eksekusi saat ini (baris, posisi, dll).
- `gambar`, menampilkan status kanvas jika ada (`lebar`, `tinggi`, `warna`).
- `semua`, menampilkan **memori dan konteks** sekaligus.
- `:nama[indeks]:`, menampilkan elemen daftar di memori berdasarkan indeks tertentu.
- `nama_daftar`, jika variabel tersebut adalah daftar, tampilkan isinya.
- `nama_kelas`, jika variabel adalah objek kelas, tampilkan atribut dan _instancenya_.

## Tips:
- Sangat cocok digunakan saat membuat program panjang atau melacak bug.
- Kombinasikan dengan perintah `tampilkan` untuk melihat hasil yang lebih rapi atau diformat.

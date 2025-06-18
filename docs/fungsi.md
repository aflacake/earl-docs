# `fungsi`
`fungsi` digunakan untuk membuat **fungsi sendiri** di Pearl. Fungsi ini bisa dipanggil berkali-kali dengan parameter yang berbeda, seperti bahasa pemrograman pada umumnya.

## Format Penulisam
```pearl
fungsi namaFungsi(param1, param2)
(
   -- isi kode fungsi ---
)
```
- Gunakan `(` dan `)` dibaris terpisah sebagai pembuka dan penutup blok fungsi
- Gunakan kembalikan nilai untuk mengembalikan hasil dari fungsi

## Contoh Fungsi Menyapa
```pearl
fungsi halo(nama)
(
  tampilkan "Halo, " nama
)
```
Pemanggilan:
```bash
Halo "Dunia"
```
Keluaran:
```pearl
Halo, Dunia
```

Aturan penting
- Nama fungsi hanya boleh terdiri dari huruf, angka, dan `_`, dan tidak boleh diawali dengan angka.
- Parameter dipisahkan dengan koma: (x, y, z).
- Harus menggunakan tanda kurung `(` dan `)` untuk membungkus isi fungsi.
- Fungsi disimpan sebagai modul sementara dan bisa langsung dipanggil setelah didefiniskan.

Tips
- Simpan fungsi umum seperti `tambah`, `kalikan`, `format` dalam file `.pearl` dan impor jika dibutuhkan.
- Gunakan `kembalikan` untuk menghentikan fungsi lebih awal dan memberi hasil.

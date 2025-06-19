# `atur`
Perintah `atur` digunakan untuk **menyimpan, mengubah, dan menghapus data** di memori Pearl. Ini bisa berupa:
- Variabel biasa.
- Elemen array.
- Blok kode.
- Atribut instance objek.

## Format Umum
```pearl
atur :nama: = nilai
atur :nama:[] = [isi_array]
atur namaObjek.atribut = nilai
atur :nama:[indeks]: = nilai
```

## Fitur-fitur
1. Mengatur Nilai ke Variabel
   Format:
   ```bash
   atur :namaVar: = nilai
   ```

   Contoh:
   ```pearl
   atur :nama: = "Andi"
   atur :usia: = 25
   ```
   Menyimpan nilai ke dalam variabel bernama `:nama` dan `:usia:`.

   Hasil:
   ```bash
   memory = {
     nama: "Andi",
     usia: 25
   }
   ```

2. Menyimpan Array
   ```pearl
   atur :daftar: = [1, 2, 3]
   ```
   Menyimpan array ke dalam variabel `daftar`.

3. Menyimpan Blok Kode
   ```pearl
   atur :blok: (
       tampilkan "Ini blok kode"
   )
   ```
   Menyimpan beberapa baris sebagai satu string di variabel `blok`.

4. Menghapus Variabel
   Format:
   ```bash
   atur hapus :namaVar: konfirmasi
   ```

   Contoh:
   ```Pearl
   atur hapus :usia: konfirmasi
   ```
   Tanpa kata `konfirmasi`, variabel tidak akan dihapus. Wajib menambahkan `konfirmasi` untuk alasan keamanan.

5. Mengatur Nilai Array Berdasarkan Indeks
   ```pearl
   atur :daftar[1]: = 99
   ```
   Mengganti isi indeks ke-1 dari array `daftar` menjadi `99`.

6. Mengatur Atribut dari Instance Objek
   ```pearl
   atur orang.nama = "Siti"
   ```
   Mengubah atribut `nama` dari instance `orang`.
   Syarat:
   - `orang` harus instance dari kelas yang sudah dibuat sebelumnya.
   - Atribut `nama` harus didefiniskan di kelas tersebut.


Catatan tambahan:
- Gunakan `:` di awal dan akhir nama variabel untuk mengaksesnya, contoh: `:x:`.
- Untuk menyimpan data kompleks seperti array dan objek, gunakan tanda `[` `]` dan `(` `)`.
- Saat menyimpan objek:
  ```pearl
  atur :data: = (nama: "Ani", usia: 20)
- Nilai bisa berupa:
  - Angka, `25`
  - Teks (_string_), `"Andi"`
  - Referensi variabel, `:usia:`
  - Daftar, `[1, 2, 3]` (didukung)

## Contoh Lengkap
```pearl
atur :angka: = 7
atur :teks: = "Halo"
atur :data: = (id: 1, nama: "Udin")
atur :list: = [1, 2, 3, 4, 5]

atur :list[2]: = 99
atur :blok: (
    tampilkan :angka:
    tampilkan :teks:
)
atur hapus :angka: konfirmasi
```

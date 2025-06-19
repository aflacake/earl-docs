# `ambil`
Fungsi `ambil` bertugas untuk **mengisi nilai ke variabel dari sumber lain** yang sudah tersedia dalam memori, seperti:
- Variabel biasa.
- _Array_.
- Objek.
- Atribut dari instance objek.
- Nilai dalam _dictionary_ (disebut "dikta").

## Format Umum
```earl
ambil :tujuan: dari sumber
```

## Format
1. Ambil dari Variabel Biasa
   ```earl
   ambil :x: dari :a:
   ```
   Mengambil nilai dari `:a:` dan menyimpannya ke variabel `:x:`.

2. Ambil Seluruh _Array_
   ```earl
   ambil :data: dari :daftar:
   ```
   Jika `:daftar:` adalah array, maka seluruh isi array diambil.

3. Ambil Atribut dari Instance Objek
   ```earl
   ambil :nama: dari user.nama
   ```
   Mengambil atribut `:nama:` dari instance `user`.

4. Ambil Nilai dari Dikta (_dictionary_)
   ```earl
   ambil :nilai: dari :info: usia
   ```
   Jika `:info:` adalah objek `{ usia: 30 }`, maka `:nilai:` akan berisi `30`.

## Validasi & Pesan Kesalahan
Modul ini juga:
- Memeriksa apakah sumber data ada di lingkup atau memori global.
- Menampilkan pesan kesalahan jika:
  - Format salah.
  - Variabel tidak ditemukan.
  - Atribut tidak valid.
  - Akses ke dikta gagal.
 
## Contoh lengkap
```earl
atur :angka: = 100
atur :info: = (nama: "Rani", usia: 20)

ambil :x: dari :angka:
ambil :umur: dari :info: usia

atur user (
    nama: "Fajar"
)

ambil :namaUser: dari user.nama
```

## Fungsi Internal
- `cariDariLingkup(nama)`, Mencari variabel dari dalam lingkup saat ini atau dari `memory`.
- `ambilDaftarJikaPerlu(sumber)`, Mengecek apakah `sumber` adalah nama _array_ valid dalam format `:nama:`.

Dokumentasi ini diharapkan dapat memberikan gambaran yang jelas tentang bagaimana modul `ambil.js` bekerja dan bagaimana cara menggunakannya di dalam skrip Earl.

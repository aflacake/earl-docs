# `buka`
Fungsinya membaca isi file teks dan menyimpannya ke dalam variabel.

## Cara Pakai
```earl
buka :variabel: dari "path/ke/file.txt"
```
Penjelasan:
- `:variabel:`, Nama variabel tempat isi file akan disimpan.
- `"path/ke/file.txt`, Nama atau path file yang ingin dibaca.

## Contoh Penggunaan
```earl
buka :isiFile: dari "catatan.txt"
tampilkan :isiFile:
```
> Ini akan membuka file `catatan.txt` dan menyimpan seluruh isinya ke variabe `:isiFile:`.

Penjelasan:
- Membuka file `catatan.txt`, path atau nama file yang ingin dibaca.
- Tanda kutip **wajib** digunakan untuk nama file, terutama jika mengandung spasi.
- Menyimpan isinya ke variabel `:isiFile:`, nama variabel tempat isi file disimpan.
- Menampilkan isi file ke layar.

## Keluaran:
Jika berhasil:
```bash
File 'catatan.txt' dibuka dan disimpan ke variabel ':isiFile:'
```
Jika gagal:
```bash
Gagal membuka file 'catatan.txt': [penjelasan error]
```

## Digunakan bersama:
```earl
buka :teks: dari "dokumen.txt"
tampilkan "Isi file adalah:" :teks:
```

## Catatan:
- File harus berformat bukan biner.
- Jika file tidak ditemukan, akan muncul pesan error. Jadi file harus **ada** dan dapat diakses dari direktori kerja program.
- Modul ini hanya membaca file teks (`utf-8`).
- Variabel yang menampung isi file dapat ditampilkan menggunakan perintah `tampilkan`.
- Pastikan nama file ditulis diantara tanda kutip `" "`.

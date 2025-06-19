# `buka`
Fungsinya membaca isi file teks dan menyimpannya ke dalam variabel.

## Cara Pakai
```earl
buka :variabel: dari "nama_file.earl"
```
Penjelasan:
- `:variabel:`, Nama variabel tempat isi file akan disimpan.
- `"nama_file.earl`, Nama atau path file yang ingin dibaca.

## Contoh Penggunaan
```earl
buka :isi: dari "catatan.earl"
tampilkan :isi:
```
Penjelasan:
- Membuka file `catatan.earl`.
- Menyimpan isinya ke variabel `:isi:`.
- Menampilkan isi file ke layar.

Catatan:
- File harus berformat bukan biner.
- Jika file tidak ditemukan, akan muncul pesan error.
- Pastikan nama file ditulis diantara tanda kutip `" "`.

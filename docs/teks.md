# `teks`
Modul `teks` digunakan untuk mengelola variabel bertipe teks (_string_) dalam konteks memori program. Kamu bisa memanipulasi isi teks, seperti mengubah, mengambil bagian, mengganti _substring_, dan lain-lain.

## Cara Memakai:
Format umum perintah:
```bash
teks <aksi> :nama_variabel: [argumen...]
```
- `:nama_variabel:` adalah nama variabel teks yang sudah tersimpan di memori.
- `<aksi>` adalah perintah apa yang ingin dilakukan padateks.
- `[argumen...]` adalah tambahan parameter sesuai aksi.

## Contoh Penggunaan:
```earl
atur :judul: = "Halo Dunia"
teks panjang :judul:
teks gabung :judul: "!!!"
teks besarkan :judul:
teks ganti :judul: "DUNIA" "SEMUA"
```
Penjelasan singkat:
- `atur :judul: = "Halo Dunia"`, menyimpan teks awal di variabel `judul`.
- `teks panjang :judul:`, menampilkan jumlah karakter dalam teks.
- `teks gabung :judul: "!!!"`, menambahkan `"!!!"` ke akhir teks.
- `teks besarkan :judul:`, mengubah semua huruf menjadi kapital.
- `teks ganti :judul: "DUNIA" "SEMUA"`, mengganti semua kata `"DUNIA"` menjadi `"SEMUA"`.


## Daftar Aksi dan Penjelasannya:
| Aksi | Deskripsi | Contoh Penggunaan |
| --- | --- | --- |
| `panjang` | Menampilkan panjang teks di variabel. | `teks panjang :judul:` |
| `gabung` | Menambahkan teks baru ke akhir isi variabel. | `teks gabung :judul: " tambahan"` |
| `besarkan` | Mengubah seluruh isi teks menjadi huruf besar. | `teks besarkan :judul:` |
| `kecilkan` | Mengubah seluruh isi teks menjadi huruf kecil. | `teks kecilkan :judul:` |
| `ganti` | Mengganti semua kemunculan _substring_ dengan string baru. | `teks ganti :judul: "lama" "baru"` |
| `ambil` | Mengambil sebagian teks mulai indeks tertentu dengan panjang tertentu. | `teks ambil :judul: 0 5` |
| `hapus` | Menghapus bagian teks mulai indeks tertentu dengan panjang tertentu. | `teks hapus :judul: 3 4` |
| `pangkas` | Menghapus spasi kosong di awal dan akhir teks. | `teks pangkas :judul:` |
| `isi` | Mengganti isi variabel dengan teks baru. | `teks isi :judul: "teks baru"` |
| `pecah` | Memecah teks menjadi daftar berdasarkan pemisah tertentu (bawaan spasi jika kosong). | `teks pecah :judul: ","` |
| `cocok` | Memeriksa apakah _substring_ ada dalam teks (menghasilkan `true` atau `false`). | `teks cocok :judul: "kata"` |

## Catatan:
- Nama variabel harus dalam format `:nama:`.
- Variabel harus sudah berisi teks untuk sebagian besar aksi kecuali `isi` dan `pecah`.
- Argumen berupa _string_ bisa berupa token literal (`"teks"`) atau variabel yang bisa diselesaikan oleh `resolveToken`.
- Kesalahan format akan menghasilkan pesan _error_ di konsol.

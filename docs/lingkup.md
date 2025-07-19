# `lingkup`
Modul ini mengatur konsep lingkup (_scope_) variabel dalam program Earl. Lingkup adalah tempat penyimpanan variabel yang bisa bersarang dan diatur secara hierarkis.

## Fungsi-fungsi:
1. `masuklingkup(tokens, modules, context)`
   - Fungsi, membuka lingkup baru (menambahkan _scope_ baru ke dalam tumpukan lingkup).
   - Penggunaan, ketika kamu ingin mulai blok kode baru yang memiliki variabel sendiri tanpa memengaruhi lingkup sebelumnya.
   - Cara kerja, menambahkan objek kosong baru ke `context.lingkup` sebagai lingkup baru.
2. `keluarlingkup(tokens, modules, context)`
   - Fungsi, menutup lingkup saat ini dan menggabungkan variabel dari lingkup itu ke lingkup _global_.
   -  Penggunaan, ketika kamu selesai dengan blok kode dan ingin variabel yang dibuat di dalamnya dipindahkan ke lingkup _global_.
   -  Cara kerja:
     - Jika lingkup saat ini bukan _global_, lingkup tersebut dihapus dari tumpukan lingkup.
     - Semua variabel dalam lingkup yang ditutup dipindahkan (di-merge) ke lingkup _global_ (indeks 0).
     - Jika sudah di lingkup _global_, keluar lingkup tidak dilakukan dan muncul peringatan.
3. `periksalingkup(tokens, modules, context)`
   - Fungsi, menampilkan isi semua lingkup saat ini di konsol.
   - Penggunaan, untuk memeriksa variabel apa saja yang ada di setiap lingkup.
   - Keluaran, daftar lingkup beserta isi variabel masing-masing.
  
## Penjelasan Konsep:
- `context.lingkup` adalah array yang menyimpan objek-objek lingkup bertingkat.
- Lingkup _global_ ada di `context.lingkup[0]`.
- Lingkup yang lebih dalam berada di indeks yang lebih tinggi.
- Variabel di lingkup dalam akan dicari mulai dari yang paling dalam (akhir array) ke yang paling luar (awal array).
- Fungsi ini membantu mengelola variabel supaya tidak bercampur antara blok kode yang berbeda.

## Contoh Penggunaan:
```earl
masuklingkup
atur :x: = 10
-- keluaran: 10 --
tampilkan :x:
keluarlingkup
-- menampilkan isi lingkup global dengan variabel x --
periksalingkup
```

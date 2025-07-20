# `memanjat`
Modul `memanjat` digunakan untuk menjalankan satu blok kode baris demi baris secara berurutan, seperti memanjat tangga langkah demi langkah.

## Fungsi Utama:
```earl
async function memanjat(tokens, modules, context)
```
Cara kerja:
- Menerima beberapa baris kode dalam `context.lines`.
- Menjalankan setiap baris secara berurutan.
- Menyimpan hasil eksekusi setiap baris ke `context.log`.
- Jika ada baris yang gagal dijalankan (_error_), eksekusi langsung dihentikan.
- Mendukung pemanggilan `memanjat` secara bersarang (_nested_), sehingga bisa memproses blok dalam blok.

Parameter:
- `tokens`
  _Array_ token dari baris kode saat ini (tidak langsung dipakai di fungsi ini, tapi wajib ada).
- `modules`
  Objek berisi semua modul atau fungsi yang tersedia untuk eksekusi kode.
- `context`
  Objek konteks yang berisi informasi eksekusi saat ini, termasuk:
  - `context.lines`: _array_ baris kode yang akan dijalankan.
  - `context.log`: _array_ yang akan diisi hasil tiap baris setelah dijalankan.
  - Properti lain seperti `memory`, `lingkup`, dll.
 
## Contoh Penggunaan:
Misalnya dalam kode Earl:
```earl
memanjat
  atur :x: = 10
  tampilkan :x:
selesai
```
Modul `memanjat` akan menjalankan baris `atur :x: = 10` dulu, simpan hasilnya, lalu menjalankan `tampilkan :x:`. Jika salah satu baris gagal, maka proses berhenti.

## _Output_ dan _logging_:
- Setiap baris yang berhasil dijalankan akan dicatat di `context.log` sebagai objek `{ line: <kode>, result: <hasil> }`.
- Jika terjadi _error_ pada baris tertentu, eksekusi berhenti dan pesan _error_ dicetak.

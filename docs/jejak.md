# `jejak`
Modul `jejak` berfungsi untuk menampilkan kondisi saat ini dari program Earl yang sedang berjalan. Ini membantu pengguna memahami isi konteks eksekusi dan memori (variabel yang tersimpan) selama program dijalankan.

## Fungsi Utama
`jejak(tokens, modules, context)`
- Tujuan: menampilkan isi `context` dan `memory` scara rapi di konsol.
- Parameter
  - `tokens`, array token dari baris perintah (tidak digunakan di fungsi ini).
  - `modules`, objek modul yang sedang aktif, termasuk `memory`.
  - `context`, objek yang berisi data dan status saat program berjalan.
- Keluaran: mencetak ke layar isi `context` dan `modules.memory` dengan format yang mudah dibaca.

## Contoh Penggunaan dalam Kode Earl
```earl
atur :x: = 10
jejak
```
Perintah `jejak` akan menampilkan kondisi saat itu, seperti variabel yang ada di memori dan status konteks eksekusi.

## Kegunaan
- Membantu **debugging** untuk melihat nilai variabel dan status internal program.
- Memudahkan pemahaman tentang bagaimana data tersimpan dan berubah selama eksekusi script.
- Berguna saat mengembangkan _script_ agar bisa mengetahui apa yang terjadi "di balik layar".

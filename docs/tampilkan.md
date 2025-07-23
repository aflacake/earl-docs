# `tampilkan`
Modul ini berfungsi untuk **menampilkan nilai variabel atau ekspresi** dalam konteks program, dengan kemampuan untuk mengakses variabel sederhana, _nested object_, _array_, dan juga menyimpan hasil keluaran ke file.

## Fungsi Utama:
`tampilkan(tokens, modules, context)`
- Deskripsi:
  Menampilkan isi dari token-token yang diberikan. Token bisa berupa:
  - String literal (contoh: `"Halo Dunia"`).
  - Nama variabel (contoh: `:nama:`).
  - Ekspresi matematika sederhana.
  - Akses ke objek bersarang atau _array_.
  - Perintah khusus seperti menampilkan seluruh memory atau menyimpan _output_ ke file.
- Parameter
  - `tokens`, _array_ string dari perintah dan argumen (contoh: `['tampilkan', ':nama:']`).
   `modules`, objek modul lain (tidak dipakai dalam fungsi utama ini).
  - `context`, objek yang berisi data konteks seperti memory (penyimpanan variabel), `lingkup` (scope variabel lokal), dan `ini` (objek khusus).
- Fitur Utama:
  - Mendukung flag `-v` untuk _output verbose_ (lebih detail dan format JSON).
  - Mendukung perintah `memory` untuk menampilkan seluruh isi variabel yang tersimpan.
  - Mendukung _output_ ke file menggunakan simbol `>`.
  - Mendukung akses variabel _nested_, _array_, dan objek menggunakan format token seperti `:var:key:`, `:var[0]:`, dan `:obj.atribut:`.
- Contoh Penggunaan:
  ```earl
  tampilkan :nama:
  tampilkan -v :data:
  tampilkan "Halo" :user.name:
  tampilkan :list[2]:
  tampilkan > "output.txt"
  tampilkan memory
  ```

## Fungsi Pendukung:
`resolveToken(token, context, modules)`
- Mengubah token menjadi nilai yang sesuai dari `memory`, `lingkup`, atau objek `ini`.
- Mendukung berbagai format token seperti variabel biasa, nested keys, _array index_, objek atribut, dan ekspresi matematika.
`evalMathExpression(expr)`
- Mengevaluasi ekspresi matematika sederhana dari _string_.
- Aman terhadap karakter non-angka/operator.
`formatValue(val, verbose)`
- Memformat nilai agar tampil lebih menarik di _console_ dengan warna, misalnya:
  - Angka berwarna cyan.
  - String berwarna hijau dengan tanda kutip.
  - Boolean berwarna kuning.
  - Array dan objek bisa tampil ringkas atau _verbose_ (JSON _pretty print_).
 
## Keluaran:
- Jika tidak ada perintah simpan file, hasil ditampilkan di _console_ dengan format warna.
- Jika ada simbol `>` diikuti nama file, hasil _output_ disimpan ke file tersebut.

## Catatan:
- Modul ini membantu debugging dan melihat isi variabel dengan cara yang mudah dibaca.
- Format token fleksibel untuk mengakses data kompleks.
- Cocok digunakan dalam CLI _scripting_ atau REPL berbasis konteks memory.

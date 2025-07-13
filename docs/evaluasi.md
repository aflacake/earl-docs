# `evaluasi`
Modul `evaluasi` berfungsi untuk menghitung dan mengeksekusi ekspresi matematika atau logika dalam bahasa Earl secara dinamis. Modul ini dapat mengenali variabel, angka, string, serta operator matematika dan logika.

## Cara Pakai:
Perintah evaluasi diikuti ekspresi yang ingin dihitung.
### Contoh:
```earl
atur :x: = 5
atur :y: = 10
evaluasi :x: + :y: * 2
```
Keluaran:
```earl
25
```

## Sintaks:
```bash
evaluasi <ekspresi>
```
- `<ekspresi>` adalah gabungan token yang terdiri dari:
  - Variabel, misalnya `:x:`.
  - Nilai literal (angka, _string_ atau teks).
  - Operator matematika (+, -, *, /, %).
  - Operator logika (&&, ||, !, ==, !=, >, <, >=, <=).
  - Kurung `(` dan `)` untuk pengelompokan.

## Penjelasan:
- Modul ini membaca token satu per satu dari ekspresi.
- Jika token adalah operator, langsung dimasukkan ke ekspresi hasil tanpa diubah.
- Jika token variabel atau nilai, _diresolve_ nilainya terlebih dahulu.
- Nilai _string_ dibungkus tanda kutip agar bisa dihitung sebagai _string_ di JavaScript.
- Ekspresi yang sudah lengkap kemudian dieksekusi dengan JavaScript `Function()` untuk mendapatkan hasilnya.

## Fitur:
- Mendukung operator matematika dasar.
- Mendukung operator logika.
- Mendukung penggunaan variabel yang sudah diatur.
- Menangani _string_ dan angka dengan benar.
- Menampilkan hasil evaluasi langsung ke konsol.

## Catatan:
- Jika ekspresi tidak valid, modul akan menampilkan pesan error.
- Pastikan variabel sudah didefinisikan sebelum digunakan dalam ekspresi.
- Gunakan tanda `:` untuk variabel, misal `:nama:`.

# `jika`
Modul `jika` digunakan untuk membuat percabangan logika dalam program Earl. Fungsinya mirip dengan `if` di bahasa pemrograman lain. Ia menjalankan perintah tertentu hanya jika kondisi terpenuhi (benar atau _true_).

## Format Umum
```bash
jika <kiri> <operator> <kanan> maka <perintah> [argumen]
```

Contoh:
```earl
jika :nilai: > 80 maka tampilkan "Nilai kamu bagus!"
```

### Parameter
- `<kiri>`, nilai di sebelah kiri operator. Bisa berupa angka, _string_, atau variabel (`:nama:`).
- `<opearator>`, operator pembanding: `==`, `!=`, `>`, `<`, `>=`, `<=`
- `<kanan>`, nilai disebelah kanan operator.
- `maka`, kata kunci wajib setelah kondisi.
- `<perintah>`, nama perintah yang dijalankan jika kondisi benar (misal: `tampilkan`, `atur`, dll).
- `[argumen]`, argumen tambahan untuk perintah tersebut.

## Operator yang Didukung
- `==`, sama dengan.
- `!=`, tidak sama dengan.
- `>`, lebih besar.
- `<`, leih kecil.
- `>=`, lebih besar atau sama.
- `<=`, lebih kecil atau sama.

## Contoh Penggunaan
1. Cek nilai sederhana
   ```earl
   atur :angka: = 10
   jika :angka: == 10 maka tampilkan "Angka benar1"
   ```
2. Dengan atribut _instance_ (objek)
   ```earl
   atur :pengguna.nama: = "Siti"
   jika :pengguna.nama: == "Siti" maka tampilkan "Selamat datang, Siti~"
   ```

Catatan:
- Token seperti `:variabel:` akan otomatis dicari nilainya dari memory.
- Dukung juga pemanggilan atribut kelas seperti `:objek.nama:`.

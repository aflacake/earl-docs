# `hitung`
Modul `hitung` berfungsi untuk melakukan perhitungan matematis dari sebuah ekspresi yang diberikan dalam bentuk token, kemudian menyimpan hasilnya ke variabel tertentu di `memory`.

## Fungsi Utama:
`hitung(tokens)`
Deskripsi:
Memproses perintah hitung dengan format:
```earl
hitung ke :nama_variabel: dari (ekspresi matematis)
```
Fungsi ini akan mengevaluasi ekspresi tersebut dan menyimpan hasilnya ke variabel memori bernama `nama_variabel`.

## Contoh Penggunaan:
```earl
hitung ke :hasil: dari 3 + 4 * 2
tampilkan :hasil:

set ke :a: dari 5
set ke :b: dari daftar 1 2 3
hitung ke :res: dari :a: + panjang :b:
tampilkan :res:

hitung ke :x: dari sqrt(25)
tampilkan :x:

hitung ke :y: dari 10 % 3 + 2 ^ 3
tampilkan :y:

```

## Cara Kerja:
1. Validasi format perintah
   Memastikan format perintah benar (`hitung ke :var: dari (ekspresi)`).
2. Membaca nama variabel tujuan
   Nama variabel hasil hitung diambil dari token ke-3, contoh: `:hasil:`.
3. Menggabungkan ekspresi
   Ekspresi matematika yang ada setelah kata `dari` digabungkan menjadi _string_ ekspresi.
4. Mengganti token khusus
   - `panjang :nama_daftar:`, diganti dengan panjang _array_ pada memori.
   - `:nama_variabel:`, diganti dengan nilai variabel di memori (jika ada dan tipe _number_).
5. Tokenisasi ekspresi
   Ekspresi dipecah menjadi token-token yang mudah diolah.
6. Resolusi token
   Token yang berupa variabel atau fungsi akan diubah menjadi nilai numerik yang sesuai.
7. Konversi ke postfix
   Ekspresi _infix_ diubah menjadi _postfix_ agar mudah dievaluasi.
8. Evaluasi postfix
   Menghitung hasil dari ekspresi postfix secara bertahap.
9. Menyimpan hasil
   Hasil evaluasi disimpan ke variabel di `memory` sesuai nama yang ditentukan.

## Fungsi Pendukung:
- `tokenizeExpression(expr)`
  Memecah _string_ ekspresi menjadi token matematis dan fungsi (misalnya sqrt, sin, dll).
- `toPostfix(tokens)`
  Mengubah token _infix_ menjadi _postfix_ (notasi RPN) berdasarkan prioritas operator.
- `evaluatePostfix(postfix)`
  Menghitung hasil dari ekspresi _postfix_ menggunakan tumpukan.

## Operator dan Fungsi yang Didukung:
- Operator: `+`, `-`, `*`, `/`, `%`, dan `^`.
- Fungsi: `sqrt()`, `abs()`, `sin()`, `cos()`, dan `tan()`.
- Modulus (`%`) mendukung operasi antara angka dan _array_ angka (dengan _array_ di kiri).

## Catatan:
- Ekspresi harus valid dan lengkap (operator membutuhkan dua operand).
- Fungsi trigonometri menggunakan radian.
- Jika terjadi kesalahan, modul akan menampilkan pesan error dan mengembalikan `NaN`.
- Variabel disimpan di objek `memory` yang bisa diakses oleh modul lain.

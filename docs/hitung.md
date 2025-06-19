# `hitung`
Melakukan perhitungan matematika dan menyimpan hasilnya ke dalam variabel.

## Sintaks
```pearl
hitung ke :nama_variabel: dari (ekspresi)
```
- `nama_variabel`, Tempat hasil disimpan (tanpa spasi).
- `ekspresi`, Perhitungan matematika di dalam tanda kurung.

## Contoh:
```pearl
hitung ke :hasil: dari (5 + 3 * 2)
```
Akan menyimpan `11` ke variabel `hasil`.

## Mendukung:
- Operator: `+ - * / % ^`
- Fungsi: `sqrt(...)`, `abs(...)`, `sin(...)`, `cos(...)`, dan `tan(...)`
- Variabel: bisa pakai nilai dari `:nama_variabel:`.
- Panjang daftar: `panjang :nama_daftar:`

Contoh dengan variabel dan fungsi:
```pearl
hitung ke :luas: dari (3.14 * :r: * :r:)
hitung ke :akar: dari (sqrt(16))
```

Catatan:
- Pastikan ekspresi ditulis di dalam tamda kurung `(...)`.
- Nilai variabel harus berupa angka.
- Daftar belum bisa digunakan langsung sebagai operand (kecuali untuk `panjang`).

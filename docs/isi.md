# `isi`
Mengisi variabel dalam memori dengan nilai tertentu.

## Format Perintah:
```earl
isi :nama_variabel: dengan nilai
```

## Keterangan:
- `:nama_variabel:` harus ditulis dengan tanda titik dua di depan dan belakang, misal `:x:`.
- nilai bisa berupa angka, variabel lain, atau string dengan tanda kutip (`""`).
- string harus diawali dan diakhiri dengan tanda kutip ganda (`""`).
- variabel dan nilainya disimpan dalam konteks memori (`context.memory`).

## Contoh:
```earl
isi :umur: dengan 25
isi :nama: dengan "Andi"
```

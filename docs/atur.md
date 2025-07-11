# `atur`
Menyimpan atau memperbarui nilai sebuah variabel di dalam memori global program.

## Format Perintah:
```earl
atur :nama: = nilai
```
Penjelasan:
- `:nama:`, nama variabel (harus diapit diawali dan diakhiri dengan titik dua).
- `nilai`, bisa berupa angka, teks, variabel lain, atau gabungan beberapa token.

## Contoh Penggunaan:
Menyimpan teks:
```earl
atur :pesan: = "Halo Dunia!"
```

Menyimpan angka atau nilai dari variabel lain:
```earl
isi :angka: dengan 10
atur :salin: = :angka:
```

Menyimpan beberapa kata:
```earl
atur :salam: = "Halo" dunia!
```
Hasilnya variabel `:salam:` berisi teks "Halo dunia!"

## Cara Kerja:
1. Mengecek format `atur :nama: = ...`.
2. Menghapus tanda `:` dari nama variabel.
3. Jika hanya satu nilai, langsung simpan.
4. Jika banyak nilai (lebih dari satu token setelah `=`), gabungkan jadi satu _string_ atau teks.
5. Nilai disimpan ke `context.memmory`.

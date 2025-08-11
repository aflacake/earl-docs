# `tampilkan`
Modul `tampilkan` digunakan untuk mencetak teks, nilai variabel, _array_, objek, atau ekspresi ke layar (atau ke file jika diarahkan).

## Sintaks Perintah
```earl
tampilkan [opsi] nilai1 nilai2 ... [> "nama_file"]
```

- `nilai` bisa berupa:
  - Teks dalam tanda kutip, `"Halo"`.
  - Variabel, `:nama:`.
  - Objek atau array, `:data:`.
  - Ekspresi, bisa berupa `:objek.kunci:` atau `:daftar[0]:`.
- Opsi tambahan:
  - `-v`, tampilkan dalam format verbose (misalnya JSON objek atau _array_).
  - `memory`, tampilkan semua isi memori.

## Contoh Penggunaan
### Contoh 1: Menampilkan teks biasa
```earl
tampilkan "Selamat datang"
```

Keluaran: `Selamat datang`.

### Contoh 2: Menampilkan isi variabel
```earl
atur :nama: = "Budi"
tampilkan :nama:
```

Keluaran: `"Budi"`.

### Contoh 3: Menampilkan array
```earl
atur :angka: = [1, 2, 3]
tampilkan :angka:
```

Keluaran: `1 2 3`.

### Contoh 4: Menampilkan objek
```earl
atur :orang: = {nama: "Sari", usia: 30}
tampilkan -v :orang:
```

Keluaran (verbose):
```bash
{
  "nama": "Sari",
  "usia": 30
}
```

### Contoh 5: Menampilkan atribut objek
```earl
tampilkan :orang.nama:
```

Keluaran: `"Sari"`.

### Contoh 6: Menampilkan elemen array
```earl
tampilkan :angka[1]:
```

Keluaran: `2`.

### Contoh 7: Menyimpan hasil ke file
```earl
tampilkan "Data selesai." > "log.txt"
```

Keluaran akan disimpan ke `log.txt`.

### Contoh 8: Menampilkan seluruh memory
```earl
tampilkan memory
```

Keluaran: semua variabel dan nilainya.

Catatan Tambahan:
- Modul ini menggunakan `resolveToken` untuk memahami variabel, objek, atribut, dan ekspresi kompleks lainnya.
- Sangat cocok digunakan saat debugging atau saat ingin melihat hasil proses secara langsung.

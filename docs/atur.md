# Modul atur
Modul ini digunakan untuk mengatur atau menyimpan nilai ke dalam variabel di memori. Variabel selalu dalam format `:nama:`.

## Sintaks Perintah
```bash
atur :nama_variabel: = nilai
```
atau
```bash
atur :nama_variabel: [nilai1 nilai2 nilai3 ...]
```

- `:nama_variabel:`, nama variabel yang akan diatur, harus dalam format `:nama:`.
- `nilai`, bisa berupa angka, _string_, objek JSON, _array_, atau ekspresi matematika yang akan dihitung.

## Penjelasan
- Jika menggunakan tanda sama dengan (`=`), nilai bisa berupa:
  - Ekspresi matematika (contoh: `3 + 4 * 2`)
  - Objek JSON (contoh: `{key: "value", count: 5}`)
  - _Array_ JSON (contoh: `[1, 2, 3]`)
- Jika tanpa tanda sama dengan, dan langsung diikuti _array_ (contohnya `[nilai1 nilai2 ...]`), akan _di-parse_ menjadi _array_ biasa.
- Nilai ekspresi yang mengandung variabel lain (`:variabel_lain:`) akan digantikan dengan nilai variabel tersebut.
- Variabel yang sudah diatur disimpan di `context.memory`.

## Contoh Penggunaan
### Contoh 1: Mengatur angka
```earl
atur :umur: = 25
tampilkan :umur:
```

Keluaran: `25`

### Contoh 2: Mengatur _string_
```earl
atur :nama: = "Andi"
tampilkan :nama:
```

Keluaran: `"Andi"`

### Contoh 3: Mengatur _array_ dengan tanda sama dengan
```earl
atur :angka: = [1, 2, 3, 4]
tampilkan :angka:
```

Keluaran: `1 2 3 4`

### Contoh 4: Mengatur _array_ tanpa tanda sama dengan
```earl
atur :buah: [apel pisang jeruk]
tampilkan :buah:
```

Kelauaran: `apel pisang jeruk`

### Contoh 5: Mengatur objek JSON
```earl
atur :mobil: = {merk: "Toyota", tahun: 2020}
tampilkan -v :mobil:
```

Keluaran (verbose):
```bash
{
  "merk": "Toyota",
  "tahun": 2020
}
```

### Contoh 6: Menggunakan ekspresi matematika dengan variabel lain
```earl
atur :a: = 10
atur :b: = :a: * 2 + 5
tampilkan :b:
```

Keluaran: `25`.

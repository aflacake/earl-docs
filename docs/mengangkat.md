# `mengangkat`
Modul ini berfungsi untuk menaikkan atau menambahkan nilai sebuah variabel yang ada di memori. Variabel bisa berupa angka, array, atau objek.

## Sintaks Perintah
```bash
mengangkat :nama_variabel: nilai_kenaikan
```

- `:nama_variabel:`, variabel target, harus dalam format `:nama:`.
- `nilai_kenaikan`, nilai yang akan ditambahkan, bisa berupa angka atau ekspresi matematika.

## Penjelasan
- Jika variabel bertipe angka, nilai akan langsung ditambah.
- Jika variabel bertipe _array_:
  - Jika elemen adalah objek, semua atribut angka di setiap objek akan dinaikkan.
  - Jika elemen bukan objek, nilai baru akan ditambahkan ke array.
- Jika variabel bertipe objek, semua atribut angka akan dinaikkan.
- Jika tipe variabel tidak cocok, perintah akan gagal.

## Contoh Penggunaan
### Contoh 1: menaikkan angka
```earl
atur :score: = 10
mengangkat :score: 5
tampilkan :score:
```

Keluaran: 15

### Contoh 2: menaikkan atribut angka dalam array objek
```earl
atur :data: = [{point: 2}, {point: 3}]
mengangkat :data: 2
tampilkan -v :data:
```

Keluaran (verbose):
```bash
[
 {
    "point": 4
 },
 {
   "point": 5
  }
]
```

### Contoh 3: menaikkan atribut angka dalam objek
```earl
atur :coords: = {x: 3, y: 7}
mengangkat :coords: 1
tampilkan -v :coords:
```

Keluaran (verbose):
```bash
{
  "x": 4,
  "y": 8
}
```

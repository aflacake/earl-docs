# `jikaLainnya`
Modul `jikaLainnya` memperluas logika **percabangan bersyarat** dalam bahasa Earl dengan mendukung blok seperti:
- `jika`,
- `jika-lainnya` (else-if),
- `lain` (else),
- `selesai-jika` (penutup blok).
Fungsinya mirip seperti `if`, `else if` dan `else` di bahasa pemrograman populer lainnya seperti JavaScript, Python, dll.

## Fungsi Utama:
`async function jikaLainnya(tokens, modules, context)`
- Tujuan: mengeksekusi satu dari beberapa blok kondisi seperti ratai if-else.
- Parameter:
  - `tokens`, token baris awal biasanya diabaikan karena logika diproses dari `context.lines`).
  - `modules`, objek modul aktif, digunakan untuk memanggil perintah lain.
  - `context`, konteks eksekusi, termasuk seluruh baris kode (`lines`) dan posisi saat ini (`index`).
 
## Format Sintaks:
```earl
atur :x: = 5

jika :x: > 10 maka
    tampilkan "Lebih besar dari 10"
jika-lainnya :x: == 10 maka
    tampilkan "Pas 10"
lain
    tampilkan "Kurang dari 10"
selesai-jika
```

### Cara Kerja:
1. Membaca baris satu per satu dari posisi saat ini (`context.index`).
2. Jika menemukan `jika` dan kondisinya **benar**, maka blok itu dieksekusi, yang lain dilewati.
3. Jika tidak terpenuhi, akan lanjut ke `jika-lainnya`, lalu `lain`.
4. Hanya **satu blok pertama yang terpenuhi** yang akan dijalankan.
5. Proses berakhir saat menemukan `selesai-jika`.

## Contoh Lengkap:
```earl
atur :nilai: = 75

jika :nilai: >= 90 maka
    tampilkan "A"
jika-lainnya :nilai: >= 80 maka
    tampilkan "B"
jika-lainnya :nilai: >= 70 maka
    tampilkan "C"
lain
    tampilkan "D"
selesai-jika
```

## Kegunaan:
- Membuat **logika bercabang** lebih kompleks dan fleksibel.
- Menyederhanakan banyak `jika` bertumpuk dengan bentuk yang lebih rapi.
- Membantu penulisan skrip yang **lebih mudah dibaca dan diatur**.

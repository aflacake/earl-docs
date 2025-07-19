# `langkah`
Modul `langkah` berfungsi menjalankan kode **secara langkah demi langkah** (step-by-step). Ini berguna untuk memeriksa atau memahami jalannya program secara perlahan.

## Fungsi Utama:
```js
async function langkah(tokens, modules, context)
```
- `tokens`, daftar dari perintah `langkah`.
- `modules`, objek yang berisi fungsi-fungsi perintah lain, termasuk `tokenize` dan `resolveToken`.
- `context`, objek yang berisi informasi tentang program saat ini, seperti `lines` (baris-baris kode) dan `index` (pada posisi baris yangs sedang dijalankan).

## Contoh Penggunaan:
```earl
-- Contoh program Earl untuk modul langkah --
langkah
atur :a: = 5
tampilkan :a:

atur :a: = 10
tampilkan :a:

atur :b: = [1 2 3]
tampilkan :b[1]:
berakhir
```

## Cara Menggunakan:
- Jalankan perintah `langkah` di program.
- Program akan masuk mode interaktif.
- Tekan ENTER untuk menjalankan baris kode berikutnya.
- Ketik `berakhir` lalu ENTER untuk keluar dari mode langkah.

## Cara Kerja:
1. Ambil baris kode berikutnya dari `context.lines` setelah posisi `context.index`.
2. Tampilkan baris kode satu per satu ke layar.
3. Tunggu pengguna menekan ENTER untuk lanjut ke baris berikutnya.
4. Jika pengguna mengetik `berakhir`, mode langkah berhenti.
5. Untuk setiap baris, lakukan:
   - Pecah baris menjadi token dengan `modules.tokenize`.
   - Proses token menggunakan `modules.resolveToken`.
   - Jalankan perintah yang sesuai dengan token pertama.
6. Setelah selesai, perbarui `context.index` supaya eksekusi bisa lanjut dari baris berikutnya.

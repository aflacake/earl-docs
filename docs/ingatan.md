# `ingatan`
Modul `ingatan` digunakan untuk menampilkan berapa banyak memori (RAM) yang sedang digunakan oleh sistem komputer saat ini. Ini berguna untuk memahami seberapa besar sumber daya yang sedang dipakai, terutama saat menjalankn program besar.

## Contoh Penggunaan
```earl
ingatan
```

## Fungsi yang Disediakan
`ingatan(tokens, modules, context)`
**Fungsi Utama: ** Menampilkan informasi penggunaan memori.
**Parameter:**
- `tokens`: _array_ kata-kata yang sudah di-_tokenize_ dari baris perintah.
- `modules`: kumpulan modul lain yang bisa digunakan.
- `context`: informasi konteks saat ini, seperti baris program dan memori sementara.

**Keluaran:**
- Langsung mencetak ke layar seeperti ini:
  ```bash
  Penggunaan memori saat ini: 523.87 MB dari total 8123.56 MB
  ```

Catatan Tambahan:
- Modul ini tidak menyimpan hasilnya ke variabel.
- Modul ini hanya membaca status memori dari sistem operasi.
- Cocok digunakan untuk debugging atau optimasi.

## Dibalik Layar: Bagaimana Ini Bekerja?
Modul ini menggunakan fungsi bawaan dari Node.js:
```js
const os = require('os');
```
Lalu menghitung:
- Total memori: `os.totalmem()`
- Memori yang tersisa: `os.freemem()`
- Memori yang digunakan = total - sisa
Dan akhirnya mencetak ke layar.

## Cocok Untuk
- Pemula yang ingin tahu seberapa besar memori yang digunakan.
- Pengembang yang ingin memantau performa program di Earl

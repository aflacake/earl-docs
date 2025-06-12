# Dokumentasi Pearl
**Pearl** adalah bahasa pemrograman eksperimental yang dirancang agar mudah dibaca, mudah ditulis, dan fleksibel untuk berbagai kebutuhan seperti otomatisasi sederhana, logika kondisional, pemrosesan data, serta pembuatan struktur modular.

Pearl dibangun menggunakan Node.js, dengan pendekatan berbasis modul. Setiap perintah utama dalam Pearl diimplementasikan sebagai modul atau fungsi terpisah.

## Fitur Utama:
- Sintaks yang sederhana dan mudah dipahami
- Pendekatan modular
- Mendukung eksekusi `.pearl` maupun mode REPL
- Cocok untuk pembelajaran mengenai interpreter, tokenisasi, dan ekseskusi perintah baris demi baris.

## Contoh Penggunaan:
1. Menampilkan teks ke layar:
   ```pearl
   tampilkan "Halo Dunia!"
   ```
2. Menyimpan dan menggunakan variabel
   ```bash
   masukkan :nama:
   tampilkan :nama:
   ```
4. Perulangan sederhana:
   ``` pearl
   masukkan :n: 5
   ulangi :n: {
     tampilkan "Perulangan ke-" :index:
   }
   selesai
   ```

# Cara Menjalankan Pearl
Untuk menjalankan kode Pearl dari file `.pearl`, gunakan perintah:
```bash
node index.js nama_file.pearl
```

Jika ingin mencoba secara langsung dalam mode interaktif (REPL), cukup jalankan:
```bash
node index.js
```
Lalu ketik perintah langsung di terminal. Ketik `keluar` untuk menghentikan REPL.

# Instalasi dan Pengembangan
Karena Pearl berbasis Node.js, kamu hanya perlu:
```bash
git clone https://github.com/aflacake/pearl
cd pearl
npm install
```

> Beberapa konten ini juga dihasilkan dari AI

> Peringatan:
> Dokumentasi ini beberapa informasi mungkin sudah tidak diperbarui atau tertinggal informasi. Bantu kontribusi proyek ini atau beri usulkan diatas isu.

<p align="right">Bahasa: Indonesia</p>

# Dokumentasi Earl
**Earl** adalah bahasa pemrograman eksperimental yang dirancang agar mudah dibaca, mudah ditulis, dan fleksibel untuk berbagai kebutuhan seperti otomatisasi sederhana, logika kondisional, pemrosesan data, serta pembuatan struktur modular.

Earl dibangun menggunakan Node.js, dengan pendekatan berbasis modul. Setiap perintah utama dalam Pearl diimplementasikan sebagai modul atau fungsi terpisah.

## Fitur Utama:
- Sintaks yang sederhana dan mudah dipahami
- Pendekatan modular
- Mendukung eksekusi `.earl` maupun mode REPL
- Cocok untuk pembelajaran mengenai interpreter, tokenisasi, dan ekseskusi perintah baris demi baris.

## Contoh Penggunaan:
1. Menampilkan teks ke layar:
   ```earl
   tampilkan "Halo Dunia!"
   ```
2. Menyimpan dan menggunakan variabel
   ```earl
   masukkan :nama:
   tampilkan :nama:
   ```
4. Perulangan sederhana:
   ```earl
   atur :jumlah: = 2

   ulangi :jumlah:
     tampilkan "Perulangan berdasarkan variabel!
   selesai
   ```

# Cara Menjalankan Earl
### Bahan dari Pihak Ketiga
- Menginstal paket tambahan di Node.js untuk keperluan merender visual atas perintah aturan 'gambar' dengan
  ```bash
  npm install canvas
  ```
- Menginstal `chalk` pustaka untuk memberi warna pada teks terminal.
  ```bash
  npm install chalk@4
  ```
- Menginstal `form-data` untuk memuat request HTTP yang mengandung form data, biasanya untuk `multipart/formdata`, misalnya kirim file lewat `fetch`, `axios`, atau `http.request`.
  ```bash
  npm install form-data
  ```
- Memanggil API GitHub, misalnya untuk `picuAlurKerja`.
  ```bash
  npm install axios
  ```
- Memungkinkan memasang Electron bisa bikin dan kontrol jendela aplikasi desktop dari skrip.
  ```bash
  npm install electron
  ```

## Dengan Node.js
Untuk menjalankan kode Earl dari file `.earl`, gunakan perintah:
```bash
node index.js nama_file.earl
```

Jika ingin mencoba secara langsung dalam mode interaktif (REPL), cukup jalankan:
```bash
node index.js
```
Lalu ketik perintah langsung di terminal. Ketik `keluar` untuk menghentikan REPL.

## Dengan CLI
### Global
```bash
npm link
```
Lalu uji:
```bash
earl "atur :angka: = 42\ntampilkan :angka:"
earl tes.earl
```

### Pengguna Windows
File CLI bernama: `earl.cmd`.
File `package.json` dan `earl.cmd` sudah disiapkan maka langsung arahkan ke folder, lalu jalankan:
```bash
npm link
```

#### Tambahkan ke PATH
1. Salin semua file atau download semua file ini dengan keterangan versi terbaru (rekomendasi) atau pada saat proses pengembangan juga terbaik (perlu perbaikan).
   > Misalnya di C:\Users\KAMU\earl
2. Tambahkan folder tersebut ke PATH:
   - Tekan `Win + R`, ketik _Edit the system environment variables_ lalu _Enter_
   - Tab _**Advanced**_ > _Environment Variables_
   - Dibagian _User variables_, pilih _Path_ lalu
   - **New** > masukkan
     > Misalnya di C:\Users\KAMU\earl
   - **OK** dan restart terminal

Jalankan dengan menggunakan perintah:
```bash
earl contoh.earl
```

### Pengguna Linux dan MacOS
File CLI bernama: `earl`
#### Tambahkan ke PATH
Dengan menjalankan folder langsung atau saat ini:
```bash
./earl contoh.earl
```
atau

Berikan hak akses eksekusi:
```bash
chmod +x bin/earl
```
link ke global:
``` bash
npm link
```

# Instalasi dan Pengembangan
Karena Earl berbasis Node.js, kamu hanya perlu:
```bash
git clone https://github.com/aflacake/earl-lang
cd earl-lang
npm install
```
## npm
```bash
npm install github:aflacake/earl-lang
```
Atau
```bash
npm install earl-lang@2.0.3
```
Atau juga
```bash
npm i earl-lang
```

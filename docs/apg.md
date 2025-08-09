# `apg`
Modul `apg` memungkinkan membuka jendela antarmuka grafis menggunakan **Electron**, mengirim pesan ke dalamnya, dan menutup jendela tersebut langsung dari kode Earl.

Jika Anda adalah pemula, anggap ini sebagai cara untuk "menampilkan tampilan web" langsung dalam skrip bahasa Earl.

## Kebutuhan:
Pastikan menjalankan program menggunakan **Electron** karena modul ini memakai fitur `BrowserWindow` dari Electron.

## Sintaks Perintah:
1. `apg buka <url>`
   Membuka jendela baru yang menampilkan halaman dari URL tertentu.\
   Contoh:
   ```earl
   apg buka https://example.com
   ```
   Jika `<url>` tidak diberikan, maka akan membuka `https://example.com` secara bawaan.

2. `apg kirim <pesan>`
   Mengirim pesan dari proses utama ke jendela yang terbuka.\
   Contoh:
   ```earl
   apg kirim Halo dari Earl!
   ```
   
   Di dalam jendela web, kamu bisa menangkap pesan ini menggunakan:
   ```js
   const { ipcPenyaji } = require('electron');
   ipcPenyaji.on('pesan-dari-utama', (event, msg) => {
     console.log('Pesan dari utama:', msg);
   });
   ```

3. `apg tutup`
   Menutup jendela yang sedang terbuka.\
   Contoh:
   ```earl
   apg tutup
   ```

## Penanganan Kesalahan:
Jika terjadi kesalahan (misalnya membuka jendela sebelum Electron siap), pesan kesalahan akan disimpan dalam `context.return`.

## Catatan Teknis:
- Modul menggunakan `ipcMain` untuk mendengarkan pesan dari jendela.
- Jendela hanya akan ditampilkan saat sudah siap (`ready-to-show`).
- `nodeIntegration` dan `contextIsolation` disesuaikan untuk kemudahan komunikasi, **jangan digunakan untuk produksi tanpa mempertimbangkan keamanan**.

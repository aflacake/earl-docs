# `apg`
Modul ini memungkinkan skrip Earl berinteraksi dengan antarmuka grafis berbasis Electron, seperti **membuka halaman web**, **mengirim dan menerima pesan**, serta **menutup jendela**.

## Struktur Umum:
```bash
apg <perintah> <opsi>
```

## Perintah yang Didukung:
1. `apg buka <url> [opsi]`
   Membuka jendela Electron dengan halaman tertentu.\
   Contoh:
   ```earl
   apg buka https://example.com :id=utama :lebar=1024 :tinggi=768 :judul="Demo" :layarpenuh=false
   ```
   Opsi:
   1. `:id=nama`, ID unik jendela (bawaan: `default`).
   2. `:lebar=800`, lebar jendela (bawaan: 800).
   3. `:tinggi=600`, tinggi jendela (bawaan: 600).
   4. `:judul=teks`, judul jendela.
   5. `:layarpenuh=true/false`, menampilkan layarpenuh atau tidak.
  
2. `apg kirim <pesan> [:id=nama]`
   Mengirim pesan ke jendela tertentu dan menunggu **balasan** dari jendela tersebut.\
   Contoh:
   ```earl
   apg kirim "Hai jendela!" :id=utama
   ```
   Pesan akan dikirim otomatis dikirim ke channel `pesan-dari-utama` dan balasan akan diterima dari penyaji melalui `saluranBalasan`.

3. `apg tutup [:id=nama]`
   Menutup jendela tertentu.\
   Contoh:
   ```earl
   apg tutup :id=utama
   ```

## Komunikasi Pesan:
- Pesan dikirim dari `main process` ke `penyaji` dengan channel `pesan-dari-utama`.
- `penyaji` dapat mengirim balasan ke saluran dinamis yang dikirim bersamaan (`saluranBalasan`).
- `ipcMain` akan otomatis menangani dan membalas jika `saluranBalasan` tersedia.

## Catatan Penting:
- Modul ini hanya berfungsi saat dijalankan di lingkungan **Electron**.
- URL harus diawali `http://`, `https://`, atau `file://`.
- ID jendela membolehkan beberapa jendela dibuka dan dikontrol secara paralel.
- Sangat cocok untuk integrasi GUI dengan skrip Earl CLI.

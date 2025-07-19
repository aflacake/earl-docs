# `masukkan`
Berfungsi untuk mengambil input dari pengguna dan menyimpan nilainya ke dalam memori program Earl, sekaligus mendukung pembuatan instance dari kelas yang sudah terdefinisi.

## Fungsi Utama:
- Tujuan:
  Membaca input dari pengguna untuk variabel atau membuat instance dari kelas, lalu menyimpan hasilnya di memori.

## Cara Kerja:
1. Deteksi pembuatan _instance_ kelas:
   Jika format perintah seperti:
   ```earl
   masukkan :NamaKelas: sebagai namaInstance
   ```
   - Cek apakah `NamaKelas` sudah ada di `memory` dan bertipe kelas (`__tipe === 'kelas'`).
   - Jika benar, buat objek _instance_ baru dengan atribut kelas diset `null`.
   - Simpan _instance_ di `memory` dengan nama `namaInstance`.
   - Tampilkan pesan bahwa _instance_ telah dibuat.
2. Input nilai variabel:
   Jika format perintah seperti:
   ```bash
   masukkan :variabel: [prompt opsional]
   ```
   - Cek apakah variabel sudah ada di `memory`. Jika sudah ada, beri peringatan dan batalkan input.
   - Tampilkan prompt input ke pengguna, dengan teks _prompt default_ atau yang diberikan.
   - Baca input pengguna dari terminal.
   - Jika input berupa token `:namaVariabel:`, _resolve_ nilai token tersebut.
   - Jika nilai adalah angka, simpan sebagai `number`.
   - Jika nilai adalah _string_ singkat dan hanya terdiri dari huruf dan spasi, simpan sebagai teks valid.
   - Jika input tidak valid, tampilkan error.
   - Jika valid, simpan nilai ke `memory`.
3. Promise:
   Fungsi mengembalikan Promise, sehingga bisa digunakan dengan `await`.

## Contoh Penggunaan:
```earl
masukkan :a:
```
- Akan memunculkan prompt:
   `Masukkan nilai untuk :a: :`
- Setelah user mengetik nilai, nilai tersebut disimpan sebagai `a` di memori.

```earl
kelas :Orang:
  atribut nama umur
selesai

masukkan :Orang: sebagai mahasiswa
tampilkan :mahasiswa.nama:
```
- Jika `Orang` adalah kelas yang sudah didefinisikan, akan dibuat instance `mahasiswa` dengan atribut sesuai kelas `Orang`.

## Catatan:
- Input teks hanya diterima jika panjangnya ≤ 10 karakter dan hanya terdiri dari huruf dan spasi.
- Untuk nilai angka, otomatis konversi ke tipe `number`.
- Variabel yang sudah ada tidak bisa diisi ulang tanpa dihapus dulu.

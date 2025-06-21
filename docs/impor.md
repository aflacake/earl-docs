# `impor`
Digunakan untuk memuat dan menjalankan kode dari file `.earl` lain ke dalam program Earl yang sedang berjalan.

## Cara Penggunaan:
```earl
impor nama_file
```
- `nama_file`, Nama file `.earl` yang ingin diimpor.
- Tidak perlu menulis ekstensi `.earl`, Interpreter akan menambahkannya secara otomatis.

## Contoh:
```earl
impor utilitas
```
Interpreter akan mencari dan menjalanan file: `utilitas.earl`.

## Apa yang Terjadi Saat `impor` Dijalankan?
1. Mengecek apakah nama_file sudah ada.
2. Menambahkan `.earl` ke nama file jika belum ada.
3. Membaca isi file tersebut.
4. Menjalankan kode di dalamnya seolah-olah bagian dari program saat ini.

Catatan Penting:
- File yang diimpor **harus berada di direktori yang sama** atau jalur relatif yang benar.
- Jika file tidak ditemukan, maka akan muncul pesan kesalahan seperti:
  ```bash
  Gagal; mengimpor file 'namafile.earl': ENOENT: no such file or directory
  ```

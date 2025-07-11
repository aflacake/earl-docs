# `aturheader`
Menyimpan atau memperbarui nilai header dalam objek `memory.__headers` untuk digunakan lebih lanjut dalam aplikasi.

## Format Perintah:
```earl
aturheader "Header-Nama" nilai
```
Penjelasan:
- `"Header-Nama"`, nama header yang ingin disimpan. Harus berupa teks yang diapit oleh tanda kutip ganda (`"`).
- `nilai`, nilai yang ingin diberikan untuk header tersebut. Bisa berupa teks biasa.

## Contoh Penggunaan:
Menyimpan Header:
```earl
aturheader "Content-Type" "application/json"
```
Hasilnya `memory.__headers["Content-Type"]` akan diset ke `"application/json"`.

Mengatur Header dengan Nilai Kombinasi:
```earl
aturheader "Authorization" "Bearer 12345"
```
Hasilnya `memory.__headers["Authorization"]` akan diset ke `"Bearer 12345"`.

## Cara Kerja:
1. Memeriksa format perintah aturheader `"Header-Nama" nilai`.
2. Menghapus tanda kutip di sekitar nama header dan nilai.
3. Menyimpan pasangan header dan nilai dalam objek `memory.__headers`.
4. Jika objek `memory.__headers` belum ada, maka akan dibuat terlebih dahulu.

## Validasi:
- Nama header harus diapit tanda kutip (`"`) dan tidak boleh kosong.
- Jika ada kesalahan dalam format perintah, pesan error akan ditampilkan.

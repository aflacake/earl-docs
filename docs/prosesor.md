# `prosesor`
Modul `prosesor` digunakan untuk menampilkan informasi **persentase penggunaan CPU** secara keseluruhan pada komputer yang menjalankan program.

## Fungsi Utama:
`prosesor(tokens, modules, context)`
- Deskripsi:
  Menghitung dan menampilkan persentase rata-rata penggunaan CPU berdasarkan data dari semua core CPU.
- Parameter:
  - `tokens`, _array string_, berisi token dari perintah yang dijalankan (tidak digunakan dalam fungsi ini).
  - `modules`, objek modul lain yang mungkin digunakan (tidak digunakan).
  - `context`, konteks eksekusi saat ini (tidak digunakan).
  - Keluaran:
    Menampilkan ke konsol informasi berupa:
    `Penggunaan CPU: XX.XX%`

## Cara Kerja:
1. Mengambil data CPU menggunakan `os.cpus()` dari modul `os` bawaan Node.js.
2. Menghitung total waktu CPU dan waktu idle untuk semua _core_.
3. Menghitung persentase penggunaan CPU berdasarkan perbandingan waktu idle terhadap total waktu.
4. Menampilkan hasil penggunaan CPU dalam persen dengan dua angka desimal.

## Contoh Penggunaan
Saat modul ini dipanggil melalui perintah `prosesor`, output yang akan tampil misalnya:
```bash
Penggunaan CPU: 23.45%
```

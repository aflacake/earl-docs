# `peranti`
Modul ini digunakan untuk mendapatkan informasi perangkat disk dari sistem operasi yang sedang digunakan. Modul ini mendeteksi platform sistem operasi (Windows, Linux, atau macOS) dan menampilkan statistik penggunaan disk, termasuk ukuran total, ruang yang terpakai, dan persentase penggunaan disk.

## Fungsi Utama:
- **Windows (win32)**, menggunakan perintah `wmic` untuk mendapatkan informasi tentang disk.
- **Linux dan macOS (darwin)**, menggunakan perintah `df -k` untuk mendapatkan informasi tentang disk.
- **Platform yang tidak didukung**, menampilkan pesan error.

1. `peranti(tokens, modules, context)`
   Fungsi utama dalam modul ini yang digunakan untuk menampilkan informasi disk berdasarkan sistem operasi yang terdeteksi.
   Argumen:
   - `tokens`, array yang berisi token perintah. Pada modul ini, token pertama akan mengarah pada perintah untuk mendapatkan informasi disk, tetapi argumen lainnya tidak digunakan.
   - `modules`, modul-modul yang dimuat untuk dapat digunakan dalam pemrosesan kode.
   - `context`, konteks yang berisi informasi terkait eksekusi kode, termasuk variabel dan lingkup eksekusi.
   
   Contoh Penggunaan:
   Jika kita ingin melihat informasi disk pada sistem operasi yang digunakan, cukup menjalankan perintah:
   ```earl
   peranti
   ```

2. Contoh Kasus
   Misalkan menjalankan perintah ini pada sistem operasi Windows dan Linux, keluaran yang akan muncul bisa berupa:
   
   Windows (win32)
   ```bash
   Informasi Disk (Windows):
   Drive C: Terpakai 150 GB / 500 GB (30.0%)
   Drive D: Terpakai 100 GB / 500 GB (20.0%)
   ```

   Linux/macOS (linux/darwin)
   ```bash
   Informasi Disk (Unix-like):
   Root /: Terpakai 120 GB / 500 GB (24.0%)
   ```

3. Penanganan Kesalahan
   - Jika sistem operasi tidak dikenali, seperti pada sistem operasi yang tidak didukung atau kesalahan lainnya, akan muncul pesan error yang sesuai.
   - Jika perintah untuk mendapatkan informasi disk gagal, seperti kesalahan dalam menjalankan perintah di sistem, maka akan muncul pesan error.
  
## Catatan:
- Pastikan **akses ke perintah sistem** tersedia pada lingkungan di mana kode ini dijalankan.

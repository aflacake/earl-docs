# `melahirkan`
Modul ini digunakan untuk:
1. **Membuat array (daftar) dari sejumlah nilai.**
2. **Menjalankan fungsi atau membuat instance kelas secara eksplisit.**

## Contoh Penggunaan:
1. Membuat Daftar dari Nilai
   Format:
   ```earl
   melahirkan daftar[N]: val1 val2 val3 ... valN
   ```
   - `N` adalah jumlah nilai yang ingin dimasukkan ke dalam daftar.
   - Nilai bisa berupa:
     - Angka, misal `123`.
     - Teks yang diapit tanda kutip, misal `"halo"`.
     - Variabel, misal `:nama:`.    
   Contoh:
   ```earl
   melahirkan daftar[3]: 1 2 3
   ```
   Menyimpan ke `memory` seperti:
   ```bash
   memory["daftar_<timestamp>"] = [1, 2, 3]
   ```
   Atau
   ```earl
   melahirkan daftar[2]: :umur: "hai"
   ```
   Jika `memory["umur"] = 20`, maka hasil:
   ```bash
   memory["daftar_<timestamp>"] = [20, "hai"]
   ```
3. Menjalankan Fungsi atau Membuat _Instance_ Kelas
   Format:
   ```earl
   melahirkan namaFungsi
   melahirkan NamaKelas
   ```
   - Jika `namaFungsi` adalah fungsi yang tersimpan di `memory`, maka fungsi itu akan **dipanggil**.
   - Jika `NamaKelas` adalah konstruktor (fungsi) untuk kelas, maka akan dibuat instance dari kelas tersebut.
   Contoh:
   ```earl
   melahirkan mulaiPermainan
   ```
   Jika `memory["mulaiPermainan"]` adalah fungsi, maka akan dijalankan.
   ```earl
   melahirkan Mahasiswa
   ```
   Jika `Mahasiswa` adalah kelas, maka `memory["Mahasiswa"]` akan berisi _instance_ baru dari kelas tersebut.

## Cara Kerja:
- Modul membaca `tokens[1]`,
  - Jika cocok dengan pola `daftar[N]:`, maka akan membuat array dari N elemen.
  - Jika tidak, akan mengasumsikan perintah untuk menjalankan fungsi atau buat instance.

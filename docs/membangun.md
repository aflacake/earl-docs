# `membangun`
Modul **"membangun"** pada bahasa **Earl** memungkinkan pengguna untuk membuat urutan nilai dalam variabel, baik berupa angka maupun huruf, dengan menggunakan perintah `membangun`. Modul ini mendukung pembuatan urutan dalam bentuk _range_, seperti angka dari 1 hingga 5 atau huruf dari "a" hingga "e", dan bahkan mendukung urutan mundur.

## Fungsi Utama:
Modul ini mengandung fungsi `membangun` yang berfungsi untuk membangun suatu urutan nilai berdasarkan parameter yang diberikan.

## Format Perintah:
- Perintah:
  ```bash
  atur :nama_variabel: = dari "nilai_awal" sampai "nilai_akhir" [mundur]
  ```
  Keterangan:
  - `:nama_variabel:`, nama variabel yang ingin diatur.
  - `nilai_awal`, nilai awal urutan (angka atau huruf).
  - `nilai_akhir`, nilai akhir urutan (angka atau huruf).
  - `mundur` (Opsional), menentukan apakah urutan akan mundur (dari besar ke kecil, atau dari huruf terakhir ke pertama).

## Cara Menggunakan:
1. Membangun Urutan Angka (Naik):
   - Urutan angka dibuat dengan menggunakan kata kunci `dari` dan `sampai`.
   - Sintaks:
     ```bash
     atur :nama_variabel: = dari "angka_awal" sampai "angka_akhir"
      ```
   - Contoh:
      ```earl
      atur :angka: = dari "1" sampai "5"
      ```
      Ini akan menghasilkan `"dari 1 sampai 5"`.
2. Membangun Urutan Huruf (Naik):
   - Urutan huruf dibuat dengan cara yang sama seperti angka, namun menggunakan huruf sebagai nilai.
   - Sintaks:
     ```bash
     atur :nama_variabel: = dari "huruf_awal" sampai "huruf_akhir"
      ```
   - Contoh:
     ```earl
     atur :huruf: = dari "a" sampai "e"
     ```
     Ini akan menghasilkan `"dari a sampai e"`.
3. Membangun Urutan Mundur (Angka):
   - Modul ini juga mendukung urutan mundur dengan angka, di mana angka akan diurutkan dari angka yang lebih besar ke angka yang lebih kecil.
   - Sintaks:
     ```bash
     atur :nama_variabel: = dari "angka_awal" sampai "angka_akhir" mundur
      ```
   - Contoh:
     ```earl
     atur :angka_mundur: = dari "10" sampai "1" mundur
     ```
   Ini akan menghasilkan `"dari 10 sampai 1 mundur"`.
4. Membangun Urutan Mundur (Huruf):
   - Juga bisa membuat urutan mundur dengan huruf.
   - Sintaks:
     ```bash
     atur :nama_variabel: = dari "huruf_awal" sampai "huruf_akhir" mundur
     ```
   - Contoh:
     ```earl
     atur :huruf_mundur: = dari "z" sampai "a" mundur
     ```
     Ini akan menghasilkan `"dari z sampai a mundur"`
 
## Catatan:
- Urutan angka atau huruf yang dihasilkan disimpan dalam memori menggunakan nama variabel yang ditentukan (misalnya, `:angka:`, `:huruf:`).
- Bisa menggunakan `tampilkan` untuk melihat nilai dari variabel yang sudah diatur menggunakan `membangun`.
- Modul ini mendukung pembuatan urutan angka atau huruf, baik naik maupun mundur.

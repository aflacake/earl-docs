# `ambil`
Fungsi `ambil` bertugas untuk mengambil nilai dari suatu sumber dan menyimpannya pada variabel target di `memory`. Nilai tersebut bisa berasal dari variabel lain, objek yang terdapat di dalam `memory`, atau atribut dari instance kelas.

## Format perintah
```pearl
ambil :targetVar: dari :sumber:
```
- `:targetVar:`: Nama variabel target tempat nilai akan disalin di dalam `memory`.
- `sumber`: Sumber nilai yang bisa berupa:
   - Variabel lain yang disimpan di dalam memory (misalnya `:varName:`).
   - Nilai yang ada dalam sebuah objek atau instance kelas (misalnya `instanceName.atribut`).
   - Nilai langsung yang ada di `memory` (misalnya nama variabel).

## Langkah-langkah Pengecekan dan Pemrosesan
1. Validasi Format Perintah:
   - Fungsi memeriksa apakah perintah mengikuti format yang benar: `ambil :var: dari sumber`
   - Jika format salah, akan muncul pesan kesalahan
2. Pengambilan Nilai:
   - Jika sumber adalah sebuah instance kelas dengan atribut:
     - Misalnya `:instanceName: :atributName:`.
     - Periksa apakah `instanceName` ada di dalam `memory`, dan apakah itu merupakan objek yang dimiliki tipe kelas.
     - Periksa apakah atribut (`atributName`) ada didalam kelas tersebut.
     - Jika semua valid, ambil nilai dari atribut dan simpan ke dalam variabel target.
   - Jika sumber adalah varibel:
     - Periksa apakah nilai varibel (misalnya `:varName:` ada di dalam `memory`.
     - Jika variabel adalah objek (bukan daftar atau _array_) dan ada kunci tambahan yang diberikan (mislanya, tokens[4]), periksa apakah kunci tersebut ada dalam objek tersebut.
     - Jika tidak ada kunci atau variabel, muncul tampilan pesan kesalahan.
3. Penyimpanan Nilai:
   - Nilai yang diambil dari sumber disalin ke dalam variabel target yang di tentukan di `memory`.
4. Pesan Log:
   - Fungsi mencetak pesan di konsol yang menunjukkan variabel target yang diisi dari sumber yang ditentukan beserta nilainya.
  
## Contoh Penggunaan
1. Mengambil Nilai dari Variabel Lain:
   ```pearl
   ambil :x: dari :y:
   ```
   ini akan mengambil nilai yang ada pada `:y:` dan menyimpannya ke dala `:x:`.

2. Mengambil Nilai dari Atribut dalam Instance Kelas:
   Misalnya, jika `memory` berisi objek `person` yang memiliki atribut `name`:
   ```pearl
   ambil :personNmae: dari :person.name:
   ```
   Ini akan mengambil nilai dari atribut `name` di dalam objek `person` dan menyimpannya ke dalam variabel `:personName:`.

3. Mengambil Nilai dari Objek:
   Jika sebuah objek disimpan di `memory` dan kamu ingin mengakses nilai dari kunci tertentu, misalnya:
   ```pearl
   ambil :address: dari :user.address.street:
   ```
   Jika `user` adalah sebuah objek dan memiliki atribut `address` yang memiliki kunci `street`, maka nilai dari `street` akan disalin ke dalam `:address:`.

4. Mengambil Nilai Langsung dari `memory`:
   ```pearl
   ambil :z: dari :a:
   ```
   Ini akan menyalin nilai dari variabel `:a:` yang sudah ada didalam memory ke dalam `:z:`.

## Pesan Kesalahan yang Dapat Ditemui:
- Format salah:
  ```bash
  Format salah. Gunakan: ambil :var: dari sumber
  ```

- Instance atau Kelas Tidak Ditemukan:
  ```bash
  Instance 'namaInstance' tidak ditemukan.
  ```

- Kelas Tidak Valid:
  ```bash
  'namaKelas' buka kelas yang valid.
  ```

- Atribut Tidak Ditemukan di dalam Kelas:
  ```bash
  Atribut 'namaAtribut' tidak didefinisikan di kelas 'namaKelas'.
  ```

- Variabel Tidak Ditemukan:
  ```bash
  Variabel :namaVar: tidak ditemukan.
  ```

- Kunci Tidak Ditemukan di dalam Objek
  ```bash
  Kunci 'namaKunci' tidak ditemukan di dikta 'namaVar'.
  ```

Catatan:
- Jika `sumber` adalah objek dan perintah mengakses kunci tertentu, pastikan bahwa kunci tersebut ada di dalam objek. Jika tidak, pesan kesalahan akan muncul.
- Fungsi ini juga menangani sumber yang berupa instance dari kelas dan akses ke atribut di dalamnya.

Dokumentasi ini diharapkan dapat memberikan gambaran yang jelas tentang bagaimana modul `ambil.js` bekerja dan bagaimana cara menggunakannya di dalam skrip Pearl.

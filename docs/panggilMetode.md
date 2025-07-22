# `panggilMetode`
Modul ini memungkinkan pengguna untuk memanggil metode pada _instance_ objek yang merupakan bagian dari kelas yang sudah didefinisikan. Ketika metode dipanggil, kode dari metode tersebut akan dieksekusi dengan konteks yang tepat. Metode yang dipanggil akan dijalankan di dalam konteks _instance_ yang diberikan, memungkinkan akses ke atribut atau metode lainnya yang ada di dalam _instance_ tersebut.

## Fungsi Utama:
- **Memanggil metode** pada _instance_ kelas yang sudah didefinisikan.
- **Mengeksekusi kode** metode dalam konteks _instance_ yang dipilih, memungkinkan akses ke data dan fungsi dari objek tersebut.

1. `panggilMetode(tokens, modules, context)`
   Fungsi utama dalam modul ini yang digunakan untuk memanggil metode pada _instance_ objek.
   Argumen:
   - `tokens`, array yang berisi token perintah. Token pertama adalah nama _instance_, token kedua adalah nama metode yang akan dipanggil.
     - Contoh token: `['panggilMetode', ':myInstance:', 'myMethod']`.
   - `modules`, modul-modul yang dimuat untuk dapat digunakan dalam pemrosesan kode.
   - `context`, konteks yang berisi informasi terkait eksekusi kode, termasuk variabel dan lingkup eksekusi.
  
   Cara Kerja:
   1. Nama Instance: Fungsi pertama-tama mencari _instance_ objek yang ditentukan dalam `memory`. Nama _instance_ biasanya diawali dengan tanda titik dua (`:`).
   2. Metode Instance: Setelah menemukan _instance_, modul ini akan mencari apakah metode yang diminta ada di dalam kelas yang diacu oleh _instance_ tersebut. Metode dicari dalam objek `metode` yang ada pada kelas tersebut.
   3. Eksekusi Metode: Jika metode ditemukan, kode dari metode tersebut akan dieksekusi dalam konteks baru dengan variabel `ini` yang mengacu pada _instance_ yang dimaksud. Proses eksekusi ini menggunakan REPL (`runEarl`), dan variabel instance akan tersedia untuk digunakan dalam metode tersebut.

  Contoh Penggunaan:
  Jika memiliki kelas `Person` dengan metode `greet`, dapat memanggil metode `greet` pada _instance_ `person1` seperti berikut:
  ```earl
  panggilMetode :person1: greet
  ```

2. Contoh Kasus:
   Misalkan memiliki kelas `Person` dengan struktur berikut:
   ```earl
   kelas :Person:
    atribut :nama:
    metode greet:
        tampilkan :nama: "Hello!"
    ```
   Kemudian buat instance `person1`:
   ```earl
   atur :person1: = :Person:
   atur :person1:.nama: = "John"
   ```
   Sekarang, bisa memanggil metode `greet` pada `person1`:
   ```earl
   panggilMetode :person1: greet
   ```
   Keluaran:
   ```bash
   Hello! "John"
   ```

## Catatan Penting:
- Jika _instance_ atau metode tidak ditemukan, akan muncul pesan error yang sesuai.
- Pastikan bahwa _instance_ sudah didefinisikan sebelumnya dan metode yang diminta ada di dalam kelas yang tepat.
   

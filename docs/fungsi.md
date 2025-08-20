# `fungsi`
Modul `fungsi` memungkinkan pengguna untuk mendefinisikan fungsi buatan sendiri di bahasa Earl, lengkap dengan parameter dan isi kode yang dapat dipanggil ulang.

## Dua Mode:
- Mode skrip (non-REPL), menggunakan tanda kurung `(` dan `)` untuk membuka atau tutup blok fungsi.
- Mode REPL, harus menggunakan tanda `selesai` sebagai akhir blok fungsi.

## Format Penulisan:
```earl
fungsi namaFungsi(param1, param2)
  tampilkan :param1:
  tampilkan :param2:
selesai
```

## Contoh Penggunaan:
```earl
fungsi sapa(nama)
  tampilkan "Halo," :nama:
selesai

sapa "Earl"
```
Keluaran:
```bash
Halo, Earl
```


## Cara Memanggil Fungsi:
```earl
namaFungsi "Halo" "Dunia"
```

## Cara Kerja:
1. Deklarasi Fungsi:
   - Didefinisikan dengan keyword `fungsi`.
   - Nama fungsi diikuti parameter dalam tanda kurung.
   - Setelah itu harus ada tanda kurung `(` sebagai pembuka blok kode.
2. Isi Fungsi:
   - Baris-baris perintah di dalam blok hingga kurung tutup `)`.
3. Penyimpanan:
   - AST fungsi disimpan dalam `memory.__fungsi_ast__`.
   - Fungsi disimpan di _scope_ saat ini dan juga `modules` jika di _global scope_.
4. Pemanggilan:
   - Saat fungsi dipanggil, argumen dipetakan ke parameter.
   - Fungsi dijalankan dalam konteks lingkup lokal baru (_local scope_).

## Catatan:
- Fungsi mendukung _nested scope_ dan dapat menggunakan variabel lokal.
- Tokenisasi menggunakan `modules.tokenize`.
- Fungsi bisa akses modul global dan fungsi lokal.
- Return value disimpan di `localContext.return`.


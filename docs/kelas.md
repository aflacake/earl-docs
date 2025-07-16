# `kelas`
Modul ini digunakan untuk mendefinisikan kelas dalam bahasa Earl, termasuk atribut, metode, dan pewarisan.

## Format Umum:
```earl
kelas :NamaKelas:
    atribut nama1 nama2 ...
    metode :namaMetode:
        # isi perintah metode
    selesai
selesai
```

### Pewarisan:
Gunakan mewarisi untuk membuat kelas turunan:
```earl
kelas :AnakKelas: mewarisi :IndukKelas:
    atribut tambahan1
    metode :tambahMetode:
        tampilkan "Metode dari anak"
    selesai
selesai
```

## Yang Dilakukan Modul Ini:
- Menyimpan struktur kelas ke dalam `memory`, dengan format:
  ```json
  {
    "NamaKelas": {
      "__tipe": "kelas",
      "mewarisi": "IndukKelas" (opsional),
      "atribut": [...],
      "instance": { "__tipe": "NamaKelas", ... },
      "pengaturan": {},
      "metode": {
        "namaMetode": "kode metode"
      }
    }
  }
  ```
- Jika `mewarisi` digunakan:
  - Atribut, instance, dan metode dari kelas induk akan diwarisi otomatis.

## Validasi dan Kesalahan Umum:
- Nama kelas tidak boleh kosong.
- Nama metode harus ditulis seperti `:nama:`.
- Jika `mewarisi` digunakan, kelas induk harus sudah didefinisikan sebelumnya.
- Perintah lain selain `atribut` atau `metode` akan diabaikan dan muncul peringatan.

## Contoh Lengkap:
```earl
kelas :Hewan:
    atribut nama suara
    metode :bersuara:
        tampilkan :ini.suara:
    selesai
selesai

kelas :Anjing: mewarisi :Hewan:
    metode :berlari:
        tampilkan "Anjing berlari!"
    selesai
selesai
``

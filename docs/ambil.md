# `ambil`
Memindahkan nilai dari satu variabel ke variabel lain dalam konteks program yang sedang berjalan.

## Format perintah
```earl
ambil :namaTujuan: dari :namaSumber:
```

### Penjelasan:
- `:namaTujuan:`, variabel yang ingin diisi nilainya.
- `:namaSumber:`, variabel sumber tempat nilai diambil.
- Keduanya harus ditulis dengan format `:nama:` (pakai tanda tiitk dua diapit diawal dan akhir).

## Contoh:
Jika sebelumnya ada:
```earl
isi :angka: dengan 42
```

Lalu:
```earl
ambil :salinan: dari :angka:
```
Maka variabel `:salinan:` berisi `42`.

## Validasi dan Error:
Akan muncul kesalahan jika:
- Format salah (kurang `dari` atau variabel tidak memakai `:...:`).
- Variabel sumber tidak ditemukan di konteks saat ini.

## Kegunaan:
- Mempermudah penyalinan nilai antar variabel tanpa menulis ulang nilainya.
- Berguna dalam blok fungsi, perulangan, atau kondisi untuk dublikasi data.

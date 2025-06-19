Modul ini memungkinkan Anda **mengambil** atau **mengirim data** dari dan ke server API menggunakan HTTPS.

## `ambildata`
Sintaks:
```pearl
ambildata "https://url-api.com" ke :nama_variabel: [opsi]
```

Penjelasan:
- `"https://..."`, Alamat URL API.
- `ke :nama_variabel:`, Menyimpan hasil respon ke variabel.
- [opsi]:
  - `bataswaktu 5000`, Maksimal waktu tunggu (dalam milidetik).
  - `coba 3`, Jumlah percobaan ulang jika gagal.
  - `header "Authorization: Bearer token"`, Header tambahan.
 
### Contoh:
```pearl
ambildata "https://api.example.com/data" ke :respon: coba 2 bataswaktu 3000
```

## `kirimdata`
Sintaks:
```pearl
kirimdata "https://url-api.com" :data: [opsi] ke :nama_variabel:
```

Penjelasan:
- `:data:`, Variabel yang berisi objek data untuk dikirim.
- `sebagai "json"`, Kirim sebagai JSON (default: form-url-encoded).
- `method POST`, Metode HTTP (bisa juga `PUT`, `PATCH`, dll).
- `upload "file.jpg" nama_isian`, Upload file bersamaan.
- `ke :nama_variabel:`, Menyimpan respon ke variabel.

### Contoh:
Kirim data sebagai JSON:
```pearl
kirimdata "https://api.example.com/post" :dataku: sebagai "json" method POST ke :respon:
```

Upload file:
```pearl
kirimdata "https://api.example.com/upload" :info: upload "gambar.png" file ke :respon:
```

Tips:
- Selalu gunakan `https://` di URL.
- Variabel seperti `:dataku:` harus sudah berisi objek (misalnya: `{ nama: "Ali" }`).
- Jika tidak pakai `ke :nama_variabel`, respon tetap akan ditampilkan ke konsol.

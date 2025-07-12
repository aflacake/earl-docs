# `dikta`
Modul dikta digunakan untuk membuat dan menyimpan struktur data mirip objek atau _dictionary_ (disebut "dikta") dalam memori. Kamu bisa membuat dikta sederhana, bertingkat (nested), atau bahkan otomatis dari alfabet.

## Sintaks dan Penggunaan:
1. Membuat dikta dari pasangan kunci-nilai
   ```earl
   dikta :nama_dikta: kunci1 nilai1 kunci2 nilai2 ...
   ```
   Contoh:
   ```bash
   dikta :huruf: a A b B c C
   ```
   Akan menghasilkan:
   ```bash
   {
     "a": "A",
     "b": "B",
     "c": "C"
   }
   ```
2. Membuat dikta alfabet otomatis
   ```earl
   dikta :nama_dikta:
   ```
   Contoh:
   ```earl
   dikta :huruf:
   ```
   Akan menghasilkan:
   ```bash
   {
     "a": "A",
     "b": "B",
     ...
     "z": "Z"
   }
   ```
3. Dikta bertingkat (_nested dikta_)
   Gunakan awal `{` dan akhir `}` untuk membuat dikta di dalam dikta.
   Contoh:
   ```earl
   dikta :data: nama "andi" alamat { kota "jakarta" kodepos "12345" }
   ```
   Hasil:
   ```bash
   {
   "nama": "andi",
   "alamat": {
     "kota": "jakarta",
     "kodepos": "12345"
    }
   }
   ```

## Contoh Lengkap:
```earl
dikta :profil: nama "budi" umur 30 alamat { kota "bandung" kodepos "40123" }

tampilkan :profil:nama:
tampilkan :profil:umur:
tampilkan :profil:alamat:
tampilkan :profil:alamat:kota:
tampilkan :profil:alamat:kodepos:
```

## Catatan:
- Nama dikta harus dalam format `:nama:`.
- Gunakan tanda kutip (`"`) jika nilai adalah teks yang mengandung spasi.
- Untuk dikta bertingkat, pastikan `{...}` ditutup dengan benar.
- Jika format salah, akan muncul pesan error yang membantu pengguna.



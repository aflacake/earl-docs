# `dikta`
`dikta` adalah perintah di Earl untuk membuat kamus (_dictionary_), yaitu struktur data berisi pasangan **kunci dan nilai**.

## Contoh Sederhana
```earl
dikta :huruf: a A b B c C
```
Hasil:
```bash
memory['huruf'] = {
  a: "A",
  b: "B",
  c: "C",
}
```

# Format Dasar
```txt
dikta :nama: kunci1 nilai1 kunci2 nilai2 ...
```
Penjelasan:
- `:nama:`, Nama kamus di memori
- `kunci`, Teks yang jadi kunci
- `nilai`, Isi dari kunci tersebut

# Contoh kamus Alfabet Otomatis
```earl
dikta :huruf:
```
Ini akan membuat huruf a-Z dan A-Z secara otomatis:
```bash
memory['huruf'] = {
   a: "A", b: "B", c: "C", ... z: "Z"
};
```

 # Kamus Bersarang (_Nested_)
```earl
dikta :data: nama { depan Ani belakang Budi } umur 20
```

Hasil:
```bash
memory['data'] = {
  nama: {
    depan: "Ani",
    belakang: "Budi"
  },
  umur: "20"
}
```

Catatan Penting:
- Nama harus dalam format `:nama:`.
- Tidak boleh ada kunci tanpa nilai.
- Gunakan `{}` untuk membuat struktur bersarang.

Tips:
- Gunakan `tampilkan :nama:` untuk melihat isi kamus
- Bisa digabung dengan perintah lain seperti `ambil`, `atur`, dan `jika`

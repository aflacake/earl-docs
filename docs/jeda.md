# `jeda`
Menghentikan eksekusi selama waktu tertentu.

## Format Perintah:
```bash
jeda <angka> <satuan>
```

### Parameter:
- `angka`: waktu jeda, harus berupa angka positif.
- `satuan`: `md` (milidetik), `d` (detik), dan `m` (menit).

## Contoh:
```earl
jeda 500 md
jeda 2 d
jeda 1 m
```

## Catatan:
- `jeda` akan menunda eksekusi selama waktu yang diberikan.
- Jika format atau satuan salah, akan menampilkan error.

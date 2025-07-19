# `kembalikan`
Modul ini digunakan untuk mengembalikan nilai dari sebuah fungsi atau blok kode dalam bahasa Earl.

## Fungsi Utama:
### Deskripsi:
- Menghentikan eksekusi fungsi atau block saat ini dan mengirimkan nilai hasil kembali ke pemanggil.
- Bisa mengembalikan satu nilai atau hasil evaluasi ekspresi matematika sederhana.

## Cara Kerja:
- Jika tidak ada nilai yang diberikan, mengembalikan `undefined`.
- Jika ada satu token, nilai token tersebut akan dikembalikan.
- Jika ada beberapa token, modul akan mencoba menggabungkan token menjadi ekspresi matematika dan menghitungnya, lalu mengembalikan hasilnya.
- Jika evaluasi gagal, mengembalikan ekspresi dalam bentuk string.

## Contoh Penggunaan:
```earl
fungsi hitung(x, y)
(
  kembalikan x + y * 2
)
-- Keluaran: 11 --
tampilkan hitung(3, 4)
```
```earl
fungsi kosong()
(
  kembalikan
)
-- Keluaran: undefined --
tampilkan kosong()
```

## Parameter Fungsi:
- `tokens`: array token perintah, misalnya `['kembalikan', 'x', '+', '1']`.
- `modules`: objek modul lain yang tersedia (misal untuk resolve token).
- `context`: konteks eksekusi yang menyimpan hasil return dan status berhenti eksekusi.

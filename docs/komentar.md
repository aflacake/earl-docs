# Komentar
1. Komentar Satu Baris: `-- komentar --`
   Contoh:
   ```pearl
   -- Ini adalah komentar satu baris --
   ```
   Ciri-ciri:
   - Baris harus **dimulai dan diakhiri dengan** `--`.
   - Isi di antaranya akan **sepenuhnya diabaikan** oleh interpreter. Artinya interpreter tidak akan mengolah baris ini, ia langsung "lompat" ke baris berikutnya.
   - Tidak boleh ada kode lain di baris tersebut.
2. Komentar Multi-baris: `/--...--/`
   Contoh:
   ```earl
   /--
   Ini komentar panjang
   yang bisa terdiri dari
   beberapa baris
   --/
   ```
   Ciri-ciri:
   - Komentar harus **dimulai dengan** `/--` di satu baris.
   - Berakhir dengan `--/` di baris lain.
   - Semua baris di antara `/--` dan `--/` akan diabaikan. Artinya saat interpreter menemukan `/--`, dia mengaktifkan mode "jangan proses baris-baris berikutnya",  ketika menemukan `--/`, dia menonaktifkan mode itu dan lanjut lagi parsing baris berikutnya. Semua baris ditengahnya diabaikan total.
   - Berguna untuk menyembunyikan blok besar kode atau catatan.

Kelebihan desain ini:
- Lebih mudah di-parse, konsisten seperti bahasa minimalis.
- Membedakan Pearl dari bahasa lain yang pakai `#`, `//`, dll.

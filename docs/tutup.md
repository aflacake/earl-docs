# `tutup`
Fungsi: Tutup file yang sedang dibuka dan reset memori.

Format:
```earl
tutup
```

Keluaran:
```bash
Memori direset (file ditutup).
```

Contoh Interaksi Lengkap Earl:
```bash
earl>simpan :pesan: "Halo dunia"
Variabel 'pesan' disimpan dengan isi: "Halo dunia"

earl>baca :pesan:
"Halo dunia"

earl>buka :fileData: dari "contoh.txt"
File 'contoh.txt' dibuka dan disimpan ke variabel 'fileData'

earl>baca :fileData:
Ini adalah isi contoh.txt
Baris kedua teks.

earl>tutup
Memori direset (file ditutup).

earl>baca :pesan:
Variabel 'pesan' tidak ditemukan.
```

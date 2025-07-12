# `berhenti`
Modul `berhenti` digunakan untuk menghentikan sementara eksekusi program Earl dan menunggu pengguna menekan tombol **ENTER** untuk melanjutkan.

## Cara Kerja:
- Saat perintah `berhenti` dijalankan, program akan berhenti sejenak.
- Pesan **Diberhentikan. Tekan ENTER untuk melanjutkan...** akan ditampilkan saat diproses.
- Program akan menunggu pegguna sampai menekan tombol **ENTER**.
- Setelah itu, eksekusi program akan dilanjutkan.

## Contoh Penggunaan:
```earl
tampilkan "Mulai"
berhenti
tampilkan "Lanjut"
```
Keluaran:
```bash
Mulai
Diberhentikan. Tekan ENTER untuk melanjutkan ...
[tekan ENTER]
Lanjut
```

### Catatan:
- Perintah ini bersifat **asynchronous**, artinya program menunggu input pengguna tanpa membuat komputer membeku.
- Sangat berguna saat pengguna ingin memberi waktu untuk keluaran sebelum melanjutkan proses berikutnya

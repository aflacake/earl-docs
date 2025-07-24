# `ulangiKontrol`
## Fungsi Utama:
```bash
fungsi ulangiKontrol(tokens, modules, context)
```
Cara kerja:
- Kalau `tokens` berisi `berhenti`, maka `context.berhenti` di-set `true` supaya perulangan di modul `ulangi` berhenti.
- Kalau `tokens` berisi `lanjutkan`, maka `context.lanjutkan` di-set `true` supaya perulangan lompat ke iterasi berikutnya.

## Contoh pakai
```earl
ulangi 10
    jika index == 5 maka
        berhenti
    selesai
    tampilkan "Iterasi ke-" :index:
selesai
```
Pada contoh di atas, perulangan berhenti saat `index` sama dengan 5.

## Ringkasan:
`ulangiKontrol`, fungsinya mengatur berhenti atau lanjutkan, variabel lokalnya tidak ada, perintah kontrol set `context.berhenti = true` atau `context.lanjutkan = true`.

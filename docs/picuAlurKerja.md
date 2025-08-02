# `picuAlurKerja`
Memicu atau menjalankan **GitHub Actions Workflow** secara otomatis dari dalam kode Earl menggunakan GitHub REST API.

## Persyaratan:
Harus **ada token GitHub** di _environment variable_: 
```bash
GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxxxx
```
Cara menambahkan:
1. Buat file `.env` (opsional jika tidak langsung di _environment_).
2. Tambahkan baris:
   ```
   GITHUB_TOKEN=ghp_...
   ```
Atau ekspor langsung di terminal sebelum menjalankan:
- Linux atau macOS:
   ```bash
   export GITHUB_TOKEN=ghp_...
   ```
- Windows:
   ```bash
   set GITHUB_TOKEN=ghp_...
   ```

## Format Penggunaan:
```bash
picuAlurKerja pemilik/repo nama_alurkerja.yml [ref]
```
- `pemilik/repo`, nama pemilik dan nama repositori GitHub.
  Contoh: `johndoe/proyek`
- `nama_alurkerja.yml`, nama file alur kerja di folder`.github/workflows/`
- `[ref]` nama _branch_ atau tag. Bawaan: `main`.

### Contoh:
```earl
picuAlurKerja johndoe/proyek deploy.yml main
```
Perintah di atas akan menjalankan _workflow_ `deploy.yml` di repo `johndoe/proyek` pada _branch_ `main`.

## Catatan Kesalahan Umum:
- `Bad credentials`, token GitHub salah atau tidak diatur.

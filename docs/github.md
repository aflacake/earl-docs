# `github`
Modul ini menyediakan fungsi untuk **memicu (_trigger_) alur kerja GitHub Actions** pada _repository_ tertentu langsung dari skrip Earl.

## Fungsi Utama:
`picuAlurKerja(tokens, modules, context)`
Memicu alur kerja GitHub Actions di repository yang ditentukan.

## Cara Pemakaian di Skrip Earl:
```bash
picuAlurKerja "pemilik/repo" "nama_alurkerja.yml" "ref"
```
- `pemilik/repo`
   Nama pemilik dan _repository_ GitHub, misalnya: `"aflacake/earl-pengujian"`.
- `nama_alurkerja.yml`
  Nama file alur kerja yang ada di `.github/workflows/`, misalnya: `"deploy.yml"`.
- `ref` (opsional)
  _Branch_ atau tag yang akan dipicu, bawaannya `"main"` jika tidak diisi.

### Contoh:
```earl
picuAlurKerja "aflacake/earl-pengujian" "deploy.yml" "main"
```
Ini akan memicu alur kerja `deploy.yml` pada _branch_ `main` di repository `aflacake/earl-pengujian`.

## Error Handling:
- Jika token atau parameter kurang lengkap, modul akan memberi pesan error dan tidak memicu _workflow_.
- Jika gagal memicu alur kerja, akan menampilkan pesan error dari API GitHub.

## Persyaratan:
- Harus mempunyai **GitHub Personal Access Token** dengan izin `workflow` dan `repo`.
- Token harus disimpan di variabel lingkungan (_environment variable_).

Di terminal Linux atau macOS:
```bash
export GITHUB_TOKEN="token_anda_di_sini"
```

Di terminal Windows:
```bash
set GITHUB_TOKEN=token_anda_di_sini
```

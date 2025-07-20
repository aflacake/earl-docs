# `matematika`
Modul `matematika` menyediakan perintah untuk melakukan operasi matematika sederhana hingga lanjutan, dengan fitur menyimpan hasil ke variabel.

## Cara Penggunaan:
Format umum:
```bash
matematika [:nama_variabel:] operasi [argumen...]
```
- `:nama_variabel:` (_opsional_)
  Menyimpan hasil operasi ke variabel di memory dengan nama `nama_variabel`.
- `operasi`
  Nama operasi matematika (lihat daftar di bawah).
- `argumen`
  Angka atau variabel yang akan dihitung.

## Daftar Operasi yang Didukung:
| Operasi | Keterangan | Argumen |
| --- | --- | --- |
| `tambah` | Penjumlahan | 2 angka |
| `kurang` | Pengurangan | 2 angka |
| `kali` | Perkalian | 2 angka |
| `bagi` | Pembagian | 2 angka (pembagi ≠ 0) |
| `mod` | Modulus (sisa bagi) | 2 angka |
| `akar` | Akar kuadrat | 1 angka |
| `akarKubik` | Akar kubik | 1 angka |
| `akarKeN` | Akar pangkat n | 2 angka (nilai, pangkat) |
| `bulatkan` | Pembulatan ke bilangan bulat terdekat | 1 angka |
| `lantai` | Pembulatan ke bawah (floor) | 1 angka |
| `plafon` | Pembulatan ke atas (ceil) | 1 angka |
| `acak` | Angka acak dalam rentang | 2 angka (min, max) opsional |
| `mutlak` | Nilai mutlak (absolute) | 1 angka |
| `faktorial` | Faktorial (n!) | 1 angka positif |
| `log` | Logaritma natural (ln) | 1 angka > 0 |
| `log2` | Logaritma basis 2 | 1 angka > 0 |
| `log10` | Logaritma basis 10 | 1 angka > 0 |
| `sin` | Sinus (dalam radian) | 1 angka |
| `cos` | Kosinus (dalam radian) | 1 angka |
| `tan` | Tangen (dalam radian) | 1 angka |
| `sec` | Secan	1 | angka |
| `csc` | Kosekan | 1 angka |
| `cot` | Kotangen | 1 angka |
| `pi` | Konstanta π | Tidak perlu argumen |
| `derajatKeRadian` | Konversi derajat ke radian | 1 angka |
| `radianKeDerajat` | Konversi radian ke derajat | 1 angka |

## Contoh:
- Menampilkan hasil penjumlahan 3 + 4:
  ```earl
  matematika tambah 3 4
  ```
  Keluaran: `7`
- Menyimpan hasil perkalian 5 × 6 ke variabel `hasil`:
  ```earl
  matematika :hasil: kali 5 6
  ```
  Variabel `hasil` sekarang berisi `30`.
- Menghitung akar kuadrat 16:
  ```earl
  matematika akar 16
  ```
  Keluaran: `4`

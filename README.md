# Ekstraksi Nomor Telepon dengan Regex

Merapikan daftar kontak keluarga memakai regex Python: mengekstrak nomor
telepon dari 1000 baris phonebook yang formatnya berantakan, lalu
menormalisasi semuanya ke satu format standar.

Proyek ini adalah Module 1 dari kursus Applied Information Extraction in
Python (University of Michigan).

## Data

Folder `data` berisi `phonebook.txt`: 1000 baris dengan pola "Nama: nomor".
Nomornya ditulis dalam 6 format berbeda: kurung, tanda hubung, titik, spasi,
internasional (+1), dan polos (10 digit berurutan). Sebanyak 230 baris berisi
data rusak seperti angka pendek "68359" atau "229.62402682655153" yang bukan
nomor telepon.

## Yang dikerjakan

1.  Regex ekstraksi dengan digit boundary di kedua sisi, supaya tidak cocok
    sebagian pada angka rusak. Dari 1000 baris, 770 nomor valid berhasil
    diekstrak dan 230 baris rusak dilewati. Lihat
    `charts/02_valid_vs_rusak.png`.
2.  Distribusi format asli: internasional 117, spasi 135, kurung 119, titik
    140, tanda hubung 131, polos 128. Lihat
    `charts/01_distribusi_format.png`.
3.  Normalisasi ke format standar: kode area dalam kurung, lalu 3 digit,
    lalu tanda hubung, lalu 4 digit. Lihat
    `charts/04_contoh_normalisasi.png`.
4.  Sebaran 522 kode area unik, dengan 10 kode area tersering divisualkan.
    Lihat `charts/03_kode_area.png`.

## Cara menjalankan

```bash
python analyze_phones.py
```

Script ini memuat phonebook, mengekstrak nomor dengan regex, menyimpan chart
ke folder `charts`, dan menulis ringkasan angka ke `findings.json`.

## Tools

Python, regex (re), pandas, matplotlib.

+++
date = '2026-07-14T20:06:00+07:00'
draft = false
title = 'Mengganti Teks pada Semua File dengan Bash'
categories = ["Programming"]
+++
![bash](bash.jpg)

Suatu saat aku ingin menggabungkan isi seluruh file teks menjadi satu file teks baru. Hal ini terlaksana dengan menggunakan script *Python* berikut : 
```
import glob
import shutil

files = glob.glob("*.txt")

with open("gabungan.txt", "wb") as outfile:
    for fname in files:
        with open(fname, "rb") as infile:
            shutil.copyfileobj(infile, outfile)
```
Jika script di atas dijalankan pada suatu direktori maka isi semua file .txt yang ada pada direktori tersebut akan di-copy-paste ke file gabungan.txt.

Namun ternyata ada banyak frasa/kata yang harus dihilangkan atau diganti. Jika hal ini dilakukan hanya pada gabungan.txt tanpa melakukan penggantian pada setiap file .txt di direktori, tentunya hal ini akan sia-sia. Jadi aku harus mencari cara mengganti teks terlarang pada setiap file .txt tanpa membuka file satu per satu. Untungnya setelah browsing aku temukan script *Bash* berikut :
```
find . -type f -name ".txt" -exec sed -i 's/anjrot//g' {} +
```
dengan menjalankan script di atas, teks "anjrot" pada setiap file .txt dalam direktori ini, diganti "" (string kosong).

Bagaimana jika ingin menghilangkan karakter non-ASCII pada isi setiap file .txt? Begini script Bash-nya :
```
#!/bin/bash
for file in *.txt;do [ -f "$file" ] && LC_ALL=C tr -d '\200-\377' < "$file" > "${file}.tmp" && mv "${file}.tmp" "$file";done
```
simpan script di atas dengan ekstensi .sh kemudian jalankan di Terminal Linux atau Terminal Gygwin. Tuliskan dalam satu baris kode, jangan dipenggal!.

Cara mencari file yang mempunyai teks tertentu dengan *Bash*. 
Misal kita ingin mencari semua file .txt yang mempunyai teks *"Josjis"* di dalamnya. Berikut scriptnya :
```
find . -type f -name "*.txt" -exec grep -l "Josjis" {} +
```
+++
date = '2026-07-15T12:32:33+07:00'
draft = false
title = 'Manajemen File dengan Pathlib'
categories = ["Programming"]
+++
![python](python.png)
Manajemen file pada Python sebenarnya bisa dilakukan dengan beberapa modul. Salah satunya, kita bisa menggunakan modul **Pathlib**.
Pertama, impor dulu modul Pathlib :
```
from pathlib import Path
```
Misalnya kita punya file dengan path lengkap : *D:\folder_utama\sub_dir\myfile.jpg*. Bagaimana kita dapat menentukan path direktori, nama file, dan ekstensinya?.
Begini caranya :
```
path_asal = "D:\folder_utama\sub_dir\myfile.jpg"
mypath = Path(path_asal)

print(mypath.nama) # ini akan menghasilkan : nama file dan ekstensi (myfile.jpg)
print(mypath.stem) # ini akan menhasilkan nama file saja (myfile)
print(mypath.suffix) # memhasilkan ekstensi saja, dengan titik (.jpg)

```

Bagaimana jika ingin menggabungkan path dengan string?, gampang gunakan slash ("/") :
```
mydir = "data/2026/baru/"
myfile = "dir/123.txt"

newfile = f"{Path(mydir)}/{Path(myfile)}" 

print(newfile) # akan menghasilkan "data/2026/baru/dir/123.txt"
```

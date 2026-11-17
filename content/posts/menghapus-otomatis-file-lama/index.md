+++
date = '2026-11-17T13:29:31+07:00'
draft = true
title = 'Menghapus File berdasarkan Usia file di Hosting'
categories = ["Programming"]
+++

Bagi kalian para pemilik web, akan ada saatnya kalian merasa perlu untuk _membersihkan_ file-file yang sudah tidak digunakan namun masih berada pada direktori hosting.
Berikut ini script _Bash_ yang dapat digunakan untuk melakukan penghapusan file yang berusia lebih dari 7 (tujuh) hari :

```
find /home/username/direktoriku -maxdepth 1 -type f \( -name "backup_*" \) -mtime +7 -print -delete >> /home/username/direktoriku/log-hapus.log 2>&1
```

Script di atas akan melakukan menghapus file berawalan _backup__ yang berusia lebih dari 7 hari yang berada di _/home/username/direktoriku_.
Daftar file yang dihapus akan dicantumkan pada _/home/username/direktoriku/log-hapus.log_.

Pastikan kode di atas ditulis dalam **1 (satu) baris**.

Otomatis yang kumaksud di sini, tentunya jika script tadi didaftarkan dalam _Cron Job_ di hosting.

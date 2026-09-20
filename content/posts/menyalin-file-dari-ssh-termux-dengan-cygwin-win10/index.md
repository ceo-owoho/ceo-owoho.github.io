+++
date = '2026-09-20T22:00:30+07:00'
draft = false
title = 'Menyalin File dari SSH Termux dengan Cygwin pada Windows 10'
categories = ["Programming"]
+++

![termux-ssh](termux.jpg)

Pernah suatu ketika aku ingin memindahkan banyak file dari Hapeku ke Laptop namun banyak file yang berukuran besar (biasanya > 10 MB) menjadi _corupt_ saat diakses di Laptop. Hal yang sama terjadi jika aku salin ke PC. Hingga akhirnya aku menemukan solusinya dengan menggunakan SSH Termux untuk kemudian diakses dan disalin dari Laptop/PC Windows dengan menggunakan _command_ **scp** pada aplikasi _Windows PowerShell_ dengan pola :

```scp -P 8022 -c aes128-ctr [user_ssh_termux]@[ip_ssh_termux]:[alamat_file_di_hape]/[file_yang_ingin_dicopy] "[direkori_di_windows]"```

misal :

```scp -P 8022 -c aes128-ctr u0_u212@123.456.7.8:/data/data/com.termux/files/home/storage/downloads/Kisah_Cinta_Di_Kota_Kecil.mp3 "D:\lagu\"```

Namun ternyata, sintaks dengan _scp_ ini sering terkendala pada PC yang menggunakan _WIFI dongle USB_. Ya, saat di laptop script di atas berjalan dengan lancarnya, namun saat dijalankan di PC dengan WIFI dongle, sering kali proses salin file terhenti dan error, sehingga harus mengulang dari awal. 

Nah, ternyata ada untungnya juga meng-install _Dola AI_. Dari aplikasi AI ini aku menemukan solusi dari kendala di atas yaitu menggunakan _command_ **rsync** dan menjalankan pada **cygwin** yang telah aku install sejak lama. Jadi polanya adalah :

```rsync -avzP -e "ssh -p 8022 -o ServerAliveInterval=15 -o ServerAliveCountMax=3" [user_ssh_termux]@[ip_ssh_termux]:[alamat_file_di_hape]/[file_yang_ingin_dicopy] "[direkori_di_windows_dengan_format_cygwin]"```

```rsync -avzP -e "ssh -p 8022 -o ServerAliveInterval=15 -o ServerAliveCountMax=3" u0_u212@123.456.7.8:/data/data/com.termux/files/home/storage/downloads/Kisah_Cinta_Di_Kota_Kecil.mp3 "/cygdrive/d/lagu"```

Ingat direktori Windows ```D:\folderku\subfoldernya``` harus dituliskan di cygwin menjadi ```/cygdrive/d/folderku/subfoldernya```

Begitulah, kawan

+++
date = '2026-06-13T19:53:48+07:00'
draft = false
title = 'Prevent Git Asking Username and Password'
categories = ["Programming"]
+++
![github](github_image.jpg)

Entah sejak kapan aku tidak ingat, github mengubah mekanisme otentifikasi API-nya pada Terminal, baik itu dari *Command-prompt* Windows maupun dari *Terminal* Linux atau *Termux*. Hal ini mengakibatkan pengguna tidak bisa hanya mengandalkan username dan password akun Githubnya seperti sebelumnya.

Semenjak itu pula bila kita ingin menjalankan sintaks ```git remote add origin ... ``` atau ```git pull origin ... ``` maupun sintaks ```git push origin ... ```, pengguna akan diminta memasukkan username dan selanjutnya akan diminta memasukkan password. Nah, isian dari password ini tidak dapat lagi diisi dengan password akun github, melainkan harus mengisikan *token* yang dihasilkan pada menu *setting* akun Github. Token ini biasanya berupa satu baris karakter acak yang diawali oleh *string* ```ghp_[karakter acak]```. Hal ini tentu sangat merepotkan karena pengguna harus meng-*copy* karakter panjang dan acak tadi untuk kemudian mem-*paste*-kan ke layar *Command-prompt* atau *Terminal* mereka.

Untungnya ternyata ada sintaks yang bisa kita jalankan pada *Command-promt* atau *Terminal* agar isian token tadi dapat diingat oleh sistem dan kita tidak perlu berulang kali mengisikan username dan password. Sintaks tersebut adalah 

```git config --global credential.helper cache```

atau jika ingin membatasi durasi waktu simpan (misal : selama 1 jam), gunakan sintaks ini :

```git config credential.helper 'cache --timeout=3600'```






*sumber : https://sudogem.wordpress.com/*

*gambar dari : https://media.licdn.com/*

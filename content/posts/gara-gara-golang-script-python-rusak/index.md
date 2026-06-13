+++
date = '2026-06-13T21:37:12+07:00'
draft = false
title = 'Gara Gara Golang Script Python Rusak'
categories = ["Programming"]
+++
![golang](golang.png)

Akhir-akhir ini aku lagi tertarik untuk mempelajari **Golang**. Bagiku Golang ini versi moderen dari **Python**. Berbasis CLI juga, jadi mirip sekali dengan Python. Namun ada juga perbedaannya, yang paling aku rasa adalah **learning curve**nya terjal banget, beda dengan Python. 
Contoh paling sederhana, dalam penulisan package yang di-**import**. Jika misal aplikasi kita mengimpor package AAA, package BBB, dan package CCC, maka di Python kita bisa menulis :

``` 
    from AAA import A
    from BBB import B
    from CCC import C
```

pada Golang jadi begini :

```
  import (
    AAA
    BBB
    CCC
  )
```

maksudku : *tanpa tanda koma pemisah*

begitu pula penulisan **array** atau **slice** (view dari array). Misal ada variabel array **kota** dengan isi : "Ngawi", "Sragen", "Solo", "Jogja". Di python kita bisa menuliskan :

```kota = ["Ngawi", "Sragen", "Solo", "Jogja"]```

sangat sederhana dan mudah. Namun pada bahasa Golang, jadi begini :

``` kota := []string{"Ngawi", "Sragen", "Solo", "Jogja"}```

udah harus ada tanda kurung siku ```[]```, nentuin tipe datanya yaitu :```string``` dan anehnya pakai kurung kurawal lagi ```{}``` duh.... "*Sangat Jang...gal*" kata anakku...dan masih adalah kejanggalan yang lain.

Oke, kita kembali ke judul artikel ini. Karena utak-atik gathuk-ku mengoprek Golang ini, yang hingga membuatku pusing tujuh keliling, hingga dalam keputusasaanku, kuputuskan untuk menginstall ulang *Termux* yang sudah cukup lama aku pakai ini.

Setelah aku unistall, kembali aku menginstall versi Termux yang lebih baru dan berharap ini akan menjadikan proses belajar Golangku jauh lebih mudah. Eh, taunya dengan Termux baru ini ada paket inti dari aplikasi Pythonku tidak bisa berjalan. Nah, paniklah aku karena aplikasi ini akan mempengaruhi suksesnya program **Indonesia Emas 2445** *(pret....)*

Aku jadi sangat menyesal meng-uninstall Termux tadi tapi nasi telah menjadi bubur, langkah terbaik adalah menjadikan bubur ini enak dimakan dan itu artinya bagaimana mencari solusi error-nya aplikasi Pythonku tadi.

Kapan-kapan aku ceritain gimana kerepotanku mencari solusi ini.



*Gambar dari : https://miro.medium.com/*

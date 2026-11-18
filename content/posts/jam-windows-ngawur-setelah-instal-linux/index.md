+++
date = '2026-11-18T08:11:52+07:00'
draft = false
title = 'Mengatasi Jam Windows Error setelah Instal Linux'
categories = ["Programming"]
+++

![dual-boot](dual-boot.png)
Sebenarnya bukan error sih, tapi setting awal yang sudah tepat, berubah mengunakan zona waktu yang tidak tepat.

Jadi kejadian ini bermula ketika aku memutuskan untuk meng-install _Zorin OS_ pada laptop _Lenovo_ _T470s_ ku. Seperti PC dan laptopku yang lain, aku selalu tergoda untuk membuat _dual-boot_ dengan Linux.

- Laptop ASUS (_Windows 10 - Ubuntu_)
- PC Rakitan (_Windows 10 - Ubuntu_)
- Laptop HP 245 G7 (_Windows 11 - Linux-Lite_)

Kemudian aku ingin juga melakukan _dual-boot_ dengan _Lubuntu_ di laptop _Lenovo T470s_. Sebelumnya pada laptop ini sudah terinstal Windows 11, namun karena ada kendala saat instalasi _Lubuntu_ ini, aku kemudian beralih ke _Zorin OS_.

Kelebihan yang langsung terasa dari OS terakhir ini adalah tampilannya yang rapi dan sangat menarik. Bahkan sekilas mirip _Macintosh_.

Setelah instalasi OS baru ini selesai, setingan _time_ pada Windows 11 tiba-tiba berubah dan tidak akurat.

Solusinya, jalankan perintah berikut pada _Terminal Zorin_ :

```
timedatectl set-local-rtc 1 --adjust-system-clock
```

kemudian cek dengan :

```
timedatectl
```

pastikan terdapat baris:

```
RTC in local TZ: yes
```

Lanjut, balik ke Windows 11, pilih _settings_ -> _Time & Language_ -> _Date & time_ -> cek _Set time zone automatically_ dan cek _Set time automatically_

Done.

---
title: "Menggunakan 2 akun atau lebih di satu komputer"
date: 2020-07-06
toc: true
tags:
- Pemula
- Git
- Tips
draft: true
authors:
- Admin Inacode
featured_image: https://id.m.wikipedia.org/wiki/Berkas:Git-logo.svg
images: 
- https://id.m.wikipedia.org/wiki/Berkas:Git-logo.svg
---

Ada saatnya kita harus menggunakan dua atau lebih akun git yang berbeda di satu komputer. Contoh kasus: 1 akun git untuk pekerjaan personal, 1 akun lainnya khusus untuk pekerjaan kantor. Berikut cara sederhana untuk menggunakan 2 akun git berbeda

<!--more--> 

Yang pertama 

```
git config --list
```

maka akan tampil kurang lebih seperti ini:

```
user.name=Adi Setiawan
user.email=myemail@gmail.com
```

Ini berarti secara *default* akun git diatas yang akan digunakan setiap kamu melakukan perintah git apapun. Untuk menggunakan 




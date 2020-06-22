---
title: "Pengantar GunDB, Database Tanpa Server Terpusat"
date: 2020-06-21
tags:
- Menengah
- Database
draft: false
authors:
- Admin Inacode
---

> Bayangkan sebuah database yang bisa berjalan tanpa ada server terpusat, bisa tetap berfungsi normal ketika offline dan otomatis melakukan proses sinkronisasi tanpa developer pusing memikirkan *conflict resolution*, *zero maintenance*, nggak perlu devops, *sharding*, *master/slave*. Ada ? mari berkenalan dengan GunDB

<!--more--> 

{{< figure src="https://camo.githubusercontent.com/36a3253e47dad84b51c325ef5c2b532916a016e1/68747470733a2f2f636c6475702e636f6d2f5445793979476834356c2e737667" alt="gundb" >}}


## Tipe Topologi Jaringan Database

Sebelum kita mempelajari GunDB, secara garis besar ada tiga tipe topologi network yang digunakan dalam sebuah jaringan

{{< figure src="https://user-images.githubusercontent.com/194400/50022916-9c49cf80-ffd5-11e8-9931-c59378ae1a11.png" alt="gundb" >}}

* Centralized - Umumnya client/server database yang biasa kita gunakan menggunakan topologi centralized, dimana ada server terpusat dimana lokasi database tersebut berada. Untuk mengaksesnya, kita bisa menggunakan *native driver* atau API, contoh: MySQL, PostgreSQL, MongoDB, dsb.

* Decentralized - Konsep *master/slave* database umumnya menggunakan topologi ini, dimana ada *single source of truth* yang disebut *master* melakukan distribusi beban trafik ke masing-masing *slave*, misal: *slave* digunakan khusus operasi *read*, sedangkan operasi *write* menggunakan master.

* Distributed - GunDB salah satu jenis database open source yang masuk di kategori ini, karena tidak ada *single source of truth*, menggunakan konsep P2P atau *peer to peer* dimana proses sinkronisasi data dilakukan secara langsung antar pengguna tanpa perlu adanya server terpusat


## Apa itu GunDB ?

[GunDB](https://github.com/amark/gun) adalah *distributed database* berbasis open source, menggunakan javascript, yang dibuat oleh Mark Nadal yang bisa berjalan di browser tanpa server terpusat, artinya apa ?

> Tanpa server terpusat, GunDB memiliki karakteristik yang berbeda dengan tipikal client/server database lainnya. GunDB tidak memerlukan server pusat melainkan *peer to peer* atau *master to master*, dan bisa tetap berjalan di browser user bahkan ketika user offline.

GunDB lebih dari sekedar dabatase, lebih tepat disebut protokol, yang bisa di implentasikan di bahasa lain. GunDB menggunakan strukut data graph, serta *realtime* sync yang sangat cepat, menggunakan websocket dan webrtc dibelakangnya.


## Fitur GunDB ?

Selain proses sinkronisasi data yang cepat, Bisa berjalan secara offline, ada beberapa fitur spesifik yang dimiliki GunDB

* *Relay Peer*, berfungsi sebagai *relay* diantara masing-masing peer, dimana fungsi relay tidak lain adalah peer seperti biasa, yang membedakan umumnya peer server berjalan online 24 jam. 

* Penyimpanan data yang unik, GunDB secara pintar menyimpan data secara *sharding* hal ini diperlukan karena browser memiliki keterbatasan jumlah penyimpanan. Sehingga proses sinkronisasi tidak dilakukan secara menyeluruh melainkan sebagian atau *partial*

* *Builtin decentralized user authentication* GunDB memiliki fitur yang disebut yaitu *Security, Encryption, & Authorization* disingkat SEA, yaitu fitur *asymetric cryptography* berbasis *public key/private key*


## Penutup

Di artikel GunDB selanjutnya kita akan mengulik lebih dalam GunDB, membahas aplikasi yang tepat digunakan menggunakan GunDB serta nanti kita langsung belajar membuat sebuah aplikasi decentralized web based berbasis GunDB.

Tertarik lebih lanjut dengan GunDB ? silahkan cek [dokumentasi nya](https://gun.eco/docs/). Saat ini memang dokumentasinya terasa kurang lengkap, informasinya masih tersebar. Namun mudah-mudahan kedepan setelah penggunanya semakin banyak, dokumentasi dan userbase nya pun semakin banyak.


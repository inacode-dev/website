---
title: "Pengantar Blockchain"
date: 2020-07-01
toc: true
tags:
- Menengah
- Blockchain
draft: false
authors:
- Admin Inacode
featured_image: https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Blockchain_Illustration_4.jpg/640px-Blockchain_Illustration_4.jpg
---

Istilah blockchain saat ini sudah banyak terdengar dan banyak artikel yang membahas teknologi blockchain, tapi sayangnya masih banyak miskonsepsi mengenai teknologi blockchain. Di artikel ini, saya berusaha untuk menjelaskan dengan bahasa yang sederhana yang mudah-mudahan bisa dipahami oleh semua orang. Jika kamu sudah memahami konsep blockchain mungkin artikel ini bisa menjadi tambahan informasi yang sudah kamu pahami sebelumnya.

<!--more--> 

## Bitcoin != Blockchain

Sebelum kita membahas blockchain, masih banyak pemahaman yang salah mengenai blockchain, ini karena Bitcoin, *crypto currency* pertama yang paling populer sampai saat ini. Banyak yang salah beranggapan bahwa blockchain adalah bitcoin. 

> Bitcoin menggunakan teknologi blockchain dibelakangnya

Sebenarnya, bitcoin hanya salah satu dari implementasi teknologi blockchain yang sukses dan populer hingga saat ini. Bitcoin menggunakan hampir semua komponen yang dipersyaratkan sebagai sebuah teknologi blockchain yaitu:

* Hash & cryptography 
* Blocks
* P2P database
* Consensus

Kita akan membahas secara detail masing-masing komponen blockchain di artikel lain karena pembahasan komponen cukup panjang. Untuk saat ini cukup kita mengetahui konsep dasar dari komponen blockchain.

## Apa itu blockchain ?

Blockchain secara sederhana adalah sebuah kumpulan informasi yang disebut *block* yang saling terhubung dan terikat antara *block* satu dengan yang lain. Setiap *block* memiliki komponen *header*, yaitu informasi *metadata* yang berfungsi sebagai identitas sebuah *block* untuk menjamin bahwa data yang disimpan di *block* tersebut adalah valid. 

Sifat block adalah *immutable* artinya, ketika ada seseorang yang ingin merubah informasi yang disimpan di *block* maka sistem akan mengetahui bahwa *block* tersebut tidak valid dan sudah berubah. Untuk membuat *link* antar *block* maka diperlukan suatu cara agar masing-masing *block* terikat satu sama lain. Setiap *block* memiliki identitas unik yang disebut *hash* dimana *hash* dibuat dari beberapa komponen yaitu *hash* dari *block* sebelumnya, *nonce* yaitu angka random, dan informasi metadata lainnya.

*Hash* bersifat unik masing-masing *block*, maka ketika seseorang ingin merubah informasi di *block* maka *hash* menjadi tidak valid lagi. Inilah yang dimaksud dengan sifat *immutable* di dalam *block*

*block* menjadi komponen awal dari sebuah blockchain, dan karena sifatnya yg immutable, informasi yang di simpan di dalam *block* sangat berguna untuk menyimpan informasi penting yang tidak bisa dirubah, seperti: 

* Data transaksi keuangan
* Rekam medis pasien
* Sertifikat keabsahan

Dan banyak lagi.

*Block* saja tidak cukup untuk dibilang sebagai blockchain. Sekumpulan *block* tersebut membentuk sebuah rantai panjang yang disebut blockchain. Setelah menjadi blockchain, maka diperlukan media penyimpanan atau database. 

Database yang menyimpan informasi blockchain bersifat [*distributed*]({{< ref "gundb-database-tanpa-server" >}}). Tidak seperti database rekening kita di Bank yang terpusat di server Bank tersebut, informasi blockchain tersebar di setiap pengguna blockchain yang berpartisipasi di dalamnya. Setiap pengguna tersebut yang umumnya disebut dengan *node* saling terhubung satu sama lain agar informasi *block* masing-masing selalu *up-to-date*. Di bitcoin sendiri ada ribuan atau mungkin puluhan ribu node yang saling terhubung satu sama lain dimana masing-masing *node* memiliki *copy* database yang sama dan valid. 

Ketika ada satu *node* yang berusaha merubah sebuah informasi di suatu *block* tersebut, maka sebuah algoritma akan melakukan proses validasi terhadap *hash* dari *block* tersebut, jika ternyata tidak valid, maka *node* tersebut dianggap tidak valid pula. Algoritma verifikasi ini biasa disebut dengan *consensus*

Dengan *consensus* atau aturan bersama yang disepakati, sebuah blockchain akan tetap terjamin validitas dan keabsahan data yang disimpan. Di artikel selanjutnya kita akan membahas lebih detail tentang masing-masing komponen pembentuk blockchain.

## Keunggulan blockchain

Karena sifatnya yang *immutable* dan bisa dijamin validitas datanya, konsep blockchain sangat tepat digunakan di dunia keuangan atau perbankan yang sering disebut dengan *distributed ledger* seperti bitcoin, dimana tidak ada otoritas terpusat yang memiliki hak atas pencatatan transaksi dan penyimpanan data. Semua informasi tersebar di masing-masing *node* dan dijamin keabsahan datanya.

Selain industri keuangan dan perbankan, teknologi blockchain juga bisa di implentasikan ke dalam industri yang memerlukan keabsahan suatu informasi seperi: sertifikat tanah, rekam medis pasien, dan banyak lagi.

## Kekurangan blockchain

Dibalik kelebihan blockchain, tentu ada beberapa kekurangan yang saat ini masih menjadi kendala dalam penerapannya. Kekurangan utama dalam blockchain adalah waktu yang diperlukan dalam melakukan proses verifikasi sebuah *block* dan kemudian menyebarkan informasi *block* yang sudah terikat ke setiap *node*. Proses ini disebut *block time* yaitu lamanya sebuah *block* diproses dan di validasi. Bitcoin memerlukan waktu kurang lebih 10 menit, sedangkan Ethereum memerlukan waktu kurang lebih 20 detik.

Kekurangan ini yang masih menjadi kendala, tidak seperti perbankan tradisional yang bisa memproses suatu transaksi ribuan transaksi per detik. Namun demikian sudah ada beberapa teknologi blockchain yang berusaha untuk mempercepat proses *block time* meelalui berbagai macam implementasi seperti menggunakan *proxy node*. Di artikel berikutnya kita akan membahas lebih detail mengenai berbagai platform blockchain terutama yang berbasis open-source.

## Penutup

Blockchain saat ini masih merupakan teknologi baru, namun kedepannya, kekurangan yang ada di teknologi blockchain tentu akan bisa diatasi, tinggal menunggu waktu saja, ketika proses komputasi semakin cepat, jaringa yang cepat, maka kendala-kendala blockchain bisa diatasi.

> Jika kamu seorang developer, programmer atau software engineer yang tertarik untuk mempelajari secara teknis teknologi blockchain menggunakan Ethereum, InaCode membuka [kelas online perdana blockchain & ethereum development]({{< ref "/kelas-online-blockchain-ethereum.md" >}}) di bulan Agustus 2020. Dapatkan harga spesial selama masa early bird, Yuk segera lakukan [pendaftaran disini]({{< ref "/kelas-online-blockchain-ethereum.md" >}}).


---
layout: post
title: "Fitur-Fitur Java"
date: 2014-07-21 19:33:45 +0800
comments: true
categories: J2SE
---
Java telah mengadopsi fitur-fitur dari bahasa lain yang dianggap memiliki kelebihan, sehingga menjadikannya sebagai bahasa yang  portable, efisien, tangguh dan sederhana. Berikut akan dijelaskan beberapa fitur Java yang membedakannya dengan pemograman  lainnya.

`Java Virtual Machine (JVM)` JVM adalah sebuah mesin maya yang bekerja menyerupai aplikasi pada sebuah mesin nyata. JVM menyediakan spesifikasi peranti keras dan platform dimana konfilasi java terjadi. Spesifikasi inilah yang membuat aplikasi berbasis Java menjadi bebas platform mana pun karena proses kompilasi diselesaikan oleh JVM.
Aplikasi progam Java diciptakan dengan file teks berektensi . Java. Program ini dikompilasi menghasilkan satu berkas bytecode berekstensi .class atau lebih. Bytecode adalah serangkaian instruksi serupa instruksi kode mesin. Perbedaannya adalah kode mesin harus dijalankan pada system computer diman kompilasi ditujukan, sementara bytecode berjalan pada interpreter Java yang tersedia di semua platform system computer dan system operasi.

`Garbage Collection` Garbage Collection adalah sebuah fasilltias pengelolaan memori secara dinamis yang dilakukan oleh bahasa pemograman, termasuk Java, Dengan fasilitisas ini seorang programmer tidak perlu mealokasikan memori sendiri sebagaimana pada pemograman C/C++.Hal ini berarti mengurangi kesalahan programmer, apabila ia lupa mengosongkan blok memori yang dipakai program, maka akan menjadikan penuh. Kondisi ini dikenal dengan Memory leaks.
(Dalam pengertian lain)
GC atau garbage collection adalah penghapusan object yang tidak terpakai secara otomatis.
Kapan GC terjadi : Gc terjadi ketika memori yang digunakan aplikasi melebihi dari batas memory yang ditentukan
 
`Code security` Code security terimplementasi pada Java melalui penggunaan Java Runtime Evironment (JRE). Setelah Melewati proses Code Security, Barulah kode program java dijalankan. Java menggunakan model pengamanan 3 lapis untuk melindungi sistem dari untrusted Java Code.
`Class-Loader` menangani pemanggilan kelas Java ke interpreter runtime. Proses ini melakukan pemilihan kelas-kelas yang berasal dari disk local dengan kelas kelas yang berasal dari jaringan. Hal ini dapat melindungi system dari Torajan.
`Bytecode Verifer` menangani pembacaan bytecode sebelum dijalankan  dan memastikan bytecode memenuhi aturan-aturan bahasa java. 
`Security Managament` menangani keamanan tingkat aplikasi dengan mengendalikan program yang berhak mengakses sumber daya seperti system file, port jaringan, proses eksternal, dan system windowing.

`Java` juga menyediakan beragam teknik pengamanan lain yakni bahasa dirancang untuk mempersulit eksekusi kode perusak. Peniadaan pointer merupakan langkah besar pengamanan. Java tidak mengenal operasi pointer. Ditangan programmer andal, operasi pointer merupakan hal yang luar biasa untuk optimasi dan pembuatan program yang efisien serta mengagumkan. Namun mode ini dapat menjadi petaka di hadapan programmer jahat. Pointer merupakan sarana luas biasa untuk pengaksesan tak diotorisasi. Dengan peniadaan operasi pointer, Java dapat menjadi bahasa yang lebih aman.

`Java` memiliki beberapa pengaman terhadap applet. Untuk mencegah program bertindak mengganggu media penyimpanan, maka applet tidak diperbolehkan melakukan open , read, ataupun write terhadap berkas secara sembarangan. Oleh karena Java applet dapat membuka jendela browser yang baru , maka jendela mempunyai logo java  dan teks identifikasi terhadap jendela yang dibuka. Hal ini mencegah jendela pop-up menipu sebagai permintaan keterangan nama pengguna dan kata sandi. 

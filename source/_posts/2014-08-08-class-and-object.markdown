---
layout: post
title: "Class &amp; Object"
date: 2014-08-08 02:19:23 +0800
comments: true
categories: j2se
---
untuk mengakses data atau atribut yang ada pada kelas tertentu disarankan terlebih dahulu membuat `getter` dan `setter`, dengan menggunkaan mettode `getter` dan `setter` ini berarti melakukan setelah suatu object sudah kita buat / tercipata. setelah itu bari kita mengakses atau melakukan pengaturan pengaturan nilai data / atribut yang ada dalam object tertentu, yang dimana setter digunakan untuk melakukan pengaturan nilai data / atribut dan untuk mengambil nilai itu kita akan menggunakan yang disebut getter, dengan demikian kita sudah melakukan akses tak langsung pada data / atribut yang dimiliki oleh obeject tertentu itu, pendekatan inilah yang disarankan saat kita melakukan pemograman menggunakan bahasa pemograman java , dan juga saat menggunakan bahasa pemograman `OOP` lainnya.
Bagaimana jika kita menghendaki supaya pengaturan pengaturan itu bersamaan saat suatu object tercipta.? Untuk melakukan hal itu kita bisa membuat / menggunakan constructor, sebelum itu tau ngga sih apat itu constructor ? “Tau dong :D” constructor adalah suatu metode yang dieksekusi / dijalankan secara otomatis, saat suatu object tercipta dari suatu kelas (class). Menurut konvensi, konstruktor harus memiliki nama yang sama dengan nama kelasnya. Saat membuat constructor kita bisa langsung memberikan parameter didalam constructor karena constructor juga bisa disebut prosedure / method. Berikut contoh sederhananya :
```java class Guitar
public class Gitar{

	String warna;
	int jumlah_senar;
	int jumlah_spool;

	//konstruktor 1
	public Gitar(){
		super();
	}

	//konstruktor 2
	public Gitar(String warna, int jumlah_senar, int jumlah_spool){

		super();
		this.warna = warna;
		this.jumlah_senar = jumlah_senar;
		this.jumlah_spool = jumlah_spool;
	}

	public int getJumlah_senar() {
        return jumlah_senar;
    }

    public void setJumlah_senar(int jumlah_senar) {
        this.jumlah_senar = jumlah_senar;
    }

    public int getJumlah_spool() {
        return jumlah_spool;
    }

    public void setJumlah_spool(int jumlah_spool) {
        this.jumlah_spool = jumlah_spool;
    }

    public String getWarna() {
        return warna;
    }

    public void setWarna(String warna) {
        this.warna = warna;
    }
    
    public int Freet(int freet){
        int jumlahFreet = 0;
        jumlahFreet = jumlahFreet + freet;
        return (jumlahFreet);
    }

}
```


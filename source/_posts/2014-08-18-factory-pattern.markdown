---
layout: post
title: "Factory Pattern"
date: 2014-08-18 03:32:28 +0800
comments: true
categories: j2se
---
factory pattern adalah satu dari banyak digunakan di design pattern java. type desing pattern ini menyediakan satu dari cara terbaik untuk pembuatan object.
Dalam factory pattern, kita membuat objek tanpa menyingkapkan logika penciptaan kepada klien dan merujuk ke objek yang baru dibuat menggunakan interface pada umumnya. Untuk mempertajam visi ups maksudnya mempertajam pemahaman tentang factory patter berikut contoh sederhana implementasinya:

membuat interfaca senjata
```java Senjata.java
public interface Senjata {

    void suaraTembak();

}
```
membuat kelas yang mengimplementasikan interface Senjata
```java AK_47.java
public class AK_47 implements Senjata {

    public void suaraTembak() {
        System.out.println("deerrreeeetttettr");
    }

}

```
```java FN_FAL.java
public class FN_FAL implements Senjata {

    public void suaraTembak() {
        System.out.println("dorrrr dorrrr");
    }

}

```
```java M16.java
public class M16 implements Senjata {

    public void suaraTembak() {
        System.out.println("Breeet Brettt");
    }

}

```
Buat factory untuk menghasilkan objek Senjata berdasarkan informasi yang diberikan.
```java Tentara.java
public class Tentara {

    //menggunakan method getSenjata untuk mendapatkan object dari type Senjata

    public Senjata getSenjata(String typeSenjata){
        if(typeSenjata == null){

            return null;
        }

        if(typeSenjata.equalsIgnoreCase("AK_47")){

            return new AK_47();

        }else if(typeSenjata.equalsIgnoreCase("FN_FAL")){

            return new FN_FAL();

        }else if(typeSenjata.equalsIgnoreCase("M16")){

            return new M16();

        }

        return null;
    }
}

```
gunakan factory untuk mendapatkan object dari Senjata dari passing type sebagai informasi
```java Main.java
public class Main {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here

        Tentara tentara = new Tentara();

        //get an object of Circle and call its draw method.
        Senjata senjata1 = tentara.getSenjata("AK_47");
        senjata1.suaraTembak();

        Senjata senjata2 = tentara.getSenjata("FN_FAL");
        senjata2.suaraTembak();

        Senjata senjata3 = tentara.getSenjata("M16");
        senjata3.suaraTembak();

    }

}


```
virify the output
{% codeblock %}
run:
deerrreeeetttettr
dorrrr dorrrr
Breeet Brettt
{% endcodeblock %}

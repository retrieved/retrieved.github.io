---
layout: post
title: "Stack dan Heap Memory di Java"
date: 2014-08-10 04:47:29 +0800
comments: true
categories: j2se
---
Tau ngga sih?  “tau dongg” apa itu memori stack dan heap pada java, sebenarnya banyak artikel yang mejelaskan pengertian antara memori stack dan heap, kali ini ane coba kembali menuliskan apa perbedaan kedua memori tersebut, oke saat nya newbie action :D !!

<h5>ruang heap di java :</h5>
Ketika kita mulai meprogram dengan java, system operasi yang kita gunakan aka memeberikan beberapa memori ke JVM, java menggunakan memori ini untuk semua kebutuhan, nah bagian memori yang digunakan JVM inilah yang desebut heap memory, setiapa kali kita membuat object menggunakan operator new maka akan di alokasikan memori dari heap, dan ketika  object selesai digunakan memori kembali ke ruang heap di java

<h5>Ruang stack di java:</h5>
Semua parameter pada method dan local variable akan dialokasikan memori dari stack,  jadi jika mengambalikan nilai primitive (bukan varibel) maka akan dialokasikan memori dari stack,
<blockquote>
Stack space :
<ul>
<li><em>method Main</em></li>
<li><em>Saat menciptakan method tanpa /beserta parameter<em></li>
<li><em>Variable reference yang ada di scope method<em><li>
</ul>
Heap space:
<ul>
<li><em>variable reference milik class</em></li>
<li><em>Saat menciptakan object dengan operator `new` </em></li>
</ul>
</blockquote>

```java ManagemenMemory.java
public class ManagementMemory {

    String nama;//instace variabel = Heap space
    int id ;//instace variabel = Heap space
    
    public static void main(String[] args){
       ManagementMemory m; //variable referance = stack space
        m = new ManagementMemory();//object ManagementMemory = heap space 
        
    }


    public String getNama() {//stack space = function
        return nama;
    }

    public void setNama(String nama) {//stack space = method and parameter
        this.nama = nama;
    }



}
```
referensi :
http://javarevisited.blogspot.com/2013/01/difference-between-stack-and-heap-java.html



---
layout: post
title: "Singleton Pattern"
date: 2014-08-21 02:12:08 +0800
comments: true
categories: j2se
--- 
jenis design pattern ini bagian dari creational pattern. pola ini melibatkan satu class yang bertanggung jawab untuk menciptakan object  dengan memastikan hanya satu object tunggal yang dapat dibuat. dengan memberikan visibilty private pada contruktornya maka class tidak dapat di instansiasi, dan membuat static instansiasi itu sendiri. didalam class SingelObject nantinya menyediakan static method untuk mendapatkan static instansiasi object ini sendiri untuk dapat diakses. untuk lebih jelas berikut contohnya:

```java SingleObject.java
public class SingelOBject {
    
    private String nama;
    
    //mebuat object dari SingleObject
    private static SingelOBject instance = new SingelOBject();
    //memberikan visibilti private pada construktor agar tidak dapat di 
    private SingelOBject(){}
    //mendapatkan object satu-satunya yang tersedia
    public static SingelOBject getSingelOBject(){
        return instance;
    }

    public String getNama() {
        return nama;
    }

    public void setNama(String nama) {
        this.nama = nama;
    }


}


```
```java SinglePatternDemo.java
public class SingllePatternDemo {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
	//tidak lagi bisa meinstansiasi object sprti ini
        //SingelOBject singelOBject = new SingelOBject();

        //satu-satunya langkah untuk mendapatkan object yang tersedia
        SingelOBject object = SingelOBject.getSingelOBject();
        object.setNama("asary");
        System.out.println(object.getNama());

        SingelOBject object2 = SingelOBject.getSingelOBject();
        object.setNama("ramadhan");
        System.out.println(object.getNama());
    }

}

```
{% codeblock %}
run:
asary
ramadhan
BUILD SUCCESSFUL (total time: 0 seconds)
{% endcodeblock %}

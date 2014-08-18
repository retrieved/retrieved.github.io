---
layout: post
title: "Abstract Factory Pattern"
date: 2014-08-19 03:32:52 +0800
comments: true
categories: j2se
---
abstact factory pattern bekerja disekitar super-factory yang menciptakan factories lain. factory ini juga disebut Factory dari factoris. jenis design pattern ini naungan dari creational pattern. design pattern ini memberikan salah satu cara terbaik untuk membuat sebuah objek. Dalam Abstrak factory pattern sebuah incterface bertanggung jawab untuk menciptakan sebuah factory obyek terkait,
tanpa secara eksplisit menentukan kelas mereka. setiap factory yang dihasilkan dapat memberikan object sesuai dengan Factory Pattern.
<h5>Implementasi</h5>
Kita akan membuat class interface senjata dan sifat senjata dan concrete class implementasi dari class tersebut. dan akan kita lanjutkan membuat class absctract factory sebagai langkah berikutnya. FactoryclasseSenjataFactory dan SifatSenjataFactory didefinisikan dimana setiap factory meng-extends AbstractFactory. 
AbstractFactoryPatternDemo, dengan menggunakan class FactoryProducer untuk mendapatkan objek AbstractFactory. ini akan menyampaikan informasi (M16,AK_47, FN_FAL untuk Senjata)ke AbstractFactory untuk mendapatkan jenis objek yang dibutuhkan, begitu juga dengan (FullOtomatis,SemiOtomatis,NonOtomatis untuk SifatSenjata) ke AbstractFactory untuk mendapatkan jenis objek yang dibutuhkan.

mebuat interfaca senjata
```java Senjata.java
public interface Senjata {

    void suaraTembak();

}
```
membuat concrete class yang mengimplementasikan interface Senjata
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
membuat interface SifatSenjata.java
```java SifatSenjata.java
public intercafe SifatSenjata {

    void jangkauanTembak();
        

}

```
membuat concrete class yang mengimplementasikan interface SifatSenjata
```java FullOtomatis.java
public class FullOtomatis implements SifatSenjata {

    public void jangkauanTembak() {
        System.out.println("300 M");
    }

}

```
```java SemiOtomatis.java
public class SemiOtomatis implements SifatSenjata {

    public void jangkauanTembak() {
        System.out.println("400 M");
    }

}

```
```java NonOtomatis.java
public class NonOtomatis implements SifatSenjata {

    public void jangkauanTembak() {
        System.out.println("500 M");
    }

}

```
membuat Abstract class untuk mendapatkan factories dari Object Senjata dan SifatSenjata
```java AbstractFactory.java
public abstract class AbstractFactory {

    abstract Senjata getSenjata(String senjata);
    abstract SifatSenjata getSifatSenjata(String sifatSenjata);   
    

}

```
Buat kelas Factory meng-extends AbstractFactory untuk menghasilkan obyek dari concrete class berdasarkan
informasi diberikan. 
```java SenjataFactory.java
public class SenjataFactory extends AbstractFactory {

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

    public SifatSenjata getSifatSenjata(String sifatSenjata){
        
            return null;
    }  
	

}

```
```java SifatSenjataFactory.java
public class SifatSenjataFactory extends AbstractFactory {

    public Senjata getSenjata(String typeSenjata){
        
          return null;
    }  

    public SifatSenjata getSifatSenjata(String sifatSenjata){
         if(sifatSenjata == null){
		return null;
	 }
     
        if(sifatSenjata.equalsIgnoreCase("SemiOtomatis")){

            return new SemiOtomatis();

        }else if(sifatSenjata.equalsIgnoreCase("NonOtomatis")){

            return new NonOtomatis();

        }else if(sifatSenjata.equalsIgnoreCase("FullOtomatis")){

            return new FullOtomatis();

        }

        return null;
    } 
	

}

```
Buat kelas Factory produsen untuk mendapatkan factories dengan mempassing informasi seperti
Senjata atau SifatSenjata. 
```java FactoryProducer.java
public class FactoryProducer {

    public static AbstractFactory getFactory(String choice){
	if(choice.equalsIgnoreCase("SENJATA")){
	   return new SenjataFactory();
	}else if(choice.equalsIgnoreCase("SIFAT_SENJATA")){
	   return new SifatSenjataFactory();
	}
	return null;
      
    }
}

```
Gunakan FactoryProducer untuk mendapatkan AbstractFactory untuk mendapatkan factoris dari concrete class dengan
passing informasi seperti jenisnya. 
```java AbstractFactoryPatternDemo.java

public class AbstractFactoryPatternDemo {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        //get senjata factory
        AbstractFactory senjataFactory = FactoryProducer.getFactory("SENJATA");
        //get an object of senjata AK_47
        Senjata senjata1 = senjataFactory.getSenjata("AK_47");
        //call suaraTembak method of Senjata AK_47
        senjata1.suaraTembak();
        ///get an object of senjata FN_FAL
        Senjata senjata2 = senjataFactory.getSenjata("FN_FAL");
        //call suaraTembak method of Senjata FN_FAl
        senjata2.suaraTembak();
        ///get an object of senjata M16
        Senjata senjata3 = senjataFactory.getSenjata("M16");
        //call suaraTembak method of Senjata M16
        senjata3.suaraTembak();
        //get SifatSenjata factory
        AbstractFactory sifatSenjataFactory = FactoryProducer.getFactory("SIFAT_SENJATA");
        //get an object of sifatSenjata FullOtomatis
        SifatSenjata sifatSenjata1 = sifatSenjataFactory.getSifatSenjata("FullOtomatis");
        //call jankauanTembak method of FullOtomatis
        sifatSenjata1.jangkauanTembak();
        //get an object of sifatSenjata SemiOtomatis
        SifatSenjata sifatSenjata2 = sifatSenjataFactory.getSifatSenjata("SemiOtomatis");
        //call jankauanTembak method of SemiOtomatis
        sifatSenjata2.jangkauanTembak();
        //get an object of sifatSenjata NonOtomatis
        SifatSenjata sifatSenjata3 = sifatSenjataFactory.getSifatSenjata("NonOtomatis");
        //call jankauanTembak method of NonOtomatis
        sifatSenjata3.jangkauanTembak();


    }

}

```
virify the output
{% codeblock %}
run:
deerrreeeetttettr
dorrrr dorrrr
Breeet Brettt
300 M
400 M
500 M
BUILD SUCCESSFUL (total time: 0 seconds)
{% endcodeblock %}
<blockquote>
sumber asli : http://www.tutorialspoint.com/design_pattern/
</blockquote>

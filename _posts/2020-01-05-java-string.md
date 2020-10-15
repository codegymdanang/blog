---
layout: course-java
title: Tất tần tật về String trong lập trình Java
slug : tat-tan-tat-ve-string-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Strings  
image: /images/blog/java.png

description : Trong ngôn ngữ lập trình Java, String (chuỗi) là một kiểu dữ liệu đặc biệt, về cơ bản nó là một đối tượng chứa nhiều phương thức để xử lí các nhiệm vụ bao gồm lấy độ dài chuỗi, chuyển hoá chữ thành chữ hoa và chữ thường, trả về vị trí một kí tự trong chuỗi, nối hai chuỗi lại với nhau, hiển thị các giá trị đặc biệt. Cụ thể mỗi phương thức được thao tác như thế nào với String trong ngôn ngữ Java sẽ được làm rõ thông qua các hình ảnh ví dụ cụ thể.
youtubeId: fR05ShUphxA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Không chỉ riêng trong <b>ngôn ngữ lập trình hướng đối tượng Java</b>, bất kể một ngôn ngữ lập trình nào cũng vậy. Thao tác với String (chuỗi) là những thao tác đòi hỏi các bạn cần nắm vững. Vì những phương thức với String được sử dụng rất nhiều trong các chương trình Java. 
Bài viết dưới đây giúp bạn hiểu được:
•	String trong lập trình hướng đối tượng Java là gì? 
•	Có các loại phương thức nào trong String? 
•	Cách thao tác với mỗi phương thức đó như thế nào? 
•	Ví dụ cụ thể cho mỗi phương thức với String trong ngôn ngữ lập trình Java.



<br>
## **1. Strings trong lập trình hướng đối tượng Java là gì?**

String được sử dụng để lưu trữ các giá trị Text (gồm nhiều ký tự). Ví dụ nhưng 

{% highlight java  %}

String greeting = "Hello";

{% endhighlight %}

String trong ngôn ngữ <b>lập trình Java</b> là một kiểu dữ liệu đặt biệt, nó thật ra là một đối tượng chứa đựng nhiều phương thức để xử lý một số nhiệm vụ như sau.

## **2. String length**

- Dùng để lấy độ dài của một chuỗi

{% highlight java  %}

String txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
System.out.println("The length of the txt string is: " + txt.length());

{% endhighlight %}


## **3. String toUperCase và toLowerCase**

- Dùng để chuyển hoá chữ thành chữ hoa và chữ thường

{% highlight java  %}

String txt = "Hello World";
System.out.println(txt.toUpperCase());   // Outputs "HELLO WORLD"
System.out.println(txt.toLowerCase());   // Outputs "hello world"

{% endhighlight %}

## **4. String IndexOf**

- Dùng để trả về vị trí 1 ký tự trong chuỗi

{% highlight java  %}

String txt = "Please locate where 'locate' occurs!";
System.out.println(txt.indexOf("locate")); // Outputs 7

{% endhighlight %}

## **5. String Concatenation**

- Dùng để nối 2 chuỗi lại với nhau

{% highlight java  %}

String firstName = "John";
String lastName = "Doe";
System.out.println(firstName + " " + lastName);

{% endhighlight %}

## **6. String hiển thị các giá trị đặt biệt**

- Dùng để hiển thị các ký tự như đấu 1 nháy, 2 nháy. Ví dụ khi ta biến sau 

{% highlight java  %}

String text = " le vu" nguyen"

{% endhighlight %}

- Như vậy thì sẽ bị lỗi vì dấu 2 nháy sau chữ vu sẽ gây nhầm lẫn cho trình biên dịch. Như vậy làm sao sử dụng được chữ vu". Thì ta dùng ký tự \ đằng trước đấu 2 nháy như sau.

{% highlight java  %}

String txt = "le vu\" nguyen";

{% endhighlight %}

Ngoài ra String hỗ trợ các ký tự đặt biệt khác như

- \n : dùng để xuống dòng.

{% highlight java  %}

String txt = "Hello\nWorld!";

{% endhighlight %}


- \t : cách nhau một khoảng tab

{% highlight java  %}

 String txt = "Hello\tWorld!";

{% endhighlight %}
- \b : cách nhau một khoảng backspace

{% highlight java  %}

String txt = "Hello\tWorld!";

{% endhighlight %}


## **7. Dấu +**

Khi ta sử dụng dấu + thì đối với kiểu int thì nó là cộng 2 số, còn đối với kiểu String thì sẽ là concatenation (nối chuỗi)

{% highlight java  %}

int x = 10;
int y = 20;
int z = x + y;      // z là 30

{% endhighlight %}

{% highlight java  %}

String x = "10";
String y = "20";
String z = x + y;   // z là chuỗi 1020 

{% endhighlight %}



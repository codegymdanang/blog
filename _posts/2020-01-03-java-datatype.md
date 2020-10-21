---
layout: course-java
title: Kiểu dữ liệu trong lập trình Java
slug : kieu-du-lieu-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Kiểu dữ liệu  
image: /images/blog/java.png

description : Kiểu dữ liệu trong lập trình hướng đối tượng Java là gì? Có các loại kiểu dữ liệu nào trong ngôn ngữ lập trình Java? Cụ thể mỗi kiểu và cách áp dụng mỗi kiểu dữ liệu vào làm chương trình Java như thế nào? Bài viết sẽ giúp giải đáp tất cả các thắc mắc trên cho bạn. Nắm vững và phân biệt rõ ràng mỗi kiểu dữ liệu cũng giúp bạn biết nên lựa chọn kiểu dữ liệu nào phù hợp nhất khi viết các chương trình Java.
youtubeId: fR05ShUphxA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Bạn đang thắc mắc làm cách nào để biểu diễn những thông tin trong thực tế vào việc viết ra các chương trình trên máy tính? Bài chia sẻ về kiểu dữ liệu trong ngôn ngữ <b>lập trình Java</b> dưới đây sẽ giúp bạn giải đáp cho câu hỏi trên. Việc hiểu sâu các <b>kiểu dữ liệu trong lập trình hướng đối tượng Java<b> cũng sẽ giúp bạn biết nên sử dụng kiểu nào phù hợp nhất khi viết các chương trình Java. Vì vậy, trước khi chuyển sang học các kiến thức nâng cao thì các bạn cần nắm vững các <b>kiến thức Java cơ bản</b> này trước nhé. 

<br>
## **Kiểu dữ liệu trong lập trình hướng đối tượng Java là gì**

Trong <b>lập trình Java</b> chúng ta có 2 loại kiểu dữ liệu đó là kiểu nguyên thuỷ và kiểu đối tượng.

## **1.  Kiểu dữ liệu Nguyên Thuỷ**

- Kiểu nguyên thuỷ bao gồm có các loại sau. Ứng với mỗi loại kiểu dữ liệu bộ nhớ sẽ cấp phát vùng nhớ tương ứng

{:class="table table-bordered"}
|  kiểu dữ liệu		  	 	|  kích thướt		            |   khoảng giá trị	|
|---	                 	|---	                        |---	     	    |
| byte			         	|	1 byte						| từ -128 đến 127	|
| short						|	2 bytes						| từ -32.768 đến 32.676	|	
| int 						|	4 bytes						| từ -2.147.483.648 đến 2.147.483.647	|
| long						|	8 bytes						| từ -9.223.372.036.854.775.808 to 9.223.372.036.854.775.807 |
| float						|	4 bytes						| 6 đến 7 thập phân 1.000,1232321 |
| double					|	8 bytes						| 15 dấu thập phân |
| boolean					|	1 bit						| chứa giá trị true hoặc false|
| char						|	2 bytes						| chứa các ký tự đơn |


## **2.  Kiểu dữ liệu Integer**

- Byte có thể chứa giá trị từ -128 đến 127. 

{% highlight java  %}

byte myNum = 100;
System.out.println(myNum);

{% endhighlight %}

- Short có thể chứa giá trị từ -32768 to 32767

{% highlight java  %}

short myNum = 5000;
System.out.println(myNum);

{% endhighlight %}

- int chứa giá trị từ  -2147483648 to 2147483647

{% highlight java  %}

int myNum = 100000;
System.out.println(myNum);

{% endhighlight %}

- long chứa giá trị từ -9223372036854775808 to 9223372036854775807

{% highlight java  %}

long myNum = 15000000000L;
System.out.println(myNum);

{% endhighlight %}

## **3.  Kiểu dữ liệu Float**

- float chứa từ 3.4e−038 to 3.4e+038

{% highlight java  %}

float myNum = 5.75f;
System.out.println(myNum);

{% endhighlight %}

- double chứa giá trị từ 1.7e−308 to 1.7e+308

{% highlight java  %}

double myNum = 19.99d;
System.out.println(myNum);

{% endhighlight %}


## **4.  Kiểu dữ liệu Khoa học**

Chúng ta có thể dùng e để mô tả  bội số của 10.

{% highlight java  %}

float f1 = 35e3f;
double d1 = 12E4d;
System.out.println(f1);
System.out.println(d1);

{% endhighlight %}

## **5.  Kiểu dữ liệu Boolean**

- Chỉ chứa kết quả đúng hay sai

{% highlight java  %}

boolean isJavaFun = true;
boolean isFishTasty = false;
System.out.println(isJavaFun);     
System.out.println(isFishTasty); 

{% endhighlight %}

## **6.  Kiểu dữ liệu ký tự**

- Kiểu char chỉ chứa 1 ký tự duy nhất

{% highlight java  %}

char myGrade = 'B';
System.out.println(myGrade);

{% endhighlight %}

- Trong kiểu ký tự chúng ta có thể sử dụng bảng mã ASCII để hiển thị giá trị


{% highlight java  %}

char a = 65, b = 66, c = 67;
System.out.println(a);
System.out.println(b);
System.out.println(c);

{% endhighlight %}

## **7.  Kiểu dữ liệu chuỗi**

- Kiểu String dùng để lưu dạng chuỗi các ký tự

{% highlight java  %}

String greeting = "Hello World";
System.out.println(greeting);

{% endhighlight %}

## **8.  Kiểu dữ liệu đối tượng**

- Kiểu dữ liệu đối tượng thường tham chiếu tới 1 đối tượng. Anh lấy ví dụ như 

{% highlight java  %}

Student student = new Student()

{% endhighlight %}




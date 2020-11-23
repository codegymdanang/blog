---
layout: course-java
title: Tính kế thừa trong lập trình hướng đối tượng Java
slug : tinh-ke-thua-trong-lap-trinh-huong-doi-tuong-java
category: laptrinhjava
tags: [java core]
summery: Tính kế thừa 
tuong: /images/blog/java.png
featureImage: /images/post/javacore/feature_oop.png
description : Tiếp nối chuỗi các bài viết chia sẻ về các đặc tính của lập trình hướng đối tượng Java, trong bài viết này trình bày về tính kế thừa, inheritance trong lập trình. Hướng dẫn thông qua các ví vụ minh hoạ và video demo để bạn hiểu hơn và áp dụng được tính chất này vào khi viết các chương trình lập trình Java. Và mục đích, lợi ích của việc sử dụng tính kế thừa trong lập trình Java.
youtubeId: MGWT_Y9Oi8I
youtubeId1: B2Zx3wZoawk
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Tiếp nối chuỗi các bài viết chia sẻ về các đặc tính của <b>lập trình hướng đối tượng Java</b> bao gồm tính đa hình, tính đóng gói, tính trừu tượng, tính kế thừa. Trong bài viết này anh sẽ trình bày về <b>tính kế thừa, inheritance</b> trong lập trình. Hướng dẫn thông qua các ví vụ minh hoạ và video demo để bạn hiểu hơn và áp dụng được tính chất này vào khi viết các chương trình lập trình Java. Và mục đích, lợi ích của việc sử dụng <b>tính kế thừa trong lập trình Java</b>.


<br>
## **1. Tính kế thừa trong lập trình hướng đối tượng Java là gì**

<b>Tính kế thừa</b> các em hiểu nôm na giống như ngoài đời vậy. Anh lấy ví dụ như mình kế thừa ADN của cha và mẹ mình thì mình sẽ có hết tất cả các gen tốt của cha và mẹ. Trong lập trình Java khi nói đến kế thừa thì mình cũng nói khái niệm lớp cha và lớp con. Lớp con sẽ dùng từ khoá extends để mô tả nó sẽ kế thừa lớp cha. Trong lập trình khi lớp cho có 10 thuộc tính nếu lớp con kế thừa lớp cha thì mặc định lớp con có 10 thuộc tính như cha.
Anh ví dụ như mình có lớp cha là lớp Vehical (Xe cộ), trong lớp cha này mình định nghĩa các thuộc tính như color, model và phương thức run. Giả sử như anh có 1 lớp con là Bicycle hoặc Car kế thừa lớp Vihical thông qua từ khoá extends thì lúc này lớp Bicycle và Car mặc định có thuộc tính là color, model và phương thức run.

Sử dụng kế thừa giúp mình tiết kiệm dòng code. Như vậy ở class Bicycle hay Car anh không phải khai báo lại biến color, model nữa.


{% highlight java linenos %}

class Vehicle {
  protected String model = "Ford"; 
  protected String color = "Red";   

  public void run() {                    
    System.out.println("Tuut, tuut!");
  }
}

class Bicycle extends Vehicle {
 
  public static void main(String[] args) {
    Bicycle myBike = Bicycle Car();
    myBike.run();
    System.out.println(myBike.color + " " + myBike.model);
  }
}

class Car extends Vehicle {

  private String modelName = "Mustang";    // Car attribute
 
  public static void main(String[] args) {
    Car myCar = new Car();
    myCar.run();
    System.out.println(myCar.color + " " + myCar.model);
  }
}


{% endhighlight %}

<br>
## **2. Không cho lớp con kế thừa**

Trong trường hợp mình có lớp cha nhưng không muốn cho lớp con kế thừa thì mình dùng từ khoá final.

{% highlight java linenos %}

final class Vehicle {
  protected String model = "Ford"; 
  protected String color = "Red";   

  public void run() {                    
    System.out.println("Tuut, tuut!");
  }
}

class Bicycle extends Vehicle {
 
  public static void main(String[] args) {
    Bicycle myBike = Bicycle Car();
    myBike.run();
    System.out.println(myBike.color + " " + myBike.model);
  }
}

{% endhighlight %}

Như vậy khi chạy chương trình thì nó sẽ báo lỗi ở lớp Bicycle vì kế thừa lớp Vehicle. Chương trình sẽ thôgn báo cho chúng ta là lớp Bicycle không thể kế thừa lớp Vehicle được 

## **3. Hướng dẫn cách tạo Kế thừa trong Java**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **4. Tại sao lại sử dụng kế thừa. Mục đích sử dụng kế thừa trong lập trình**
{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId1 %}
{: refdef}



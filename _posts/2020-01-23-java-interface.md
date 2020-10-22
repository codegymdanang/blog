---
layout: course-java
title: Sử dụng Interface trong lập trình Java
slug : su-dung-interface-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Interface
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_interfaces_vs_abstract.png
description : Sau khi đọc bài chia sẻ, bạn sẽ hiểu được Interface trong lĩnh vực lập trình Java là gì? Các tính chất, thuộc tính, thành phần, phương thức của nó trong lập trình Java như thế nào? Biết khi nào cần áp dụng Interface trong quá trình lập trình Java. Bài chia sẻ bao gồm các ví dụ minh hoạ và video bài học kèm theo cuối bài.
youtubeId1 : hxTH18XG4qs
youtubeId2 : kfQ7O7Fky8U
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Bạn đã từng nghe đề cập về khái niệm Interface trong lập trình hướng đối tượng Java. Nhưng bạn đã thực sự biết khi nào thì nên dùng Interface trong quá trình lập trình Java chưa? 
Bài viết dưới đây sẽ giúp bạn hiểu được Interface là gì? Các tính chất, thuộc tính, phương thức của Interface. Cũng như biết khi nào thì nên áp dụng Interface vào trong quá trình code các chương trình lập trình Java. Bài chia sẻ sẽ hướng dẫn bạn cách thao tác với Interface thông qua các ví dụ minh hoạ. Kèm theo video tổng kết bài học ở cuối bài sẽ giúp bạn một lần nữa hệ thống lại kiến thức. Từ đó giúp bạn ghi nhớ bài học lâu hơn.
 

<br>
## **1. Interface trong lập trình Java là gì**

- Như các em đã học bài học hôm trước về tính trừu tượng, nếu các em quên thì có thể xem lại tại [đây] (https://levunguyen.com/laptrinhjava/2020/01/01/tinh-truu-tuong/). Thì Interface chính là cách mà chúng ta làm tính trừu tượng trong lập trình. Ngoài cách dùng abstract class thì để thực hiện được tính trừu tượng ta có thể sử dụng Interface.

- Interface chính là 100% abstract class có nghĩa là trong abstract class ta có 10 phương thức như ta chỉ cần 5 phương thức abstract cũng được. 5 phương thức còn lại là các phương thức bình thường. Tuy nhiên nếu Abstract Class có 10 phương thức abstract thì lớp con phải Override lại 10 phương thức. Cũng tương tự như vậy tất cả các phương thức trong interface nếu có lớp con kế thừa nó thì bắt buộc lớp con phải Override lại 10 phương thức giống như abstract class vậy.

- Chúng ta sử dụng từ khoá interface để khai báo một Interface trong java.


{% highlight java linenos %}
// interface
interface Animal {
  public void animalSound(); 
  public void run(); 
}
{% endhighlight %}

- Để sử dụng được interface thì cúng ta sử dụng từ khoá implements

{% highlight java linenos %}
// Interface
interface Animal {
  public void animalSound(); // interface method (does not have a body)
  public void sleep(); // interface method (does not have a body)
}

// Pig "implements" the Animal interface
class Pig implements Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // The body of sleep() is provided here
    System.out.println("Zzz");
  }
}

class MyMainClass {
  public static void main(String[] args) {
    Pig myPig = new Pig();  // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}

{% endhighlight %}

- Trong Java 1 class con chỉ có thể kế thừa 1 lớp cha. Ví dụ Class Cat extends Animals mà thôi chứ không thực hiện đa kế thừa được như 
Cat extends Animals,Vihecial được

- Nhưng trong Interface chúng ta có thể thực hiện đa kế thừa được.

{% highlight java linenos %}
interface FirstInterface {
  public void myMethod(); // interface method
}

interface SecondInterface {
  public void myOtherMethod(); // interface method
}

class DemoClass implements FirstInterface, SecondInterface {
  public void myMethod() {
    System.out.println("Some text..");
  }
  public void myOtherMethod() {
    System.out.println("Some other text...");
  }
}

class MyMainClass {
  public static void main(String[] args) {
    DemoClass myObj = new DemoClass();
    myObj.myMethod();
    myObj.myOtherMethod();
  }
}
{% endhighlight %}


<br>
## **2. Demo tạo interface trong Java**  

<center>
{% include youtubePlayer.html id=page.youtubeId2 %}
</center>

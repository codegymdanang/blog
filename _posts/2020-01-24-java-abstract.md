---
layout: course-java
title: Sử dụng Abstract trong lập trình Java
slug : su-dung-abstract-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Abstract
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_interfaces_vs_abstract.png
description : Bài viết chia sẻ về Abstract trong lập trình hướng đối tượng Java. Giúp hiểu được thuật ngữ Abstract trong ngôn ngữ Java là gì? Tại sao nên dùng Abstract trong lập trình? Nó được áp dụng cho Class và Method như thế nào trong lập trình Java? Hay cách làm để tạo Abstract trong lập trình Java. Đồng thời hướng dẫn cách thao tác với Abstract thông qua các ví dụ minh hoạ. Kèm theo video tổng kết lại toàn bộ bài học ở cuối bài giúp hệ thống lại kiến thức một lần nữa.
youtubeId1 : hxTH18XG4qs
youtubeId2 : kfQ7O7Fky8U
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Một trong những tính chất của lập trình hướng đối tượng Java là tính trừu tượng. Để thực hiện được tính trừu tượng này, trong <b>lập trình Java</b> sử dụng từ khoá <b>Abstract</b> và Interface. Trong đó, anh đã có bài chia sẻ về Interface, các bạn có thể tìm đọc lại bài viết tại đây.

Trong bài viết hôm nay, anh sẽ chia sẻ về <b>Abstract</b>. Cụ thể Abstract là gì? Tại sao nên dùng Abstract trong lập trình Java? Nó được áp dụng cho Class và Method như thế nào trong lập trình Java? Hay cách để tạo <b>Abstract trong ngôn ngữ lập trình Java</b>. Ngoài ra, ở cuối bài viết có video tổng kết lại toàn bộ bài học giúp các bạn hệ thống lại kiến thức một lần nữa để giúp ghi nhớ bài học lâu hơn.
 

<br>
## **1. Abstract trong lập trình Java là gì**

<b>Trừu tượng trong lập trình Java</b> có nghĩa là tuyến trình che giấu đi những chi tiết quan trọng và chỉ hiển thị những thông tin cần thiết cho người sử dụng. Để thực hiện được tính trừu tượng chúng ta sử dụng từ khoá abstract hoặc interface. Trong bài này anh sẽ giới thiệu về các sử dụng abstract. Chúng ta có thể áp dụng từ khoá abstract cho class hoặc method. Khi áp dụng abstract cho class thì chúng ta không thể tạo đối tượng từ lớp abstract được. Abstract method chỉ được sử dụng và khai báo trong abstract class. Abstract method sẽ không có phần thân (code thực thi). Phần thân code thực thi sẽ được viết bởi lớp con kế thừa abstract class.

- Abstract class Animal ví dụ sau đây dùng từ khoá abstract. Chú ý chúng ta không thể tạo đối tượng Animal ani = new Animal() được.

<br>
{% highlight java linenos %}

abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    System.out.println("Zzz");
  }
}

{% endhighlight %}

- Ví dụ hoàn chỉnh về abstract class và code thực thi abstract method trong lớp con
<br>
{% highlight java linenos %}

// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}

// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}

class MyMainClass {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}

{% endhighlight %}

## **2. Tại sao chúng ta sử dụng Abstract**

- Để đảm bảo tính bảo mật.
- Chúng ta chỉ đưa ra những thông tin cần thiết và che giấu những thông tin quan trọng.

## **3. Cách tạo abstract trong Java**  

<center>
{% include youtubePlayer.html id=page.youtubeId1 %}
</center>


---
layout: course-java
title: Tính trừu tượng trong lập trình hướng đối tượng Java
slug : tinh-truu-tuong-trong-lap-trinh-huong-doi-tuong-java
category: laptrinhjava
tags: [java core]
summery: Tính trừu tượng
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_oop.png
description : Tiếp nối chuỗi các bài viết chia sẻ về các đặc tính của lập trình hướng đối tượng Java, trong bài viết này trình bày về tính trừu tượng trong lập trình, hướng dẫn thông qua các ví vụ minh hoạ để bạn hiểu hơn và áp dụng được tính chất này vào khi viết các chương trình lập trình Java. Và mục đích, lợi ích của việc sử dụng tính trừu tượng trong lập trình Java.
youtubeId: 8vYpMzAoz2E
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Tiếp nối chuỗi các bài viết chia sẻ về các đặc tính của <b>lập trình hướng đối tượng Java</b>, bao gồm tính đa hình, tính đóng gói, tính trừu tượng, và tính kế thừa. Trong bài viết này sẽ trình bày về tính trừu tượng trong lập trình, hướng dẫn thông qua các ví dụ minh hoạ để bạn hiểu hơn và áp dụng được tính chất này vào khi viết các chương trình <b>ngôn ngữ lập trình Java</b>. Và mục đích, lợi ích của việc sử dụng <b>tính trừu tượng trong lập trình Java</b>.

<br>
## **1.  Tính trừu tượng trong lập trình hướng đối tượng Java là gì**

Tính trừu tượng là cách mình dấu đi các chi tiết quan trọng và chỉ hiển thị những thông tin cần thiết. Anh lấy ví phát triển một ứng dụng web trong đó có chức năng login với Facebook. Thì lúc này Facebook sẽ được cho mình một đường link kèm với 1 đoạn code của facebook và yêu cầu mình bỏ vào trong trang web của mình thì lúc đó mình mới có chức năng login được. Như vậy trừu tượng ở chỗ mình không thấy cái code thực sự facebook viết như thế nào mà mình có thể gọi được login của facebook. Như vậy Facebook đã giấu đi các đoạn code xử lý quan trọng . Facebook chỉ cần mình cho tham số đầu vào sau đó Facebook tự xử lý trong hệ thống của nó và trả kết quả lại cho mình. Facebook chỉ hiển thị những thông tin cần thiết đó chính là cái code mà Facebook bắt mình nhập vào trang web của mình. Nếu mình nhập đúng như Facebook yêu cầu thì mình sẽ tích hợp được khả năng login của nó. Như vậy tính trừu tượng ở đây là mình không biết cái code bên trong facebook như thế nào nhưng mình biết một điều là khi mình cung cấp đủ thông tin thì mình sẽ nhận lại kết quả từ facebook.

Trong lập trình anh sử dụng rất nhiều tính đa hình trong code của mình. Mục đích che giấu đi những nghiệp vụ quan trọng. Ví dụ như ứng dụng thanh toán ngân hàng mà anh đã làm. Thì trong ứng dụng của anh có kết nối với hệ thống MasterCard để thanh toán thẻ visa và master cho người dùng. Bên nhà cung cấp thứ 3 là MasterCard. Họ chỉ đưa cho anh một đường link trong đường link đó yêu cầu nhập các tham số đầu vào. Nếu nhập đúng giá trị truyền lên cho MasterCard thì sẽ nhận được kết quả. Như vậy nghiệp vụ bên trong MasterCard như thế nào thì anh không biết nhưng anh biết MasterCard cung cấp cho anh một đường link. Anh chỉ cần nhập đúng sẽ nhận được kết quả

Ví dụ sau đây anh sẽ tạo một lớp Animal có phương thức abstract là animalSound. Để tạo 1 lớp abstract thì ta dùng từ khoá abstract class.
Lớp Abstract là lớp đặt biệt chúng ta không thể tạo đối tượng từ nó. Ví dụ Animal animal = new Animal là không được.

Trong một lớp abstract ta khai báo một phương thức abstract bằng từ khoá abstract tên method.

{% highlight java linenos %}

// Abstract class
abstract class Animal {
  public abstract void animalSound();
  public void sleep() {
    System.out.println("Zzz");
  }
}

class Pig extends Animal {
  public void animalSound() {
    System.out.println("The pig says: wee wee");
  }
}

class MyMainClass {
  public static void main(String[] args) {
    Pig myPig = new Pig(); 
    myPig.animalSound();
    myPig.sleep();
  }
}
{% endhighlight %}

<br>

Như vậy ta thấy lớp Animal có phương thức abstract là animalSound. Người sử dụng chỉ biết có phương thức đó thôi còn nội dung code bên trong cài đặt như thế nào thì không biết. Các em có thể tưởng tượng trong ví dụ Facebook ở trên của anh. Các hàm  abstract void animalSound() tương ứng với việc là Facebook cho mình cái link và mình nhúng vào, còn nội dung bên trong thì mình không biết. Như vậy phương thức animalSound() ở lớp Animal giúp che giấu đi những code quan trọng và chỉ để lớp con của nó cài đặt những code thực thi. Người dùng chỉ biết gọi hàm animalSound và nhận kết quả.


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

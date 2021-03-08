---
layout: course-java
title: Sử dụng Method trong lập trình Java
slug : su-dung-method-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Method  
image: /images/blog/java.png

description : Phương thức, Method trong ngôn ngữ lập trình Java là gì? Cách khai báo Method trong ngôn ngữ lập trình Java? Truyền tham số trong Method Java được tiến hành như thế nào? Kết quả của một phương thức đã được xử lí xong sẽ được trả về bằng cách nào? Cách ghi đè phương thức và lợi ích của việc nạp chồng các phương thức trong Java? Bài viết sẽ giúp bạn giải đáp các thắc mắc trên. Đồng thời hướng dẫn bạn cách thao tác Method trong ngôn ngữ lập trình hướng đối tượng Java thông qua các ví dụ chi tiết trong mỗi phần.
youtubeId: U-7EE2LZhOk
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

<b>Phương thức, Method trong ngôn ngữ lập trình Java</b> là gì? Cách khai báo Method trong <b>ngôn ngữ lập trình Java</b>? Truyền tham số trong Method Java được tiến hành như thế nào? Kết quả của một phương thức đã được xử lí xong sẽ được trả về bằng cách nào? Cách ghi đè phương thức và lợi ích của việc nạp chồng các phương thức trong Java? Bài viết sẽ giúp bạn giải đáp các thắc mắc trên. Đồng thời hướng dẫn bạn cách thao tác Method trong <b>ngôn ngữ lập trình hướng đối tượng Java</b> thông qua các ví dụ chi tiết trong mỗi phần.


## **1. Method trong ngôn ngữ lập trình Java là gì**

Method là một khối tập trung các dòng lệnh code để thực hiện mục đích của method khi chương trình gọi method. Các em có thể truyền data (tham số) vào trong method. Chúng ta sử dụng method thuận tiện cho việc sử dụng lại. Các em có thể viết method một lần và chạy nhiều lần.

Method mình có thể dịch ra là phương thức hay hàm đều được cả.

## **2. Tạo Method**

{% highlight java  %}

public class MyClass {

  public void myMethod() {

    // code to be executed
  }

}

{% endhighlight %}

- Method  được tạo trong một class
- myMethod() là tên của method
- Các dòng code để thực thi được đặt trong dấu { }

## **3. Gọi Method**

Để gọi method chúng ta dùng tên method() như sau

{% highlight java  %}

public class MyClass {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
  }
}

{% endhighlight %}

- Như vậy các em thấy trong hàm main chúng ta gọi myMethod() để gọi phương thức. Khi chương trình chạy hàm main sẽ chạy trước. Nó sẽ thực thi dòng code myMethod(). Sau đó nó thực thi các dòng code trong phương thức myMethod và in ra dòng I just got exectute

## **4. Gọi Method nhiều lần**

Method được viết ra 1 lần nhưng có thể thực thi nhiều lần tuỳ vào nơi cần gọi hàm.

{% highlight java  %}

public class MyClass {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
    myMethod();
    myMethod();
  }
}

{% endhighlight %}

## **5. Truyền tham số trong phương thức**

Các em có thể truyền thông tin vào method, những thông tin truyền vào được gọi là tham số cho phương thức. Chúng ta có thể truyền nhiều tham số cho method, mỗi tham số cách nhau bằng dấu phẩy.

{% highlight java  %}

public class MyClass {
  static void myMethod(String fname) {
    System.out.println(fname + " Refsnes");
  }

  public static void main(String[] args) {
    myMethod("Liam");
    myMethod("Jenny");
    myMethod("Anja");
  }
}
// Liam Refsnes
// Jenny Refsnes
// Anja Refsnes

{% endhighlight %}

## **6. Truyền nhiều tham số trong phương thức**

{% highlight java  %}

public class MyClass {
  static void myMethod(String fname, int age) {
    System.out.println(fname + " is " + age);
  }

  public static void main(String[] args) {
    myMethod("Liam", 5);
    myMethod("Jenny", 8);
    myMethod("Anja", 31);
  }
}

// Liam is 5
// Jenny is 8
// Anja is 31
{% endhighlight %}

## **7. Trả về kết quả trong phương thức**

Khi một phương thức xử lý công việc xong thì nó phải trả về một kết quả cho nơi gọi nó. Chúng ta sử dụng từ khoá return để trả lại kết quả trong phương thức

{% highlight java  %}

public class MyClass {
  static int myMethod(int x) {
    return 5 + x;
  }

  public static void main(String[] args) {
    System.out.println(myMethod(3));
  }
}

{% endhighlight %}

- Chú ý hàm void thì không có return trả về 

{% highlight java  %}

public class MyClass {
  static void myMethod(int x) {
      System.out.println("không có return")
  }

  public static void main(String[] args) {
      myMethod();
  }
}

{% endhighlight %}

## **8. Phương thức override**

Nhiều phương thức có thể có cùng tên nhưng khác tham số và kiểu dữ liệu truyền vào cũng hợp lệ


{% highlight java  %}

static int plusMethodInt(int x, int y) {
  return x + y;
}

static double plusMethodDouble(double x, double y) {
  return x + y;
}

public static void main(String[] args) {
  int myNum1 = plusMethodInt(8, 5);
  double myNum2 = plusMethodDouble(4.3, 6.26);
  System.out.println("int: " + myNum1);
  System.out.println("double: " + myNum2);
}

{% endhighlight %}

## **9. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **10. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Java-Method" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

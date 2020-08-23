---
layout: course-java
title: Method 
slug : method
category: laptrinhjava
tags: [java core]
summery: Method  
image: /images/blog/java.png

description : Hiểu về Method là gì trong lập trình hướng đối tượng trong lập trình? Giải thích các khái niệm về Method trong lập trình hướng đối tượng. Lợi ích của việc sử dụng Method trong lập trình hướng đối tượng trong lập trình.
youtubeId: fR05ShUphxA
---

# **Giới thiệu nội dung bài viết**

Chào các em. Hôm nay chủ đề của chúng ta sẽ về Method (phương thức) trong lập trình java. 


# **1. Method là gì**

Method là một khối tập trung các dòng lệnh code để thực hiện mục đích của method khi chương trình gọi method. Các em có thể truyền data (tham số) vào trong method. Chúng ta sử dụng method thuận tiện cho việc sử dụng lại. Các em có thể viết method một lần và chạy nhiều lần.

Method mình có thể dịch ra là phương thức hay hàm đều được cả.

# **2. Tạo Method**

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

# **2. Gọi Method**

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

# **2. Gọi Method nhiều lần**

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





















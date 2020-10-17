---
layout: course-java
title: Sử dụng Iterator trong Java
slug : su-dung-iterator-trong-java
category: laptrinhjava
tags: [java core]
summery: Iterator
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Sử dụng Iterator trong lập trình java. Khái niệm Iterator trong học lập trình java. Sử dụng Iterator duyệt qua các tập hợp như List , Vector , Set , Queue, Dequee, Map.
youtubeId: 5C2OqlhiYsg
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chủ đề của chúng ta sẽ hướng dẫn cách tạo ra một <b>Iterator</b> trong lập trình java theo mong muốn của chúng ta.


# **1. Iterator là gì**

Thông thường chúng ta hay sử dụng vòng lặp for để duyệt qua các phần tử trong tập hợp. Hôm nay mình có thêm một công cụ mới để duyệt qua các phần tử trong tập hợp nữa đó là Iterator.

- Ví dụ như anh có một ArrayList về xe sau. Trong tập hợp xe này anh lưu các giá trị như Volvo,BMW,Ford,Mazda

{% highlight java linenos %}

import java.util.ArrayList;
import java.util.Iterator;

public class MyClass {
  public static void main(String[] args) {

    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next());
  }
}

{% endhighlight %}

+ Đầu tiên anh sẽ khai báo một Iterator bằng cách sử dụng 

{% highlight java linenos %}

Iterator<String> it = cars.iterator();

{% endhighlight %}


- Để duyệt qua các phần tử trong tập hợp xe anh sử dụng phương thức hasNext mà Iterator cung cấp. Phương thức hasNext sẽ duyệt qua từng phần tử trong tập hợp cho đến khi đi tới phần tử cuối cùng của tập hợp.

{% highlight java linenos %}

while(it.hasNext()) {
  System.out.println(it.next());
}

{% endhighlight %}

+ Hàm while sẽ chạy hết các phần tử trong tập hợp. Nếu chúng ta muốn lấy phần tử ra thì sử dụng phương thức next().
Trong ví dụ trên chúng ta sẽ dùng it.next().


- Xoá một phần tử trong tập hợp chúng ta sử dụng phương thức remove.

{% highlight java linenos %}

import java.util.ArrayList;
import java.util.Iterator;

public class MyClass {
  public static void main(String[] args) {
    ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(12);
    numbers.add(8);
    numbers.add(2);
    numbers.add(23);
    Iterator<Integer> it = numbers.iterator();
    while(it.hasNext()) {
      Integer i = it.next();
      if(i < 10) {
        it.remove();
      }
    }
    System.out.println(numbers);
  }
}

{% endhighlight %}

- Trong ví dụ trên chúng ta tạo ra một ArrayList chứa các số 12,8,2,23. Sau đó chúng ta duyệt qua các phần tử trong tập hợp này. Nếu phần tử nhỏ hơn 10 thì ta sẽ xoá phần tử đó ra khỏi tập hợp thông qua phương thức it.remove().








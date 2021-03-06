---
layout: course-java
title: Đối tượng trong lập trình java
slug : doi-tuong-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Object  
image: /images/blog/java.png

description : Trong bài viết này, chúng ta sẽ được tìm hiểu về đối tượng Object, lớp Class trong ngôn ngữ lập trình Java là gì? Sự khác nhau giữa đối tượng và lớp trong Java? Cách tạo lớp và đối tượng, các hàm khởi tạo trong Java? Thuộc tính và cách thao tác với các thuộc tính của mỗi đối tượng như thế nào? Cũng như phương thức của mỗi đối tượng hoạt động làm sao?
youtubeId: N-tFo_LiCLs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Mọi thứ trong <b>lập trình Java</b> đều liên quan đến <b>Object (đối tượng)</b>, các thuộc tính và phương thức của đối tượng. Các chương trình được thiết kế trong Java đều dựa trên các đối tượng và các lớp. Vì vậy để có thể viết ra được các chương trình Java, đòi hỏi bạn phải nắm được kiến thức Java này và vận dụng được vào trong thực hành. Bài viết dưới đây sẽ lần lượt chia sẻ, đi từ khái niệm chung cho đến cách tạo lớp và đối tượng, các hàm khởi tạo trong Java. Thuộc tính và cách thao tác với các thuộc tính của mỗi đối tượng như thế nào. Cũng như phương thức của mỗi đối tượng hoạt động làm sao trong <b>lập trình hướng đối tượng Java</b>. 

<br>
## **1. Object là gì**

Mọi thứ trong <b>lập trình Java</b> đều liên quan đến <b>Object (đối tượng)</b>, các thuộc tính và phương thức của đối tượng. Ví dụ ở ngoài đời chúng ta có chiếc xe hơi đó chính là đối tượng. Chiếc xe hơi có các thuộc tính như cân nặng, màu sắc và phương thức là chạy

Một Class giống như 1 bản vẽ thiết kế ra đối tượng. Anh ví dụ như khi mình muốn xây một ngôi nhà thì mình sẽ có bản vẽ thiết kế ngôi nhà. Từ đó ta có thể xây dựng ra các ngôi nhà khác nhau dựa và bản thiết kế. Có thể cho ra ngôi nhà màu xanh, màu đỏ khác nhau. Cũng như trong lập trình ta tạo ra các classes đó chính là bản thiết kế. Khi chương trình mình chạy dựa vào toán tử new (House house = new House()) nó sẽ sinh ra các đối tượng khác nhau.


## **2. Tạo một Class**

- Chúng ta sử dụng từ khoá class để tạo ra 1 class java.
<br>
{% highlight java  %}

public class MyClass {
  int x = 5;
}

{% endhighlight %}

## **3. Tạo một Object**

- Từ 1 class chúng ta tạo ra Object thông qua từ khóa new
<br>
{% highlight java  %}

public class MyClass {
  int x = 5;

  public static void main(String[] args) {
    MyClass myObj = new MyClass();
    System.out.println(myObj.x);
  }
}

{% endhighlight %}

## **4. Tạo nhiều Object từ một Class**

- Như anh đã nói phần trên từ 1 Class ta có thể tạo ra nhiều đối tượng khác nhau. Class như một bản vẽ thiết kế vậy từ đó cho ra nhiều ngôi nhà
<br>
{% highlight java  %}

public class MyClass {
  int x = 5;

  public static void main(String[] args) {
    MyClass myObj1 = new MyClass();  // Object 1
    MyClass myObj2 = new MyClass();  // Object 2
    System.out.println(myObj1.x);
    System.out.println(myObj2.x);
  }
}

{% endhighlight %}



## **5. Hàm khởi tạo constructor**

- Hàm khởi tạo trong Class là hàm giúp mình tạo ra một đối tượng. Như các em thấy khi mình gọi Car car = new Car(). Lúc này nó sẽ gọi hàm khởi tạo trong Class Car để tạo đối tượng cho mình. Hàm khởi tạo có một đặt điểm là tên hàm khởi tạo phải giống tên của Class và không có kiểu dữ liệu trả về
<br>
{% highlight java  %}

public class Car {
  int x;  // Create a class attribute

  // Create a class constructor for the Car class
  public Car() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    Car myObj = new Car(); // Create an object of class Car (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}

{% endhighlight %}

## **6. Hàm khởi tạo constructor có tham số**

Hàm khởi tạo có thể có tham số truyền vào để khởi tạo một số giá trị có sẵn ban đầu cho đối tượng
<br>
{% highlight java  %}

public class MyClass {
  int x;

  public MyClass(int y) {
    x = y;
  }

  public static void main(String[] args) {
    MyClass myObj = new MyClass(5);
    System.out.println(myObj.x);
  }
}

{% endhighlight %}

## **7. Hàm khởi tạo constructor có nhiều tham số**
<br>
{% highlight java  %}

public class Car {
  int modelYear;
  String modelName;

  public Car(int year, String name) {
    modelYear = year;
    modelName = name;
  }

  public static void main(String[] args) {
    Car myCar = new Car(1969, "Mustang");
    System.out.println(myCar.modelYear + " " + myCar.modelName);
  }
}

{% endhighlight %}

## **8. Thuộc tính**

- Trong mỗi đối tượng đều có thuộc tính của nó. Thuộc tính là những tính chất của đối tượng. Anh lấy ví dụ chiếc xe hơi có màu xanh, sản xuất năm 2020 thì màu xanh (color)và năm sản xuất (model) chính là thuộc tính của chiếc xe hơi. Trong lập trình hướng đối tượng thuộc tính sẽ trở thành các biến trong Class. Như vậy thuộc tính thường là tính từ của đối tượng.
<br>
{% highlight java  %}

public class Car {
  
  private String color;
  
  private int model

}

{% endhighlight %}

## **9. Thao tác với thuộc tính**

Chúng ta có thể lấy thuộc tính bằng sử dụng dấu .
<br>
{% highlight java  %}
public class Car {
  private int model = 2020;

  public static void main(String[] args) {
    Car myObj = new Car();
    int modelCar = myObj.model;
    
  }
}
{% endhighlight %}

## **10. Phương thức**

- Phương thức là những hành động của một đối tượng. Anh ví dụ như chiếc xe hơi có hành động là chạy. Thì chạy chính là phương thức. Phương thức bắt buộc là động từ
<br>
{% highlight java  %}

public class Car {

  static void run() {
    System.out.println("Xe đang chay");
  }
}

{% endhighlight %}

## **10. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **11. Source code**

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Java-Object" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}











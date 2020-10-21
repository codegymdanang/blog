---
layout: course-java
title: Sử dụng Mảng trong lập trình Java
slug : su-dung-mang-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Mảng  
image: /images/blog/java.png

description : Mảng,Array trong ngôn ngữ lập trình Java là gì? Cách lấy và cập nhật giá trị phần tử trong mảng thông qua vị trí index? Cách duyệt qua các phần tử của mảng? Độ dài của mảng? Tìm hiểu hơn về mảng nhiều chiều. Bài viết sẽ lần lượt đi qua các phần trên, cùng với các ví dụ cụ thể trong bài sẽ hướng dẫn bạn cách thao tác với Mảng trong lập trình Java. Từ đó giúp áp dụng ngay vào trong thực hành. 
youtubeId: fR05ShUphxA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em. Hôm nay chủ đề chúng ta chia sẻ sẽ về <b>Mảng trong lập trình Java</b>. Mảng (Array) trong ngôn ngữ <b>lập trình Java</b> là gì? Cách lấy và cập nhật giá trị phần tử trong mảng thông qua vị trí index? Cách duyệt qua các phần tử của mảng? Độ dài của mảng? Tìm hiểu hơn về mảng nhiều chiều. Bài viết sẽ lần lượt đi qua các phần trên, cùng với các ví dụ cụ thể trong bài sẽ hướng dẫn chi tiết cách thao tác với <b>Mảng trong lập trình Java</b>. Từ đó giúp các em có thể áp dụng ngay vào trong thực hành. 


## **1. Mảng trong ngôn ngữ lập trình Java là gì**

Mảng được sử dụng để lưu nhiều giá trị vào một biến. Giả sử nếu không có mảng nếu anh có 1000 sinh viên anh phải tạo 1000 dòng code và biến để lưu 1000 sinh viên. Nhờ có mảng ta chỉ sử dụng 1 dòng code và 1 biến để lưu trữ 1000 sinh viên.

- Chúng ta sử dụng [] để khai báo mảng

{% highlight java  %}

String[] cars;

{% endhighlight %}

- Chúng ta có thể khai báo mảng và chưa các giá trị như sau

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"}; 

{% endhighlight %}

## **2. Lấy giá trị phần tử trong mảng thông qua vị trí index**

- Một đều quan trọng vị trí bắt đầu của mảng luôn là vị trí 0. Trong ví dụ dưới đây vị trí 0 là giá trị Volvo, vị trí 1 là BMW, vị trí 2 là Ford, vị trí 3 là Mazda. Như vậy mảng có 4 phần tử và vị trí luôn luôn bắt đầu là 0.

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
System.out.println(cars[0]);
// Kết quả Volvo
{% endhighlight %}

## **3. Cập nhật giá trị phần tử trong mảng thông qua vị trí index**

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
cars[0] = "Opel";
System.out.println(cars[0]);
// kết quả là Opel chứ không phải là Volvo

{% endhighlight %}

## **4. Độ dài của mảng**

- Để lấy được kích thướt của mảng chứa bao nhiêu phần tử ta dùng phương thức length

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};

System.out.println(cars.length);

// kích thước sẽ là 4. Mảng có chứ 4 phần tử

{% endhighlight %}

## **5. Duyệt qua các phần tử của mảng**

- Chúng ta có thể sử dụng vòng lặp for hoặc for-each để duyệt qua các phần tử

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (int i = 0; i < cars.length; i++) {
  System.out.println(cars[i]);
}

{% endhighlight %}

{% highlight java  %}

String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (String i : cars) {
  System.out.println(i);
}

{% endhighlight %}

## **6. Mảng nhiều chiều**

- Mảng nhiều chiều hay còn gọi là mảng của mảng chứ một hoặc nhiều mảng.

- Khai báo mảng nhiều chiều bằng dấu [][]. Trong ví dụ này là mảng 2 chiều

{% highlight java  %}

int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };

{% endhighlight %}

- Duyệt qua mảng nhiều chiều ta sử dụng 2 vòng lặp. Vòng lặp đầu tiên truy xuất các phần tử trong mảng đầu tiên còn vòng lặp thứ 2 duyệt qua các giá trị trong mảng thứ 2.


{% highlight java  %}

public class MyClass {
  public static void main(String[] args) {
    int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
    for (int i = 0; i < myNumbers.length; ++i) {
      for(int j = 0; j < myNumbers[i].length; ++j) {
        System.out.println(myNumbers[i][j]);
      }
    }
  }
}

{% endhighlight %}





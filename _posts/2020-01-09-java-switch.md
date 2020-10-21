---
layout: course-java
title: Mệnh đề Switch trong lập trình Java
slug : menh-de-switch-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Switch  
image: /images/blog/java.png

description : Bài viết giúp hiểu được lệnh Switch trong ngôn ngữ lập trình Java là gì? Cùng với các ví dụ cụ thể kèm theo, hướng dẫn cách thao tác, cú pháp thực hiện như thế nào với lệnh Switch để đạt được tối ưu nhất. Cũng như chỉ ra những lợi ích mà lệnh Switch mang lại khi sử dụng trong ngôn ngữ lập trình hướng đối tượng Java.
youtubeId: fR05ShUphxA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em. Hôm nay chủ đề của chúng ta sẽ về <b>Switch trong lập trình Java</b>. Switch dùng để chọn thực thi một khối lệnh đúng trong nhiều khối lệnh đưa ra. Câu lệnh Switch trong <b>lập trình Java</b> được sử dụng cho nhiều trường hợp. Người dùng thường chọn sử dụng lệnh Switch thay thế cho các câu lệnh điều kiện If-Else vì tính ngắn gọn, rõ ràng của nó. Các biểu thức sử dụng trong Switch được yêu cầu phải là các kiểu dữ liệu Byte, Short, Int, Long, Enum và có thể là String. Cụ thể Switch là gì, cú pháp để dùng câu lệnh như thế nào, bài chia sẻ dưới đây sẽ giúp bạn hiểu rõ hơn.

- If : kiểm tra nếu đều kiện đúng, ta thực hiện các câu lệnh trong khối lệnh if.
- Else : kiểm tra điều kiện và  thực hiện các khối lệnh ngược lại với điều kiện
- Else If : tạo thêm một điều kiện mới nếu điều kiện trước đó là false
- Switch  : gồm nhiều điều kiện if và else

## **1. Cú pháp Switch**

{% highlight java  %}

switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}

{% endhighlight %}

- switch : sẽ kiểm tra giá trị expression
- case   : nếu giá trị trong expression mà đúng với case thì sẽ chạy khối lệnh trong case
- break  : dùng để thoát ra khỏi switch
- default : khi không có giá trị nào thoả mãn thì sẽ chạy khối lệnh trong default

- Trong ví dụ dưới đây ta kiểm tra xem hôm nay là thứ mấy. Trong mệnh đề switch ta có 7 trường hợp xảy ra từ thứ 2 đến thứ 7. Tuỳ vào giá trị truyền vào là số nào thì sẽ vào case tương ứng. Như ví dụ dưới đây ta truyền vào day = 4 thì nó sẽ rơi vào case 4 và in ra là thứ 5

{% highlight java  %}

int day = 4;
switch (day) {
  case 1:
    System.out.println("Monday");
    break;
  case 2:
    System.out.println("Tuesday");
    break;
  case 3:
    System.out.println("Wednesday");
    break;
  case 4:
    System.out.println("Thursday");
    break;
  case 5:
    System.out.println("Friday");
    break;
  case 6:
    System.out.println("Saturday");
    break;
  case 7:
    System.out.println("Sunday");
    break;
}
//Kết quả là "Thursday" (day 4)
{% endhighlight %}



















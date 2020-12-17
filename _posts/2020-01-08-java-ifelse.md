---
layout: course-java
title: Mệnh đề If Else trong lập trình Java
slug : menh-de-if-else-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: If Else  
image: /images/blog/java.png
description : Bài viết cung cấp kiến thức về mệnh đề điều kiện if else được tạo ra trong lập trình Java. If Else dùng để kiểm tra một điều kiện nào đó có đúng hay không. Các biểu thức điều kiện sẽ trả về 2 giá trị TRUE hoặc FALSE. Cụ thể trong đó gồm các câu lệnh điều kiện If, Else, If Else, If Else rút gọn. Cú pháp thực hiện mỗi câu lệnh điều kiện là khác nhau. Các câu lệnh của các câu điều kiện được đặt trong dấu ngoặc nhọn.
youtubeId: 0zkm4Km8d-A
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em. Hôm nay chủ đề của chúng ta sẽ về <b>If Else trong lập trình Java</b>. Trong bài viết về các loại toán tử trong lập trình bài [trước](https://levunguyen.com/laptrinhjava/2020/01/04/toan-tu/) phần toán tử so sánh. Dựa vào những điều kiện trên ta sẽ thực hiện những hành động khác nhau dựa trên kết quả so sánh. 

Trong <b>ngôn ngữ lập trình hướng đối tượng Java</b> hỗ trợ ta các câu lệnh điều kiện. Mà điều kiện dựa vào các điều kiện mà ta đưa vào để thực hiện các yêu cầu của bài toán

- If : kiểm tra nếu đều kiện đúng, ta thực hiện các câu lệnh trong khối lệnh if.
- Else : kiểm tra điều kiện và  thực hiện các khối lệnh ngược lại với điều kiện
- Else If : tạo thêm một điều kiện mới nếu điều kiện trước đó là false
- Switch  : gồm nhiều điều kiện if và else

## **1. Mệnh đề If**

- Sử dụng if để thực hiện các dòng code bên trong nó nếu điều kiện là đúng

{% highlight java  %}

if (condition) {
  // block of code to be executed if the condition is true
}

{% endhighlight %}

{% highlight java  %}

int x = 20;
int y = 18;
if (x > y) {
  System.out.println("x is greater than y");
}

{% endhighlight %}

## **2. Mệnh đề Else**

- Sử dụng Else để thực thi các dòng code bên trong nó nếu đều kiện là sai

{% highlight java  %}

if (condition) {
  // block of code to be executed if the condition is true
} else {
  // block of code to be executed if the condition is false
}

{% endhighlight %}

{% highlight java  %}

int time = 20;
if (time < 18) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}

{% endhighlight %}

## **3. Mệnh đề If Else**

- Dùng để thực hiện thêm một điều kiện mới nếu điều kiện trước đó là sai

{% highlight java  %}

if (condition1) {
  // block of code to be executed if condition1 is true
} else if (condition2) {
  // block of code to be executed if the condition1 is false and condition2 is true
} else {
  // block of code to be executed if the condition1 is false and condition2 is false
}

{% endhighlight %}

{% highlight java  %}

int time = 22;
if (time < 10) {
  System.out.println("Good morning.");
} else if (time < 20) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}

{% endhighlight %}


## **4. Mệnh đề If Else thu gọn**

{% highlight java  %}

variable = (condition) ? expressionTrue :  expressionFalse;

{% endhighlight %}

- Ví dụ thay vì viết như sau

{% highlight java  %}

int time = 20;
if (time < 18) {
  System.out.println("Good day.");
} else {
  System.out.println("Good evening.");
}

{% endhighlight %}

- Chúng ta có thể viết gọn lại là

{% highlight java  %}

int time = 20;
String result = (time < 18) ? "Good day." : "Good evening.";

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}















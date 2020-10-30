---
layout: course-html
title: Sử dụng thuộc tính style trong HTML   
slug : su-dung-thuoc-tinh-trong-html
category: laptrinhweb
tags: [html]
summery: Style   
image: /images/blog/angular.png
description : Trình bày về các thuộc tính style trong lập trình web HTML. Hướng dẫn cú pháp để khai báo thuộc tính Style, cách thao tác với màu nền cho trang web, màu sắc và font chữ, thiết lập kích thước chữ cũng như cách để canh giữa cho chữ và đoạn văn bản. Chỉ ra các thuộc tính style quan trọng được sử dụng trong lập trình web HTML như background color, color, font-family, font-size, text-align.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình làm với <b>lập trình web HTML</b>, để giúp cho trang web trở nên bắt mắt, đẹp hơn. Lúc này, các lập trình viên sẽ sử dụng <b>thuộc tính style</b> để thêm màu sắc, font chữ và kích thước cho các thành phần web.
<br>
Bài viết dưới đây sẽ hướng dẫn cho các bạn biết được cách thực hiện cú pháp khai báo <b>thuộc tính Style trong HTML</b>, cách để thao tác với màu nền cho trang web, màu sắc và font chữ, thiết lập kích thước chữ cũng như cách để canh giữa cho chữ và đoạn văn bản.


## **1. Thuộc tính Style trong HTML**

Chúng ta sử dụng thuộc tính style trong các thành phần web để thêm màu sắc, font chữ và kích thướt cho các thành phần web giúp trang web trở nên đẹp hơn.

Ví dụ chúng ta sử dụng thuộc tính style trong thẻ p như sau. Ta sẽ thấy các chữ trong thẻ p sẽ được in màu xanh, đỏ

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<body>

<p>I am normal</p>
<p style="color:red;">I am red</p>
<p style="color:blue;">I am blue</p>
<p style="font-size:50px;">I am big</p>

</body>
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![color1](/images/post/html/style.png){:class="img-responsive"}
{: refdef}

## **2. Cú pháp khai báo thuộc tính Style**

{% highlight html linenos %}

<tagname style="property:value;">

{% endhighlight %} 

- tagname : là tên các thành phần web có thể là thẻ p, div và các thẻ khác
- style   : ta khai báo thuộc tính style sẽ được sử dụng trong thẻ HTML
- property và value : ta khai báo thuộc tính và giá trị cho thuộc tính đó. Ở ví dụ trên ta có <p style="color:red;"> nghĩa là ta khai báo màu sắc các chữ trong thẻ p sẽ có màu đỏ. Hoặc <p style="font-size:50px > nghĩa là kích thướt chữ sẽ là 15px.


## **3. Màu nền cho trang web**

Chúng ta có thể chọn màu nền cho trang web bằng thuộc tính background-color như sau.

{% highlight html linenos %}

<body style="background-color:powderblue;">

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>

{% endhighlight %} 

## **4. Màu sắc cho chữ**

Chúng ta có thể thay đổi màu sắc cho chữ bằng cách sử dụng thuộc tính color như sau

{% highlight html linenos %}

<h1 style="color:blue;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

{% endhighlight %} 

## **5. Sử dụng font chữ**

Để thiết lập font chữ ta sử dụng thuột tính font-family như sau

{% highlight html linenos %}

<h1 style="font-family:verdana;">This is a heading</h1>
<p style="font-family:courier;">This is a paragraph.</p>

{% endhighlight %} 

## **6. Thiết lập kích thướt font chữ**

Chúng ta sử dụng thuột tính font-size như sau

{% highlight html linenos %}

<h1 style="font-size:300%;">This is a heading</h1>
<p style="font-size:160%;">This is a paragraph.</p>

{% endhighlight %} 

## **7. Canh giữa cho chữ và đoạn văn bản**

Chúng ta sử dụng thuột tính text-align để canh giữa cho văn bản

{% highlight html linenos %}

<h1 style="text-align:center;">Centered Heading</h1>
<p style="text-align:center;">Centered paragraph.</p>

{% endhighlight %} 

## **7. Kết luận**

Chúng ta sử dụng <b>thuột tính style trong các thành phân của HTML</b> nhằm trang trí cho website trở nên đẹp hơn. Chúng ta sử dụng background-color để tạo ra màu nền cho website và các phần tử web. Sử dụng color để tạo màu cho các chữ. Sử dụng font-family để thiết lập kiểu font. Sử dụng font-size để thiết lập kích thướt nội dung trong website và text-align để canh giữa các đoạn văn bản.












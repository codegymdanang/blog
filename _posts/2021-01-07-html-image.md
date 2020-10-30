---
layout: course-html
title: Sử dụng thẻ Image trong HTML   
slug : su-dung-the-image-trong-html
category: laptrinhweb
tags: [html]
summery: Hình Ảnh   
image: /images/blog/angular.png
description : Trình bày và hướng dẫn các cách sử dụng phổ biến và quan trọng của thẻ hình ảnh img trong lập trình web HTML bao gồm chèn ảnh vào văn bản, thêm kích thước, tạo border, canh chỉnh cho hình ảnh và cách thêm đường link vào hình ảnh. Để sử dụng thẻ hình ảnh image trong HTML, chúng ta sẽ sử dụng các thẻ và các thuộc tính như thẻ img, thẻ a, thuộc tính src, alt, width, height, border, align, href.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình học và làm việc với <b>lập trình web HTML</b>,  chắc hẳn các bạn sẽ cần sử dụng các <b>thẻ hình ảnh img</b> rất nhiều. Vì vậy đòi hỏi người học lập trình web HTML như chúng ta phải nắm vững các loại thẻ cũng như cách sử dụng mỗi loại thẻ hình ảnh img để áp dụng thành thạo khi làm trong các dự án lập trình web HTML.
<br>
Trong phạm vi bài viết này, anh sẽ trình bày về các cách sử dụng <b>thẻ hình ảnh img quan trọng và phổ biến trong lập trình web HTML</b> bao gồm chèn ảnh vào văn bản, thêm kích thước, tạo border, canh chỉnh cho hình ảnh và cách thêm đường link vào hình ảnh. Để sử dụng thẻ hình ảnh image trong HTML, chúng ta sẽ sử dụng các thẻ và các thuộc tính.
<br>
Cụ thể cách thao tác với các thẻ và các thuộc tính như thế nào để sử dụng <b>thẻ hình ảnh trong HTML</b> ? Những chia sẻ dưới đây sẽ sớm giúp bạn giải đáp những thắc mắc trên ngay nhé.


## **1. Chèn ảnh vào văn bản**

Để chèn ảnh vào văn bản ta sử dụng thẻ img với cú pháp như sau

{% highlight html linenos %}

<img src = "Image URL" ... attributes-list/>

{% endhighlight %} 

Ví dụ chúng ta chèn một ảnh test.png vào tài liệu 

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Using Image in Webpage</title>
   </head>
   
   <body>
      <p>Simple Image Insert</p>
      <img src = "/html/images/test.png" alt = "Test Image" />
   </body>
   
</html>

{% endhighlight %} 

- Thuộc tính src : chỉ ra nơi nào chúng ta chứa file ảnh

- Thuộc tính alt : chú thích cho hình ảnh

## **2. Thêm kích thướt cho hình ảnh**

Chúng ta có thể thêm kích thước chiều dài và rộng cho hình ảnh bằng thuộc tính width và height như sau

{% highlight html linenos %}

<!DOCTYPE html>

<html>

   <head>
      <title>Set Image Width and Height</title>
   </head>
   
   <body>
      <p>Setting image width and height</p>
      <img src = "/html/images/test.png" alt = "Test Image" width = "150" height = "100"/>
   </body>
   
</html>

{% endhighlight %}

## **3. Tạo border hình ảnh**

Chúng ta có thể tạo border cho hình ảnh bằng cách dùng thuộc tính border


{% highlight html linenos %}

<!DOCTYPE html>

<html>

   <head>
      <title>Set Image Border</title>
   </head>
   
   <body>
      <p>Setting image Border</p>
      <img src = "/html/images/test.png" alt = "Test Image" border = "3"/>
   </body>
   
</html>

{% endhighlight %}

## **4. Canh chỉnh hình ảnh**

Chúng ta có thể canh chỉnh hình ảnh ở vị trí bên trái, phải hay ở giữa bằng cách sử dụng thuộc tính align như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Set Image Alignment</title>
   </head>
   
   <body>
      <p>Setting image Alignment</p>
      <img src = "/html/images/test.png" alt = "Test Image" border = "3" align = "right"/>
   </body>
   
</html>

{% endhighlight %}

## **5. Image link**

Chúng ta có thể thêm đường link vào ảnh. Khi người dùng click vô ảnh sẽ chạy tới trang web mà chúng ta link đến bằng cách sử dụng thẻ a và thuộc tính href (trang web sẽ được mở)

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Image Hyperlink Example</title>
   </head>
   
   <body>
      <p>Click following link</p>
      <a href = "https://levunguyen.com" target = "_self"> 
         <img src = "/images/logo.png" alt = "Tutorials Point" border = "0"/> 
      </a>
   </body>
   
</html>

{% endhighlight %}






















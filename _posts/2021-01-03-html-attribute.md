---
layout: course-html
title: Thuộc tính trong HTML  
slug : thuoc-tinh-trong-html
category: laptrinhweb
tags: [html]
summery: Thuộc tính   
image: /images/blog/angular.png
description : Nhằm giúp người học lập trình web HTML dễ dàng tìm kiếm và tra cứu các thuộc tính trong thẻ HTML để phục vụ cho việc học và làm việc với các dự án lập trình web. Bài chia sẻ dưới đây sẽ trình bày và hướng dẫn cách sử dụng các thuộc tính trong thẻ HTML bao gồm thuộc tính chính (id , title, class và style) và thuộc tính lang.  Với những chia sẻ lí thuyết có kèm theo các ví dụ minh hoạ cho mỗi thuộc tính trong thẻ HTML trong bài viết. Người học lập trình web HTML có thể  hiểu và tự tin sử dụng được vào quá trình làm các dự án lập trình web HTML. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Nhằm giúp người học <b>lập trình web HTML</b> dễ dàng tìm kiếm và tra cứu các <b>thuộc tính trong thẻ HTML</b> để phục vụ cho việc học và làm việc với các dự án <b>lập trình web</b>
Bài chia sẻ dưới đây sẽ trình bày và hướng dẫn cách sử dụng các thuộc tính trong thẻ HTML bao gồm thuộc tính chính (id , title, class và style) và thuộc tính lang.  

<br>
Hi vọng với những chia sẻ lí thuyết có kèm theo các ví dụ minh hoạ cho mỗi <b>thuộc tính trong thẻ HTML</b> trong bài viết dưới đây. Các bạn học lập trình web HTML có thể nắm bắt và áp dụng được vào quá trình thực hành làm <b>lập trình web HTML</b>.


## **1. Thuộc tính trong thẻ HTML**

Hầu hết các thể HTML đều có thuộc tính để chúng ta có thể thêm một số thành phần cho thẻ HTML. Thuộc tính được khai báo với cú pháp là name và giá trị. Ví dụ như thẻ p sau đây. Chúng ta khai báo thuột tính align (canh chỉnh vị trí văn bản) có giá trị là center (canh giá trị văn bản trong thẻ p là ở giữa)

{% highlight html linenos %}

<!DOCTYPE html> 
<html>
 
   <head> 
      <title>Align Attribute  Example</title> 
   </head>
   
   <body> 
      <p align = "left">This is left aligned</p> 
      <p align = "center">This is center aligned</p> 
      <p align = "right">This is right aligned</p> 
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![attribute](/images/post/html/attribute1.png){:class="img-responsive"}
{: refdef}

## **2. Thuộc tính chính HTML**

Có 4 loại thuộc tính chính được dùng trong các phần tử HTML đó là : id , title, class và style

- id : giống như mình đặt tên (định danh) cho một phần tử HTML. Mục đích đặt id để sau này mình có thể lấy được phần tử web để xử lý thông qua id.

Ví dụ

{% highlight html linenos %}

<p id = "html">This para explains what is HTML</p>
<p id = "css">This para explains what is Cascading Style Sheet</p>

{% endhighlight %} 


- title : Đặt tiêu đề cho một phần tử web

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>The title Attribute Example</title>
   </head>
   
   <body>
      <h3 title = "Hello HTML!">Titled Heading Tag Example</h3>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![attribute2](/images/post/html/attribute2.png){:class="img-responsive"}
{: refdef}

- class : được sử dụng để ta trang trí màu sắc, chỉnh lại giao diện của phần tử web. Một phần tử HTML có thể có một hoặc nhiều class.

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>The style Attribute</title>
   </head>
   
   <body>
      <p class = "redhat">Some text...</p>
   </body>
   
</html>

{% endhighlight %} 

- style : cũng giống như class nhưng trong style ta thêm thẳng giá trị css vào

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>The style Attribute</title>
   </head>
   
   <body>
      <p style = "font-family:arial; color:#FF0000;">Some text...</p>
   </body>
   
</html>

{% endhighlight %} 

## **3. Thuộc tính lang HTML**

Thuộc tính lang giúp chúng ta khai báo là ngôn ngữ chính hiển thị trong trang web là tiếng Anh hoặc tiếng Việt hay một thứ tiếng bất kỳ. Ví dụ chúng ta muốn khai báo là trang web đang sử dụng tiếng anh thì ta thêm thuộc tính lang = en trong thẻ bắt đầu của HTML như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html lang = "en">

   <head>
      <title>English Language Page</title>
   </head>

   <body>
      This page is using English Language
   </body>

</html>

{% endhighlight %} 













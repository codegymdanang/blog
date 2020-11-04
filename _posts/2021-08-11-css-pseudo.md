---
layout: course-css
title: Sử dụng Pseudo Class trong CSS
slug : su-dung-pseudo-class-trong-css
category: laptrinhweb
tags: [css]
summery: Pseudo Class 
image: /images/blog/angular.png
description : Bài viết lần lượt đi qua các phần bao gồm giải thích cho các bạn hiểu được Pseudo Class là gì? Các hiệu ứng có thể sử dụng như link pseudo class, visited pseudo class, hover pseudo class, active pseudo class, focus pseudo class và cách tạo hiệu ứng phần tử con đầu tiên trong lập trình web CSS. Kèm theo các ví dụ minh hoạ hướng dẫn sử dụng đối với mỗi giá trị hiệu ứng trong lập trình web CSS.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Thuộc tính <b>Pseudo Class</b> và Pseudo Element trong <b>lập trình web CSS</b> thường rất dễ bị nhầm lẫn, kể cả một số các bạn lập trình viên đã đi làm đôi khi vẫn không phân biệt rõ ràng được. Vì vậy để giúp các bạn-những người học <b>lập trình web</b> có thể nhận biết được sự khác nhau giữa hai thuộc tính Pseudo Class và Pseudo Element để chọn đúng thuộc tính phù hợp áp dụng vào làm web. Anh đã có bài chia sẻ về Pseudo Element, các bạn có thể xem tại đây. Và trong bài viết này, anh sẽ chia sẻ về Pseudo Class. Hi vọng qua 2 bài viết này, các bạn sẽ hiểu rõ được 2 thuộc tính và áp dụng được vào làm web mà không bị nhầm lẫn nữa.
<br?
Trong bài viết này anh sẽ lần lượt đi qua các phần bao gồm giải thích cho các bạn hiểu được <b>Pseudo Class</b> là gì? Các hiệu ứng có thể sử dụng như link pseudo-class, visited pseudo-class, hover pseudo-class, active pseudo-class, focus pseudo-class và cách tạo hiệu ứng phần tử con đầu tiên trong <b>lập trình web</b> CSS.


## **1. Pseudo Class là gì**

Chúng ta sử dụng pseduo class để thêm hiệu ứng cho một số thành phần trong web, ví dụ khi người dùng sử dụng con chuột di chuyển qua các phần tử web mình có thể xây dựng các hiệu ứng cho hành động này hoặc khi người dùng rê chuột vào một đường link mình có thể thêm hiệu ứng thay đổi màu sắc. Mình không cần dùng javascript để làm hiệu ứng mà cái này có sẵn trong css

- Cú pháp như sau

{% highlight html linenos %}

selector:pseudo-class {property: value}

{% endhighlight %}

- Hoặc ta cũng có thể kết hợp với css class

{% highlight html linenos %}

selector.class:pseudo-class {property: value}

{% endhighlight %}

## **2. Hiệu ứng :link pseudo-class**

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         a:link {color:#000000}
      </style>
   </head>

   <body>
      <a href = "">Black Link</a>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo1](/images/post/css/pseudo1.png){:class="img-responsive"}
{: refdef}

- Link Backlink sẽ có màu đen

## **3. Hiệu ứng :visited pseudo-class**

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         a:visited {color: #006600}
      </style>
   </head>

   <body>
      <a href = "">Click this link</a>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo2](/images/post/css/pseudo2.png){:class="img-responsive"}
{: refdef}

- Khi click vào link sẽ có hiệu ứng biến màu của link thành màu xanh lục.

## **4. Hiệu ứng :hover pseudo-class**

Khi di chuyển chuột ngang qua đường link thì sẽ đổi màu

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         a:hover {color: #FFCC00}
      </style>
   </head>

   <body>
      <a href = "">Bring Mouse Here</a>
   </body>
</html> 

{% endhighlight %}

## **5. Hiệu ứng :active pseudo-class**

{% highlight html linenos %}


<html>
   <head>
      <style type = "text/css">
         a:active {color: #FF00CC}
      </style>
   </head>

   <body>
      <a href = "">Click This Link</a>
   </body>
</html>

{% endhighlight %}

## **6. Hiệu ứng :focus pseudo-class**

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         a:focus {color: #0000FF}
      </style>
   </head>

   <body>
      <a href = "">Click this Link</a>
   </body>
</html> 

{% endhighlight %}

## **7. Hiệu ứng phần tử con đầu tiên**

Trong ví dụ này ta có thẻ div, bên trong nó có 2 thẻ P . Nhưng bây giờ chúng ta chỉ muốn lấy thẻ p đầu tiên. Ta sử dụng first-child

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         div > p:first-child {
            text-indent: 25px;
         }
      </style>
   </head>

   <body>
   
      <div>
         <p>First paragraph in div. This paragraph will be indented</p>
         <p>Second paragraph in div. This paragraph will not be indented</p>
      </div>
      <p>But it will not match the paragraph in this HTML:</p>
      
      <div>
         <h3>Heading</h3>
         <p>The first paragraph inside the div. This paragraph will not be effected.</p>
      </div>
      
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo3](/images/post/css/pseudo3.png){:class="img-responsive"}
{: refdef}












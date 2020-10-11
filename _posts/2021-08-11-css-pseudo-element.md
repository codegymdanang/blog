---
layout: course-css
title: Sử dụng Pseudo Element trong CSS
slug : su-dung-pseudo-element-trong-css
category: laptrinhweb
tags: [css]
summery: Pseudo Element 
image: /images/blog/angular.png
description : Sử dụng Pseudo Element trong trong dự án làm web. Hướng dẫn Sử dụng Pseudo Element trong CSS vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>Pseudo Element</b> là như thế nào?


# **1. Pseudo Element là gì**

Chúng ta sử dụng pseduo element để thêm các hiệu ứng vào các phần tử của HTML mà không cần dùng Javascript hay bất cứ một thư viện nào khác vào

- Cú pháp như sau

{% highlight html linenos %}

selector:pseudo-element {property: value}

{% endhighlight %}

- Một số Pseudo Element hay dùng là 

+ :first-line : Sử dụng để thêm các hiệu ứng đặt biệt vào dòng đầu tiên của văn bản 
+ :first-letter : Sử dụng để thêm các hiệu ứng vào chữ đầu tiên của văn bản
+ :before   : thêm nội dung trước một phần tử
+ :after    : thêm nội dung sau một phần tử

# **2. Sử dụng :first-line trong CSS**

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         p:first-line { text-decoration: underline; }
         p.noline:first-line { text-decoration: none; }
      </style>
   </head>

   <body>
      <p class = "noline">
         This line would not have any underline because this belongs to nline class.
      </p>
      
      <p>
         The first line of this paragraph will be underlined as defined in the 
         CSS rule above. Rest of the lines in this paragraph will remain normal. 
         This example shows how to use :first-line pseduo element to give effect 
         to the first line of any HTML element.
      </p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo-firstline](/images/post/css/pseudo-firstline.png){:class="img-responsive"}
{: refdef}

# **3. Sử dụng :first-letter trong CSS**

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         p:first-letter { font-size: 5em; }
         p.normal:first-letter { font-size: 10px; }
      </style>
   </head>

   <body>
      <p class = "normal">
         First character of this paragraph will be normal and will have font size 10 px;
      </p>
      
      <p>
         The first character of this paragraph will be 5em big as defined in the 
         CSS rule above. Rest of the characters in this paragraph will remain 
         normal. This example shows how to use :first-letter pseduo element 
         to give effect to the first characters  of any HTML element.
      </p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo-firstletter](/images/post/css/pseudo-firstletter.png){:class="img-responsive"}
{: refdef}

# **4. Sử dụng :before trong CSS**

Chúng ta sẽ thêm ảnh trước thẻ P như sau.

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         p:before {
            content: url(/images/bullet.gif)
         }
      </style>
   </head>

   <body>
      <p> This line will be preceded by a bullet.</p>
      <p> This line will be preceded by a bullet.</p>
      <p> This line will be preceded by a bullet.</p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo-before](/images/post/css/pseudo-before.png){:class="img-responsive"}
{: refdef}

# **5. Sử dụng :after trong CSS**

Chúng ta sẽ thêm ảnh sau thẻ P như sau.

{% highlight html linenos %}

<html>
   <head>
      <style type = "text/css">
         p:after {
            content: url(/images/bullet.gif)
         }
      </style>
   </head>

   <body>
      <p> This line will be succeeded by a bullet.</p>
      <p> This line will be succeeded by a bullet.</p>
      <p> This line will be succeeded by a bullet.</p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![pseudo-before](/images/post/css/pseudo-before.png){:class="img-responsive"}
{: refdef}




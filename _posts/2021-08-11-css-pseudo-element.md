---
layout: course-css
title: Sử dụng Pseudo Element trong CSS
slug : su-dung-pseudo-element-trong-css
category: laptrinhweb
tags: [css]
summery: Pseudo Element 
image: /images/blog/angular.png
description : Trong lập trình web, nếu muốn tạo các hiệu ứng cho các phần tử trong HTML, chúng ta sẽ cần sử dụng thuộc tính Pseudo Element trong CSS. Sử dụng thuộc tính Pseudo Element giúp tạo ra các hiệu ứng như hiệu ứng đặc biệt cho chữ, dòng đầu tiên của văn bản, thêm nội dung vào trước hoặc sau một phần tử. Bài viết này sẽ giúp bạn hiểu rõ hơn về Pseudo Element là gì? Hướng dẫn cách sử dụng các giá trị trong thuộc tính Pseudo Element gồm first-line, first-letter, before, after trong CSS. Kèm theo các ví dụ minh hoạ cụ thể cách thao tác với mỗi giá trị trong bài viết sẽ giúp bạn áp dụng ngay vào thực hành và làm các dự án web.
youtubeId: BpEyoVI3erw
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Đối với những lập trình viên trong quá trình <b>lập trình web</b>, để làm ra được một trang website hoàn thiện thì đòi hỏi phải thực hiện qua nhiều bước khác nhau. Trong đó bao gồm có các bước giúp cho website có giao diện bắt mắt hơn nhờ vào các hiệu ứng như hiệu ứng đặc biệt cho chữ, dòng đầu tiên của văn bản, thêm nội dung vào trước hoặc sau một phần tử. Để sử dụng được các hiệu ứng đó vào trong trang web, chúng ta sẽ sử dụng <b>thuộc tính Pseudo Element trong lập trình web CSS</b>.
<br>
Vậy <b>thuộc tính Pseudo Element trong lập trình web</b/> là gì? Cách sử dụng các giá trị trong <b>thuộc tính Pseudo Element</b> gồm first-line, first-letter, before, after trong CSS như thế nào? Trong những chia sẻ ngay dưới đây, anh sẽ giúp các bạn giải đáp những thắc mắc trên từ đó có thể tự tin hơn với kiến thức về Pseudo Element để áp dụng được vào quá trình làm các dự án web.



## **1. Pseudo Element là gì**

Chúng ta sử dụng pseudo element để thêm các hiệu ứng vào các phần tử của HTML mà không cần dùng Javascript hay bất cứ một thư viện nào khác vào

- Cú pháp như sau

{% highlight html linenos %}

selector:pseudo-element {property: value}

{% endhighlight %}

- Một số Pseudo Element hay dùng là 

+ :first-line : Sử dụng để thêm các hiệu ứng đặt biệt vào dòng đầu tiên của văn bản 
+ :first-letter : Sử dụng để thêm các hiệu ứng vào chữ đầu tiên của văn bản
+ :before   : thêm nội dung trước một phần tử
+ :after    : thêm nội dung sau một phần tử

## **2. Sử dụng :first-line trong CSS**

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

## **3. Sử dụng :first-letter trong CSS**

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

## **4. Sử dụng :before trong CSS**

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

## **5. Sử dụng :after trong CSS**

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
![pseudo-after](/images/post/css/pseudo-after.png){:class="img-responsive"}
{: refdef}

## **6. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


## **7. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/CSS-Fundamental" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

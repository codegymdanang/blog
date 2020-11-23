---
layout: course-css
title: Sử dụng Margin trong CSS
slug : su-dung-margin-trong-css
category: laptrinhweb
tags: [css]
summery: Margin 
image: /images/blog/angular.png
description : Trong lập trình web CSS, để bố cục một trang web, đoạn văn cân đối và rõ ràng, CSS cung cấp thuộc tính margin để thiết lập được khoảng cách giữa các phần tử trong HTM. Trong đó bao gồm các giá trị như margin bottom canh dưới, margin top canh trên, margin left canh trái và margin right canh phải. Bài viết giới thiệu giúp hiểu được thuộc tính margin trong lập trình web CSS là gì? Các giá trị sử dụng trong thuộc tính này cũng như sẽ đi sâu vào hướng dẫn cụ thể cách làm của mỗi giá trị. Và trong mỗi giá trị như vậy có kèm theo ví dụ minh hoạ cách thao tác cụ thể để người học lập trình web dễ dàng nắm bắt và áp dụng được vào quá trình thực hành, làm việc với các dự án.
youtubeId: _9kxE9m-znI
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web CSS</b>, để bố cục một trang web, đoạn văn cân đối và rõ ràng, giúp người dùng có những trải nghiệm tốt hơn. CSS cung cấp <b>thuộc tính margin</b> để thiết lập được khoảng cách giữa các phần tử trong HTM. Trong đó bao gồm các giá trị như margin-bottom canh dưới, margin-top canh trên, margin-left canh trái và margin-right canh phải.
<br>
Trong các phần chia sẻ ngay dưới đây, anh sẽ lần lượt giới thiệu để các bạn hiểu được <b>thuộc tính margin trong lập trình web CSS</b> là gì? Các giá trị sử dụng trong thuộc tính này cũng như sẽ đi sâu vào hướng dẫn cụ thể cách làm của mỗi giá trị. Và trong mỗi giá trị như vậy anh sẽ kèm theo ví dụ minh hoạ cách thao tác cụ thể để bạn dễ dàng nắm bắt và áp dụng được vào quá trình thực hành, làm việc với các dự án <b>lập trình web</b>.

## **1. Margin là gì**

Chúng ta sử dụng <b>thuộc tính margin</b> để thiết lập khoảng cách giữa các phần tử trong HTML. Margin gồm có các giá trị như margin-bottom canh dưới, margin-top canh trên, margin-left canh trái, và margin-right canh phải


## **2. Thuộc tính Margin**

Ví dụ như anh sẽ thiết lập <b>4 thuộc tính của margin</b> cho đoạn văn bản như sau.

{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "margin: 15px; border:1px solid black;">
         all four margins will be 15px
      </p>
      
      <p style = "margin:10px 2%; border:1px solid black;">
         top and bottom margin will be 10px, left and right margin will be 2% 
         of the total width of the document.
      </p>
      
      <p style = "margin: 10px 2% -10px; border:1px solid black;">
         top margin will be 10px, left and right margin will be 2% of the 
         total width of the document, bottom margin will be -10px
      </p>
      
      <p style = "margin: 10px 2% -10px auto; border:1px solid black;">
         top margin will be 10px, right margin will be 2% of the total 
         width of the document, bottom margin will be -10px, left margin 
         will be set by the browser
      </p>
   </body>
</html> 
{% endhighlight %}

{:refdef: style="text-align: center;"}
![margin1](/images/post/css/margin1.png){:class="img-responsive"}
{: refdef}

## **3. Thuộc tính Margin bottom**

Sử dụng để canh chỉnh ở phần dưới của phần tử web. Chúng ta có các giá trị là pixel hoặc %

{% highlight html linenos %}

<html>
   <head>
   </head>

   <body>
      <p style = "margin-bottom: 15px; border:1px solid black;">
         This is a paragraph with a specified bottom margin
      </p>
      
      <p style = "margin-bottom: 5%; border:1px solid black;">
         This is another paragraph with a specified bottom margin in percent
      </p>
   </body>
</html> 
{% endhighlight %}

{:refdef: style="text-align: center;"}
![margin2](/images/post/css/margin2.png){:class="img-responsive"}
{: refdef}

## **4. Thuộc tính Margin top**

Sử dụng để canh chỉnh ở phần trên của phần tử web. Chúng ta có các giá trị là pixel hoặc %

{% highlight html linenos %}

<html>
   <head>
   </head>

   <body>
      <p style = "margin-top: 15px; border:1px solid black;">
         This is a paragraph with a specified top margin
      </p>
      
      <p style = "margin-top: 5%; border:1px solid black;">
         This is another paragraph with a specified top margin in percent
      </p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![margin3](/images/post/css/margin3.png){:class="img-responsive"}
{: refdef}

## **5. Thuộc tính Margin left**

Sử dụng để canh chỉnh ở phần bên trái của phần tử web. Chúng ta có các giá trị là pixel hoặc %

{% highlight html linenos %}

<html>
   <head>
   </head>

   <body>
      <p style = "margin-left: 15px; border:1px solid black;">
         This is a paragraph with a specified left margin
      </p>
      
      <p style = "margin-left: 5%; border:1px solid black;">
         This is another paragraph with a specified top margin in percent
      </p>
   </body>
</html> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![margin4](/images/post/css/margin4.png){:class="img-responsive"}
{: refdef}

## **6. Thuộc tính Margin right**

Sử dụng để canh chỉnh ở phần bên phải của phần tử web. Chúng ta có các giá trị là pixel hoặc %

{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "margin-right: 15px; border:1px solid black;">
         This is a paragraph with a specified right margin
      </p>
      <p style = "margin-right: 5%; border:1px solid black;">
         This is another paragraph with a specified right margin in percent
      </p>
   </body>
</html> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![margin5](/images/post/css/margin5.png){:class="img-responsive"}
{: refdef}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}













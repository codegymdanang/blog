---
layout: course-css
title: Sử dụng Padding trong CSS
slug : su-dung-padding-trong-css
category: laptrinhweb
tags: [css]
summery: Padding 
image: /images/blog/angular.png
description : Trong lập trình web CSS, bên cạnh thiết lập khoảng cách giữa các phần tử HTML, thì lập trình viên cũng cần thiết lập khoảng cách giữa các nội dung trong một phần tử web. Để thực hiện được, ta sẽ sử dụng thuộc tính padding để canh chỉnh gồm có các giá trị padding bottom canh chỉnh dưới, padding top canh chỉnh trên, padding left canh chỉnh trái và padding right canh chỉnh phải. Bài viết giới thiệu về thuộc tính padding trong lập trình web là gì? Các giá trị có trong thuộc tính này cũng như đi sâu vào hướng dẫn cụ thể cách làm của mỗi giá trị. Đồng thời kèm theo ví dụ minh hoạ cách thao tác cụ thể để bạn dễ dàng nắm bắt và áp dụng vào quá trình làm việc với các dự án lập trình web.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web CSS</b>, để bố cục một trang web, nội dung cân đối và rõ ràng, giúp người dùng có những trải nghiệm tốt hơn. Bên cạnh thiết lập khoảng cách giữa các phần tử trong HTML, thì các lập trình viên cũng cần thiết lập khoảng cách giữa các nội dung trong một phần tử web. Để thực hiện được thao tác này, CSS cung cấp cho chúng ta <b>thuộc tính padding</b> để áp dụng vào <b>lập trình web</b>. Trong đó có các giá trị bao gồm padding-bottom canh chỉnh dưới, padding-top canh chỉnh trên, padding-left canh chỉnh trái và padding-right canh chỉnh phải.
<br>
Trong các phần chia sẻ ngay dưới đây, anh sẽ lần lượt giới thiệu để các bạn hiểu được <b>thuộc tính padding trong lập trình web</b> là gì? Các giá trị sử dụng trong thuộc tính này cũng như sẽ đi sâu vào hướng dẫn cụ thể cách làm của mỗi giá trị. Trong mỗi giá trị như vậy anh sẽ kèm theo ví dụ minh hoạ cách thao tác cụ thể để bạn dễ dàng nắm bắt và áp dụng được vào quá trình thực hành, làm việc với các dự án <b>lập trình web</b>.


## **1. Padding là gì**

Chúng ta sử dụng <b>thuộc tính padding</b> để thiết lập khoảng cách giữa các nội dung trong một phần tử web. Các thuộc tính của padding bao gồm padding-bottom canh chỉnh  dưới, padding-top canh chỉnh trên, padding-left canh chỉnh trái, và padding-right canh chỉnh phải.


## **2. Thuộc tính Padding-bottom**

Dùng để thiết lập canh dưới cho nội dung bên trong của phần tử. Chúng ta sử dụng thuộc tính padding-bottom


{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "padding-bottom: 15px; border:1px solid black;">
         This is a paragraph with a specified bottom padding
      </p>
      
      <p style = "padding-bottom: 5%; border:1px solid black;">
         This is another paragraph with a specified bottom padding in percent
      </p>
   </body>
</html> 
{% endhighlight %}

{:refdef: style="text-align: center;"}
![padding1](/images/post/css/padding1.png){:class="img-responsive"}
{: refdef}


## **3. Thuộc tính Padding-top**

Dùng để thiết lập canh phía trên cho nội dung bên trong của phần tử. Chúng ta sử dụng thuộc tính padding-top


{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "padding-top: 15px; border:1px solid black;">
         This is a paragraph with a specified top padding
      </p>
      
      <p style = "padding-top: 5%; border:1px solid black;">
         This is another paragraph with a specified top padding in percent
      </p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![padding2](/images/post/css/padding2.png){:class="img-responsive"}
{: refdef}

## **4. Thuộc tính Padding-left**

Dùng để thiết lập canh trái cho nội dung bên trong của phần tử. Chúng ta sử dụng thuộc tính padding-left


{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "padding-left: 15px; border:1px solid black;">
         This is a paragraph with a specified left padding
      </p>
      
      <p style = "padding-left: 15%; border:1px solid black;">
         This is another paragraph with a specified left padding in percent
      </p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![padding3](/images/post/css/padding3.png){:class="img-responsive"}
{: refdef}

## **5. Thuộc tính Padding-right**

Dùng để thiết lập canh phải cho nội dung bên trong của phần tử. Chúng ta sử dụng thuộc tính padding-right


{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "padding-right: 15px; border:1px solid black;">
         This is a paragraph with a specified right padding
      </p>
      
      <p style = "padding-right: 5%; border:1px solid black;">
         This is another paragraph with a specified right padding in percent
      </p>
   </body>
</html> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![padding4](/images/post/css/padding4.png){:class="img-responsive"}
{: refdef}

## **6. Thuộc tính Padding**

Chúng ta sử dụng thuộc tính padding để canh trái, phải, trên dưới cho nội dung bên trong của phần tử. Chúng ta sử dụng thuộc tính padding


{% highlight html linenos %}

<html>
   <head>
   </head>
   
   <body>
      <p style = "padding: 15px; border:1px solid black;">
         all four padding will be 15px 
      </p> 
      
      <p style = "padding:10px 2%; border:1px solid black;"> 
         top and bottom padding will be 10px, left and right
         padding will be 2% of the total width of the document. 
      </p> 
      
      <p style = "padding: 10px 2% 10px; border:1px solid black;">
         top padding will be 10px, left and right padding will 
         be 2% of the total width of the document, bottom padding will be 10px
      </p> 
      
      <p style = "padding: 10px 2% 10px 10px; border:1px solid black;">
         top padding will be 10px, right padding will be 2% of
         the total width of the document, bottom padding and top padding will be 10px 
      </p>
   </body>
</html> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![padding5](/images/post/css/padding5.png){:class="img-responsive"}
{: refdef}






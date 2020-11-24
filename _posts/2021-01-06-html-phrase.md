---
layout: course-html
title: Sử dụng các thẻ cụm từ trong HTML   
slug : su-dung-cac-the-cum-tu-trong-html
category: laptrinhweb
tags: [html]
summery: Cụm từ   
image: /images/blog/angular.png
description : Bài viết giới thiệu và hướng dẫn cách thao tác thông qua các ví dụ minh hoạ kèm theo trong bài. Nhằm giúp các bạn sử dụng được các thẻ cụm từ phrasal trong lập trình web HTML bao gồm các thẻ em, mark, strong, abbr, blockquote, code và thẻ address. Trong đó, mỗi thẻ có chức năng khác nhau như nhấn mạnh, highlight, in đậm, gạch dưới hay trích dẫn văn bản, hiển thị địa chỉ hay nhúng source code của các ngôn ngữ vào html. 
youtubeId: LOKdU1QaJEA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web HTML</b>, mỗi <b>thẻ cụm từ phrasal</b> được tạo ra cho mỗi mục đích cụ thể khác nhau. Để giúp các bạn hiểu rõ hơn về các thẻ cụm từ trong HTML, bài viết này anh sẽ giới thiệu và hướng dẫn cách thao tác để các bạn sử dụng được các <b>thẻ cụm từ phrasal trong lập trình web HTML</b> bao gồm các thẻ em, mark, strong, abbr, blockquote, code và thẻ address. Trong đó, mỗi thẻ có chức năng khác nhau như nhấn mạnh, highlight, in đậm, gạch dưới hay trích dẫn văn bản, hiển thị địa chỉ hay nhúng source code của các ngôn ngữ vào html. 
<br>
Vậy để nắm kĩ hơn chức năng mỗi thẻ cũng như cách thực hiện với các <b>thẻ cụm từ phrasal trong lập trình web HTML</b>, các bạn đọc thêm những chia sẻ dưới đây nhé!.  


## **1. Nhấn mạnh văn bản**

Để nhấn mạnh một nội dung trong văn bản ta sử dụng thẻ em như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Emphasized Text Example</title>
   </head>
   
   <body>
      <p>The following word uses an <em>emphasized</em> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![phrase1](/images/post/html/phrase1.png){:class="img-responsive"}
{: refdef}


## **2. Highlight văn bản**

Chúng ta sử dụng thẻ mark để làm highlight một từ hoặc nhiều từ như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Marked Text Example</title>
   </head>
   
   <body>
      <p>The following word has been <mark>marked</mark> with yellow</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![phrase2](/images/post/html/phrase2.png){:class="img-responsive"}
{: refdef}


## **3. In đậm văn bản**

Chúng ta sử dụng thẻ strong để in đậm chữ

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Strong Text Example</title>
   </head>
   
   <body>
      <p>The following word uses a <strong>strong</strong> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![phrase3](/images/post/html/phrase3.png){:class="img-responsive"}
{: refdef}

## **4. Gạch dưới văn bản**

Chúng ta muốn gạch dưới một từ thì sử dụng thẻ abbr như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Text Abbreviation</title>
   </head>
   
   <body>
      <p>My best friend's name is  <abbr title = "Abhishek">Abhy</abbr>.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![phrase4](/images/post/html/phrase4.png){:class="img-responsive"}
{: refdef}

## **5. Trích dẫn văn bản**

Để trích dẫn một văn bản ở nơi khác vào trang web của mình chúng ta sử dụng thẻ blockquote như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Blockquote Example</title>
   </head>
   
   <body>
      <p>The following description of XHTML is taken from the W3C Web site:</p>

      <blockquote>XHTML 1.0 is the W3C's first Recommendation for XHTML,following on 
         from earlier work on HTML 4.01, HTML 4.0, HTML 3.2 and HTML 2.0.</blockquote>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![phrase5](/images/post/html/phrase5.png){:class="img-responsive"}
{: refdef}

## **6. Nhúng source code của các ngôn ngữ vào html**

Chúng ta có thể hiển thị code của các ngôn ngữ lên trang web bằng cách sử dụng thẻ code như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   
   <head>
      <title>Computer Code Example</title>
   </head>
   
   <body>
      <p>Regular text. <code>This is code.</code> Regular text.</p>
   </body>
   
</html>

{% endhighlight %} 

## **7. Địa chỉ**

Chúng ta sử dụng thẻ address để hiển thị địa chỉ như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   
   <head>
      <title>Address Example</title>
   </head>
   
   <body>
      <address>388A, Road No 22, Jubilee Hills -  Hyderabad</address>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}














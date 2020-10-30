---
layout: course-html
title: Sử dụng định dạng text trong HTML   
slug : su-dung-dinh-dang-text-trong-html
category: laptrinhweb
tags: [html]
summery: Formatting   
image: /images/blog/angular.png
description : Nằm trong chuỗi các bài viết chia sẻ về lập trình web HTML từ cơ bản tới nâng cao, bài viết này sẽ tiếp theo giới thiệu đến các bạn về các định dạng text trong HTML. Bên cạnh giới thiệu các kiểu định dạng có trong HTML, trong bài viết cũng sẽ hướng dẫn các bạn, những người học lập trình web HTML cách thao tác như thể nào với các định dạng bao gồm: Hiển thị chữ đậm, nghiêng, gạch chân, gạch ngang đoạn text, monospace chữ, superscript chữ, chèn thêm chữ, sử dụng chữ to, chữ nhỏ hơn, và cách để nhóm các thẻ lại với nhau trong lập trình web HTML. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Nằm trong chuỗi các bài viết chia sẻ về <b>lập trình web HTML từ cơ bản tới nâng cao</b>, hôm nay anh sẽ tiếp theo giới thiệu đến các bạn về các <b>định dạng text (formating) trong HTML</b>. Bên cạnh giới thiệu <b>các kiểu định dạng (formating) có trong HTML</b>, anh cũng sẽ hướng dẫn các bạn – những người học <b>lập trình web HTML</b> cách thao tác như thể nào với các định dạng bao gồm: Hiển thị chữ đậm, nghiêng, gạch chân, gạch ngang đoạn text, monospace chữ, superscript chữ, chèn thêm chữ, sử dụng chữ to, chữ nhỏ hơn, và cách để nhóm các thẻ lại với nhau trong <b>lập trình web HTML</b>. 
<br>
Để biết cụ thể như thế nào thì chúng ta hãy tiếp tục đọc những chia sẻ bên dưới ngay nhé!


## **1. Hiển thị chữ đậm**

Để hiển thị chữ đậm trong <b>HTML</b> ta dùng thẻ b như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Bold Text Example</title>
   </head>
   
   <body>
      <p>The following word uses a <b>bold</b> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating1](/images/post/html/formating1.png){:class="img-responsive"}
{: refdef}

## **2. Hiển thị nghiêng**

Để hiển thị chữ nghiêng ta dùng thẻ i như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Italic Text Example</title>
   </head>
   
   <body>
      <p>The following word uses an <i>italicized</i> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating2](/images/post/html/formating2.png){:class="img-responsive"}
{: refdef}

## **3. Gạch chân đoạn text**

Để gạch chân đoạn text ta sử dụng thẻ u như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Underlined Text Example</title>
   </head>
   
   <body>
      <p>The following word uses an <u>underlined</u> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating3](/images/post/html/formating3.png){:class="img-responsive"}
{: refdef}

## **4. Gạch ngang đoạn text**

Để gạch ngang đoạn text ta sử dụng thẻ strike như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Strike Text Example</title>
   </head>
   
   <body>
      <p>The following word uses a <strike>strikethrough</strike> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating4](/images/post/html/formating4.png){:class="img-responsive"}
{: refdef}

## **5. Monospace chữ**

Chúng ta có thể làm một số chữ nhỏ hơn trong cùng một câu bằng cách dùng thẻ tt như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Monospaced Font Example</title>
   </head>
   
   <body>
      <p>The following word uses a <tt>monospaced</tt> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating5](/images/post/html/formating5.png){:class="img-responsive"}
{: refdef}

## **6. Superscript chữ**

Ví dụ như ta muốn làm đơn vị đo là m2. Số 2 được đưa lên phía trên thì ta dùng thẻ sup như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Superscript Text Example</title>
   </head>
   
   <body>
      <p>The following word uses a <sup>superscript</sup> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating6](/images/post/html/formating6.png){:class="img-responsive"}
{: refdef}

## **7. Chèn thêm chữ**

Chúng ta có thể chèn thêm chữ vào đoạn văn bằng thẻ ins và delete chữ bằng thẻ del như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Inserted Text Example</title>
   </head>
   
   <body>
      <p>I want to drink <del>cola</del> <ins>wine</ins></p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating7](/images/post/html/formating7.png){:class="img-responsive"}
{: refdef}

## **8. Sử dụng chữ to hơn**

Chúng ta dùng thẻ big để làm chữ to hơn trong một câu

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Larger Text Example</title>
   </head>
   
   <body>
      <p>The following word uses a <big>big</big> typeface.</p>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating8](/images/post/html/formating8.png){:class="img-responsive"}
{: refdef}

# **9. Sử dụng nhỏ hơn**

Chúng ta có thể sử dụng thẻ small để làm chữ nhỏ hơn như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Smaller Text Example</title>
   </head>

   <body>
      <p>The following word uses a <small>small</small> typeface.</p>
   </body>

</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating9](/images/post/html/formating9.png){:class="img-responsive"}
{: refdef}

# **9. Nhóm các thẻ lại với nhau**

Chúng ta sử dụng thẻ div hoặc span để nhóm các thẻ lại với nhau.

- Ví dụ chúng ta sử dụng div để nhóm các thành phần của HTML vào một chỗ. Thẻ div là một thẻ quan trọng. Khi ta set giá trị cho thẻ div, các phần tử bên trong thẻ div sẽ được áp dụng chung thuộc tính mà ta set cho div. 

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   
   <head>
      <title>HTML div Tag</title>
   </head>
   
   <body>
      <!-- First group of tags -->
      <div style = "color:red">
         <h4>This is first group</h4>
         <p>Following is a list of vegetables</p>
         
         <ul>
            <li>Beetroot</li>
            <li>Ginger</li>
            <li>Potato</li>
            <li>Radish</li>
         </ul>
      </div>

      <!-- Second group of tags -->
      <div style = "color:green">
         <h4>This is second group</h4>
         <p>Following is a list of fruits</p>
         
         <ul>
            <li>Apple</li>
            <li>Banana</li>
            <li>Mango</li>
            <li>Strawberry</li>
         </ul>
      </div>
   </body>
   
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating10](/images/post/html/formating10.png){:class="img-responsive"}
{: refdef}

- Ví dụ thẻ span được sử dụng nhóm các thuộc tính trên cùng một dòng. Sự khác nhau giữa span và div là . Span chỉ áp dụng trên một dòng (inline) ở các phần tử còn div sẽ áp dụng cho một nhóm (blocked) nhiều thành phần.

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>Span Tag Example</title>
   </head>
   
   <body>
      <p>This is the example of <span style = "color:green">span tag</span>
         and the <span style = "color:red">div tag</span> alongwith CSS</p>
   </body>
   
</html>


{% endhighlight %} 

{:refdef: style="text-align: center;"}
![formating11](/images/post/html/formating11.png){:class="img-responsive"}
{: refdef}



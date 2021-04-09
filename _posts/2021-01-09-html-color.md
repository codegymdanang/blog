---
layout: course-html
title: Sử dụng màu sắc trong HTML
slug : su-dung-mau-sac-trong-html
category: laptrinhweb
tags: [html]
summery: Màu sắc
image: /images/blog/angular.png
description : Hướng dẫn được cho các người học lập trình web HTML cách sử dụng màu sắc trong HTML. Trình bày chi tiết 3 cách để thêm màu sắc vào website bao gồm dùng tên màu sắc, dùng bảng mã hex codes hoặc sử dụng RGB làm giá trị của thuộc tính màu sắc. Bài viết cũng sẽ chia sẻ cách thay đổi background của website bằng thuộc tính bgcolor. 
youtubeId: AXZHAqTUDWs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Khi làm trong các dự án <b>lập trình web HTML</b>, bên cạnh sử dụng các thẻ, thuộc tính, định dạng, cụm từ, hình ảnh và bảng, không thể không sử dụng màu sắc để thêm vào trong website để giúp phân biệt rõ ràng giữa các đối tượng cũng như giúp website trở nên bắt mắt hơn.
<br>
Vậy làm cách nào để sử dụng màu sắc trong lập trình web HTML? Cách để “đổ” những màu sắc như mong muốn cho website? Hay có đổi được background của website hay không? Bài viết dưới đây sẽ lần lượt giải đáp những thắc mắc trên cho bạn, đồng thời với những ví dụ minh hoạ kèm theo trong bài viết sẽ giúp bạn biết cách để tự thêm được các màu sắc vào website.


## **1. Màu sắc**

Trong HTML chúng ta có 3 cách để thêm màu sắc vào website, chúng ta có thể dùng tên màu sắc, dùng bảng mã hex codes hoặc sử dụng rgb làm giá trị của thuộc tính màu sắc.


## **2. Sử dụng tên**

Chúng ta có tên các màu sắc sau đây. 

{:refdef: style="text-align: center;"}
![color1](/images/post/html/color1.png){:class="img-responsive"}
{: refdef}

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Colors by Name</title>
   </head>
   
   <body text = "blue" bgcolor = "green">
      <p>Use different color names for for body and table and see the result.</p>
      
      <table bgcolor = "black">
         <tr>
            <td>
               <font color = "white">This text will appear white on black background.</font>
            </td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

## **3. Sử dụng Hex Codes**

Chúng ta có bảng mã hex code như sau

{:refdef: style="text-align: center;"}
![color2](/images/post/html/color2.png){:class="img-responsive"}
{: refdef}

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Colors by Hex</title>
   </head>
   
   <body text = "#0000FF" bgcolor = "#00FF00">
      <p>Use different color hex for for body and table and see the result.</p>
      
      <table bgcolor = "#000000">
         <tr>
            <td>
               <font color = "#FFFFFF">This text will appear white on black background.</font>
            </td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %} 

## **4. Sử dụng RGB**

{:refdef: style="text-align: center;"}
![color3](/images/post/html/color3.png){:class="img-responsive"}
{: refdef}

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Colors by RGB code</title>
   </head>
   
   <body text = "rgb(0,0,255)" bgcolor = "rgb(0,255,0)">
      <p>Use different color code for for body and table and see the result.</p>
      
      <table bgcolor = "rgb(0,0,0)">
         <tr>
            <td>
               <font color = "rgb(255,255,255)">This text will appear white on black background.</font>
            </td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %}

## **5. Background của website**

Mặc định các background màu nền của website đều là màu trắng. Chúng ta có thể thay đổi màu nền hoặc thêm ảnh nền của website bằng cách sử dụng thuộc tính bgcolor 

- Ví dụ thay đổi màu nền

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Background Colors</title>
   </head>
   
   <body>
      <!-- Format 1 - Use color name -->
      <table bgcolor = "yellow" width = "100%">
         <tr>
            <td>
               This background is yellow
            </td>
         </tr>
      </table>
 
      <!-- Format 2 - Use hex value -->
      <table bgcolor = "#6666FF" width = "100%">
         <tr>
            <td>
               This background is sky blue
            </td>
         </tr>
      </table>
 
      <!-- Format 3 - Use color value in RGB terms -->
      <table bgcolor = "rgb(255,0,255)" width = "100%">
         <tr>
            <td>
               This background is green
            </td>
         </tr>
      </table>
   </body>
   
</html>

{% endhighlight %}

- Ví dụ thay đổi ảnh nền

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>HTML Background Images</title>
   </head>
   
   <body>
      <!-- Set table background -->
      <table background = "/images/html.gif" width = "100%" height = "100">
         <tr><td>
            This background is filled up with HTML image.
         </td></tr>
      </table>
   </body>
   
</html>
{% endhighlight %}

## **6. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **7. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/HTML-Color" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

















---
layout: course-css
title: Sử dụng CSS trong HTML  
slug : su-dung-css-trong-html
category: laptrinhweb
tags: [css]
summery: Sử dụng CSS trong HTML  
image: /images/blog/angular.png
description : Để tác động vào cách hiển thị của các phần tử HTML trong trang, chúng ta cần phải nhúng CSS vào HTML. Vậy có những cách nhúng nào? Bài viết sẽ giới thiệu và hướng dẫn 3 cách để nhúng CSS vào HTML trong lập trình web bao gồm sử dụng thẻ style, thông qua file riêng biệt, và cách nhúng CSS vào HTML trong một hàng. Bên cạnh đó chia sẻ cách để thêm comment chú thích trong lập trình web CSS. 
youtubeId: QntpkPKLAdU
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Như những bài chia sẻ của anh về kiến thức <b>lập trình web</b> HTML ở phần trước, ngôn ngữ HTML được sử dụng để tạo nên các định dạng, các kiểu phần tử, nội dung trong trang web. Về các quy định cho cách hiển thị các phần tử này trong trang web thì lúc này đòi hỏi cần sử dụng đến ngôn ngữ CSS. Như vậy có thể nói rằng hai ngôn ngữ <b>lập trình web CSS</b> và ngôn ngữ <b>lập trình web HTML</b> luôn đi cùng nhau trong quá trình chúng ta làm trang web.
<br>
Để tác động vào cách hiển thị của các phần tử HTML trong trang, chúng ta cần phải nhúng CSS vào HTML. Vậy có những cách nhúng nào? Bài viết hôm nay anh sẽ giới thiệu cho các bạn 3 cách để nhúng CSS vào HTML bao gồm sử dụng thẻ style, thông qua file riêng biệt, và cách nhúng CSS vào HTML trong một hàng. Bên cạnh đó anh sẽ chia sẻ thêm cách làm để các bạn có thể thêm comment chú thích trong <b>lập trình web CSS</b>.
<br>
Hi vọng với những chia sẻ kèm theo các ví dụ minh hoạ cụ thể cho mỗi phần dưới đây, các bạn có thể hiểu rõ và thực hiện được thao tác <b>nhúng CSS vào HTML trong lập trình web</b>.


## **1. Nhúng CSS vào HTML thông qua thẻ style**

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   <head>
      <style type = "text/css" media = "all">
         body {
            background-color: linen;
         }
         h1 {
            color: maroon;
            margin-left: 40px;
         }
      </style>
   </head>   
   <body>
      <h1>This is a heading</h1>
      <p>This is a paragraph.</p>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![css1](/images/post/css/css1.png){:class="img-responsive"}
{: refdef}

## **2. Nhúng CSS vào HTML trong một hàng**

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   <head>
   </head>

   <body>
      <h1 style = "color:#36C;"> 
         This is inline CSS 
      </h1>
   </body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![css2](/images/post/css/css2.png){:class="img-responsive"}
{: refdef}


## **3. Nhúng CSS vào HTML qua file**

Giả sử chúng ta có một file css tên my.css như sau

{% highlight css linenos %}

h1, h2, h3 {
   color: #36C;
   font-weight: normal;
   letter-spacing: .4em;
   margin-bottom: 1em;
   text-transform: lowercase;
}

{% endhighlight %}

Ta sẽ nhúng file my.css này vào trang HTML thông qua thẻ link như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>
   <head>
      <link type = "text/css" href = "my.css" media = " all" />
   </head>

   <body>
      <h1 style = "color:#36C;"> 
         This is inline CSS 
      </h1>
   </body>
</html>


{% endhighlight %}

- Ngoài cách dùng thẻ link chúng ta có thể sử dụng annotation @import như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>
   <head>
     @import "my.css";
   </head>

   <body>
      <h1 style = "color:#36C;"> 
         This is inline CSS 
      </h1>
   </body>
</html>


{% endhighlight %}

## **4. Comment chú thích trong CSS**

Chúng ta dùng /* để ghi chú thích các dòng code CSS như sau.


{% highlight html linenos %}

<!DOCTYPE html>
<html>
   <head>
      <style>
         p {
            color: red;
            /* This is a single-line comment */
            text-align: center;
         }
         /* This is a multi-line comment */
      </style>
   </head>

   <body>
      <p>Hello World!</p>
   </body>
</html>

{% endhighlight %}


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}









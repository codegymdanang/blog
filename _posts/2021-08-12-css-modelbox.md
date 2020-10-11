---
layout: course-css
title: Sử dụng Box Model trong CSS
slug : su-dung-box-model-trong-css
category: laptrinhweb
tags: [css]
summery: Box Model 
image: /images/blog/angular.png
description : Sử dụng Box Model trong trong dự án làm web. Hướng dẫn Sử dụng Box Model trong CSS vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>Box Model</b> là như thế nào?


# **1. Box Model là gì**

Tất các các thành phần của HTML như thẻ button, p, div ect được bao bọc xung quanh một khối hộp (box). Hiểu được khái niệm của box model sẽ giúp chúng ta dể dàng thiết kế và điều chỉnh các phần tử của HTML vào đúng vị trí mà mình mong muốn.

Bao bọc quanh các phần tử của HTML là box model với các thành phần của box model là : margin, border, padding, và content như sau

{:refdef: style="text-align: center;"}
![box-model](/images/post/css/box-model.png){:class="img-responsive"}
{: refdef}

- Content : Chính là nội dung bên trong, nơi mà chúng ta thấy chữ và hình ảnh của một phần tử HTML
- Padding : Chính là phần nằm giữa nội dung bên trong và border của box
- Border  : Chính là đường viên xung quanh nội dung và padding
- Margin  : Chính là khoảng cách của phần tử HTML so với các phần tử khác. Các này khác với Padding ở chỗ.
Padding chỉ là khoảng các nội dung bên trong phần tử HTML còn Margin là so sánh với các phần tử bên ngoài.

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: lightgrey;
  width: 300px;
  border: 15px solid green;
  padding: 50px;
  margin: 20px;
}
</style>
</head>
<body>

<h2>Demonstrating the Box Model</h2>

<p>The CSS box model is essentially a box that wraps around every HTML element. It consists of: borders, padding, margins, and the actual content.</p>

<div>This text is the content of the box. We have added a 50px padding, 20px margin and a 15px green border. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>

</body>
</html>

{% endhighlight %}


{:refdef: style="text-align: center;"}
![boxmodel1](/images/post/css/boxmodel1.png){:class="img-responsive"}
{: refdef}

- Ta thấy border được viền bằng màu xanh lục với độ dày là 15px
- Khoảng cách giữa border và đoạn text bên ngoài ở phía trên chính là margin 20px. Như vậy dùng margin để ta xát định khoảng cách thẻ div với thẻ bên ngoài div.
- Ta thấy đoạn text Thí is the content nằm bên trong div và có khoảng cách với border là 50px thì đó chính là padding. Padding dùng để canh chỉnh nội dụng bên trong 1 cái div.

# **2. Chiều cao và rộng của thẻ HTML**

- Ví dụ khi khai báo thẻ DIV sau

{% highlight html linenos %}

div {
  width: 320px;
  padding: 10px;
  border: 5px solid gray;
  margin: 0;
}

{% endhighlight %}

- Sẽ có nhiều người sẽ nghĩ là chiều width của thẻ div là 320px. Vì thấy thuộc tính width: 320px. Điều này là sai vì như ta nói ở phần trên các phần tử HTML được bao bọc trong một cái gọi là box model. Trong Box model là có thêm phần  padding, border. Chính vì vậy khi ta tính ra chiều rộng của một thẻ div thì ta phải cộng thêm chiều rộng của padding, border vào nữa.

- Như vậy chiều rộng đúng sẽ là : 320px + 10px (padding trái) + 10 px (padding phải) + 5 px (border trái) + 5px (border phải) = 350 px. 





















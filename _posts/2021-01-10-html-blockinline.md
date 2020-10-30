---
layout: course-html
title: Sử dụng Block và Inline trong HTML  
slug : su-dung-block-inline-trong-html
category: laptrinhweb
tags: [html]
summery: Block và Inline   
image: /images/blog/angular.png
description : Sử dụng thuộc tính display mặc định Block và Inline trong lập trình web HTML nhằm mục đích để các thẻ có thể được hiển thị lên website. Bài viết sẽ giới thiệu về Block và Inline trong HTML, và hướng dẫn thao tác được các thẻ phổ biến sử dụng thuộc tính Block và Inline trong lập trình web HTML bao gồm thẻ DIV và thẻ Span. Sự khác nhau giữa 2 thẻ này trong HTML để từ đó biết được khi nào thì dùng thẻ DIV, khi nào thì dùng thẻ Span cho phù hợp trong lập trình web HTML.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web HTML</b>, để các thẻ có thể được hiển thị lên website thì mỗi thẻ trong HTML đều có thuộc tính display với giá trị mặc định. Có 2 giá trị display mặc định trong HTML là <b>block</b> và <b>inline</b>.
<br>
Trong bài viết hôm nay, anh sẽ giới thiệu đến các bạn về <b>Block và Inline trong lập trình web HTML</b>, hướng dẫn áp dụng được các thẻ phổ biến sử dụng thuộc tính <b>Block và Inline trong lập trình web HTML</b> bao gồm thẻ DIV và thẻ Span. Sự khác nhau giữa 2 thẻ này trong HTML để từ đó biết được khi nào thì dùng thẻ DIV, khi nào thì dùng thẻ Span cho phù hợp trong <b>lập trình web</b>.


## **1. Block và Inline trong HTML**

Mọi thẻ trong HTML đều có thuộc tính display với giá trị mặc định để thẻ đó được hiển thị lên website. Có 2 giá trị display mặc định là <b>block</b> và <b>inline</b> 

## **2. Block trong HTML**

Một block luôn luôn bắt đầu bằng một dòng mới và có độ dài full màn hình từ trái sang phải. Ví dụ sau đây ta dùng thẻ DIV là một block. Mặc định thuộc tính display của thẻ DIV là block.

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<body>

<div style="border: 1px solid black">Hello World</div>

<p>The DIV element is a block element, and will always start on a new line and take up the full width available (stretches out to the left and right as far as it can).</p>

</body>
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![list1](/images/post/html/block.png){:class="img-responsive"}
{: refdef}

Như ta thấy thẻ div chứa chữ helloworld được trải dài từ trái sang phải.

Ngoài thẻ DIV có thuộc tính display có giá trị là block thì chúng ta còn có các thẻ khác trong HTML như : address ,dl , h1 -> h6, ol, video, article, dt, header, p, aside, fieldset, hr, pre, blockquote, figcaption, li, section, canvas, figure, main, table, dd, footer, nav, tfoot, div, form, noscript, ul.

## **3. Inline trong HTML**

Thẻ inline không bắt đầu bằng một dòng mới và không chiếm diện tích full màn hình website từ trái qua phải mà chỉ chiếm diện tích nhất định. Ví dụ sau đây ta dùng thẻ span

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<body>

<p>This is an inline span <span style="border: 1px solid black">Hello World</span> element inside a paragraph.</p>

<p>The SPAN element is an inline element, and will not start on a new line and only takes up as much width as necessary.</p>

</body>
</html>

{% endhighlight %} 

{:refdef: style="text-align: center;"}
![list1](/images/post/html/span.png){:class="img-responsive"}
{: refdef}

Như các em thấy border (đường viền) xung quanh chữ helloworld chữ chiếm diện tích xung quanh chữ đó mà thôi chứ không tràn màn hình như block.

Chúng ta có những thẻ inline tương tự như span như : a, button, input, samp, sup, abbr, cite, script, textarea, acronym, code, label, select, time, b, map, small, tt, bdo, em, object, span, img.

## **4. Thẻ DIV trong HTML**

Thẻ div được sử dụng như một container (chứ nhiều thẻ khác trong nó). Các em tưởng tượng như mình dùng thẻ div để bọc tất cả các phần tử HTML vào trong một nhóm. Thẻ  DIV được sử dụng chung với CSS để thiết lập các thuộc tính cho các phần tử bên trong nó.

Ví dụ dưới đây anh tạo một trang web login để người dùng nhập vào username và password. Các em thấy anh có thẻ div bên ngoài cùng để bọc lại (nhóm lại) các thành phần web khác như lable, input, button mà liên quan đến giao diện login. Như vậy anh có thể canh chỉnh các thành phần bên trong div bằng cách thêm các thuộc tính trong thẻ DIV ngoài, các thành phần bên trong sẽ ảnh hưởng theo.

{% highlight html linenos %}

<div class="container">
    <label for="uname"><b>Username</b></label>
    <input type="text" placeholder="Enter Username" name="uname" required>

    <label for="psw"><b>Password</b></label>
    <input type="password" placeholder="Enter Password" name="psw" required>

    <button type="submit">Login</button>
    <label>
      <input type="checkbox" checked="checked" name="remember"> Remember me
    </label>
  </div>
{% endhighlight %}


Như vậy thẻ DIV là một block. Chúng ta sử dụng Block khi muốn nhóm các thành phần với nhau lại thành một khối. Đồng thời chúng ta muốn block đó phải bắt đầu bằng một dòng mới.

## **5. Thẻ Span trong HTML**

Thẻ Span thì sử dụng thuộc tính inline. Nó là một container như khác với DIV nó chỉ chứa một phần của Text hoặc một phần của tài liệu. Nó không chứa các thành phần web



{% highlight html linenos %}

<!DOCTYPE html>
<html>
<body>

<h1>The span element</h1>

<p>My mother has <span style="color:blue;font-weight:bold">blue</span> eyes and my father has <span style="color:darkolivegreen;font-weight:bold">dark green</span> eyes.</p>

</body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![list1](/images/post/html/span1.png){:class="img-responsive"}
{: refdef}

Ở ví dụ trên ta thấy chỉ mỗi từ blue là được in màu xanh nước biển còn lại các chữ khác thì bình thường.

## **6. Kết luận**

Chúng ta có 2 cách để hiện thị các thẻ HTMl lên website là block và inline. Block được sử dụng để nhóm các thành phần web khác lại với nhau thành một khối và nó bắt đầu bằng một dòng mới. Inline thì không bắt đầu bằng một dòng mới mà nó chỉ có tác dụng một phần nào đó trong text hay trong đoạn văn. DIV mặc định là sử dụng giá trị Block còn Span là giá trị inline


















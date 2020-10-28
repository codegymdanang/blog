---
layout: course-css
title: Sử dụng thuộc tính overflow trong CSS
slug : su-dung-overflow-trong-css
category: laptrinhweb
tags: [css]
summery: Overflow 
image: /images/blog/angular.png
description : Sử dụng thuộc tính overflow trong trong css. Hướng dẫn Sử dụng thuộc tính overflow trong CSS vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>overflow</b> là như thế nào?

# **1. Thuộc tính overflow làm gì**

Chúng ta sử dụng thuộc tính overflow khi nội dung trong phần tử HTML có kích thướt chiều dài và cao lớn hơn phần tử bên ngoài bao bọc nó. Khi đó sẽ xuất hiện thanh trượt xuống hoặc trượt ngang.

Ví dụ sau đây ta có nội dung bên trong thẻ div lớn hơn kích thướt của thẻ div bọc ngoài nội dung  

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
#overflowTest {
  background: #4CAF50;
  color: white;
  padding: 15px;
  width: 50%;
  height: 100px;
  overflow: scroll;
  border: 1px solid #ccc;
}
</style>
</head>
<body>

<div id="overflowTest">This text is really long and the height of its container is only 100 pixels. Therefore, a scrollbar is added to help the reader to scroll the content. Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi. Nam liber tempor cum soluta nobis eleifend option congue nihil imperdiet doming id quod mazim placerat facer possim assum. Typi non habent claritatem insitam; est usus legentis in iis qui facit eorum claritatem.</div>

</body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/overflow.png){:class="img-responsive"}
{: refdef}

# **2. Các giá trị có trong thuộc tính overflow**

- visible : đây là giá trị mặc định. Khi nội dung bên trong lớn hơn phần tử bọc nó thì nội dung sẽ tràn ra ngoài.

- hidden : Khi nội dung bên trong lớn hơn phần tử bọc bên ngoài nó sẽ bị ẩn đi

- scroll : Khi nội dung bên trong lớn hơn phần tử bọc bên ngoài thanh trượt sẽ xuất hiện để người dùng có thể kéo.

- auto : tương tự như scroll nhưng thanh trượt sẽ xuất hiện khi cần thiết

# **3. Giá trị visible**


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: #eee;
  width: 200px;
  height: 50px;
  border: 1px dotted black;
  overflow: visible;
}
</style>
</head>
<body>

<h2>CSS Overflow</h2>
<p>By default, the overflow is visible, meaning that it is not clipped and it renders outside the element's box:</p>

<div>You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.</div>

</body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/overflow1.png){:class="img-responsive"}
{: refdef}

# **4. Giá trị hidden**


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: #eee;
  width: 200px;
  height: 50px;
  border: 1px dotted black;
  overflow: hidden;
}
</style>
</head>
<body>

<h2>CSS Overflow</h2>
<p>With the hidden value, the overflow is clipped, and the rest of the content is hidden:</p>
<p>Try to remove the overflow property to understand how it works.</p>

<div>You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.</div>

</body>
</html>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/overflow2.png){:class="img-responsive"}
{: refdef}

# **5. Giá trị scroll**

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: #eee;
  width: 200px;
  height: 100px;
  border: 1px dotted black;
  overflow: scroll;
}
</style>
</head>
<body>

<h2>CSS Overflow</h2>
<p>Setting the overflow value to scroll, the overflow is clipped and a scrollbar is added to scroll inside the box. Note that this will add a scrollbar both horizontally and vertically (even if you do not need it):</p>

<div>You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.</div>

</body>
</html>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/overflow3.png){:class="img-responsive"}
{: refdef}

# **6. Giá trị auto**

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: #eee;
  width: 200px;
  height: 50px;
  border: 1px dotted black;
  overflow: auto;
}
</style>
</head>
<body>

<h2>CSS Overflow</h2>
<p>The auto value is similar to scroll, only it add scrollbars when necessary:</p>

<div>You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.</div>

</body>
</html>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/overflow4.png){:class="img-responsive"}
{: refdef}

# **7. Thuộc tính overflow-x và overflow-y**

Chúng ta sử dụng thuộc tính overflow-x và overflow-y để canh chỉnh nội dung theo chiều dài và cao. Nếu chiều dài hoặc chiều rộng mà cao và rộng hơn thành phần chứa nó ta có thể thêm các thanh trược vào theo chiều rộng và cao mà mình muốn hoặc chỉ thêm thanh trược chiều cao hoặc chỉ thêm thanh trược chiều rộng

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  background-color: #eee;
  width: 200px;
  height: 50px;
  border: 1px dotted black;
  overflow-x: hidden;
  overflow-y: scroll;
}
</style>
</head>
<body>

<h2>CSS Overflow</h2>
<p>You can also change the overflow of content horizontally or vertically.</p>
<p>overflow-x specifies what to do with the left/right edges of the content.<br>
overflow-y specifies what to do with the top/bottom edges of the content.</p>

<div>You can use the overflow property when you want to have better control of the layout. The overflow property specifies what happens if content overflows an element's box.</div>

</body>
</html>


{% endhighlight %}
















---
layout: course-bootstrap
title: Sử dụng Grid trong Bootstrap 
slug : su-dung-grid-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Grid
image:
description : Trong lập trình web, một trong những thuộc tính giúp website trở nên responsive đó chính là thuộc tính hệ thống lưới Grid trong Bootstrap. Bài viết giúp hiểu rõ hơn về thuộc tính này là gì cũng như hướng dẫn để sử dụng được thành thạo trong quá trình làm các dự án lập trình web. Tìm hiểu về 5 Grid Class trong lập trình web Bootstrap gồm col, col-sm, col-md, col-lg, col-xl. Bên cạnh đó, hướng dẫn cách chia tỉ lệ và đưa ra ví dụ cấu trúc hệ thống lưới Grid trong quá trình lập trình web.
youtubeId: mmbJCJ8XnxU
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web</b>, các lập trình viên thường rất quan tâm đến khả năng responsive trên các thiết bị khác nhau của website. Một trong những thuộc tính giúp website trở nên responsive đó chính là sử dụng <b>hệ thống lưới grid</b>.

<br>
Để giúp các bạn hiểu hơn về thuộc tính này cũng như sử dụng được thành thạo trong quá trình làm các dự án <b>lập trình web</b>; trong bài chia sẻ này anh sẽ giải thích cho các bạn hiểu rõ được Grid trong Bootstrap là gì? Sau đó cùng tìm hiểu về 5 Grid Class trong <b>lập trình web</b> Bootstrap gồm col, col-sm, col-md, col-lg, col-xl. Bên cạnh đó, trong những chia sẻ dưới đây anh cũng sẽ hướng dẫn các bạn cách chia tỉ lệ và ví dụ cấu trúc hệ thống lưới Grid trong quá trình <b>lập trình web</b> Bootstrap.
 

## **1. Grid là gì**

<b>Grid</b> là một hệ thống lưới nó chia trang web chúng ta thành 12 cột. Hầu hết các website sử dụng bootstrap đều sử dụng hệ thống lưới để làm layout cho trang web và bố trí các phần tử trong này. Hệ thống lưới giúp website trở nên responsive trên các thiết bị khác nhau. 

{:refdef: style="text-align: center;"}
![Grid](/images/post/boostrap/grid.PNG){:class="img-responsive"}
{: refdef}

## **2. Grid Class**

Trong grid nó hỗ trợ cho chúng ta 5 loại class để hiển thị trên những thiết bị khác nhau tùy theo kích thước. 

- .col-  	: sử dụng cho những thiết bị có kích thước chiều rộng nhỏ hơn 576px
- .col-sm-	: sử dụng cho những thiết bị có kích thước chiều rộng bằng hoặc lớn hơn 576px
- .col-md-	: sử dụng cho những thiết bị có kích thước chiều rộng bằng hoặc lớn hơn 768px
- .col-lg-	: sử dụng cho những thiết bị có kích thước chiều rộng bằng hoặc lớn hơn 992px
- .col-xl	: sử dụng cho những thiết bị có kích thước chiều rộng lớn hơn 1200px

Ví dụ dưới đây là cách sử dụng class vào trong thẻ html.

<br>
{% highlight html  linenos %}

<div class="row">
  <div class="col-sm-4"></div>
  <div class="col-sm-8"></div>
</div>

{% endhighlight %}


## **3 .Ví dụ cấu trúc hệ thống lưới Grid**

Ví dụ dưới đây ta có 1 dòng gồm có 2 div trong đó, ta chia tỉ lệ là div 1 chiếm 3 cột và div 2 chiếm 9 cột như sau.

<br>
{% highlight html  linenos %}

<div class="row">
  <div class="col-*-*"></div>
  <div class="col-*-*"></div>
</div>
{% endhighlight %}

Đầu tiên chúng ta tạo ra 1 dòng (<div class="row" </div>). Sau đó chúng ta thêm các cột mà chúng ta mong muốn vào và nhớ tổng số cột chúng ta mong muốn là bằng 12.

Tiếp đến ta cấu hình col đầu tiên col-*-* . Dấu * thứ 1 là hiển thị cho kích thước màn hình chúng có thể là sm, md, lg or xl. Đấu * thứ 2 số lượng column. Bây giờ chúng ta sẽ tạo ra 1 dòng có 12 cột hiển thị cho thiết bị lớn hơn 576px như sau:
<br>
{% highlight html  linenos %}

<div class="row">
  <div class="col-sm-3"></div>
  <div class="col-sm-9"></div>
</div>

{% endhighlight %}

- Như vậy ta sẽ có div đầu tiên chiếm 3 cols và div thứ 2 chiếm 9 cols. (tổng số cột trong row là 12 cols)

- Nếu như chúng ta để cho bootstrap tự quản lý layout thì ta không cần thêm số lượng cột vào. Lúc này bootstrap sẽ tự chia các div với kích thước bằng nhau.

<br>
{% highlight html  linenos %}

<!-- Or let Bootstrap automatically handle the layout -->
<div class="row">
  <div class="col-sm"></div>
  <div class="col-sm"></div>
  <div class="col-sm"></div>
</div>

{% endhighlight %}

Ở ví dụ trên bootstrap sẽ lấy 100% chia cho 3 div. Như vậy mỗi div sẽ có khoảng cách bằng nhau và chiếm 33.33%.

Nếu như chúng ta chỉ có 2 div thì bootstrap sẽ lấy 100% chia cho 2 mỗi div sẽ chiếm 50% như sau:

<br>
{% highlight html  linenos %}

<!-- Or let Bootstrap automatically handle the layout -->
<div class="row">
  <div class="col"></div>
  <div class="col"></div>
</div>

{% endhighlight %}

## **4 .Chia tỉ lệ**

- Chúng ta muốn chia tỉ lệ 25% cho div 1 và 75% cho div 2 trên tất cả các thiết bị (mobile, desktop, tivi, ipad) ta cấu hình như sau.

<br>
{% highlight html  linenos %}
 <div class="container-fluid">
  <div class="row">
    <div class="col-3 bg-success">
      <p>Lorem ipsum...</p>
    </div>
    <div class="col-9 bg-warning">
      <p>Sed ut perspiciatis...</p>
    </div>
  </div>
</div> 

{% endhighlight %}

Như vậy div bg-success sẽ chiếm 25% (cái này là lấy 3/12 = 0.25). Còn div bg-warning sẽ là 75% (lấy 9/12 = 0.75)

## **5. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **6. Thực hành và Source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bootstrap" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

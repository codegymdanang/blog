---
layout: course-bootstrap
title: Sử dụng card trong Bootstrap 
slug : su-dung-card-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Card
image:
description : Để tạo một hộp mà trong đó có thể bao gồm cả nội dung bên trong, màu sắc, header và footer trong lập trình web, các lập trình viên sẽ cần phải sử dụng thuộc tính Card trong Bootstrap. Bài viết dưới đầy sẽ giúp bạn hiểu được Card trong lập trình web là gì? Được sử dụng như thế nào? Trước hết bài viết sẽ giải thích các khái niệm về trong Bootstrap cũng như hướng dẫn cách thao tác với như cách thêm header, footer, background màu, title, text, link, ảnh, link cho Card cũng như cách để Overlay ảnh và tạo Column cho Card. Và cách làm với Card Desk và Card Group trong lập trình web.
youtubeId: UnPH-g4w4Hc
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Khi thao tác với một số trang website trong <b>lập trình web</b>, đã bao giờ bạn muốn tạo một hộp mà trong đó có thể bao gồm cả nội dung bên trong, màu sắc, header và footer? Nếu bạn đang tìm kiếm một thuộc tính nào đó trong <b>lập trình web</b> để có thể đáp ứng được mong muốn đó của bạn, đó chính là thuộc tính <b>Card</b> trong Bootstrap.

<br>
Cụ thể <b>Card trong lập trình web</b> là gì? Được sử dụng như thế nào? Trong những chia sẻ dưới đây anh sẽ giải thích các khái niệm về <b>Card</b> trong Bootstrap cũng như hướng dẫn cách thao tác với <b>Card</b> như cách thêm header, footer, background màu, title, text, link, ảnh, link cho Card cũng như cách để Overlay ảnh và tạo Column cho Card. Và cách làm với Card Desk và Card Group trong <b>lập trình web</b>.

<br>
Với những chia sẻ đó, kèm theo các ví dụ minh hoạ cụ thể, anh hi vọng các bạn sẽ sớm nắm bắt được kiến thức <b>lập trình web</b> Bootstrap này. Tuy nhiên để có thể áp dụng thành thạo vào thực tế, các bạn nên vận dụng những kiến thức này vào thực hành thường xuyên. Việc thực hành liên tục sẽ giúp các bạn ghi nhớ kiến thức nhanh và lâu hơn.
 

## **1. Card trong Bootstrap**

<b>Card</b> trong bootstrap làm một khung có border viền bên ngoài và nội dung bên trong được padding so với border. Một phần tử card bao gồm có header , footer, nội dung bên trong và màu sắc.

Ví dụ như chúng ta muốn tạo ra một hình Card như sau

{:refdef: style="text-align: center;"}
![card1](/images/post/boostrap/card1.png){:class="img-responsive"}
{: refdef}

Để sử dụng card chúng ta dùng class .card và nội dung chúng ta sử dụng .card-body

<br>
{% highlight html  linenos %}

<div class="card">
  <div class="card-body">Basic card</div>
</div>

{% endhighlight %}


## **2. Header và footer Card trong Bootstrap**

Để sử dụng header và footer chúng ta dùng class .card-header và class .card-footer

<br>
{% highlight html  linenos %}

<div class="card">
  <div class="card-header">Header</div>
  <div class="card-body">Content</div>
  <div class="card-footer">Footer</div>
</div>


{% endhighlight %}

## **3. Thêm background màu cho Card**

Để thêm màu nền cho card chúng ta sử dụng các class có sẵn như .bg-primary, .bg-success, .bg-info, .bg-warning, .bg-danger, .bg-secondary, .bg-dark và .bg-light

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Cards with Contextual Classes</h2>
  <div class="card">
    <div class="card-body">Basic card</div>
  </div>
  <br>
  <div class="card bg-primary text-white">
    <div class="card-body">Primary card</div>
  </div>
  <br>
  <div class="card bg-success text-white">
    <div class="card-body">Success card</div>
  </div>
  <br>
  <div class="card bg-info text-white">
    <div class="card-body">Info card</div>
  </div>
  <br>
  <div class="card bg-warning text-white">
    <div class="card-body">Warning card</div>
  </div>
  <br>
  <div class="card bg-danger text-white">
    <div class="card-body">Danger card</div>
  </div>
  <br>
  <div class="card bg-secondary text-white">
    <div class="card-body">Secondary card</div>
  </div>
  <br>
  <div class="card bg-dark text-white">
    <div class="card-body">Dark card</div>
  </div>
  <br>
  <div class="card bg-light text-dark">
    <div class="card-body">Light card</div>
  </div>
</div>

{% endhighlight %}

## **4. Thêm title, text và link cho Card**

- Chúng ta có thể thêm title, chữ và link liên kết giống như hình sau cho card

{:refdef: style="text-align: center;"}
![card2](/images/post/boostrap/card2.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<div class="card">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">Some example text. Some example text.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>

{% endhighlight %}

## **5. Thêm ảnh cho Card**

Chúng ta thêm class .card-img-top hoặc .card-img-bottom trong thẻ img. Nên nhớ chúng ta nên thêm ảnh ở ngoài class .card-body để có kích thước toàn màn hình

{:refdef: style="text-align: center;"}
![card1](/images/post/boostrap/card1.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<div class="card" style="width:400px">
  <img class="card-img-top" src="img_avatar1.png" alt="Card image">
  <div class="card-body">
    <h4 class="card-title">John Doe</h4>
    <p class="card-text">Some example text.</p>
    <a href="#" class="btn btn-primary">See Profile</a>
  </div>
</div>
{% endhighlight %}

## **6. Thêm link cho toàn bộ Card**

Chúng ta muốn click vào bất kỳ vị trí nào trên card cũng có thể dẫn đi một đường link khác chứ không nhất thiết click vào nút. Thì chúng ta dùng class .stretched-link khi đó chúng ta click vào bất kỳ vị trí nào trên card cũng được.

<br>
{% highlight html  linenos %}

<a href="#" class="btn btn-primary stretched-link">See Profile</a>

{% endhighlight %}

## **7. Overlay ảnh cho Card**

Chúng ta muốn ảnh đè lên trên text trong card như sau.

{:refdef: style="text-align: center;"}
![card3](/images/post/boostrap/card3.png){:class="img-responsive"}
{: refdef}

Thì lúc đó chúng ta sẽ sử dụng class .card-img-overlay

<br>
{% highlight html  linenos %}

<div class="card" style="width:500px">
  <img class="card-img-top" src="img_avatar1.png" alt="Card image">
  <div class="card-img-overlay">
    <h4 class="card-title">John Doe</h4>
    <p class="card-text">Some example text.</p>
    <a href="#" class="btn btn-primary">See Profile</a>
  </div>
</div>


{% endhighlight %}

## **8. Column cho Card**

Để tạo được nhiều card như hình bên dưới giống như layout của pinterest thì ta sử dụng class .card-columns

{:refdef: style="text-align: center;"}
![card4](/images/post/boostrap/card4.png){:class="img-responsive"}
{: refdef}
<br>
{% highlight html  linenos %}

<div class="card-columns">
  <div class="card bg-primary">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the first card</p>
    </div>
  </div>
  <div class="card bg-warning">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the second card</p>
    </div>
  </div>
  <div class="card bg-success">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the third card</p>
    </div>
  </div>
  <div class="card bg-danger">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the fourth card</p>
    </div>
  </div>
  <div class="card bg-light">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the fifth card</p>
    </div>
  </div>
  <div class="card bg-info">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the sixth card</p>
    </div>
  </div>
</div>

{% endhighlight %}

## **9. Card Desk**

Chúng ta muốn tạo ra nhiều card có cùng kích thước chiều cao và chiều rộng thì ta sử dụng class .card-deck

{:refdef: style="text-align: center;"}
![card5](/images/post/boostrap/card5.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<div class="card-deck">
  <div class="card bg-primary">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the first card</p>
    </div>
  </div>
  <div class="card bg-warning">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the second card</p>
    </div>
  </div>
  <div class="card bg-success">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the third card</p>
    </div>
  </div>
  <div class="card bg-danger">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the fourth card</p>
    </div>
  </div>
</div>

{% endhighlight %}

## **10. Card Group**

Nó cũng tương tự như card desk nhưng sẽ không có khoảng cách trống giữa 2 cards. Chúng ta sử dụng class .card-group 

{:refdef: style="text-align: center;"}
![card6](/images/post/boostrap/card6.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<div class="card-group">
  <div class="card bg-primary">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the first card</p>
    </div>
  </div>
  <div class="card bg-warning">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the second card</p>
    </div>
  </div>
  <div class="card bg-success">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the third card</p>
    </div>
  </div>
  <div class="card bg-danger">
    <div class="card-body text-center">
      <p class="card-text">Some text inside the fourth card</p>
    </div>
  </div>
</div>

{% endhighlight %}

## **11. Video demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **12. Thực hành và Source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bootstrap" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

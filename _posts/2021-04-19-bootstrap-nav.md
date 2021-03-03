---
layout: course-bootstrap
title: Sử dụng Nav trong Bootstrap 
slug : su-dung-nav-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Nav
image:
description : Trong lập trình web, các lập trình viên sẽ sử dụng các lớp Nav trong Bootstrap 4 để tạo ra các kiểu Menu nằm ngang hay nằm dọc. Bài viết này sẽ hướng dẫn cách thao tác với các lớp Nav để làm các kiểu Menu trên. Đồng thời cũng hướng dẫn để các bạn sử dụng được Nav trong Bootstrap để tạo kiểu Tab, Tab Pills và Dynamic tab trong Bootstrap 4.

youtubeId: rP0qARCQYHM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình web</b>, các lập trình viên sẽ sử dụng các lớp <b>Nav</b> trong Bootstrap 4 để tạo ra các kiểu Menu nằm ngang hay nằm dọc. Bài viết hôm nay, anh sẽ hướng dẫn các bạn cách thao tác với các lớp <b>Nav</b> để làm các kiểu Menu trên. Đồng thời anh cũng hướng dẫn để các bạn sử dụng được Nav trong Bootstrap để tạo kiểu Tab, Tab Pills và Dynamic tab trong Bootstrap 4.

<br>
Hi vọng với những chia sẻ về cách thao tác với <b>Nav</b> trong Bootstrap 4 sẽ giúp các bạn áp dụng vào quá trình <b>lập trình web</b> để tạo ra các trang website hoàn thiện, thu hút và đáp ứng các nhu cầu của khách hàng.
 

## **1. Nav Menu nằm ngang trong Bootstrap 4**

Chúng ta muốn làm menu cho website thì có thể sử dụng class .nav trong các thẻ ul. Và theo sau đó là các class .nav-item trong các thẻ li. Nếu trong menu có thêm link tới một website khác thì dùng class .nav-link

{:refdef: style="text-align: center;"}
![nav1](/images/post/boostrap/nav1.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="nav">
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Disabled</a>
  </li>
</ul> 

{% endhighlight %}

- Để canh giữa cho các Nav thì chúng ta sử dụng class .justify-content-center lúc này thanh menu sẽ nằm giữa màn hình. Nếu muốn thanh menu mà nằm bên trái thì dùng class .justify-content-end

<br>
{% highlight html  linenos %}

<!-- Centered nav -->
<ul class="nav justify-content-center">

<!-- Right-aligned nav -->
<ul class="nav justify-content-end">

{% endhighlight %}


## **2. Nav Menu nằm dọc trong Bootstrap 4**

Chúng ta có thể làm các thanh menu nằm dọc bằng cách thêm class là .flex-column .

{:refdef: style="text-align: center;"}
![nav2](/images/post/boostrap/nav2.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="nav flex-column">

{% endhighlight %}

## **3. Tab trong Bootstrap 4**

Chúng ta sử dụng .nav-tab và .active để tạo các tab.

{:refdef: style="text-align: center;"}
![nav3](/images/post/boostrap/nav3.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

  <ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Disabled</a>
  </li>
</ul> 

{% endhighlight %}

## **4. Tab Pills trong Bootstrap 4**

Chúng ta sử dụng .nav-pills để có thể làm toggle các 

{:refdef: style="text-align: center;"}
![nav4](/images/post/boostrap/nav4.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

  <ul class="nav nav-pills">
  <li class="nav-item">
    <a class="nav-link active" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Disabled</a>
  </li>
</ul> 

{% endhighlight %}

## **5. Dynamic tab trong Bootstrap 4**

Chúng ta sử dụng data-toggle="table", .tab-pane và .tab-content để làm Dynamic Tab như sau.

{:refdef: style="text-align: center;"}
![nav5](/images/post/boostrap/nav5.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

  <!-- Nav tabs -->
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" data-toggle="tab" href="#home">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-toggle="tab" href="#menu1">Menu 1</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-toggle="tab" href="#menu2">Menu 2</a>
  </li>
</ul>

<!-- Tab panes -->
<div class="tab-content">
  <div class="tab-pane container active" id="home">...</div>
  <div class="tab-pane container fade" id="menu1">...</div>
  <div class="tab-pane container fade" id="menu2">...</div>
</div>

{% endhighlight %}

## **6. Video demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **7. Thực hành và Source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bootstrap" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}





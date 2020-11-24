---
layout: course-bootstrap
title: Sử dụng button trong Bootstrap 
slug : su-dung-button-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Button
image:
description : Trong quá trình lập trình web, một số website cần thiết kế thêm nút button để tạo các sự lựa chọn khác nhau giúp tăng trải nghiệm, đáp ứng được nhu cầu đa dạng từ khách hàng. Bài viết sẽ giúp bạn hiểu được về thuộc tính nút Button trong lập trình web Bootstrap là gì và cách áp dụng nó vào lập trình web như thế nào? Kèm theo những hình ảnh ví dụ minh hoạ chi tiết trong mỗi phần, sẽ hướng dẫn bạn cách thao tác với Button trong lập trình web Bootstrap như cách tạo border, kích thước cho button, active, disable, nhóm các button lại với nhau, hoặc nhóm các button cùng kích thước với nhau, hay sắp xếp các button theo hàng dọc và lồng button này vào một button khác. 
youtubeId: rxGCyB4I4CI
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình <b>lập trình web</b>, một số website cần thiết kế thêm các <b>nút (button)</b> để tạo các sự lựa chọn khác nhau giúp tăng trải nghiệm và đáp ứng được nhu cầu đa dạng từ khách hàng. Ví dụ như khi bạn mua một chiếc áo, bạn sẽ muốn chọn lựa size và màu sắc cụ thể để lựa chọn được chiếc áo phù hợp nhất với bạn. Lúc này các lập trình viên cần thiết kế các nút (button) như size S, M,L, màu sắc trắng, xanh, đen…để khách hàng lựa chọn.

<br>
Để giúp bạn hiểu rõ hơn về thuộc tính <b>nút (Button)</b> trong <b>lập trình web</b> Bootstrap là gì và cách áp dụng nó vào <b>lập trình web</b> như thế nào? Trong bài viết hôm nay anh sẽ chia sẻ cho các bạn về chủ đề sử dụng <b>Button</b> trong Bootstrap.

<br>
Những chia sẻ dưới đây kèm theo những hình ảnh ví dụ minh hoạ chi tiết trong mỗi phần, hướng dẫn về cách thao tác với <b>Button trong lập trình web Bootstrap</b> như cách tạo border, kích thước cho button, active, disable, nhóm các button lại với nhau, hoặc nhóm các button cùng kích thước với nhau, hay sắp xếp các button theo hàng dọc và lồng button này vào một button khác. 
 

## **1. Button  trong Bootstrap 4**

{:refdef: style="text-align: center;"}
![button1](/images/post/boostrap/button1.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<button type="button" class="btn">Basic</button>
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-dark">Dark</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-link">Link</button> 


{% endhighlight %}

## **2. Button border trong Bootstrap 4**

{:refdef: style="text-align: center;"}
![button2](/images/post/boostrap/button2.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<button type="button" class="btn btn-outline-primary">Primary</button>
<button type="button" class="btn btn-outline-secondary">Secondary</button>
<button type="button" class="btn btn-outline-success">Success</button>
<button type="button" class="btn btn-outline-info">Info</button>
<button type="button" class="btn btn-outline-warning">Warning</button>
<button type="button" class="btn btn-outline-danger">Danger</button>
<button type="button" class="btn btn-outline-dark">Dark</button>
<button type="button" class="btn btn-outline-light text-dark">Light</button>

{% endhighlight %}

## **3. Kích thước Button trong Bootstrap 4**

Chúng ta sử dụng class .bnt-lg để tạo cho kích thước button to nhất, btn-sm cho button có kích thước nhỏ nhất. Nếu như không dùng 2 class này thì button sẽ lấy kích thước mặc định


{:refdef: style="text-align: center;"}
![button3](/images/post/boostrap/button3.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<button type="button" class="btn btn-primary btn-lg">Large</button>
<button type="button" class="btn btn-primary">Default</button>
<button type="button" class="btn btn-primary btn-sm">Small</button>

{% endhighlight %}

## **4. Kích thước Button dài bằng màn hình**

Nếu như ta muốn button có kích thước chiều dài bằng màn hình thì dùng class .btn-block

<br>
{% highlight html  linenos %}

 <button type="button" class="btn btn-primary btn-block">Full-Width Button</button> 

{% endhighlight %}

## **5. Active và Disable Button**

Chúng ta sử dụng class .active hoặc thuộc tính disable để cho người dùng có thể click hoặc không click được button.

<br>
{% highlight html  linenos %}

<button type="button" class="btn btn-primary active">Active Primary</button>
<button type="button" class="btn btn-primary" disabled>Disabled Primary</button>
<a href="#" class="btn btn-primary disabled">Disabled Link</a> 
{% endhighlight %}


## **6. Nhóm các Button lại với nhau**

Chúng ta có thể nhóm các button lại với nhau trên cùng 1 hàng

{:refdef: style="text-align: center;"}
![button4](/images/post/boostrap/button4.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<div class="btn-group">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <button type="button" class="btn btn-primary">Sony</button>
</div> 

{% endhighlight %}

## **7. Nhóm các Button cùng kích thướt lại với nhau**

Chúng ta có thể nhóm các button lại với nhau trên cùng kích thước

{:refdef: style="text-align: center;"}
![button5](/images/post/boostrap/button5.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

  <div class="btn-group btn-group-lg">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <button type="button" class="btn btn-primary">Sony</button>
</div> 

{% endhighlight %}

## **8. Sắp xếp  các Button theo hàng dọc**

Chúng ta sử dụng class .btn-group-vertical để sắp xếp các button theo chiều dọc

<br>
{% highlight html  linenos %}

 <div class="btn-group-vertical">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <button type="button" class="btn btn-primary">Sony</button>
</div> 

{% endhighlight %}

## **9. Button lồng trong một button khác**

Chúng ta có thể nhóm các button lại với nhau trên cùng kích thước

{:refdef: style="text-align: center;"}
![button6](/images/post/boostrap/button6.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <div class="btn-group">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <div class="btn-group">
    <button type="button" class="btn btn-primary dropdown-toggle" data-toggle="dropdown">
       Sony
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Tablet</a>
      <a class="dropdown-item" href="#">Smartphone</a>
    </div>
  </div>
</div>  

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

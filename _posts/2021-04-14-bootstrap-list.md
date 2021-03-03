---
layout: course-bootstrap
title: Sử dụng list trong Bootstrap 
slug : su-dung-list-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: List
image:
description : Trong quá trình lập trình web, tuỳ mỗi website mà cần sử dụng đến thuộc tính List trong Bootstrap để thiết lập các phần tử tạo thành một danh sách. Trước hết bài viết giúp bạn hiểu rõ về thuộc tính danh sách List là gì? Sau đó sẽ chuyển sang hướng dẫn cách để làm việc với thuộc tính này như cách để highlight list, liên kết và disable các phần tử trong list. Cũng như cách làm sao để xoá border xung quanh các phần tử và hiển thị danh sách list theo chiều ngang, thao tác thêm màu sắc, badges cho các phần tử trong List khi lập trình web. 
youtubeId: _N3ARNqBfII
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình <b>lập trình web</b>, khi thao tác cho một số trang website đòi hỏi bạn cần phải sử dụng đến thuộc tính <b>List</b> trong Bootstrap để thiết lập các phần tử tạo thành một danh sách các phần tử như danh sách các sản phẩm, danh sách tên các khoá học, danh sách các thể loại phim, danh sách hàng hoá…

<br>
Để giúp bạn hiểu rõ hơn về thuộc tính <b>danh sách (List)</b> trong <b>lập trình web</b> Bootstrap là gì và cách áp dụng nó vào <b>lập trình web</b> như thế nào? Trong bài viết hôm nay anh sẽ chia sẻ cho các bạn về chủ đề sử dụng <b>List</b> trong Bootstrap 4.

<br>
Như chúng ta cũng đã biết, trước khi sử dụng được bất kỳ cái gì, chúng ta cũng cần hiểu rõ về nó là gì? Vì vậy đầu tiên anh sẽ giới thiệu cho các bạn hiểu được thuộc tính <b>List</b> trong Bootstrap 4 là gì? Sau đó anh sẽ chuyển sang hướng dẫn cho các bạn cách để làm việc với thuộc tính này như cách để highlight list, liên kết và disable các phần tử trong list. Cũng như cách làm sao để xoá border xung quanh các phần tử, cách để hiển thị danh sách list theo chiều ngang và thêm màu sắc, badges cho các phần tử trong List khi các bạn <b>lập trình web</b>.  
 

## **1. List  trong Bootstrap 4**

Để tạo được list trong web thì chúng ta sử dụng thẻ ul và class .list-group như sau

{:refdef: style="text-align: center;"}
![list1](/images/post/boostrap/list1.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="list-group">
  <li class="list-group-item">First item</li>
  <li class="list-group-item">Second item</li>
  <li class="list-group-item">Third item</li>
</ul> 


{% endhighlight %}

## **2. Highlight List trong Bootstrap 4**

Để làm highlight một phần tử trong list ta sử dụng class .active như sau.

{:refdef: style="text-align: center;"}
![list2](/images/post/boostrap/list2.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="list-group">
  <li class="list-group-item active">Active item</li>
  <li class="list-group-item">Second item</li>
  <li class="list-group-item">Third item</li>
</ul> 
{% endhighlight %}

## **3. Liên kết trong list**

Chúng ta có thể tạo ra một list (danh sách) và mỗi phần tử trong danh sách sẽ link tới một địa chỉ URL. Chúng ta sử dụng thẻ div thay cho thẻ ul

<br>
{% highlight html  linenos %}

 <div class="list-group">
  <a href="#" class="list-group-item list-group-item-action">First item</a>
  <a href="#" class="list-group-item list-group-item-action">Second item</a>
  <a href="#" class="list-group-item list-group-item-action">Third item</a>
</div> 

{% endhighlight %}

## **4. Disable các phần tử trong list**

Chúng ta có thể làm mờ đi các phần tử trong list không cho người dùng bấm vào bằng cách sử dụng thuộc tính disabled

{:refdef: style="text-align: center;"}
![list3](/images/post/boostrap/list3.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <div class="list-group">
  <a href="#" class="list-group-item disabled">Disabled item</a>
  <a href="#" class="list-group-item disabled">Disabled item</a>
  <a href="#" class="list-group-item">Third item</a>
</div> 

{% endhighlight %}


## **5. Xoá border xung quanh các phần tử trong list**

Để tạo 1 list không có border chúng ta sử dụng class .list-group-flush. Chúng sẽ xoá đi border và góc tròn xung quanh list

<br>
{% highlight html  linenos %}

 <ul class="list-group list-group-flush">
  <li class="list-group-item">First item</li>
  <li class="list-group-item">Second item</li>
  <li class="list-group-item">Third item</li>
  <li class="list-group-item">Fourth item</li>
</ul> 

{% endhighlight %}

## **6. Hiển thị danh sách list theo chiều ngang**

Nếu chúng ta muốn danh sách hiển thị theo chiều ngang màn hình thì chúng ta sử dụng class .list-group-horizontal trong .list-group như sau

<br>
{% highlight html  linenos %}

 <ul class="list-group list-group-horizontal">
  <li class="list-group-item">First item</li>
  <li class="list-group-item">Second item</li>
  <li class="list-group-item">Third item</li>
  <li class="list-group-item">Fourth item</li>
</ul> 

{% endhighlight %}

## **7.Thêm màu sắc cho các phần tử**

Chúng ta có thể sử dụng các class sau đây để tạo màu sắc cho các phần tử trong list như : .list-group-item-success, list-group-item-secondary, list-group-item-info, list-group-item-warning, .list-group-item-danger, .list-group-item-primary, list-group-item-dark and list-group-item-light

{:refdef: style="text-align: center;"}
![list4](/images/post/boostrap/list4.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="list-group">
  <li class="list-group-item list-group-item-success">Success item</li>
  <li class="list-group-item list-group-item-secondary">Secondary item</li>
  <li class="list-group-item list-group-item-info">Info item</li>
  <li class="list-group-item list-group-item-warning">Warning item</li>
  <li class="list-group-item list-group-item-danger">Danger item</li>
  <li class="list-group-item list-group-item-primary">Primary item</li>
  <li class="list-group-item list-group-item-dark">Dark item</li>
  <li class="list-group-item list-group-item-light">Light item</li>
</ul>  

{% endhighlight %}

## **8. Thêm badges cho các phần tử**

{:refdef: style="text-align: center;"}
![list5](/images/post/boostrap/list5.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

 <ul class="list-group">
  <li class="list-group-item list-group-item-success">Success item</li>
  <li class="list-group-item list-group-item-secondary">Secondary item</li>
  <li class="list-group-item list-group-item-info">Info item</li>
  <li class="list-group-item list-group-item-warning">Warning item</li>
  <li class="list-group-item list-group-item-danger">Danger item</li>
  <li class="list-group-item list-group-item-primary">Primary item</li>
  <li class="list-group-item list-group-item-dark">Dark item</li>
  <li class="list-group-item list-group-item-light">Light item</li>
</ul>  

{% endhighlight %}

## **9. Video demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **10. Thực hành và Source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bootstrap" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}




---
layout: course-bootstrap
title: Sử dụng Modal trong Bootstrap 
slug : su-dung-modal-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Modal
image:
description : Trong lập trình web để hiển thị một dialog, hộp thoại hay popup, cửa sổ hiện lên trên website, các lập trình viên sẽ sử dụng Modal trong Bootstrap. Bài viết này sẽ giúp hiểu được Modal trong lập trình web là gì? Đồng thời hướng dẫn cách để tạo được Modal trong Bootstrap 4. Sau khi biết được cách tạo Modal, sẽ tìm hiểu thêm về các thao tác khác với Modal như cách thêm hiệu ứng Modal, tăng kích thước Modal trong Bootstrap 4. Hay cách để bố trí Modal nằm giữa của màn hình và cách tạo Modal có thanh cuộn trong lập trình web để xử lí trường hợp nếu nội dung bên trong quá nhiều.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình làm <b>lập trình web</b>, thiết kế các trang website cho người dùng. Các bạn chắc hẳn sẽ cần dùng đến <b>Modal</b> trong Bootstrap, nó được sử dụng để hiển thị một dialog (hộp thoại) hay popup (cửa sổ hiện lên) trên website. Ví dụ như khi khách hàng truy cập vào trang website của bạn, bạn muốn khách hàng nhận được ngay thông báo về sản phẩm mới ra mắt của bạn hay chương trình sale,…Lúc này bạn sẽ sử dụng Modal để những thông báo này đảm bảo xuất hiện ngay khi khách hàng vào website của bạn.

<br>
Vậy để hiểu được <b>Modal</b> và cách sử dụng nó trong <b>lập trình web</b> như thế nào? Bài viết hôm nay anh sẽ lần lượt chia sẻ về Modal và hướng dẫn cho các bạn về cách tạo Modal trong Bootstrap 4. Sau khi biết được cách tạo Modal, chúng at sẽ tìm hiểu thêm với các thao tác khác với Modal như cách thêm hiệu ứng Modal, tăng kích thước Modal trong Bootstrap 4. Hay cách để bố trí Modal nằm giữa của màn hình và cách tạo Modal có thanh cuộn trong <b>lập trình web</b> để xử lí trường hợp nếu nội dung bên trong quá nhiều.
 

## **1. Tạo Modal trong Bootstrap 4**

Khi chúng ta muốn hiển thị một dialog hoặc một popup trên website thì sử dụng modal

{:refdef: style="text-align: center;"}
![modal1](/images/post/boostrap/modal1.png){:class="img-responsive"}
{: refdef}

<br>
{% highlight html  linenos %}

<!-- Button to Open the Modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#myModal">
  Open modal
</button>

<!-- The Modal -->
<div class="modal" id="myModal">
  <div class="modal-dialog">
    <div class="modal-content">

      <!-- Modal Header -->
      <div class="modal-header">
        <h4 class="modal-title">Modal Heading</h4>
        <button type="button" class="close" data-dismiss="modal">&times;</button>
      </div>

      <!-- Modal body -->
      <div class="modal-body">
        Modal body..
      </div>

      <!-- Modal footer -->
      <div class="modal-footer">
        <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
      </div>

    </div>
  </div>
</div>

{% endhighlight %}

## **2. Thêm hiệu ứng Modal trong Bootstrap 4**

Chúng ta sử dụng class .fade để thêm hiệu ứng khi mở và đóng modal

<br>
{% highlight html  linenos %}

<!-- Fading modal -->
<div class="modal fade"></div>

<!-- Modal without animation -->
<div class="modal"></div>


{% endhighlight %}

## **3. Tăng kích thước Modal trong Bootstrap 4**

Chúng ta có thể thêm kích thước của modal to hay nhỏ bằng cách sử dụng class .modal-sm hoặc modal-lg hoặc .modal-xl

<br>
{% highlight html  linenos %}

<div class="modal-dialog modal-sm">


{% endhighlight %}

<br>
{% highlight html  linenos %}

<div class="modal-dialog modal-lg">


{% endhighlight %}

<br>
{% highlight html  linenos %}

<div class="modal-dialog modal-xl">


{% endhighlight %}

Mặc định modal có kích thướt trung bình.

## **4. Modal nằm giữa màn hình trong Bootstrap 4**

Để tạo modal nằm giữa màn hình chúng ta dùng class .modal-dialog-centered 

<br>
{% highlight html  linenos %}

<div class="modal-dialog modal-dialog-centered">


{% endhighlight %}

## **5. Modal có thanh cuộn nếu nội dung bên trong nhiều**

Chúng ta có thể thêm scrollbar vào bằng việc sử dụng class .modal-dialog-scrollable  .modal-dialog

<br>
{% highlight html  linenos %}

<div class="modal-dialog modal-dialog-scrollable">

{% endhighlight %}











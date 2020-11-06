---
layout: course-bootstrap
title: Sử dụng table trong Bootstrap 
slug : su-dung-table-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Table
image:
description : Khi lập trình web, một số các trang web cần một số dạng dữ liệu cần biểu diễn dưới dạng bảng. Lúc này đỏi hỏi các lập trình viên sẽ phải sử dụng thuộc tính bảng table trong Bootstrap. Bài viết này trình bày về thuộc tính bảng table, hướng dẫn cách thao tác với thuộc tính <b>bảng (table)</b> trong Bootstrap để áp dụng hiệu quả vào quá trình làm các dự án web, và cách làm với bảng như sử dụng striped Rows, tạo border, tạo hiệu ứng, xoá border, sử dụng màu sắc, header, responpsive.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Tiếp nối các bài viết chia sẻ về các thuộc tính sử dụng trong <b>lập trình web</b> Bootstrap. Trong bài viết hôm nay, chủ đề anh sẽ trình bày cho các bạn là sử dụng thuộc tính <b>bảng (table)</b> trong Bootstrap. Như khi <b>lập trình web</b> các bạn có thể biết, một số các trang web có một số dạng dữ liệu cần biểu diễn dưới dạng bảng.

<br>
Để giúp các bạn có thể nắm được cách thao tác với thuộc tính <b>bảng (table)</b> trong Bootstrap để áp dụng hiệu quả vào quá trình làm các dự án web, hôm nay anh sẽ hướng dẫn cụ thể cách làm với bảng như sử dụng striped Rows, tạo border, tạo hiệu ứng, xoá border, sử dụng màu sắc, header, responpsive.
 

## **1. Table trong Bootstrap 4**

Để sử dụng được table trong bootstrap chúng ta thêm class .table như sau

Ví dụ như ta có các màu sau.

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Basic Table</h2>
  <p>The .table class adds basic styling (light padding and horizontal dividers) to a table:</p>            
  <table class="table">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>


{% endhighlight %}


## **2. Sử dụng Striped Rows trong Bootstrap 4**

Nếu chúng ta muốn trang trí các dòng với màu sắc khác nhau. Ví dụ như các dòng lẻ màu trắng và các dòng chẵn màu đà. Thì ta có thể dùng class .table-striped

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Striped Rows</h2>
  <p>The .table-striped class adds zebra-stripes to a table:</p>            
  <table class="table table-striped">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![stripedrow.png](/images/post/boostrap/stripedrow.png){:class="img-responsive"}
{: refdef}


## **3. Tạo border trong table**

Chúng ta sử dụng class .table-bordered để tạo border cho table như sau

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Bordered Table</h2>
  <p>The .table-bordered class adds borders on all sides of the table and the cells:</p>            
  <table class="table table-bordered">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>

{% endhighlight %}

## **4. Tạo hiệu ứng cho các dòng trong table**

Chúng ta muốn khi con chuột người dùng di chuyển vào các dòng trên table thì mình làm hiệu ứng sáng cái dòng đó lên. Thì ta sử dụng class .table-hover

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Hover Rows</h2>
  <p>The .table-hover class enables a hover state (grey background on mouse over) on table rows:</p>            
  <table class="table table-hover">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>

{% endhighlight %}

## **5. Xoá border  trong table**

Chúng ta sử dụng class .table-borderless để xoá border trong table

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Borderless Table</h2>
  <p>The .table-borderless class removes borders from the table:</p>            
  <table class="table table-borderless">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>
{% endhighlight %}


## **6. Sử dụng màu sắc trong mỗi dòng trong table**

<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Contextual Classes</h2>
  <p>Contextual classes can be used to color the table, table rows or table cells. The classes that can be used are: .table-primary, .table-success, .table-info, .table-warning, .table-danger, .table-active, .table-secondary, .table-light and .table-dark:</p>
  <table class="table">
    <thead>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Default</td>
        <td>Defaultson</td>
        <td>def@somemail.com</td>
      </tr>      
      <tr class="table-primary">
        <td>Primary</td>
        <td>Joe</td>
        <td>joe@example.com</td>
      </tr>
      <tr class="table-success">
        <td>Success</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr class="table-danger">
        <td>Danger</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr class="table-info">
        <td>Info</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
      <tr class="table-warning">
        <td>Warning</td>
        <td>Refs</td>
        <td>bo@example.com</td>
      </tr>
      <tr class="table-active">
        <td>Active</td>
        <td>Activeson</td>
        <td>act@example.com</td>
      </tr>
      <tr class="table-secondary">
        <td>Secondary</td>
        <td>Secondson</td>
        <td>sec@example.com</td>
      </tr>
      <tr class="table-light">
        <td>Light</td>
        <td>Angie</td>
        <td>angie@example.com</td>
      </tr>
      <tr class="table-dark text-dark">
        <td>Dark</td>
        <td>Bo</td>
        <td>bo@example.com</td>
      </tr>
    </tbody>
  </table>
</div>
{% endhighlight %}

{:refdef: style="text-align: center;"}
![Color](/images/post/boostrap/tablecolor.png){:class="img-responsive"}
{: refdef}

## **7. Header trong table**

Chúng ta sử dụng class .thead-dark để làm cho header của table có màu đen và .thead-light làm cho header của table có màu xám


<br>
{% highlight html  linenos %}

<div class="container">
  <h2>Table Head Colors</h2>
  <p>The .thead-dark class adds a black background to table headers, and the .thead-light class adds a grey background to table headers:</p>
  <table class="table">
    <thead class="thead-dark">
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
  <table class="table">
    <thead class="thead-light">
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>john@example.com</td>
      </tr>
      <tr>
        <td>Mary</td>
        <td>Moe</td>
        <td>mary@example.com</td>
      </tr>
      <tr>
        <td>July</td>
        <td>Dooley</td>
        <td>july@example.com</td>
      </tr>
    </tbody>
  </table>
</div>

{% endhighlight %}

## **8. Làm resonpsive table**

Chúng ta sử dụng class .table-responsive để thêm thanh kéo khi table ở màn hình nhỏ, nếu ở màn hình bình thường thì sẽ không có thanh khéo xuất hiện. Table chúng ta sẽ hiển thị được nội dung trên các thiết bị khác nhau.

<br>
{% highlight html  linenos %}

 <div class="table-responsive">
  <table class="table">
    ...
  </table>
</div> 

{% endhighlight %}









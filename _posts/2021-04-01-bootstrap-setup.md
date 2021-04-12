---
layout: course-bootstrap
title: Cài đặt bootstrap
slug : cai-dat-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Cài đặt bootstrap
image:
description : Bootstrap đã trở thành một trong những ngôn ngữ lập trình web được sử dụng phổ biến hiện nay. Bài viết này sẽ giúp bạn hiểu được Bootstrap là gì? Và hướng dẫn cách cài đặt Bootstrap để sử dụng trong lập trình web. Đồng thời qua những chia sẻ trong bài viết, cũng sẽ giúp biết được ngôn ngữ lập trình này được ra đời nhằm mục đích gì, mang lại những lợi ích gì, tại sao lại dùng Bootstrap trong lập trình web? Đồng thời nắm được cách thao tác với ngôn ngữ lập trình này, cách làm sao để nhúng Bootstrap vào website hay cách để tạo web.
youtubeId: Tcp5jRYIbA4
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Các bạn khi học <b>lập trình web</b> thường nghe nhắc đến thuật ngữ Bootstrap rất nhiều. Vậy Bootstrap là gì? Làm sao để <b>cài đặt Bootstrap</b> để sử dụng được? Nó được ra đời nhằm mục đích gì, mang lại những lợi ích gì, tại sao lại dùng Bootstrap trong <b>lập trình web</b>? Sau khi hiểu được khái niệm và ý nghĩa mà Bootstrap mang lại, các bạn lúc này chắc hẳn đã bắt đầu tò mò mong muốn biết cách thao tác với ngôn ngữ lập trình này, cách làm sao để nhúng Bootstrap vào website hay cách để tạo web.

<br>
Trong những chia sẻ ngay dưới đây, anh sẽ giúp các bạn giải đáp những thắc mắc trên và hướng dẫn cài đặt và sử dụng Bootstrap trong <b>lập trình web</b> cụ thể như thế nào thông qua các ví dụ minh hoạ kèm theo.
 

## **1. Bootstrap là gì**

Bootstrap là một framework giúp chúng ta xây dựng website một cách nhanh chóng và dễ dàng. Trong framework bootstrap đã xây dựng sẵn các thiết kế và các template cho form, button, tables, navigation, modal bằng HTML và CSS. Chúng ta chỉ việc sử dụng và không cần mất thời gian để thiết kế. Ngoài ra Bootstrap còn cung cấp cho chúng ta những thư viện Javascript hỗ trợ cho việc làm hiệu ứng trên website. Sử dụng Bootstrap sẽ giúp website trở nên responsive, có nghĩa là website sẽ được hiển thị trên nhiều nền tảng khác nhau như điện thoại, máy tính, tivi 

## **2. Tại sao lại dùng Bootstrap**

Hầu hết 70% các lập trình viên đều sử dụng Bootstrap để làm web vì nó có các ưu điểm sau:

- Dễ sử dụng: Chỉ cần có nền tảng HTML và CSS mọi người có thể sử dụng thành thạo Bootstrap.

- Responsive: Chúng ta không cần mất thời gian để canh chỉnh các thành phần trên web để chúng hiển thị trên đa nền tảng (web,mobile,table).

- Tương thích các trình duyệt: Bootstrap tương thích với hầu hết các trình duyệt Chrome, Firefox, Safari, và Opera.

## **3. Làm sao nhúng Bootstrap vào website**

Có 2 cách chúng ta có thể nhúng Bootstrap vào website và sử dụng

- Chúng ta có thể lấy bootstrap từ CDN
<br>
{% highlight html  linenos %}

 <!-- Latest compiled and minified CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">

<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

<!-- Popper JS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>

<!-- Latest compiled JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script> 

{% endhighlight %}

Khi sử dụng CDN thì khi trang web mình load lên nó sẽ lên mạng lấy file boostrap.min.js về. Chúng ta không cần phải download nguyên framework bootstrap về dự án

- Download framework Bookstrap từ getbootstrap.com

Chúng ta lên website getbootstrap sau đó download nguyên bộ boostrap về folder của dự án và dùng

## **4. Tạo website với Bootstrap**

- Bước 1 : tạo trang HTML5 Doctype

Bootstrap sử dụng HTML elements và các thuộc tính Css nên yêu cầu HTML5 doctype ở đầu file html
<br>
{% highlight html  linenos %}

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  </head>
</html>

{% endhighlight %}

- Bước 2 : Cấu hình responsive trên điện thoại

Hiện nay số lượng người dùng điện thoại là rất lớn, nên website của mình cũng phải hiển thị được trên điện thoại. Chính vì vậy khi làm một website mình phải ưu tiên nó phải hiển thị được trên điện thoại trước.

Chúng ta thêm thẻ meta trong thẻ head để cấu hình

<br>
{% highlight html  linenos %}

<meta name="viewport" content="width=device-width, initial-scale=1">

{% endhighlight %}

+ Thẻ viewport cấu hình cho trang web có thể hiển thị tương thích với các thiết bị khác nhau như mobile, máy desktop, máy table hoặc tivi.

+ Thuộc tính width=device-width nói trang web sẽ có chiều rộng của mình bằng chiều rộng màn hình của thiết bị.

+ Thuộc tính initial-scale=1.0 dùng để cấu hình mức zoom ban đầu khi trang web được load lên.

- Bước 3 : Thêm framework bootstrap vào website

<br>
{% highlight html  linenos %}

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
   <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">

    <!-- jQuery library -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

    <!-- Popper JS -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>

    <!-- Latest compiled JavaScript -->
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script> 

    <body>

    </body>

</html>

{% endhighlight %}

- Bước 4 : Xây dựng trang web

Tiếp đến chúng ta sẽ xây dựng các thành phần của website trong thẻ body. Trong các chủ đề tiếp theo anh sẽ hướng dẫn mọi người cách xây dựng các thành phần

## **5. Video demo**

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

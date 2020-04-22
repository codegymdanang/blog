---
layout: blog
title: Giới thiệu về Boostrap  
category: blog
tags: [ui]
summery: Bootstrap là gì phần 1  
image: /images/blog/ui.png
description : Giới thiệu về Boostrap 
youtubeId: 2xSwAsdcwLo
---

Chào các bạn , bạn đang có ý định làm một website cho mình nhưng không biết nên sử dụng framework nào
để hỗ trợ việc làm website một cách đơn giản và đẹp .Hôm nay anh sẽ giới thiệu với các bạn Boostrap framework. 
Cái mà team anh hay dùng không làm website
<br><br>

### Trước tiên ta hãy xem Bootstrap là gì ?
Boostrap là một framework gồm HTML , CSS , JS giúp chúng ta thiết kế website theo một chuẩn nhất định. Bootstrap định nghĩa
các thư viện có sẳn và ta chỉ việc dùng nó . Sử dụng Bootstrap giúp ta tiết kiệm được thời gian phát triển web vì nó định nghĩa
sẳn các chức năng như Responsive (hiển thị được trên mobile , desktop , laptop , Ipad ) , các thành phần như button , text , form
các animation (hiệu ứng) đã được tích hợp trong Boostrap.

### Lợi ích của Boostrap
1. Dễ dàng thao tác . Boostrap có nguyên một bộ tài liệu hướng dẫn
2. Tuỳ chỉnh dể dàng
3. Sản phẩm webstie có độ tương thích cao đối với các thiết bị hiển thị website
4. Giao diện các thành phần web đẹp , dù ta có mắt thẩm mỹ xấu vẫn làm được website đẹp
5. Tái sử dụng 

### Cài đặt Boostrap cho dự án
1. Chúng ta có thể cài boostrap từ CDN 
Chúng ta thêm dòng sau vào trang HTML
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

{% highlight java linenos %}
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap 4 Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"></script>
</head>
<body>

<div class="container">
  <h1>My First Bootstrap Page</h1>
  <p>This is some text.</p>
</div>

</body>
</html>
{% endhighlight %}

2. Chúng ta có thể download trực tiếp từ trang chủ của Boostrap
https://getbootstrap.com/
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

{% include youtubePlayer.html id=page.youtubeId %}
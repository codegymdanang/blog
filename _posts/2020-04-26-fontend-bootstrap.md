---
layout: blog
title: Giới thiệu về Boostrap  
slug : su-dung-boostrap
category: laptrinhweb
tags: [ui]
summery: Bootstrap là gì phần 1  
image: /images/blog/ui.png
description : Boostrap là gì ? lập trình web , hướng dẫn sử dụng bootstrap , ví dụ về bootstrap
youtubeId: 2xSwAsdcwLo
youtubeId1: 9G2UAIWILa4
---

# **Giới thiệu nội dung bài viết**

Chào các bạn , bạn đang có ý định làm một website cho mình nhưng không biết nên sử dụng framework nào
để hỗ trợ việc làm website một cách đơn giản và đẹp .Hôm nay anh sẽ giới thiệu với các bạn Boostrap framework. Chúng ta sẽ đi qua các nội
dung sau

- Bootstrap là gì ?
- Lợi ích của Bootstrap
- Cài đặt Bootstrap
- Một số tính năng quan trong của Boostrap
- Video trình bày cách làm một trang web đẹp bằng Bootstrap

<br>
# **1. Trước tiên ta hãy xem Bootstrap là gì**

Boostrap là một framework gồm HTML , CSS , JS giúp chúng ta thiết kế website theo một chuẩn nhất định. Bootstrap định nghĩa
các thư viện có sẳn và ta chỉ việc dùng nó . Sử dụng Bootstrap giúp ta tiết kiệm được thời gian phát triển web vì nó định nghĩa
sẳn các chức năng như Responsive (hiển thị được trên mobile , desktop , laptop , Ipad ) , các thành phần như button , text , form
các animation (hiệu ứng) đã được tích hợp trong Boostrap.

<br>
# **2. Lợi ích của Boostrap**

- Dễ dàng thao tác . Boostrap có nguyên một bộ tài liệu hướng dẫn
- Tuỳ chỉnh dể dàng.
- Sản phẩm webstie có độ tương thích cao đối với các thiết bị hiển thị website.
- Giao diện các thành phần web đẹp , dù ta có mắt thẩm mỹ xấu vẫn làm được website đẹp.
- Tái sử dụng .

<br>
# **3. Cài đặt Boostrap cho dự án**

- Chúng ta có thể cài boostrap từ CDN bằng cách thêm  dòng sau vào trang HTML.

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

Để sử dụng được các thành phần của  Bootstrap ta chỉ cần sử dụng class của Boostrap trong HTML của mình.
Ví dụ <div class="container"> thì class container là của Bootstap . Như vậy ta chỉ cần sử dụng lại

- Chúng ta có thể download trực tiếp từ trang chủ của Boostrap (https://getbootstrap.com)

<br>
# **4 Một số tính năng quan trọng của Bootstrap**  

Khi mở trang web ra điều đầu tiên ta nhận thấy tất cả các trang web điều có thể Meta ,Viewport với thuột tính content ,initial-scale, shrink-to-fit. Vậy nó có nhiệm vụ gì mà bất cứ trang web nào cũng phải có. Ví dụ như sau

{% highlight xml  linenos %}
<meta name = "viewport" content = "width=device-width, initial-scale = 1, shrink-to-fit = no">
{% endhighlight %}

Viewport tạm dịch là khung nhìn, là khu vực có thể nhìn thấy của người dùng về nội dung trong một trang web. Viewport sẽ khác nhau với các thiết bị khác nhau, và sẽ nhỏ hơn trên điện thoại di động so với trên màn hình máy tính. Trước khi thiết kế cho máy tính bảng và điện thoại di động, các trang web chỉ được thiết kế cho màn hình máy tính và thông thường các trang web có thiết kế tĩnh và có kích thước cố định. Sau đó, khi chúng ta bắt đầu lướt web bằng cách sử dụng máy tính bảng và điện thoại di động, các trang web có kích thước cố định đã quá lớn để phù hợp với người dùng. Để khắc phục điều này, các trình duyệt trên các thiết bị này tự động thu nhỏ toàn bộ trang web để vừa với màn hình. Khi chiều ngang của thiết bị quá nhỏ, người dùng phải vuốt ngang để xem hết nội dung của trang web hoặc xem trang web với nội dung quá nhỏ và cần phải zoom để đọc được nội dung.

Thẻ <meta> viewport thiết lập cho trang web hiển thị tương ứng với kích thước của từng thiết bị khác nhau.

Thuộc tính width=device-width đặt chiều rộng của trang web theo chiều rộng màn hình của thiết bị.

Thuộc tính initial-scale=1.0 thiết lập mức độ phóng ban đầu khi trang được trình duyệt tải lần đầu tiên, người dùng sẽ không thể zoom khi thuộc tính này có giá trị bằng 1

# **Container Class**

+ Có 2 loại container
+ Loại container sẽ hiển thị website với giá trị fixed width (lập trình viên tự định nghĩa giá trị như sau

{% highlight html linenos %}
    <style>
         .container {
            background: #a52c644a;
            text-align: center;
            padding-top: 100px;
            padding-bottom: 100px;
         }   
      </style>

<div class = "container">
   ...
</div>
{% endhighlight %}

Loại container-fluid sẽ hiện thị full chiều rộng màn hình.

{% highlight html linenos %}
<div class = "container-fluid">
   ...
</div>
{% endhighlight %}

# Responsive breakpoints

Responsive là cách mình lập trình trang web có thể hiển thị trên nhiều thiết bị khác nhau ví dụ trên điện thoại , IPad , Tivi. Nhờ có Bootstrap
mà ta không còn phải lo lắng khi làm responsive vì Boostrap đã hỗ trợ cho mình. Bằng cách sử dụng thẻ @media ta có thể dể dành hiển thị trang web
ở những thiết bị có kích thướt khác nhau .

Anh có ví dụ dưới đây. Tuỳ vào kích thướt màn hình mà màu H3 sẽ thay đổi là đỏ , vàng , xanh , tím.
Nếu màn hình điện thoại sẽ là đỏ.
Nếu tablets là vàng.
Nếu là desktop là xanh.

{% highlight css linenos %}
/* Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) {
  h3 {
      background-color: red;
  }

}

/*  Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
    h3 {
        background-color: yellow;
    }
}

/*  Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
    h3 {
        background-color: green;
    }
}

/*  Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
    h3 {
        background-color: purple;
    }
}
{% endhighlight %}


Như vậy chúng ta sử dụng @media để chọn css tương ứng với các khích thướt hiển thị khác nhau.

<br>
# **Hệ thống lưới**

Bootstrap sử dụng hệ thống lưới 12 cột đại để là layout cho trang web.

{:refdef: style="text-align: center;"}
![Grid   ](/images/post/frontend/grid.png){:class="img-responsive"}
{: refdef}

.col- (extra small devices - screen width less than 576px).
.col-sm- (small devices - screen width equal to or greater than 576px).
.col-md- (medium devices - screen width equal to or greater than 768px).
.col-lg- (large devices - screen width equal to or greater than 992px).
.col-xl- (xlarge devices - screen width equal to or greater than 1200px).
xs = extra small screens (mobile phones).
sm = small screens (tablets).
md = medium screens (some desktops).
lg = large screens (remaining desktops).


{% highlight html linenos %}
<!-- 50%/50% split on extra small devices and 75%/25% split on larger devices -->
<div class="row">
  <div class="col-6 col-sm-9">col-6 col-sm-9</div>
  <div class="col-6 col-sm-3">col-6 col-sm-3</div>
</div>

<!-- 58%/42% split on extra small, small and medium devices and 66.3%/33.3% split on large and xlarge devices -->
<div class="row">
  <div class="col-7 col-lg-8">col-7 col-lg-8</div>
  <div class="col-5 col-lg-4">col-5 col-lg-4</div>
</div>

<!-- 25%/75% split on small devices, a 50%/50% split on medium devices, and a 33%/66% split on large and xlarge devices. On extra small devices, it will automatically stack (100%) -->
<div class="row">
  <div class="col-sm-3 col-md-6 col-lg-4">col-sm-3 col-md-6 col-lg-4</div>
  <div class="col-sm-9 col-md-6 col-lg-8">col-sm-9 col-md-6 col-lg-8</div>
</div>

{% endhighlight %}

# **Quy tắc khi thực hiện Responsive Web Design**

1. Không sử dụng các HTML element có chiều rộng cố định quá lớn - Ví dụ: Một hình ảnh có chiều rộng quá lớn so với chiều rộng của các thiết bị nhỏ thì khi hiển thị trên các thiết bị này hình ảnh sẽ bị tràn ra ngoài và cần phải cuộn ngang để xem được toàn bộ ảnh. Vì vậy, cần phải điều chỉnh hỉnh ảnh sao cho phù hợp với chiều rộng của từng thiết bị. <br>

2. Sử dụng CSS media queries để style cho từng thiết bị có chiều rộng khác nhau - Không nên sử dụng các giá trị tuyệt đối như px, pt cho các phần tử mang tính bao quát trong trang, điều này sẽ làm cho nội dung của trang web sẽ bị tràn khi xem ở thiết bị có chiều rộng nhỏ hơn giá trị đã thiết lập. Thay vì vậy, hãy sử dụng các giá trị mang tính tương đối như %, ví dụ như width: 100%. <br>

3. Sử dụng icon SVG thay cho icon hỉnh ảnh thông thường (JPG, PNG,...) Các icon, hình ảnh dạng SVG sẽ không bị mờ khi thu phóng ở bất kỳ kích thước nào, điều này sẽ giúp nội dung của trang web hiển thị tốt nhất trên các thiết bị Retina như iPhone, iPad, Macbook

<br>
# Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé .

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

<br>
# Các bạn có thể làm  một trang website giống 100% Zing.vn tại đây nhé

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId1 %}
{: refdef}

---
layout: course-jquery
title: Sử dụng cú pháp trong jquery
slug : su-dung-cu-phap-trong-jquery
category: laptrinhweb
tags: [jquery]
summery: Cú pháp 
image: /images/blog/angular.png
description : Sử dụng cú pháp Jquery và các selector được sử dụng trong Jquery để dự án làm web. Hướng dẫn Sử dụng selector trong jquery vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>Jquery</b> là như thế nào?


# **1. Thêm Jquery vào website**

Có nhiều cách để nhúng Jquery vào website để sử dụng. Một là mình có thể download thư viện Jquery về dự án của mình thông qua website jquery.com. Hai là chúng ta có thể nhúng Jquery thông qua CDN.

Nếu chúng ta download Jquery từ trang web jquery.com thì mình sẽ có 2 phiên bản :

1- Phiên bản Production : Được sử dụng cho các website đang được sử dụng bởi người dùng (production). Thư viện Jquery lúc này đã được mã hoá cho nhẹ hơn.

2- Phiên bản Developement : Được sử dụng khi chúng ta đang phát triển website. Mục đích để chúng ta có thể test và phát triển, khi nào sản phẩm okie thì lúc đó ta mới dùng phiên bản Production. Phiên bản Development thì không mã hoá, do đó chúng ta có thể vào đọc code của Jquery.

- Để nhúng Jquery vào website thì ta nhúng thông qua thẻ script. Trong ví dụ này, anh giả sử anh đã download file jquery về dự án và để chung thư mục với file index.html như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="jquery-3.5.1.min.js"></script>

</body>
</html>

{% endhighlight %}

- Nếu chúng ta không muốn download mà sử dụng Jquery từ CDN ta thêm đường link Jquery trên CDN vào trong thẻ script như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

</head>
<body>


</body>
</html>

{% endhighlight %}

# **2.Cú pháp Jquery**

Nguyên lý hoạt động của Jquery là mình chọn thành phần nào trên web sẽ sử dụng Jquery và sau đó chúng ta thực hiện các thao tác nào trên phần tử web đó.

- Cú pháp là :  $(selector).action()

+ $        : dấu $ là ký hiệu để ta khai báo sử dụng Jquery
+ selector : chính là các thành phần mình chọn trên trang web. Mình có thể chọn theo id, class, hay tên thẻ.
+ action   : chính la hành động mà ta tính thực hiện trên phần tử web mà ta đã chọn

Jquery selector được sử dụng để tìm các phần tử trên web dựa vào tên, id, class, type, attribute của một phần tử HTML 

- Ví dụ như anh muốn lấy tất cả các paragraph (thẻ p) trong một trang web. Thì anh dùng cú pháp sau :

{% highlight javascript linenos %}

$("p")

{% endhighlight %}

- Hoặc ví dụ khi click vô button thì tất cả các thẻ paragraph đều ẩn đi.

{% highlight javascript linenos %}

$("button").click(function(){
    $("p").hide();
  });

{% endhighlight %}


- Đoạn mã $("button")  : giúp chúng ta tìm ra button trên website. 
- Đoạn mã $("button").click :  sau khi tìm ra được button thì action là thêm vào sự kiện click cho button.
- function(){ $("p").hide(); }) : Khi người dùng click vô nút button thì dòng lệnh bên trong function click sẽ được chạy.
Trong trường hợp này $("p").hide();
- $("p") : giúp chúng ta tìm tất cả thẻ p có trong trang web
- $("p").hide() : khi đã tìm được thẻ p thì hành động là ẩn tất cả thẻ p đi thông qua action là hide();

# **3. Tìm phần tử HTML bằng ID**

Chúng ta có thể tìm được thành phần của web thông qua id. Như ta đã biết mỗi thành phần web đều có thuộc tính id và giá trị của nó.
Chúng ta sử dụng cú pháp Jquery #id để lấy phần tử web ta muốn

Anh ví dụ như anh có thẻ p và có id là test như sau :


{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#test").hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p id="test">This is another paragraph.</p>

<button>Click me</button>

</body>
</html>

{% endhighlight %}


Để lấy được thẻ <p id="test">This is another paragraph.</p> anh sử dụng cú pháp là $("#test"). Trong đó #test chính là id của thẻ p

{% highlight javascript linenos %}

$(document).ready(function(){

  // jQuery methods go here...

});

{% endhighlight %}

Tất cả các method chạy trong Jquery đều được đặt bên trong hàm $(document).ready. Hàm này có chức năng là khi website load các thành phần web lên xong xuôi (ready) rồi lúc đó các đoạn code Javascript bên trong hàm đó mới được chạy.

Tại sao lại như vậy, vì các em tưởng tượng nếu các thành phần trên website mà chưa load xong. Khi đó các thành phần trên website sẽ không hiện ra, đồng nghĩa với việc các thành phần website không có ID và Class. Nếu không có ID và Class thì Jquery không thể tìm thấy được phần tử này. Trường hợp này các em sẽ nhận được thông báo lỗi ở console. 

Có một số bạn lập trình viên thường viết gọn lại như sau

{% highlight javascript linenos %}
$(function(){

  // jQuery methods go here...

});

{% endhighlight %}

2 cách trên đều có chức năng như nhau. Nhưng thường các anh hay sử dụng cách 2 hơn vì ngắn gọn.

# **4. Tìm phần tử HTML bằng class**

Chúng ta có thể tìm được thành phần của web thông qua class. Như ta đã biết mỗi thành phần web đều có thuộc tính class và giá trị của nó.
Chúng ta sử dụng cú pháp Jquery .class để lấy phần tử web ta muốn

Anh ví dụ như anh có thẻ p và có class là test như sau :


{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $(".test").hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p class="test">This is another paragraph.</p>

<button>Click me</button>

</body>
</html>

{% endhighlight %}

Để lấy được thẻ <p class="test">This is another paragraph.</p> anh sử dụng cú pháp là $(".test"). Trong đó .test chính là class của thẻ p

# **5. Lấy hết tất cả phần tử HTML**


Chúng ta sử dụng $("*") để lấy tất cả các phần tử trên web.

{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("*").hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me</button>

</body>
</html>

{% endhighlight %}

# **6. Lấy phần tử HTML hiện tại**

Chúng ta sử dụng $(this) để chọn phần tự hiện tại nơi ta đang đứng.

{% highlight javascript linenos %}

<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $(this).hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me</button>

</body>
</html>

{% endhighlight %}

Trong đoạn code trên thì đoạn $(this) chính là nút button mà ta đang chọn. 

# **7. Lấy tất cả phần tử có class tương ứng**

Ví dụ như anh muốn lấy tất cả thẻ p mà có class là intro thì anh dùng cú pháp sau $("p.intro")

{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("p.intro").hide();
  });
});
</script>
</head>
<body>

<h2 class="intro">This is a heading</h2>

<p class="intro">This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me</button>

</body>
</html>


{% endhighlight %}

# **8. Lấy tất  phần tử đầu tiên có class tương ứng**

Ví dụ sau đây anh có rất nhiều thẻ p. Nhưng anh chỉ muốn lấy thẻ p đầu tiên thì anh dùng cú pháp là $("p:first") như sau

{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("p:first").hide();
  });
});
</script>
</head>
<body>

<h2>This is a heading</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<button>Click me</button>

</body>
</html>
{% endhighlight %}







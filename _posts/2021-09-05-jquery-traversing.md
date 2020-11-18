---
layout: course-jquery
title: Hướng dẫn tìm kiếm các phần tử HTML trong Jquery
slug : huong-dan-tim-kiem-cac-phan-tu-html-trong-jquery
category: laptrinhweb
tags: [jquery]
summery : Duyệt phần tử HTML 
image: /images/blog/angular.png
description : Sử dụng Jquery để duyệt qua các phẩn tử web. Hướng dẫn tìm kiếm các phần tử web thông qua các selector
youtubeId : Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>jquery duyệt và tìm kiếm các phần tử HTML</b>là như thế nào?


# **1. Jquery Traversing là gì**

Jquery traversing có nghĩa là mình duyệt qua các phần tử trên website tìm kiếm và chọn ra phần tử mình muốn tìm. Sau đó mình chỉnh sửa màu sắc, xoá, thêm hoặc cập nhật nội dung trên phần tử đó.

Ví dụ như mình có trang HTML với cấu trúc DOM như sau

{:refdef: style="text-align: center;"}
![position1](/images/post/jquery/travtree.png){:class="img-responsive"}
{: refdef}

Trong đó

- Thẻ div là cha của thẻ ul , nó là phần tử root trong DOM chứa đựng các thẻ con trong đó
- The ul là phần tử cha của thẻ li. 
- Thẻ li bên trái là cha của thẻ span. Nhưng là con của thẻ ul và cháu của thẻ div

Như vậy khi ta dùng Jquery lấy được thẻ div (root), từ đó ta sẽ lấy được các phần tử HTML con và cháu của nó. 


# **2. Jquery Traversing từ con lên cha**

Jquery cung cấp 3 phương thức có thể lấy được phần tử cha từ phần tử con. Nghĩa là nếu ta đang ở phần tử con thì ta có thể lấy được phần tử cha ở trên nó.

- Sử dung phương  parent() để lấy phần tử cha như sau


{% highlight javascript linenos %}

$(document).ready(function(){
  $("span").parent();
});

{% endhighlight %}

Như vậy ta có thể lấy được thẻ cha chứa thẻ con là span

- Sử dụng phương thức parents() để lấy tất cả các phần tử cha

{% highlight javascript linenos %}

$(document).ready(function(){
  $("span").parents();
});

{% endhighlight %

- Sử dụng phương thức parentsUntil() để lấy hết tất cả phần tử cha mà nằm giữa 2 phần tử mà ta chọn. Ví dụ như ta muốn lấy tất cả phần tử cha nằm trong khoảng span và div

{% highlight javascript linenos %}

$(document).ready(function(){
  $("span").parentsUntil("div");
});;

{% endhighlight %

# **3. Jquery Traversing từ cha xuống con**

Ngoài phương pháp tìm kiếm từ con lên cha thì Jquery cũng hỗ trợ các tìm kiếm từ cha xuống con thông qua 2 phương thức

- Tìm kiếm con thông qua phương thức children() trả về tất cả các phần tử con có trong phần tử cha

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").children();
});

{% endhighlight %

Chúng ta cũng có thể thêm tham số để lọc và tìm kiếm các phần tử con như sau. Ví dụ như anh muốn lấy tất cả phần tử p có class name tên là first

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").children("p.first");
});

{% endhighlight %

- Sử dụng phương thức find() để lấy tất cả các phần tử con

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").find("span");
});

{% endhighlight %

Chúng ta cũng có thể lấy hết các phần tử con bằng cách sử dụng dấu * như sau :

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").find("*");
});

{% endhighlight %

# **4. Jquery Filter**

Chúng ta có thể sử dụng filter (bộ lọc) để tìm ra các phần tử đầu tiên, cuối cùng hoặc phần tử theo một điều kiện nào đó.

- Chúng ta sử dụng phương thức first() để tìm phần tử đầu tiên. Ví dụ lấy phần tử div đầu tiên

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").first();
});

{% endhighlight %

- Chúng ta sử dụng phương thức last để tìm phần tử cuối cùng. Ví dụ như tìm thẻ div cuối cùng

{% highlight javascript linenos %}

$(document).ready(function(){
  $("div").last();
});

{% endhighlight %

 - Chúng ta sử dụng phương thức eq() để trả về phần tử tương ứng với vị trí index 

{% highlight javascript linenos %}

$(document).ready(function(){
  $("p").eq(1);
});

{% endhighlight %

- Sử dụng phương thức not để trả về các phần tử không match (không đúng) với điều kiện mình đưa ra

{% highlight javascript linenos %}

$(document).ready(function(){
  $("p").not(".intro");
});

{% endhighlight %









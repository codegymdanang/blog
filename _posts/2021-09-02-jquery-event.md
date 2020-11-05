---
layout: course-jquery
title: Sử dụng sự kiện trong jquery
slug : su-dung-su-kien-trong-jquery
category: laptrinhweb
tags: [jquery]
summery: Sự kiện 
image: /images/blog/angular.png
description : Sử dụng Sự kiện trong trong jquery làm các dự án làm web. Hướng dẫn Sử dụng sự kiện trong Jquery vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>sự kiện trong jquery</b> là như thế nào?


# **1. Event(sự kiện) là gì**

Tất cả những hành động mà người dùng thao tác với website được gọi là sự kiện. Anh ví dụ như khi chúng ta click vào nút đăng ký hoặc đăng nhập, thì lúc này ta phát sinh sự kiện Click từ người dùng. Hoặc khi chúng ta bấm một phím trên bàn phím thì nó cũng phát sinh một sự kiện. Khi sự kiện phát sinh chúng ta sẽ xử lý sự kiện đó và trả lại giá trị cho người dùng.

Trong lập trình web thì chúng ta có những sự kiện sau đây :

- click : khi người dùng click vào một button trên website
- dbclick : khi người dùng nhấn đúp (2 clicks liên tục)
- mouseenter : khi con chuột di chuyển vào vùng được chọn. Ví dụ như ta có 1 lable là màu xanh. Khi con trỏ (chuột) di chuyển vào vùng màu xanh thì nó sẽ phát sinh sự kiện mouseenter. Nắm được sự kiện phát sinh ta có thể viết các đoạn mã javascript để sử lý.
- mouseleave : ngược với mouseenter khi người dùng di chuyển chuột ra khỏi vùng được chọn thì phát sinh sự kiện
- keypress : phát sinh sự kiện khi người dùng nhấn bất kỳ một phím nào trên bàn phím
- keydown  : cũng tương tự như keypress, phát sinh khi người dung nhấn một phím
- keyup    : phát sinh khi chúng ta thả phím.
Như vậy khi chúng ta bấm một phím bất kỳ trên bàn phím rồi thả ra thì nó sẽ xảy ra đồng thời 3 sự kiện. Sự kiện đầu tiên là keydown được phát sinh. Tiếp sau keydown là sự kiện keypress để kiểm tra xem ký tự nào được bấm, và cuối cùng khi ta thả phím ra thì sự kiện keyup sẽ xảy ra. Chúng ta có thể sử dụng 1 trong 3 sự kiện ở trên để bắt lại sự kiện khi người dùng gõ vào bàn phím
- submit  : sự kiện phát sinh khi người dùng submit một form. Anh ví dụ như khi chúng ta điền vào form đăng ký người dùng. Khi bấm nút đăng ký thì nó sẽ gửi toàn bộ dữ liệu trên form (tên,tuổi,email etc) lên cho serve xử lý.
- change : khi dùng dùng thay đổi nội dung. Ví dụ anh có thẻ text có giá trị là levunguyen. Khi anh thay đổi là levu thì lúc này giá trị đã thay đổi nên sẽ phát sinh sự kiện.
- focus  : sự kiện xảy ra khi chúng ta bấm vào một text box. Anh ví dụ trong form login có 2 trường là username và password. Khi chúng ta dùng con chuột click vào textbox username thì lúc này sẽ xảy ra sự kiện focus trên trường username.
- blur  : ngược lại với focus khi người dùng di chuyển chuột ra khỏi trường username thì sự kiện blur sẽ xảy ra.
- load  : sự kiện xảy ra khi trang web được load lên đầu tiên
- resize : sự kiện xảy ra khi ta resize (thay đổi kích thướt) chiều cao và rộng của trình duyệt
- scroll : sự kiện xay ra khi ta kéo thanh cuộn trên trình duyệt

Như vậy nắm bắt được khi nào phát sinh sự kiện trên web, chúng ta sẽ viết những hàm để xử lý nó. Những hàm đó có thể là kiểm tra giá trị người dùng nhập vào có đúng định dạnh hay không hoặc gửi thông tin người dùng lên server để xử lý.


# **2. Cú pháp thêm một kiện click**

Ví dụ như anh muốn thêm sự kiện click cho thẻ p. Lúc này anh sẽ sử dụng hàm click() như sau


{% highlight html linenos %}

$("p").click(function(){
  // viết code sử lý sự kiện thẻ p được click ở đây!!
});

{% endhighlight %}

- $("p") : anh sử dụng jquery selector để tìm ra thẻ p.
- .click : anh gán sự kiện click cho thẻ p. Khi người dùng click vào thẻ p thì phát sinh sự kiện. 
Khi sự kiện được phát sinh thì anh sẽ viết code để xử lý nó trong function() {}.

# **2. Cú pháp thêm một kiện double click**

Ví dụ như anh muốn thêm sự kiện double click (click 2 lần liên tiếp) cho thẻ p. Anh sử dụng hàm dblclick

{% highlight html linenos %}

$("p").dblclick(function(){
  $(this).hide();
});

{% endhighlight %}

# **3. Cú pháp thêm một kiện mouseenter**

Ví dụ như anh muốn thêm sự kiện mouseenter cho thẻ p. Anh sử dụng hàm mouseenter

{% highlight html linenos %}

$("p").dblclick(function(){
  $(this).hide();
});

{% endhighlight %}

# **4. Cú pháp thêm một kiện mouseleave**

Sự kiện này xảy ra khi chuột di chuyển ra khỏi vùng được chọn, vùng chọn có thể là một nút, một đoạn văn bản hay bất kỳ một thành phần nào trên website. Ví dụ như anh muốn thêm sự kiện mouseleave cho thẻ p. Anh sử dụng hàm mouseleave

{% highlight html linenos %}

$("p").mouseleave(function(){
  $(this).hide();
});

{% endhighlight %}


# **5. Cú pháp thêm một kiện mousedown**

Sự kiện này xảy ra khi chuột được nhấn xuống trên một vùng được chọn. Ví dụ như anh muốn thêm sự kiện mousedown cho thẻ p. Anh sử dụng hàm mousedown

{% highlight html linenos %}

$("p").mousedown(function(){
  $(this).hide();
});

{% endhighlight %}

# **6. Cú pháp thêm một kiện mouseup**

Ngược với mousedown thì mouseup phát sinh khi chúng ta nhả chuột ra khỏi vùng chọn. Ví dụ như anh muốn thêm sự kiện mouseup cho thẻ p. Anh sử dụng hàm mouseup

{% highlight html linenos %}

$("p").mouseup(function(){
  $(this).hide();
});

{% endhighlight %}

# **6. Cú pháp thêm một kiện hover**

Sự kiện phát sinh khi di chuyển chuột qua vùng được chọn.Ví dụ như anh muốn thêm sự kiện hover cho thẻ p. Anh sử dụng hàm hover

{% highlight html linenos %}

$("p").hover(function(){
  $(this).hide();
});

{% endhighlight %}

# **7. Cú pháp thêm một kiện focus**

Ví dụ như anh muốn thêm sự kiện focus cho thẻ p. Anh sử dụng hàm focus

{% highlight html linenos %}

$("p").focus(function(){
  $(this).hide();
});

{% endhighlight %}

# **8. Cú pháp thêm một kiện blur**

Ví dụ như anh muốn thêm sự kiện blur cho thẻ p. Anh sử dụng hàm blur

{% highlight html linenos %}

$("p").blur(function(){
  $(this).hide();
});

{% endhighlight %}

# **9. Phương thức on**

Chúng ta sử dụng phương thức on để gán một sự kiện cho một phần tử trên web. Ví dụ như anh muốn gán sự kiện click trên thẻ p thì anh sẽ sử dụng phương thức on trên thẻ p như sau

{% highlight html linenos %}

$("p").on("click", function(){
  $(this).hide();
});

{% endhighlight %}

# **10. Thêm nhiều sự kiện cho phần tử**

Chúng ta có thể khai báo nhiều sự kiện phát sinh trên một phần tử. Anh ví dụ như thẻ p sau nó có 3 sự kiện là mouseenter, mouseleave, và click

{% highlight html linenos %}

$("p").on({
  mouseenter: function(){
    $(this).css("background-color", "lightgray");
  },
  mouseleave: function(){
    $(this).css("background-color", "lightblue");
  },
  click: function(){
    $(this).css("background-color", "yellow");
  }
});

{% endhighlight %}






---
layout: course-html
title: Giới thiệu  
slug : html-gioi-thieu
category: laptrinhweb
tags: [html]
summery: HTML là gì   
image: /images/blog/angular.png
description : Sử dụng HTML trong dự án làm web. Hướng dẫn sử dụng HTML vào dự án web. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>HTML</b> là như thế nào?

# **1. HTML là gì**

Vào những thập niên 80 khi con người muốn chia sẽ tài liệu với nhau thì mình thường copy tài liệu như word hay excel vào usb sau đưa cho người khác mở lên. Cách này rất bất tiện vì mọi người không thể chia sẽ dữ liệu với nhau được. HTML ra đời giúp cho tài liệu được chia sẽ trực tuyến trên mạng. Nó giúp cho tài liệu của chúng ta được hiển thị một cách bắt mắt và có tổ chức, các tài liệu có thể link trực tiếp qua lại với nhau được. Cụ thể như các em thấy ngày nay HTML được dùng để định dạng ra các trang web, hiển thị nội dung một cách trực quan và rất tiện lợi.

# **2. Cú pháp khai báo thẻ HTML**

HTML dùng để format lại dữ liệu hiển thị trên website. HTML cung cấp cho chúng ta những cú pháp chuẩn mà khi tuân thủ các cú pháp đó thì dữ liệu sẽ được hiển thị như chúng ta mong muốn. Cú pháp để khai báo một thẻ HTML như sau.

{% highlight html linenos %}

<Tên thẻ > Nội dung </ Đóng tên thẻ>

{% endhighlight %} 

- Ví dụ như ta muốn hiển thị một dòng chữ trên tài liệu. Thì trong HTML chúng ta sử dụng thẻ h1 như sau

{% highlight html linenos %}

<h1>This is a heading</h1>

{% endhighlight %} 

Như vậy ta có thẻ mở HTML là \< h1 \> và thẻ đóng html là \< \/h1 \>

# **3. Các thẻ HTML cơ bản**

- Ví dụ ta có một file HTML như sau

{% highlight html linenos %}

<!DOCTYPE html>
<html>

   <head>
      <title>This is document title</title>
   </head>
	
   <body>
      <h1>This is a heading</h1>
      <p>Document content goes here.....</p>
   </body>
	
</html>


{% endhighlight %} 

- !Doctype html : Dòng này dùng để khai báo phiên bản HTML mà ta sử dụng. Khi khai báo như trên chúng ta thông báo là đang dùng phiên bản mới nhất là 5. Khi sử dụng phiên bản mới nhất của HTML thì chúng ta có thêm nhiều chức năng mới của HTML. HTML có rất nhiều phiên bản từ 1.0, 2.x, 3.x , 4.x và phiên bản mới nhất là 5.

- hmlt 	: Thẻ này dùng để khai báo bắt đầu một trang HTML. Nó bao gồm các thẻ head và body của tài liệu HTML

- head 	: Sử dụng để ghi các thông tin về tài liệu HTML nó bao gồm các thể title và meta

- title : Thẻ này dùng để đặt tên cho website

- body 	: Hiển thị nội dung trang web bên trong thẻ body. Thẻ body chứa đựng nội dung của website

- h1 	:  Hiển thị phần mở đầu của một tài liệu hoặc một đoạn văn bản.

- p 	:  Dùng để hiển thị một đoạn văn bản.

Như vậy ta thấy một trang HTML cơ bản phải có những phần trên. Tuỳ vào mỗi loại văn bản hiển thị mà chúng ta sẽ viết thêm code trong phần body với các thẻ mà HTML cung cấp cho mình.

Trong các bài tiếp theo anh sẽ giới thiệu thêm các thẻ HTML để xây dựng nên một website.












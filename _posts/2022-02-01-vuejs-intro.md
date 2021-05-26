---
layout: course-vuejs
title: Giới thiệu về vuejs 
slug : vuejs-la-gi
category: laptrinhjavascript
tags: [vuejs]
summery: Giới thiệu về vuejs
image: /images/blog/feature_javascript.png
description : Giới thiệu về vuejs, là một bộ khung JavaScript nhỏ gọn giúp chúng ta xây dựng giao diện người dùng. Ðược ra đời vào khoảng đầu năm 2014 bởi Evan You

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Vue.js là một bộ khung JavaScript nhỏ gọn giúp chúng ta xây dựng giao diện người dùng. Ðược ra đời vào khoảng đầu năm 2014 bởi Evan You, với sự sinh sau đẻ muộn này giúp Vue.js thừa kế và học hỏi ý tưởng từ những người anh em: Reactjs, Angularjs. 
Trọng tâm của chuỗi bài học này chúng ta sẽ tìm hiểu về Vue.js version 2.X 



## **1. Cài đặt môi trường ( CDN )**

Tạo một file bai1.html và thêm thẻ script bên dưới vào trong khu vực của thẻ <head>

{% highlight javascript  linenos %}

 <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script> 

{% endhighlight %}

Như vậy chúng ta đã chèn mã script bộ khung JavaScript Vue.js vào trang web của mình.


## **2. Hello world**

Thêm một div block với id="app" trong tài liệu index.html 

{% highlight javascript  linenos %}

 <div id="app">{{ message }}</div> 

{% endhighlight %}

Thêm một thẻ script vào trước thẻ đóng body với nội dung như sau:

{% highlight javascript  linenos %}

var app = new Vue({ 
 el: "#app", 
 data: { 
 message: "Hello Vue!", 
 }, 
});


{% endhighlight %}

Ở đây chúng ta thấy {{ message }} là cú pháp để hiển thị giá trị của biến message thể hiện lên trang web 
new Vue() chính là một đối tượng Vue của chúng ta, được truyền vào với các tham số cơ bản như: 
el: là 1 selector để quyết định xem chúng ta sẽ đính khung Vue.js vào block nào của trang web, thông thường chúng ta sẽ tạo một thẻ div có id="app" để chuyển toàn bộ trang web của chúng ta render theo Vue.js 
data: đây chính là trạng thái của ứng dụng (sẽ nói cụ thể hơn ở bài 2) , ở đây hiển nôm na là ta đang định nghĩa biến và giá trị của nó, ở đây là biến message có giá trị là "Hello Vue!"
Mở file bai1.html lên Brower và chúng ta sẽ thấy kết quả!


{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/introduce.png){:class="img-responsive"}
{: refdef}















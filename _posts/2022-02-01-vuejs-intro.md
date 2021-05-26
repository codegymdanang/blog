---
layout: course-vuejs
title: Giới thiệu Vuejs
slug : vuejs-la-gi
category: laptrinhjavascript
tags: [vuejs]
summery:  Giới thiệu Vuejs
image: /images/blog/feature_javascript.png
description : Vue.js là một bộ khung JavaScript nhỏ gọn giúp chúng ta xây dựng giao diện người dùng. Ðược ra đời vào khoảng đầu năm 2014 bởi Evan You, với sự sinh sau đẻ muộn này giúp Vue.js thừa kế và học hỏi ý tưởng từ những người anh em: Reactjs, Angularjs

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

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/introduce.png){:class="img-responsive"}
{: refdef}















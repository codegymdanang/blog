---
layout: course-vuejs
title: Sử dụng phương thức trong Vuejs
slug : su-dung-phuong-thuc-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery: Phương thức
image: /images/blog/feature_javascript.png
description : Nghe cái tên cũng biết là em này làm gì . methods là một hook trong Vue.js nó giúp chúng ta định nghĩa các phương thức cho ứng dụng.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Nghe cái tên cũng biết là em này làm gì . methods là một hook trong Vue.js nó giúp chúng ta định nghĩa các phương thức cho ứng dụng.



## **1.Ðịnh nghĩa và sử dụng một method**


{% highlight javascript  linenos %}

<div id="app"> 
 <div>{{ sum(3,6) }}</div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 message: "Message", 
 }; 
 }, 
 methods: { 
 sum(num1, num2) { 
 return num1 + num2; 
 }, 
 }, 
 }); 
</script> 


{% endhighlight %}


## **2 . Gọi method**

Nếu chúng ta muốn gọi một biến trong data thì làm như nào? 

{% highlight javascript  linenos %}

<div id="app"> 
 <div>{{ sum(3,6) }}</div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 message: "Message", 
 num: 6, 
 }; 
 }, 
 methods: { 
 sum(num1, num2) { 
 return num1 + num2 + this.num; 
 },
 }, 
 }); 
</script> 


{% endhighlight %}

Dùng từ khóa this, nó là là con trỏ, trỏ đến chính Vue Component. 
Khi chúng ta gọi một phương thức đã định nghĩa trong một phương thức khác thì ta cũng gọi với con trỏ this



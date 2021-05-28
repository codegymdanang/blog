---
layout: course-vuejs
title: Sử dụng watcher trong vuejs
slug : su-dung-watcher-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery:  Watchers
image: /images/blog/feature_javascript.png
description : Watch giúp chúng ta định nghĩa các phương thức lắng nghe sự thay đổi của một biến, prop, computed trong chương trình. Trong watch chúng ta có thể chèn đoạn code nhiệm vụ thực thi khi biến số thay đổi với đầu vào là 2 tham số, newvalue và oldvalue từ params của từng phương thức lắng nghe này.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Watch giúp chúng ta định nghĩa các phương thức lắng nghe sự thay đổi của một biến, prop, computed trong chương trình. Trong watch chúng ta có thể chèn đoạn code nhiệm vụ thực thi khi biến số thay đổi với đầu vào là 2 tham số, newvalue và oldvalue từ params của từng phương thức lắng nghe này 



## **1. Ðịnh nghĩa và sử dụng**


{% highlight javascript  linenos %}

<div id="app"> 
 <div>{{ fullName }}</div> 
 <button @click="changeName">Change name</button> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 fullName: "Duc Hoang", 
 }; 
 }, 
 watch: { 
 fullName(newValue, oldValue) { 
 console.log("newValue", newValue); 
 console.log("oldValue", oldValue); 
 }, 
 }, 
 methods: { 
 changeName() { 
 this.fullName = "Van Anh"; 
 }, 
 }, 
 }); 
</script>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/watcher.png){:class="img-responsive"}
{: refdef}

Khi nhấn vào button khi ta sẽ thấy kết quả như trên 


{% highlight javascript  linenos %}

<div id="app"> 
 <div>{{ fullName }}</div> 
 <button @click="changeName">Change name</button> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 fullName: "Duc Hoang", 
 }; 
 }, 
 watch: { 
 fullName: "printLogs", 
 }, 
 methods: { 
 changeName() { 
 this.fullName = "Van Anh"; 
 }, 
 printLogs(newValue, oldValue) { 
 console.log("newValue", newValue); 
 console.log("oldValue", oldValue); 
 }, 
 }, 
 }); 
</script> 


{% endhighlight %}

Ðoạn mã này cũng có chung kết quả như trên, ta thấy thay vì ta định nghĩa là một phương thức và xử lí ngay tại đó, thì bây giờ ta tạo một method rồi từ định nghĩa fullName ở watch ta gán cho phương thức "printLogs" như vậy sẽ gọn gàng hơn, nếu bạn muốn mọi thứ chỉnh chu gom các phương thức định nghĩa ở methods
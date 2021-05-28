---
layout: course-vuejs
title: Sử dụng component trong vuejs
slug : su-dung-component-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery:  Component
image: /images/blog/feature_javascript.png
description : Trong lập trình giao diện, khi mà số lượng code và số lượng chức năng nhiều ta bắt buộc phải phân tách chúng ra thành nhưng thành phẩn nhỏ hơn đảm nhận từng chức năng nhỏ để gộp thành một giao diện, và định nghĩa tìm ra những điểm chung để tối ưu hóa những thành phần nhỏ đó có thể tái sử dụng trong nhưng giao diện khác nhau. Thì những thành phần đó chúng được gọi là Component. 
Component là một đối tượng rất quan trọng trong Vue.js và trong lập trình xây dựng giao diện người dùng.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Watch giúp chúng ta định nghĩa các phương thức lắng nghe sự thay đổi của một biến, prop, computed trong chương trình. Trong watch chúng ta có thể chèn đoạn code nhiệm vụ thực thi khi biến số thay đổi với đầu vào là 2 tham số, newvalue và oldvalue từ params của từng phương thức lắng nghe này 



## **1. Tạo và sử dụng component**


{% highlight javascript  linenos %}

// Define a new component called button-counter 
Vue.component("button-counter", { 
 data: function () { 
 return { 
 count: 0, 
 }; 
 }, 
 template: 
 '<button v-on:click="count++">You clicked me {{ count }} times. </button>', 
}); 
new Vue({ el: "#app" }); 
<div id="#app"> 
 <button-counter></button-counter> 
</div> 


{% endhighlight %}

Vue.component là cú nháp để khai báo một component 
“button-counter” là tên của component được đăng ký 
Tham số thứ 2 là nội dung component của chúng ta, trong phần này nó chứa những hook life cycle, data, computed, watch,... và những chức năng mà chúng ta đã học ở phần trước. 
<button-counter></button-counter> chúng ta gọi component ra theo tên của nó Run lên ta sẽ được kết quả như sau



{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/component.png){:class="img-responsive"}
{: refdef}

Click vào để tăng biến số. Như vậy ta thấy Vue.component tạo ra một thành phần có giao diện chứa một button có chức năng đếm số.




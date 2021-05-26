---
layout: course-vuejs
title: Vòng đời component
slug : vong-doi-component-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery: Vòng đời component
image: /images/blog/feature_javascript.png
description : Mỗi Vue Component trải qua một loạt các bước khởi tạo khi nó được tạo - Ví dụ: nó cần thiết lập quan sát dữ liệu, biên dịch mẫu, gắn kết cá thể vào DOM và cập nhật DOM khi dữ liệu thay đổi. Ðồng thời, nó cũng chạy các chức năng được gọi là móc vòng đời , cho phép người dùng có cơ hội thêm mã của riêng họ ở các giai đoạn cụ thể

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Mỗi Vue Component trải qua một loạt các bước khởi tạo khi nó được tạo - Ví dụ: nó cần thiết lập quan sát dữ liệu, biên dịch mẫu, gắn kết cá thể vào DOM và cập nhật DOM khi dữ liệu thay đổi. Ðồng thời, nó cũng chạy các chức năng được gọi là móc vòng đời , cho phép người dùng có cơ hội thêm mã của riêng họ ở các giai đoạn cụ thể



## **1. Các vòng đời chính**

- beforeCreate 
- created 
- mounted 
- beforeDestroy 


{% highlight javascript  linenos %}

 <div id="app"> 
 <div>{{ message }}</div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 message: "HI!", 
 }; 
 }, 
 beforeCreate() { 
 console.log("Before Create", this.message); 
 }, 
 created() { 
 console.log("Created", this.message); 
 }, 
 mounted() { 
 console.log("Mounted", this.message); 
 }, 
 beforeDestroy() { 
 console.log("beforeDestroy", this.message); 
 }, 
 }); 
</script>



{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/lifecycle1.png){:class="img-responsive"}
{: refdef}


{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/lifecycle.png){:class="img-responsive"}
{: refdef}

2. beforeCreate Hook. 
Ðược gọi đồng bộ ngay sau khi phiên bản đã được khởi tạo, trước khi thiết lập quan sát dữ liệu và sự kiện / người theo dõi. 
Ở đây chúng ta sẽ không thao tác được với trạng thái của ứng dụng vì mọi thứ chỉ là mới khởi tạo, ví dụ bạn sẽ không lấy được giá trị của data trong hook này

3. created Hook. 
Ðược gọi đồng bộ sau khi đối tượng Vue được tạo. Ở giai đoạn này, đã hoàn tất xử lý các tùy chọn có nghĩa là các tùy chọn sau đã được thiết lập: data, computed, methods, watch/event callbacks. Tuy nhiên, giai đoạn gắn kết vẫn chưa được bắt đầu và thuộc tính $el (truy cập DOM) sẽ chưa khả dụng. 

4. mounted Hook. 
Ðược gọi sau khi thể hiện đã được gắn kết (DOM đã được gắn kết.) ở đây bạn có thể truy cập dom thông qua $refs 
Lưu ý rằng trong mounted không đảm bảo rằng tất cả các thành phần con cũng đã được gắn kết. 

5. beforeDestroy Hook. 
Ðược gọi ngay trước khi một thể hiện Vue bị hủy. Ở giai đoạn này, Vue component vẫn hoạt động đầy đủ. 
Hook này được sử dụng khi bạn muốn hành động gì đó khi một thành phần trước khi bị hủy. Khi thoát trang hay sử dụng câu lệnh điều kiện v-if v-else để ẩn đi một component chẳng hạn.





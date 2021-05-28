---
layout: course-vuejs
title: Tính toán
slug : tinh-toan-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery:  Tính toán
image: /images/blog/feature_javascript.png
description : Trong một chương trình, thường chúng ta sẽ cần những thuộc tính được tính toán từ những data trạng thái có sẵn của ứng dụng, hay chúng ta muốn tạo ta một thể hiện cho một trạng thái nào đó thì ta sẽ dùng computed, computed được hiểu như 1 biến có getter và setter, có 2 cách viết.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong một chương trình, thường chúng ta sẽ cần những thuộc tính được tính toán từ những data trạng thái có sẵn của ứng dụng, hay chúng ta muốn tạo ta một thể hiện cho một trạng thái nào đó thì ta sẽ dùng computed, computed được hiểu như 1 biến có getter và setter, có 2 cách viết



## **1. Cách đơn giản nhất là chỉ định nghĩa getter**

Khi xuất hiện setter getter thì chúng hình dung là à: get và set cho biến gì, chính xác nó sẽ có 1 biến đích để chúng ta tạo ra một thể hiện computed cho biến đó. 
Lấy ví dụ: tạo một computed fullName đinh nghĩa get và set thì chúng ta có thể có được 2 biến firstName và lastName khi chúng ta cập nhật fullName. ngược lại thì khi cập nhật firstName và lastName thì chúng ta cũng có 1 fullName tương ứng.


{% highlight javascript  linenos %}

<div id="app"> 
 <div>{{ fullName }}</div>
 <button @click="changeName">Change name</button> </div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 firstName: "Duc", 
 lastName: "Hoang", 
 }; 
 }, 
 computed: { 
 fullName: { 
 get() { 
 return `${this.firstName} ${this.lastName}`;  }, 
 set(val = "") { 
 const [fistName, lastName] = val.split(" ");  this.firstName = fistName; 
 this.lastName = lastName; 
 }, 
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

Chúng ta sẽ thấy được sự thay đổi khi nhấn vào button "Change Name"


 

---
layout: course-python
title: Sử dụng biến trong python
slug : su-dung-bien-trong-python
category: laptrinhpython
tags: [python]
summery: Sử dụng biến trong python
image: /images/blog/feature_javascript.png
description : Sử dụng biến trong python

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Props là một đối tượng để lưu trữ các giá trị thuộc tính cho một thẻ một component, hiểu nôm na nó như config cho một thẻ vậy, những props này được truyền vào thẻ như cách bạn truyền attributes html element vậy.

## **1. Tạo và sử dụng Props**

2.1 Truyền vào dạng mảng gồm tên các prop mà không bắt buộc kiểu hay giá trị dữ liệu 

{% highlight javascript  linenos %}

<div id="app"> 
 <button-counter message="Vue.js"></button-counter> 
</div> 
<script> 
 Vue.component("button-counter", { 
 props: ["message"], 
 data: function () { 
 return { 
 count: 0, 
 }; 
 }, 
 template: '<button v-on:click="count++">{{message}} {{ count }}. </button>', 
 }); 
 var app = new Vue({ 
 el: "#app", 
 }); 
</script> 


{% endhighlight %}

Như trên chúng ta định nghĩa prop có tên là message, ở thẻ component được gọi ra chúng ta gán message="Vue.js" giống như ta đang sử dụng một html attributes vậy. 
Ở trên thay vì chúng ta tuyền cho message một chuỗi thì chúng ta cũng có thể gán cho nó một biến số từ component cha, với v-bind: 

{% highlight javascript  linenos %}

<div id="app"> 
 <button-counter v-bind:message="framework"></button-counter>
</div>
<script> 
 Vue.component("button-counter", { 
 props: ["message"], 
 data: function () { 
 return { 
 count: 0, 
 }; 
 }, 
 template: '<button v-on:click="count++">{{message}} {{ count }}. </button>', 
 }); 
 var app = new Vue({ 
 el: "#app", 
 data() { 
 return { 
 framework: "Vue.js", 
 }; 
 }, 
 }); 
</script> 



{% endhighlight %}

Như trên ta sử dụng v-bind: + tên props. 
Và v-bind này chúng ta cũng có thể viết ngắn gọn hơn (shorthand) bằng cách bỏ v-bind chỉ cần dấu : ở trước tên thuộc tính. 

2.2 Ðịnh nghĩa kiểu dữ liệu và các options cho một props 
Thông thường chúng ta sẽ định nghĩa kiểu dữ liệu, giá trị mặc định hay validate cho một prop để hạn chế lỗi cũng như tăng tính minh bạch cho từng thuộc tính. 
Sau đâu là một số kiểu định nghĩa props trong Vue.js 


{% highlight javascript  linenos %}

Vue.component("button-counter", { 
 props: { 
 // Basic type check (`null` and `undefined` values will pass any type validation) 
 propA: Number, 
 // Multiple possible types 
 propB: [String, Number], 
 // Required string 
 propC: { 
 type: String, 
 required: true, 
 }, 
 // Number with a default value 
 propD: { 
 type: Number,
 default: 100, 
 }, 
 // Object with a default value 
 propE: { 
 type: Object, 
 // Object or array defaults must be returned from 
 // a factory function 
 default: function () { 
 return { message: "hello" }; 
 }, 
 }, 
 // Custom validator function 
 propF: { 
 validator: function (value) { 
 // The value must match one of these strings 
 return ["success", "warning", "danger"].indexOf(value) !== -1;  }, 
 }, 
 }, 
}); 



{% endhighlight %}

Một prop có thể được định nghĩa theo một loại kiểu dữ liệu nhất định, nếu chúng ta muốn nhận vào nhiều kiểu dữ liệu hơn thì gán type thành một mảng các kiểu dữ liệu vd như propB 
Và những kiểu dữ liệu phải nằm trong các kiểu dữ liệu sau :  
String <br>
Number <br>
Boolean <br>
Array <br>
Object <br>
Date <br>
Function <br>
Symbol <br>

Một số bạn có hỏi khi định nghĩa Prop thì ta ghi tên theo kiểu lowercase cho từ đâu + capitalize cho những từ sau VD: propA vậy khi gọi ra ở thẻ thì ta gọi như nào, vâng chúng ta thêm dấu "-" trước mỗi từ in hoa và đồng thời chuyển từ đó về chữ thường : propA -> prop-a 

{% highlight javascript  linenos %}

<button-counter :prop-a="2" prop-b="Vue.js"></button-counter> 

{% endhighlight %}


Trong component chúng ta có thể gọi prop ra để sử dụng bình thường như một data. Nhưng hãy chú ý là component không được phép chỉnh sửa props của nó.
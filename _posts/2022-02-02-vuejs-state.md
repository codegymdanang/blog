---
layout: course-vuejs
title: Trạng thái và thể hiện trạng thái
slug : trang-thai-va-hien-thi-trang-thai-trong-vuejs
category: laptrinhjavascript
tags: [vuejs]
summery: Trạng thái
image: /images/blog/feature_javascript.png
description : Trong Vue.js nói riêng cũng như trong những ứng dụng nói chung thì trạng thái là những biến số những dữ liệu có thể thay đổi một của chương trình.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trạng thái trong Vue.js là gì? 
Trong Vue.js nói riêng cũng như trong những ứng dụng nói chung thì trạng thái là những biến số những dữ liệu có thể thay đổi một của chương trình. 
Ở Vue.js trạng thái được quản lý trong component sẽ được định nghĩa ở data hook 



## **1. Thể hiện biến lên tài liệu**

Như bài một chúng ta có đề cập đến cú pháp {{ }} để in giá trị một biến ra trang web của ta Bây giờ chúng ta sẽ tìm hiểu thêm về 2 cú pháp đó là 
v-text và v-html 
v-text được hiểu như {{ }} nó được đính vào attribute của một thẻ và cụ thể hơn nó là một directive (sẽ đề cập rõ hơn ở bài 25) directive sẽ có prefix v 
v-html là một directive cũng là để hiển thị giá trị của một trạng thái, nhưng với chức năng cụ thể hơn là khi biến truyền vào là một chuỗi có cú pháp HTML thì nó sẽ chuyển đoạn chuỗi này về HTML DOM luôn, chứ không phải là thuần chuỗi như v-text 



{% highlight javascript  linenos %}

 <div id="app"> 
 {{ message }} 
 <div v-text="message"></div> 
 <div v-html="message_style"></div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data: { 
 message: "Hello Vue!", 
 message_style: "Hi! <strong>Vue.js</strong> Developer",  }, 
 }); 
</script>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/vuestate.png){:class="img-responsive"}
{: refdef}

## **2. Cú pháp điều kiện v-if, v-else-if, v-else**

Giống như cú pháp câu lệnh điều kiện trong các ngôn ngữ lập trình. Thay vì những block { } thì bây giờ nó được đính vào DOM 

{% highlight javascript  linenos %}

 <div id="app"> 
 <div v-if="num===1">Số Một</div> 
 <div v-else-if="num===2">Số Hai</div> 
 <div v-else>Chưa định nghĩa</div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data: { 
 num: 2, 
 }, 
 }); 
</script>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/vueif.png){:class="img-responsive"}
{: refdef}

Với đoạn mã như trên ta sẽ nhận được kết quả là: Số Hai cũng rất dễ hình dung phải không 
Và cũng nhân tiện giới thiệu cho các bạn thẻ <template></template> khi mình muốn xài điều kiện như trên nhưng không muốn sinh ra thẻ div thì hãy thay thẻ div bằng thẻ template

{% highlight javascript  linenos %}

 <div id="app"> 
 <template v-if="num===1">Số Một</template> 
 <template v-else-if="num===2">Số Hai</template> 
 <template v-else>Chưa định nghĩa</template> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data: { 
 num: 2, 
 }, 
 }); 
</script> 


{% endhighlight %}

Thẻ <template></template> này cũng áp dụng bọc một nhóm thẻ chẳng hạn để hiển thị và xử lí theo điều kiện cho nhóm thẻ

## **3. Cú pháp điều kiện v-show**

Directive này nhận giá trị true/false và có chức năng  ẩn/hiện thẻ, component bản chất của nó là toggle style CSS display:none cho thẻ được đính vào. 
v-show không thể sử dụng được cho <template></template>. Vì hiểu đơn giản là nó không thể set CSS cho 1 thẻ mà không được render 

## **4. Vòng lặp v-for**

Giống với vòng lặp for trong các ngôn ngữ lập trình v-for có thể nhận vào một Array, một json Object hoặc một Number 

{% highlight javascript  linenos %}

<div id="app"> 
 <div v-for="(item, index) in names" :key=" index">{{ item }}</div> </div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data: { 
 names: ["Nam", "Duc", "Anh"], 
 },
}); 
</script> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/for.png){:class="img-responsive"}
{: refdef}

Ở đây chúng ta thấy có biến index . index là key của array. nếu không muốn lấy index thì ngắn gọn hơn chúng ta có thể viết 

{% highlight javascript  linenos %}

<div v-for="item in names" :key=" item">{{ item }}</div>  

{% endhighlight %}

## **5. Vòng lặp v-for Object**

{% highlight javascript  linenos %}

<div id="app"> 
 <div v-for="(item, index) in mydog" :key="index">{{index}}: {{ item }} </div> 
</div> 
<script> 
 var app = new Vue({ 
 el: "#app", 
 data: { 
 mydog: { 
 color: "White", 
 gender: "Male", 
 age: 3, 
 }, 
 }, 
 }); 
</script>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/forobject.png){:class="img-responsive"}
{: refdef}

Ở đây index sẽ hứng các key của Object 

## **6. Vòng lặp v-for cho số**

{% highlight javascript  linenos %}

<div id="app"> 
<div v-for="item in 5" :key="index">{{ item }}</div> </div>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![reactjs ](/images/post/vuejs/fornum.png){:class="img-responsive"}
{: refdef}

Ðây là cách khi bạn muốn lặp theo 1 số nhất định, với phần tử đầu tiên bắt đầu từ 1.








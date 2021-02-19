---
layout: course-css
title: Sử dụng Height và Width trong CSS
slug : su-dung-height-width-trong-css
category: laptrinhweb
tags: [css]
summery: Height & Width 
image: /images/blog/angular.png
description : Trình bày và hướng dẫn cách làm đối với mỗi thuộc tính trong lập trình web CSS kèm theo các ví dụ minh hoạ. Trước hết, các bạn sẽ được tìm hiểu các giá trị có trong thuộc tính height và width bao gồm auto, length, phần trăm, initial, inherit. Sau đó tiếp tục đi qua các thuộc tính max-width, min-width, max-height, min-height trong lập trình web CSS. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Như trong bài viết về Sử dụng CSS trong HTML anh đã chia sẻ, các thuộc tính được sử dụng trong CSS nhằm giúp hiển thị, định dạng các phần tử trong HTML khi ta <b>lập trình web</b>. Trong bài viết hôm nay anh sẽ tiếp tục chia sẻ cho các bạn về <b>thuộc tính height và width trong CSS</b> dùng để thiết lập chiều cao và dài cho phần tử HTML.
<br>
Anh sẽ trình bày và hướng dẫn cách làm cho mỗi thuộc tính thông qua các ví dụ minh hoạ. Trước hết, các bạn sẽ được tìm hiểu các giá trị có trong thuộc tính height và width bao gồm auto, length, phần trăm, initial, inherit. Sau đó tiếp tục đi qua các thuộc tính max-width, min-width, max-height, min-height trong <b>lập trình web CSS</b>.
<br>
Cụ thể cách thao tác như thế nào với mỗi thuộc tính, các bạn tiếp tục đọc những chia sẻ dưới đây của anh để tìm hiểu thêm nhé!


## **1. Thuộc tính height và width trong css**

Chúng ta sử dụng thuộc tính height và width để thiết lập chiều cao và dài cho một phần tử HTML

Thuộc tính height và width có thể có các giá trị sau.

- auto : đây là thuộc tính mặc định. Trình duyệt sẽ tính chiều cao và dài cho một phần tử HTML

- length : sử dụng px, cm, và các đơn vị đo khác để xác định chiều cao và dài cho phần tử HTML

- %      : sử dụng phần trăm để tính giá trị chiều cao và dài cho các phần tử HTML

- initial : thiết lập chiều cao và dài cho giá trị ban đầu của phần tử HTML
- inherit : thiết lập chiều cao và dài được kế thừa từ phần tử cha   

Ví dụ sau đây ta tạo ra một thẻ div có chiều cao là 200px và chiều dài là chiếm 50%

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  height: 200px;
  width: 50%;
  background-color: powderblue;
}
</style>
</head>
<body>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/heightwidth.png){:class="img-responsive"}
{: refdef}


- Ví dụ chúng ta có thể thiết lập chiều cao là 100px và chiều dài là 500px như sau


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  height: 100px;
  width: 500px;
  background-color: powderblue;
}
</style>
</head>
<body>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/heightwidth1.png){:class="img-responsive"}
{: refdef}

## **2. Thuộc tính max-width trong css**

Chúng ta sử dụng thuộc tính max-width để thiết lập giá trị maxium (giá trị lớn nhất) của chiều dài của một phần tử HTML.

Giá trị max-width có thể là px, cm, hoặc %. Ví dụ nếu ta sử dụng thẻ div nếu chiều dài của thẻ div mà lớn hơn chiều dài của trình duyệt thì nó sẽ xuất hiện một thanh kéo ngang như vậy thì rất bất tiện cho người dùng vì họ phải kéo chuột mới thấy hết những nội dung còn lại.

Chúng ta sử dụng max-width để giải quyết bất cập trên.


{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
div {
  max-width: 500px;
  height: 100px;
  background-color: powderblue;
}
</style>
</head>
<body>

<h2>Set the max-width of an element</h2>
<p>This div element has a height of 100px and a max-width of 500px:</p>

<div></div>

<p>Nếu ta thay đổi kích thước của trình duyệt nhỏ lại thì tự động thẻ div sẽ tự đều chỉnh cho vừa với trình duyệt.</p>

</body>
</html>

{% endhighlight %}



Nếu ta thay đổi kích thước của trình duyệt nhỏ lại thì tự động thẻ div sẽ tự đều chỉnh cho vừa với trình duyệt và sẽ không xuất hiện thanh kéo ngang

## **3. Thuộc tính min-width trong css**

Ngược với thuộc tính max-width thì thuộc tính min-width sử dụng để thiết lập giá trị min (nhỏ nhất) của chiều dài của một phân tử HTML

Nếu nội dung bên trong của phần tử HTML mà nhỏ hơn giá trị min-width thì giá trị min-width sẽ được sử dụng

Nếu nội dung bên trong của phần tử HTML mà lớn hơn giá trị min-width thì giá trị min-width sẽ không được sử dụng

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
span {
  background-color: yellow;  
}

span.ex1 {
  min-width: 500px;
  display: inline-block;
}
</style>
</head>
<body>
<h1>The min-width Property</h1>

<h2>min-width: none (default):</h2>
<span>Lorem ipsum dolor sit amet...</span>

<h2>min-width: 500px:</h2>
<span class="ex1">Lorem ipsum dolor sit amet...</span>

</body>
</html>


{% endhighlight %}

## **4. Thuộc tính max-height trong css**

Thuộc tính max-heigh để thiết lập giá trị maxium (giá trị lớn nhất) của chiều cao của một phần tử HTML

Nếu nội dung bên trong phần tử HTML mà cao hơn giá trị max-height thì sẽ xuất hiện thanh cuộn theo chiều dọc 

Nếu nội dung bên trong phần tử HTML mà không cao hơn giá trị max-heigh thì giá trị này không được sử dụng

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
p.ex1 {
  max-height: 50px;
  overflow: auto;
}
</style>
</head>
<body>
<h1>The max-height Property</h1>

<h2>max-height: none (default):</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam semper diam at erat pulvinar, at pulvinar felis blandit. Vestibulum volutpat tellus diam, consequat gravida libero rhoncus ut. Maecenas imperdiet felis nisi, fringilla luctus felis hendrerit sit amet. Pellentesque interdum, nisl nec interdum maximus, augue diam porttitor lorem, et sollicitudin felis neque sit amet erat.</p>

<h2>max-height: 50px:</h2>
<p class="ex1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam semper diam at erat pulvinar, at pulvinar felis blandit. Vestibulum volutpat tellus diam, consequat gravida libero rhoncus ut. Maecenas imperdiet felis nisi, fringilla luctus felis hendrerit sit amet. Pellentesque interdum, nisl nec interdum maximus, augue diam porttitor lorem, et sollicitudin felis neque sit amet erat.</p>

</body>
</html>


{% endhighlight %}

{:refdef: style="text-align: center;"}
![text1](/images/post/css/heightwidth2.png){:class="img-responsive"}
{: refdef}

## **5. Thuộc tính min-height trong css**

Sử dụng thuộc tính min-height để thiết lập chiều cao nhỏ nhất (tối thiểu) cho một phần tử HTML. Nó ngược lại với max-heigh.

Nếu nội dung bên trong phân tử mà nhỏ hơn giá trị min-height thì giá trị min-height sẽ được sử dụng

Nếu nội dung bên trong phần tử là lớn hơn giá trị min-height thì giá trị min-height không được sử dụng

{% highlight html linenos %}

<!DOCTYPE html>
<html>
<head>
<style>
p {
  background-color: yellow;  
}

p.ex1 {
  min-height: 100px;
}
</style>
</head>
<body>
<h1>The min-height Property</h1>

<h2>min-height: none (default):</h2>
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam semper diam at erat pulvinar, at pulvinar felis blandit...</p>

<h2>min-height: 200px:</h2>
<p class="ex1">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Etiam semper diam at erat pulvinar, at pulvinar felis blandit...</p>

</body>
</html>


{% endhighlight %}


## **6. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/CSS-Fundamental" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}








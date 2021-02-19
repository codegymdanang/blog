---
layout: course-css
title: Khai báo cú pháp trong CSS  
slug : khai-bao-cu-phap-trong-css
category: laptrinhweb
tags: [css]
summery: Cú pháp   
image: /images/blog/angular.png
description : Trình bày chủ đề Cú pháp trong lập trình web CSS. Nhằm giúp các bạn có thể hiểu và áp dụng được cách khai báo cú pháp trong CSS vào thực hành một cách hiệu quả nhất. Bài viết sẽ lần lượt giới thiệu thành phần của cú pháp bao gồm selector, thuộc tính và giá trị. Cách thao tác với bộ chọn thẻ TML, bộ chọn Class, ID, bộ chọn thuộc tính. Hướng dẫn cách chọn selector con, làm như thế nào để sử dụng nhiều CSS trong một style, CSS cho một nhóm selector. 
youtubeId: 1K8lGmOg4sg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Với những người học <b>lập trình web</b> và làm việc với website. Bên cạnh học và sử dụng ngôn ngữ HTM, thì CSS cũng là một trong những ngôn ngữ được sử dụng phổ biến trong làm web. Vì những tiện ích mà ngôn ngữ này mang lại cho người dùng như giúp tiết kiệm thời gian hơn nhờ vào khả năng cung cấp các rule để định dạng một trang web thay vì phải thiết lập riêng lẻ từng thuộc tính cho từng thẻ như trong lập trình web HTML.
<br>
Trong đó, khi mới bắt đầu làm quen với <b>lập trình web CSS</b>, người học trước hết phải nắm được cách <b>khai báo cú pháp trong lập trình web CSS</b>. Vì vậy trong bài viết hôm nay, anh sẽ trình bày về chủ đề <b>Cú pháp</b> trong CSS để giúp các bạn có thể hiểu và áp dụng được vào thực hành một cách hiệu quả nhất. Bài viết sẽ lần lượt giới thiệu thành phần của cú pháp. Cách thao tác với bộ chọn thẻ TML, bộ chọn Class, ID, bộ chọn là thuộc tính. Hướng dẫn cách chọn selector con, làm như thế nào để sử dụng nhiều CSS trong một style, CSS cho một nhóm selector.
<br>
Hi vọng với những chia sẻ kèm theo các ví dụ minh hoạ cụ thể cho mỗi phần dưới đây, các bạn có thể hiểu rõ và áp dụng được vào thực hành trong quá trình <b>lập trình web CSS</b>.


## **1. Cú pháp CSS**

Cú pháp của CSS được chia ra làm 3 phần

- Phần 1 gọi là selector (bộ chọn) : Gồm các các thẻ HTML 
- Phần 2 gọi là thuộc tính : gồm các thuộc tính của thẻ HTML
- Phần 3 gọi là giá trị    : Giá trị sẽ được sử dụng.

{:refdef: style="text-align: center;"}
![syntax1](/images/post/css/syntax1.png){:class="img-responsive"}
{: refdef}

- Ví dụ như ta muốn làm cho table có border là 1 px và có màu xám thì ta khai báo css như sau

{% highlight css linenos %}

   table { border :1px solid #C00; }

{% endhighlight %}

+ Trong đó table chính là selector
+ Border chính là thuộc tính
+ 1px solid #C00 chính là giá trị cho thuộc tính border

## **2. Bộ chọn thẻ HTML**

- Ví dụ như ta muốn tất cả thẻ h1 trong trong web phải có màu xanh dương. Ta khai báo như sau

{% highlight css linenos %}

h1 {
   color: #36CFFF; 
}

{% endhighlight %}

- Như vậy selector (bộ chọn) trên được gọi là bộ chọn sử dụng các thẻ HTML  như h1, table, ul, form v.v. Chúng ta áp dụng CSS trên các thẻ của HTML

## **3. Bộ chọn Class**

Chúng ta có thể tạo ra bộ chọn bằng class với cách khai báo là .tên-class như sau. Ví dụ như ta tạo ra class là black

{% highlight css linenos %}

.black {
   color: #000000; 
}

{% endhighlight %}

- Chúng ta có thể sử dụng bộ chọn class trong HTML như sau

{% highlight css linenos %}

<p class = "black">
   This para will be styled by the classes center and bold.
</p>

{% endhighlight %}

## **4. Bộ chọn ID**

Cũng tương tự như class chúng ta có thể tạo ra bộ chọn bằng ID với cách khai báo #tên-id. Ví dụ như ta muốn tạo ra Id là black như sau

{% highlight css linenos %}

#black {
   color: #000000; 
}

{% endhighlight %}

- Chúng ta có thể sử dụng bộ chọn class trong HTML như sau

{% highlight css linenos %}

<p id = "black">
   This para will be styled by the classes center and bold.
</p>
{% endhighlight %}

Sự khác nhau giữa bộ chọn class và id là Id có nghĩa là duy nhất. Chỉ áp dụng 1 phần tử trong web. Còn class thì nhiều phần tử trong web có thể dùng được.

## **5. Dấu * trong selector**

Nếu chúng ta không muốn chọn một selector cụ thể thì ta có thể sử dụng dấu * có nghĩa là chọn toàn bộ các phần tử trong HTML.

{% highlight css linenos %}

* { 
   color: #000000; 
}

{% endhighlight %}

## **6. chọn selector con**

Ví dụ như ta có thẻ HTML ul trong thẻ ul chứa đựng các thẻ em . Nhưng trong tài liệu HTML lại có nhiều thẻ em, mà ta chỉ muốn sử dụng em mà có cha là ul thôi thì ta dùng cách sau đây

{% highlight css linenos %}

ul em {
   color: #000000; 
} 

{% endhighlight %}

Như vậy màu #000000 chỉ được sử dụng cho em. Mà thẻ em đó được chứa đựng bên trong thẻ ul.

- Ngoài ra để chọn selector con em ta có thể viết như sau

{% highlight css linenos %}

ul > em {
   color: #000000; 
} 

{% endhighlight %}

## **7. Bộ chọn là thuộc tính**

Chúng ta có thể sử dụng bộ chọn trên thuộc tính của thẻ HTML. Ví dụ như trong một form chúng ta sẽ có nhiều input như text, password, hay textarea. Chúng ta chỉ muốn sử dụng CSS cho input kiểu text mà thôi. Thì chúng ta dùng cách sau

{% highlight css linenos %}

input[type = "text"] {
   color: #000000; 
}

{% endhighlight %}

## **8. Sử dụng nhiều css trong một style**

Ví dụ như chúng ta muốn sử dụng nhiều loại giá trị như màu sắc, kích thướt, khoảng cách cho thẻ H1. Thì chúng ta có thể ghi nhiều dòng thuộc tính như sau

{% highlight css linenos %}

h1 {
   color: #36C;
   font-weight: normal;
   letter-spacing: .4em;
   margin-bottom: 1em;
   text-transform: lowercase;
}
{% endhighlight %}

## **9. Sử dụng  css cho một nhóm selector**

Ví dụ như ta có các thẻ H1, H2, H3 đều có chung thuộc tính là color #36, kích thướt font là 4m thì ta có thể nhóm chúng lại với nhau như sau.

{% highlight css linenos %}

h1, h2, h3 {
   color: #36C;
   font-weight: normal;
   letter-spacing: .4em;
   margin-bottom: 1em;
   text-transform: lowercase;
}
{% endhighlight %}

- Hoặc chúng ta cũng có thể nhóm nhiều id hoặc class lại với nhau như sau

{% highlight css linenos %}

#content, #footer, #supplement {
   position: absolute;
   left: 510px;
   width: 200px;
}

{% endhighlight %}

## **10. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **11. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/CSS-Fundamental" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}



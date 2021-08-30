---
layout: course-es6
title: Sử dụng Rest Param trong ES6 
slug : su-dung-rest-param-trong-es6
category: laptrinhjavascript
tags: [es6]
summery:  Tham số rest
image: /images/blog/feature_javascript.png
description : Trình bày về cách sử dụng rest param của ES6. Lần lượt giới thiệu và giải thích khái niệm rest param trong phương thức của ES6 là gì? Đưa ra các ví dụ về Rest parameter trong ES6 và hướng dẫn cụ thể cách dùng như thế nào để bạn có thể thực hành được dễ dàng hơn. 

youtubeId: HZjpCbC4QS0
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về cách khai báo và sử dụng <b>rest param của ES6</b>. Lần lượt giới thiệu và giải thích khái niệm và ví dụ về rest param của ES6 là gì? 

## **1. Giới thiệu về rest param trong ES6**

ES6 cung cấp cho chúng ta một loại tham số mới truyền trong phương thức được gọi là rest param. Có nghĩa là chúng ta có thể truyền một mảng các tham số vào phương thức. Để truyền được mảng các tham số của một phương thức chúng ta dùng dấu 3 chấm như sau.

{% highlight javascript  linenos %}

function fn(a,b,...args) {
   //...
}
{% endhighlight %}

Như các em thấy phương thức fn có tham số là a,b và ... args. Thì ...args được gọi là rest param. Chúng ta có thể truyền nhiều giá trị vào.

Ví dụ như chúng ta gọi hàm fn và truyền tham số sau

{% highlight javascript  linenos %}

fn(1,2,3,'A','B','C');

{% endhighlight %}

Lúc này tham số ở phương thức fn(a,b,...args) thì a sẽ ứng với số 1, b sẽ ứng với số 2 và mảng [3,'A','B','C'] sẽ ứng với tham số ...args

Nếu như ta chỉ truyền 2 tham số vào phương thức fn như sau

{% highlight javascript  linenos %}

fn(1,2);

{% endhighlight %}

Thì lúc này mảng ...args sẽ là mảng rỗng [].

Chú ý rest param luôn luôn ở vị trí là tham số sau cùng của phương thức. Nếu như ta đặt tham số rest ở giữa sẽ bị lỗi như sau.


{% highlight javascript  linenos %}

function foo(a,...rest, b) {
 // error
};

{% endhighlight %}

Chúng ta phải đặt lại là foo(a,b,...rest)

## **2. Ví dụ rest parameter trong ES6**

Anh có phương thức sum như sau:


{% highlight javascript  linenos %}

function sum(...args) {
    let total = 0;
    for (const a of args) {
        total += a;
    }
    return total;
}

sum(1, 2, 3);

{% endhighlight %}

Khi gọi sum thì kết quả nhận được sẽ là 6.

Vì ...agrs là một mảng nên ta cũng có thể sử dụng vòng lặp for để duyệt qua các phần tử hoặc dùng cách phương thức có sẳn của một array như filter


{% highlight javascript  linenos %}

function sum(...args) {
    return args.filter(e => typeof e === 'number')
        .reduce((prev, curr)=> prev + curr);
} 


{% endhighlight %}


## **3. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}



































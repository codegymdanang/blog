---
layout: course-typescript
title: Sử dụng mệnh đề điều kiện trong TypeScript  
slug : su-dung-menh-de-dieu-kien-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: Câu Điều kiện   
image: /images/blog/feature_javascript.png
description : Giới thiệu về câu điều kiện trong Typescrip, cách hoạt động của câu điều kiện trong Typescrip
youtubeId: ufziMUA9ERY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về <b>câu điều kiện</b> là như thế nào? 

## **1. Câu điều kiện tử if-else**

Cũng tương tự như Javascript. Câu lệnh if else trong Typescript cũng giống như cú pháp và cách sử dụng trong JS.


{% highlight javascript  linenos %}


let x: number = 10, y = 20;

if (x > y) 
{
    console.log('x is greater than y.');
} 
else if (x < y)
{
    console.log('x is less than y.'); //This will be executed
}
else if (x == y) 
{
    console.log('x is equal to y');
}

{% endhighlight %}

- Câu điều kiện tam phân.

{% highlight javascript  linenos %}

let x: number = 10, y = 20;

x > y? console.log('x is greater than y.'): console.log('x is less than or equal to y.')

{% endhighlight %}

## **2. Câu điều kiện tử switch**

Trong Typescript cũng tương tự cách dùng switch như trong Javascrip hay Java.

{% highlight javascript  linenos %}

let day : number = 4;

switch (day) {
    case 0:
        console.log("It is a Sunday.");
        break;
    case 1:
        console.log("It is a Monday.");
        break;
    case 2:
        console.log("It is a Tuesday.");
        break;
    case 3:
        console.log("It is a Wednesday.");
        break;
    case 4:
        console.log("It is a Thursday.");
        break;
    case 5:
        console.log("It is a Friday.");
        break;
    case 6:
        console.log("It is a Saturday.");
        break;
    default:
        console.log("No such day exists!");
        break;
}

{% endhighlight %}

- Trong Typescript chúng ta cũng có thể sử dụng expression trong điều kiện như sau:

{% highlight javascript  linenos %}

let x = 10, y = 5;

switch (x-y) {
    case 0:
        console.log("Result: 0");
        break;
    case 5:
        console.log("Result: 5");
        break;
    case 10:
        console.log("Result: 10");
        break;
}

{% endhighlight %}


<br>
## **3. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}








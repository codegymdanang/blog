---
layout: course-typescript
title: Sử dụng String trong TypeScript  
slug : su-dung-spring-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: String   
image: /images/blog/feature_javascript.png
description : Giới thiệu và hướng dẫn sử dụng về String trong TypeScript. Tìm hiểu String trong TypeScript là gì? Bên cạnh đó cũng trình bày về Method charAt, Method concat, Method indexOf, Method replace, Method split và Methoad toUpperCase được sử dụng trong ngôn ngữ lập trình TypeScript. Bài viết chia sẻ kèm theo những ví dụ minh hoạ cho các thao tác thực hiện của mỗi phương thức sẽ giúp người đọc hiểu được và thực hiện được khi làm việc với các dự án lập trình web.
youtubeId: 3r74IFfylVE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về <b>String</b> là như thế nào? 

## **1. String là gì**

Chúng ta sử dụng String khi chúng ta chứa các giá trị là chữ. Chúng ta có thể sử dụng dấu ' hoặc " để tạo ra chuỗi.

{% highlight javascript  linenos %}

let employeeName:string = 'John Smith'; 
//OR
let employeeName:string = "John Smith"; 

{% endhighlight %}

## **2. Method charAt**

{% highlight javascript  linenos %}

let str: string = 'Hello TypeScript';
str.charAt(0); // returns 'H'
str.charAt(2); // returns 'l'
"Hello World".charAt(2); returns 'l'

{% endhighlight %}

## **3. Method concat**

{% highlight javascript  linenos %}

let str1: string = 'Hello';
let str2: string = 'TypeScript';
str1.concat(str2); // returns 'HelloTypeScript'
str1.concat(' ', str2); // returns 'Hello TypeScript'
str1.concat(' Mr. ', 'Bond'); // returns 'Hello Mr. Bond'

{% endhighlight %}

## **4. Method indexOf**

{% highlight javascript  linenos %}

let str: string = 'TypeScript';

str.indexOf('T'); // returns 0
str.indexOf('p'); // returns 2
str.indexOf('e'); // returns 3
str.indexOf('T', 1); // returns -1
str.indexOf('t', 1); // returns 9

{% endhighlight %}

## **5. Method replace**

{% highlight javascript  linenos %}

let str1: string = 'Hello Javascript';
let str2: string = 'TypeScript';

str1.replace('Java', 'Type'); // returns 'Hello TypeScript'
str1.replace('JavaScript', str2); // returns 'Hello TypeScript'
str1.replace(/Hello/gi, 'Hi'); // returns 'Hi TypeScript'

{% endhighlight %}

## **6. Method split**

{% highlight javascript  linenos %}

let str1: string = 'Apple, Banana, Orange';
let str2: string = ',';

str1.split(str2) // returns [ 'Apple', ' Banana', ' Orange' ]
str1.split(',') // returns [ 'Apple', ' Banana', ' Orange' ]
str1.split(',', 2) // returns [ 'Apple', ' Banana' ]
str1.split(',', 1) // returns [ 'Apple']

{% endhighlight %}

## **7. Method toUpperCase**

{% highlight javascript  linenos %}

let str: string = 'Hello Typescript';
str.toUpperCase(); // returns 'HELLO TYPESCRIPT'
'hello typescript'.toUpperCase(); // returns 'HELLO TYPESCRIPT'

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


























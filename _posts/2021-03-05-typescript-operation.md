---
layout: course-typescript
title: Sử dụng toán tử trong TypeScript
slug : su-dung-toan-tu-trong-typescript
category: laptrinhjavascript
tags: [typescript]
summery: Toán tử   
image: /images/blog/feature_javascript.png
description : Bài viết giúp hiểu được toán tử trong ngôn ngữ lập trình web TypeScript là gì? Hướng dẫn cách sử dụng các phép toán tử trong TypeScript. Bao gồm toán tử số số học, toán gán, toán tử so sánh, toán tử logic, toán tử tam phân và toán tử type trong TypeScript như thế nào cho hiệu quả khi lập trình web với ngôn ngữ TypeScript. Trong mỗi phép toán tử, bài viết có những ví dụ minh hoạ cụ thể cú pháp thực hiện sẽ giúp được người đọc dễ dàng tham khảo và áp dụng được vào thực hành.
youtubeId: GxgKxp1G5lc
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người về <b>toán tử</b> là như thế nào? 

## **1. Toán tử là gì**

Trong Typescript cũng hỗ trợ các phép tính toán học, so sánh, logic, phép gán, bitwise và điều kiện giúp cho chúng ta thực hiện các tính toán và so sánh.

## **2. Toán tử số số học**

Thực hiện các phép tính cộng, trừ, nhân, chia, mod.

{% highlight javascript  linenos %}

var x = 5, y = 10, z = 15;

x + y; //returns 15

y - x; //returns 5

x * y; //returns 50

y / x; //returns 2

x % 2; //returns 1

x++; //returns 6

x--; //returns 4

{% endhighlight %}

## **3. Toán  gán**

{% highlight javascript  linenos %}

var x = 5, y = 10, z = 15;

x = y; //x would be 10

x += 1; //x would be 6

x -= 1; //x would be 4

x \*= 5; //x would be 25

x /= 5; //x would be 1

x %= 2; //x would be 1

{% endhighlight %}

## **4. Toán tử so sánh**

{% highlight javascript  linenos %}

var a = 5, b = 10, c = "5";
var x = a;

a == c; // returns true

a === c; // returns false

a == x; // returns true

a != b; // returns true

a > b; // returns false

a < b; // returns true

a >= b; // returns false

a <= b; // returns true

a >= c; // returns true

a <= c; // returns true

{% endhighlight %}

## **5. Toán tử logic**

{% highlight javascript  linenos %}

var a = 5, b = 10;

(a != b) && (a < b); // returns true

(a > b) || (a == b); // returns false

(a < b) || (a == b); // returns true

!(a < b); // returns false

!(a > b); // returns true

{% endhighlight %}

## **6. Toán tử tam phân**

{% highlight javascript  linenos %}

var a = 10, b = 5;

var c = a > b? a : b; // value of c would be 10
var d = a > b? b : a; // value of d would be 5
{% endhighlight %}

## **7. Toán tử type**

- Toán tử in 

{% highlight javascript  linenos %}

let Bike = {make: 'Honda', model: 'CLIQ', year: 2018};
console.log('make' in Bike);   // 

{% endhighlight %}

kết quả : true

- Toán tử delete 

{% highlight javascript  linenos %}

let Bike = { Company1: 'Honda',
             Company2: 'Hero',
             Company3: 'Royal Enfield'
           };
delete Bike.Company1;
console.log(Bike);   

{% endhighlight %}

kết quả : { Company2: 'Hero', Company3: 'Royal Enfield' }

- Toán tử typeof 

{% highlight javascript  linenos %}

let message = "Welcome to " + "JavaTpoint";
console.log(typeof message);  

{% endhighlight %}

kết quả : String

- Toán tử instanceof 

{% highlight javascript  linenos %}

let arr = [1, 2, 3];
console.log( arr instanceof Array ); // true
console.log( arr instanceof String ); // false  

{% endhighlight %}


## **8. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
















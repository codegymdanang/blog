---
layout: course-javascript
title: Sử dụng toán tử trong Javascript   
slug : su-dung-toan-tu-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Toán tử   
image: /images/blog/feature_javascript.png
description : Khi lập trình web, bên cạnh sử dụng văn bản chúng ta sẽ cần dùng đến các kí tự, số học để dùng cho các phép toán học khác nhau như các phép tính, so sánh, logic và điều kiện. Để hỗ trợ các phép tính này, trong ngôn ngữ lập trình web JavaScript cung cấp cho chúng ta thuộc tính Toán tử. Với những chia sẻ trong bài viết này sẽ giúp các bạn hiểu được toán tử trong JavaScript là gì? Và lần lượt hướng dẫn sử dụng các phép toán tử trong lập trình web bao gồm toán tử số học, toán gán, so sánh, toán tử logic và tam phân. Trong mỗi phép toán, có kèm theo ví dụ minh hoạ cụ thể để các bạn có thể tham khảo thêm.
youtubeId: DfvK2Tsl4bM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Khi <b>lập trình web</b>, bên cạnh sử dụng văn bản chúng ta sẽ cần dùng đến các kí tự, số học để dùng cho các phép toán học khác nhau như các phép tính, so sánh, logic và điều kiện. Để hỗ trợ các phép tính này, trong ngôn ngữ <b>lập trình web</b> JavaScript cung cấp cho chúng ta thuộc tính <b>Toán tử</b>.

<br>
Tiếp theo trong những chia sẻ dưới đây, anh sẽ giúp các bạn hiểu được <b>toán tử</b> trong JavaScript là gì? Và lần lượt hướng dẫn để các bạn sử dụng được các phép <b>toán tử</b> trong <b>lập trình web</b> bao gồm toán tử số học, toán gán, so sánh, toán tử logic và tam phân. Trong mỗi phép toán, anh có kèm theo ví dụ minh hoạ cụ thể, các bạn có thể tham khảo thêm để dễ dàng nắm bắt và áp dụng được vào thực hành hiệu quả hơn.  


## **1. Toán tử là gì**

Trong ngôn ngữ lập trình JavaScript hỗ trợ các phép tính toán học, so sánh, logic và điều kiện giúp cho chúng ta thực hiện các tính toán.

## **2. Toán tử số số học**

Thực hiện các phép tính cộng, trừ, nhân, chia, mod

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

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}






---
layout: course-javascript
title: Sử dụng Array trong Javascript 
slug : su-dung-array-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Mảng   
image: /images/blog/feature_javascript.png
description : Trong lập trình web với ngôn ngữ lập trình JavaScript, khi muốn lưu cho nhiều hơn 1 giá trị thì lúc này chúng ta sẽ sử dụng đến thuộc tính Mảng Array. Vậy Mảng Array trong ngôn ngữ lập trình JavaScript là gì? Các cách thao tác với Mảng như khai báo, lấy các phần tử trong Mảng, kiểm tra xem có bao nhiêu phần từ trong độ dài của Mảng và tìm hiểu các phương thức có sẵn trong Mảng để áp dụng vào thực hành. Tất cả những thắc mắc trên sẽ được giải đáp thông qua nhưng chia sẻ trong bài viết này.
youtubeId: 9Dw1NuJrVJs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Như trong những chia sẻ về Biến trong <b>lập trình web</b> JavaScript, chúng ta đã biết Biến được sử dụng để lưu giá trị. Tuy nhiên nó chỉ có thể lưu được 1 giá trị, nếu trường hợp bạn muốn lưu cho nhiều hơn 1 giá trị thì lúc này đòi hỏi các bạn cần phải sử dụng đến thuộc tính <b>Mảng (Array)</b>.

<br>
Vậy <b>Mảng (Array)</b> trong ngôn ngữ lập trình JavaScript là gì? Các cách thao tác với Mảng như khai báo, lấy các phần tử trong Mảng, kiểm tra xem có bao nhiêu phần từ trong độ dài của Mảng và tìm hiểu các phương thức có sẵn trong Mảng để áp dụng vào khi sử dụng ngôn ngữ JavaScript trong <b>lập trình web</b>.

<br>
Bài viết hôm nay anh sẽ trình bày về chủ đề <b>Mảng</b> trong JavaScript, hy vọng thông qua những chia sẻ trong bài viết sẽ giúp các bạn giải đáp được những thắc mắc trên cũng như vận dụng được vào thực hành.


## **1. Mảng là gì**

Chúng ta thấy trong các bài viết trước một biến chỉ lưu trữ được 1 giá trị ví dụ như var i = 1. Nếu chúng ta muốn 1 biến chứa nhiều hơn 1 giá trị ví dụ như 10 giá trị thì ta sẽ sử dụng Array.

Array là một loại biến đặc biệt nó có thể chứa đựng nhiều giá trị trong đó. Mỗi giá trị sẽ tương ứng với một vị trí trong Array, mình gọi đó là Index. Trong Array, Index được đếm bắt đầu từ 0.

## **2. Khai báo Mảng**

- Cách 1 : Chúng ta khai báo Array như sau

Cú pháp

{% highlight javascript  linenos %}

var <array-name> = [element0, element1, element2,... elementN];

{% endhighlight %}

Ví dụ ta định nghĩa và khởi tạo mảng như sau

{% highlight javascript  linenos %}

var stringArray = ["one", "two", "three"];

var numericArray = [1, 2, 3, 4];

var decimalArray = [1.1, 1.2, 1.3];

var booleanArray = [true, false, false, true];

var mixedArray = [1, "two", "three", 4];

{% endhighlight %}

- Cách 2 : chúng ta sử dụng new đối tượng Array

Cú pháp

{% highlight javascript  linenos %}

var arrayName = new Array();

var arrayName = new Array(Number length);

var arrayName = new Array(element1, element2, element3,... elementN);

{% endhighlight %}

Ví dụ 

{% highlight javascript  linenos %}

var stringArray = new Array();
stringArray[0] = "one";
stringArray[1] = "two";
stringArray[2] = "three";
stringArray[3] = "four";

var numericArray = new Array(3);
numericArray[0] = 1;
numericArray[1] = 2;
numericArray[2] = 3;

var mixedArray = new Array(1, "two", 3, "four");

{% endhighlight %}

## **3. Lấy các phần tử trong Mảng**

Chúng ta sử dụng Index (vị trí) của các đối tượng trong mảng để lấy ra giá trị của nó. Hãy luôn nhớ rằng Mảng luôn bắt đầu từ vị trị 0 chứ không phải là 1.

{% highlight javascript  linenos %}

var stringArray = new Array("one", "two", "three", "four");

stringArray[0]; // returns "one"
stringArray[1]; // returns "two"
stringArray[2]; // returns "three"
stringArray[3]; // returns "four"

var numericArray = [1, 2, 3, 4];
numericArray[0]; // returns 1
numericArray[1]; // returns 2
numericArray[2]; // returns 3
numericArray[3]; // returns 4

{% endhighlight %}

## **4. Độ dài của mảng Mảng**

Để biết được kích thước và độ dài của mảng có bao nhiêu phần tử, ta sử dụng từ khoá length.


{% highlight javascript  linenos %}

var stringArray = new Array("one", "two", "three", "four");

var len = stringArray.length // kết quả là 4

{% endhighlight %}

## **5. Các phương thức có sẵn trong Mảng**

Array có hỗ trợ sẵn các phương thức để thao tác với các phần tử trong mảng như concat() , filter(), forEach(), join(), map(), pop(), push(), reduce(), reverse(), slice(), sort(), toString(), unship() để thao tác với các phần tử trong mảng. Các phương thức thường sử dụng phổ biến nhất là:
+ pop xoá 1 phần tử khỏi mảng
+ push là thêm 1 phần tử vào mảng 
+ slice cắt mảng      

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}



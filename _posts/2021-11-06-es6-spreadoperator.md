---
layout: course-es6
title: Sử dụng spread operator trong ES6 
slug : su-dung-spread-operator-trong-es6
category: laptrinhjavascript
tags: [es6]
summery:  Toán tử spread
image: /images/blog/feature_javascript.png
description : Trình bày về cách cách sử dụng toán tử spread của ES6. Lần lượt giới thiệu và giải thích khái niệm toán tử spread trong của ES6 là gì? 

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  cách khai báo và sử dụng <b>toán tử spread </b> của ES6. Lần lượt giới thiệu và giải thích khái niệm và ví dụ về toán tử spread của ES6 là gì? 

## **1. Giới thiệu về toán tử spread**

ES6 cung cấp cho chúng ta một loại toán tử mới gọi là spread. Cơ chế của nó hoạt động như sau. Ví dụ anh có một mảng tên là odd là lưu các giá trị số lẻ 1,3,5. Tiếp đến anh có mảng tên là compile chứa các số chẵn như sau

{% highlight javascript  linenos %}

const odd = [1,3,5];
const combined = [2,4,6, ...odd];
console.log(combined);

{% endhighlight %}

Các em thấy trong mảng combined chúng ta truyền mảng odd vào và trước nó là 3 dấu chấm (...odd). Khi chương trình chạy thì nó sẽ in ra là 2,4,6,1,3,5. 

Như vậy ...odd được gọi là toán tử spread. Tham số odd sẽ uppack (giải nén các giá trị trong nó) các giá trị trong mảng odd (1,3,5) và gán vào mảng mới. Chính vì vậy mà ta nhận được kết quả là 2,4,6,1,3,5 

## **2. Sự khác nhau toán tử spread và tham số rest**

Sự khác nhau giữa toán tử spread và tham số rest là :

- Toán tử spread là cách ta uppack các giá trị trong mảng ra thành các phần tử. Ví dụ như mảng odd có 3 phần tử. Khi gọi combined = [2,4,6, ...odd]; lúc này chúng ta có các giá trị 2,4,6,1,3,5

- Ngược lại với toán tử spread thì tham số rest nhóm các giá trị đơn lẻ thành 1 biến. Ví dụ dưới đây chúng ta nhóm các giá trị đơn lẻ thành 1 biến trong tham số của phương thức f

{% highlight javascript  linenos %}

function f(a, b, ...args) {
  console.log(args);
}

f(1,2,3,4,5);

{% endhighlight %}


Như các em thấy giá trị  3,4,5 được gán lại cho 1 biến trong mảng là args.

- Tham số rest bắt buộc phải ở cuối cùng của phương thức tuy nhiên toán tử spread có thể ở bất kỳ đâu

{% highlight javascript  linenos %}

const odd = [1,3,5];
const combined = [...odd, 2,4,6];
console.log(combined);

{% endhighlight %}





















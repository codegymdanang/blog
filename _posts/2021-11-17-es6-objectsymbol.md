---
layout: course-es6
title: Sử dụng Symbol trong ES6 
slug : su-dung-symbol-assign-trong-es6
category: laptrinhjavascript
tags: [es6]
summery: Symbol
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  symbol của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về symbol  được sử dụng trong ES6.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  <b>symbol</b> của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về symbol được sử dụng trong ES6.

## **1. Giới thiệu về symbol**

ES6 cung cấp cho chúng ta 1 kiểu dữ liệu nguyên thuỷ mới gọi là Symbol. Nó không giống như kiểu integer, string, boolean và các kiểu khác. Cú pháp tạo Symbol như sau. 


{% highlight javascript  linenos %}

let s = Symbol('foo');

{% endhighlight %}

Symbol mỗi lần được tạo ra sẽ nhận được giá trị là duy nhất và khác nhau. Ví dụ khi chúng ta so sánh

{% highlight javascript  linenos %}

console.log(Symbol() === Symbol()); // false

{% endhighlight %}

Chúng ta sẽ thấy hai giá trị Symbol sinh ra là khác nhau.

Kiểu dữ liệu Symbol cho phép chúng ta thêm các giá trị mô tả cho Symbol. Ví dụ anh thêm mô tả là first name cho biến firstName như sau.

{% highlight javascript  linenos %}

let firstName = Symbol('first name'),
    lastName = Symbol('last name');

{% endhighlight %}

Chúng ta có thể lấy giá trị môt tả của Symbol bằng phương thức toString(). 

{% highlight javascript  linenos %}

console.log(firstName); // Symbol(first name)
console.log(lastName); // Symbol(last name)

{% endhighlight %}

Hàm console.log sẽ gọi phưuong thức toString() của Symbol.

Symbol là kiểu dữ liệu nguyên thuỷ nên chúng ta không sử dụng toán tử new để khai báo Symbol.

{% highlight javascript  linenos %}

let s = new Symbol(); // error

{% endhighlight %}

## **2. Mục đích sử dụng symbol**

Chúng ta sử dụng Symbol khi chúng ta muốn có một giá trị duy nhất trong hệ thống.

Ví dụ trong đoạn code mình có các kiểu String hoặc Integer mà chứa giá trị duy nhất thì ta nên thay qua bằng cách dùng Symbol. Anh ví dụ như mình có biến status lưu các trạng thái là open, in progress, closed, completed etc. Thì ta sử dụng Symbol như sau

{% highlight javascript  linenos %}

let statuses = {
    OPEN: Symbol('Open'),
    IN_PROGRESS: Symbol('In progress'),
    COMPLETED: Symbol('Completed'),
    HOLD: Symbol('On hold'),
    CANCELED: Symbol('Canceled')
};
// complete a task
task.setStatus(statuses.COMPLETED);

{% endhighlight %}

Chúng ta sử dụng Symbol khi muốn thực hiện các tính toán thuộc tính của một đối tượng.

{% highlight javascript  linenos %}

let status = Symbol('status');

let task = {
    [status]: statuses.OPEN,
    description: 'Learn ES6 Symbol'
};
console.log(task);

{% endhighlight %}




























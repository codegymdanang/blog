---
layout: course-es6
title: Khi nào không nên dùng Arrow function trong ES6 
slug : khi-nao-khong-nen-dung-arrow-function
category: laptrinhjavascript
tags: [es6]
summery: Không nên dùng Arrow function
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta không nên dùng  Arrow function của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về các trường hợp không nên dùng nó.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về khi nào không nên sử dụng <b>Arrow function</b> của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về các trường hợp không nên dùng nó. Trong 5 trường hợp sau thì chúng ta không nên dùng arrow function để code vì arrow function không sở hữu giá trị this.

## **1. Bắt và xử lý sự kiện**

Anh có ví dụ sau đây, người dùng sẽ điền giá trị vào input sau đó anh lấy giá trị đó hiển thị ra ở một thẻ div như sau

Anh tạo một thẻ input để lấy tên người dùng.

{% highlight javascript  linenos %}

<input type="text" name="username" id="username" placeholder="Enter a username">

{% endhighlight %}


Anh tạo một thẻ div để hiển thị tên người dùng lấy được từ input

{% highlight javascript  linenos %}

<div id="greeting"></div>

{% endhighlight %}

Anh viết đoạn mã javascript để lấy tên người dùng và gán vào thẻ div như sau

{% highlight javascript  linenos %}

const greeting = document.querySelector('#greeting');

const username = document.querySelector('#username');

username.addEventListener('keyup', () => {

  greeting.textContent = 'Hello ' + this.value;

});

{% endhighlight %}


Tuy nhiên khi chương trình chạy anh sẽ nhận được kết quả là 'Hello' undefined. Có nghĩa là this.value lấy không được giá trị trong hàm bắt sự kiện addEventListener. Như đã nói trong phần mở đầu arrow function không sở hữu phạm vi biến this của input, chính vì vậy mặc dùng ta ghi this.value thì ta ngầm định this này chính là của input nhưng thật sư không phải. 

Để sửa lại đoạn code trên có thể bắt được sự kiện từ input thì ta phải dùng cách viết bình thường của javascript không dùng arrow function như sau.

{% highlight javascript  linenos %}

username.addEventListener('keyup', function () {
    input.textContent = 'Hello ' + this.value;
});

{% endhighlight %}

## **2. Các phương thức trong đối tượng**

Anh ví dụ có đối tượng Counter như sau.

{% highlight javascript  linenos %}

const counter = {
  count: 0,
  next: () => ++this.count,
  current: () => this.count
};

{% endhighlight %}

Đối tượng counter có 2 phương thức là next và current. Phương thức next để lấy giá trị tiếp theo và current là lấy giá trị hiện tại.
Anh sẽ gọi phương thức next của đối tượng counter như sau.

{% highlight javascript  linenos %}

console.log(counter.next());

{% endhighlight %}

Như vậy kết quả anh muốn muốn sẽ là 1. Tuy nhiên khi chương trình chạy anh sẽ nhận được kết quả là NaN. Nguyên nhân khi anh sử dụng this.count thì khi đó biến this này đang hiểu là đối tượng window chứ không phải là đối tượng counter. Để tránh biến this tham chiếu tới phạm vi toàn cục (global) thì ta sửa lại đoạn code trên như sau.

{% highlight javascript  linenos %}

const counter = {
    count: 0,
    next() {
        return ++this.count;
    },
    current() {
        return this.count;
    }
};

{% endhighlight %}

Chúng ta bỏ khai báo arrow function đi và viết theo cách viết bình thường.

## **3. Các phương thức trong Class**

Tương tụ như trường hợp phương thức trong đối tượng thì phương thức trong class chúng ta cũng không dùng arrow function.

{% highlight javascript  linenos %}

class Counter {
  constructor() {
    this.count = 0;
  }
  next = () => {
    return ++this.count;
  }
  current = () => {
    return this.count;
  }
}

{% endhighlight %}

Chúng ta không khai báo theo kiểu arrow function trong Class mà khai báo theo cách sau đây.

{% highlight javascript  linenos %}

class Counter {
  constructor() {
    this.count = 0;
  }
  next() {
    return ++this.count;
  }
  current() {
    return this.count;
  }
}  

{% endhighlight %}

## **4. Phương thức prototype**

Chúng ta lấy ví dụ về prototype cho đối tượng counter như sau

{% highlight javascript  linenos %}

function Counter() {
    this.count = 0;
}

Counter.prototype.next = () => {
    return this.count;
};

Counter.prototype.current = () => {
    return ++this.next;
}

{% endhighlight %}

Thì giá trị this.next và this.current đang tham chiếu tới đối tượng cục bộ (global) chứ không phải đối tượng counter. Chúng ta sẽ modify đoạn code trên lại như sau để this có thể tham chiếu đến counter.

{% highlight javascript  linenos %}

function Counter() {
    this.count = 0;
}

Counter.prototype.next = function () {
    return this.count;
};

Counter.prototype.current = function () {
    return ++this.next;
}

{% endhighlight %}


## **5. Sử dụng tham số là đối tượng arguments**

Anh có ví dụ sau 

{% highlight javascript  linenos %}

const concat = (separator) => {
    let args = Array.prototype.slice.call(arguments, 1);
    return args.join(separator);
}

{% endhighlight %}

Thay vì dùng theo arrow function thì ta nên thay đổi lại như sau

{% highlight javascript  linenos %}

function concat(separator) {
    let args = Array.prototype.slice.call(arguments, 1);
    return args.join(separator);
}

{% endhighlight %}


































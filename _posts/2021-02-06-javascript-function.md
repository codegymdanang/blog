---
layout: course-javascript
title: Sử dụng Function trong Javascript  
slug : su-dung-function-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Function   
image: /images/blog/feature_javascript.png
description : Trong ngôn ngữ lập trình web JavaScript có thuộc tính Function cho phép các bạn có thể đặt nhiều dòng code vào trong một function và sau đó có thể sử dụng nó nhiều lần khi cần. Cụ thể Function là gì? Và cách thao tác thuộc tính Function, hàm với tham số và cách để trả về kết quả trong Function khi lập trình web như thế nào? Những chia sẻ trong bài viết này sẽ lần lượt giải đáp những thắc mắc trên cho bạn.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Khi <b>lập trình web</b>, đã bao giờ các bạn gặp phải tình huống, bạn phải gõ lại một đoạn code nào đó lặp đi lặp lại mỗi khi cần dùng đến và bạn cảm thấy mất thời gian và công sức của bạn. Vậy bạn đã từng thắc mắc rằng có cách nào đề rút ngắn thời gian và tăng hiệu quả cho quá trình <b>lập trình web</b> hơn không chưa?

<br>
Tin vui cho bạn là trong ngôn ngữ lập trình JavaScript có thuộc tính <b>Function</b> cho phép các bạn có thể đặt nhiều dòng code vào trong một function và sau đó có thể sử dụng nó nhiều lần khi cần. Cụ thể Function là gì? Và cách thao tác thuộc tính Function (hàm) với tham số và cách để trả về kết quả trong <b>Function</b> khi <b>lập trình web</b> như thế nào? Bài viết này sẽ trả lời những thắc mắc trên cho bạn.


## **1. Function là gì**

Trong Javascript một function cho phép chúng ta đặt nhiều dòng code ở trong nó. Chúng ta phải đặt tên cho một function và sử dụng nó nhiều lần nếu mình cần.

Để định nghĩa một function trong Javascript chúng ta dùng từ khoá function

- Cú pháp

{% highlight javascript  linenos %}

//defining a function
function <function-name>()
{
    // code to be executed
};

//calling a function
<function-name>();

{% endhighlight %}

- Ví dụ chúng ta định nghĩa 1 function về hiển thị thông báo.

{% highlight javascript  linenos %}

function ShowMessage() {
    alert("Hello World!");
}

ShowMessage(); // chúng ta gọi function
{% endhighlight %}

## **2. Function với tham số**

Chúng ta có thể thêm 1 hoặc nhiều tham số vào trong function. Chỗ nào gọi function thì thêm đối số vào. Ví dụ ta có function là hiển thị tên, khi đối số truyền vào là firstName và lastName như thế nào thì mình hiển thị thông báo chào cho người dùng.

{% highlight javascript  linenos %}

function ShowMessage(firstName, lastName) {
    alert("Hello " + firstName + " " + lastName);
}

ShowMessage("Steve", "Jobs");
ShowMessage("Bill", "Gates");

{% endhighlight %}


## **3. Trả về kết quả trong function**

Sau khi function làm việc có thể trả về hoặc không trả về kết quả. Để trả về kết quả chúng ta dùng từ khoá return như sau.

{% highlight javascript  linenos %}

function Sum(val1, val2) {
    return val1 + val2;
};

var result = Sum(10,20); // returns 30

{% endhighlight %}









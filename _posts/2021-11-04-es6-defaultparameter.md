---
layout: course-es6
title: Giá trị mặc định cho tham số 
slug : gia-tri-mac-dinh-tham-so
category: laptrinhjavascript
tags: [es6]
summery:  Giá trị mặc định cho tham số
image: /images/blog/feature_javascript.png
description : Trình bày về cách khai báo giá trị mặc định cho tham số trong phương thức của ES6. Lần lượt giới thiệu và giải thích khái niệm giá trị mặc định trong phương thức của ES6 là gì? 

youtubeId: A21g71RGr5Y
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  cách khai báo <b>giá trị mặc định cho tham số trong phương thức </b> của ES6. Lần lượt giới thiệu và giải thích khái niệm giá trị mặc định trong phương thức của ES6 là gì? 

## **1. Phân biệt tham số và đối số**

Anh có ví dụ là phương thức add có 2 tham số truyền vào là x,y. Khi gọi phương thức add thì trả về kết quả cộng 2 số.

{% highlight javascript  linenos %}

function add(x, y) {
   return x + y;
}

add(100,200);

{% endhighlight %}

Như vậy x và y được gọi là THAM SỐ. Chúng được sử dụng để định nghĩa phương thức add sẽ có 2 giá trị truyền vào.

Còn phương thức gọi hàm add(100,200). Thì 100 và 200 được gọi là ĐỐI SỐ. Đối số là giá trị ta sẽ truyền cho phương thức.

## **2. Thiết lập giá trị mặc định cho phương thức**

Ví dụ anh có phương thức say(message) với tham số là message. Khi gọi vào phương thức say() thì in cho anh messeag.

{% highlight javascript  linenos %}

function say(message) {
    console.log(message);
}

say(); // undefined

{% endhighlight %}

Khi phương thức say() được gọi chúng ta sẽ nhận được kết quả là Undefined bởi vì chúng ta không truyền đối số cho hàm say()

Giả sử chúng ta mong muốn khi không truyền đối số vào thì chúng ta sẽ đặt giá trị mặc định cho message là 10. Lúc này ta phải chỉnh sửa lại đoạn mã ở trên và thêm phần kiểm tra giá trị biến message như sau

{% highlight javascript  linenos %}

function say(message) {
    message = typeof message !== 'undefined' ? message : 'Hi';
    console.log(message);
}

say();

{% endhighlight %}

Như vậy khi ta gọi hàm say() chúng ta sẽ nhận được giá trị là Hi.

Trong ES6 hỗ trợ chúng ta cách đặt giá trị mặc định cho tham số mà chúng ta không cần phải viết code để kiểm tra với cú pháp như sau.

{% highlight javascript  linenos %}

function fn(param1=default1,param2=default2,..) {

}

{% endhighlight %}

Chúng ta sử dụng dấu = và giá trị sau tham số để đặt giá trị mặc định. Ví dụ như chúng ta muốn đặt giá trị Hi cho biến message thì chúng ta làm như sau.

{% highlight javascript  linenos %}

function say(message='Hi') {
    console.log(message);
}

say(); // 'Hi'
say(undefined); // 'Hi'
say('Hello'); // 'Hello'

{% endhighlight %}

Khi chúng ta không truyền giá trị thì chúng ta sẽ nhận được chuỗi mặc định là Hi. Còn nếu chúng ta truyền vào đối số là chữ Hello thì sẽ nhận được kết quả Hello


## **3. Thiết lập giá trị mặc định bằng cách sử dụng tham số khác**

Anh có ví dụ như sau.

{% highlight javascript  linenos %}

function add(x = 1, y = x, z = x + y) {
    return x + y + z;
}

console.log(add()); // 4

{% endhighlight %}

Khi gọi phương thức add chúng ta có giá trị mặc định của x là 1, giá trị của y là 1 và giá trị của z là 2. Nhưng vậy khi gọi phép toán cộng ta sẽ có 1 + 1 + 2 nên kết quả nhận được sẽ là 4.

## **4. Thiết lập giá trị mặc định bằng cách sử dụng phương thức**

Anh có ví dụ như sau

{% highlight javascript  linenos %}

let taxRate = () => 0.1;
let getPrice = function( price, tax = price * taxRate() ) {
    return price + tax;
}

let fullPrice = getPrice(100);
console.log(fullPrice); // 110

{% endhighlight %}

Tham số tax trong phương thức là bằng price nhân với phương thức taxRate. Như vậy chúng ta có thể khai báo giá trị mặc định trong phương thức bằng cách gọi một phương thức khác.

## **5. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}





















































